---
name: Neutrino
description: Інструкція з інсталяції LND Neutrino
---

# Налаштування Raspberry Pi з LND

1. Завантажте Raspberry Pi OS Lite

Завантажте Raspberry Pi OS Lite, інструкції щодо завантаження та інсталяції образу на мікро SD карту для Windows, Mac та Linux можна знайти на [цій сторінці](https://www.raspberrypi.org/software/operating-systems/).

2. Форматування SD-карти

Форматуйте SD-карту за допомогою Raspberry Pi Imager або balenaEtcher.

> ПРИМІТКА: Символ `$` використовується як запрошення та дозволяє користувачу вводити команди в комп'ютер, команди будуть інтерпретовані bash в Linux. Символ `#` на початку рядка вказує на те, що наступний текст є коментарем.

3. Увімкнення SSH

Перед тим як запустити Raspberry Pi з відформатованою пам'яттю, ми повинні вставити її в комп'ютер і створити два файли, які дозволять нам підключатися віддалено. Використовуючи команду `touch`, ми створюємо порожній файл у розділі /boot, активуючи SSH-з'єднання при першому запуску свіжо відформатованої SD-карти.

```
# ПРИМІТКА: Якщо мікроSD-карта була змонтована в /media/microSD, команда
# повинна бути $ sudo touch /media/microSD/boot/ssh
$ touch /boot/ssh
```

4. Використання команди nano

ми створюємо файл wpa_supplicant.conf і відразу починаємо його редагувати. У цьому файлі нам потрібно скопіювати конфігурацію wifi, копіюючи текст між START і END, і змінюючи SSID та пароль wifi, до якого ви хочете підключитися.

```
$ nano /boot/wpa_supplicant.conf

------ START -------
country=ar
update_config=1
ctrl_interface=/var/run/wpa_supplicant

network={
 ssid="MyNetworkSSID"
 psk="password"
}
------ END -------
```

5. Підключення

Потім ми вставляємо SD-карту в Raspberry Pi і підключаємо Pi до джерела живлення, щоб запустити операційну систему. Нам потрібно ідентифікувати його в мережі, і протокол mDNS, ймовірно, присвоїть йому ім'я raspberrypi.local. Спробуємо підключитися через SSH.

```
$ ssh pi@raspberrypi.local
password: raspberry
```

Якщо це не спрацює, нам потрібно дізнатися мережу. Давайте з'ясуємо IP-адресу, до якої ми підключені.

```
$ ifconfig
```

Наприклад, якщо це 192.168.0.0, використовуйте nmap для пошуку Pi.

```
nmap -v 192.168.0.0/24
```

Припускаючи, що ми знайшли новий IP у нашій мережі, давайте увійдемо через SSH.

```
$ ssh pi@192.168.0.30
password: raspberry
```

1. Налаштування Pi

```
$ sudo raspi-config
```

- Виберіть опцію (1) і змініть пароль для користувача pi.
- Ми вибираємо опцію (8), щоб оновити інструмент налаштування до останньої версії
- Ми вибираємо опцію (4), щоб вибрати наш часовий пояс
- Ми вибираємо опцію (7) і потім Розширити файлову систему
- Завершити

  7.- Ми оновлюємо ОС

```
$ sudo apt update && sudo apt upgrade -y
$ sudo apt install htop git curl bash-completion jq qrencode dphys-swapfile vim --install-recommends -y
```

8.- Ми додаємо користувача bitcoin

```
$ sudo adduser bitcoin
```

9.- Ми захищаємо rpi

```
$ sudo apt install ufw
```
$ sudo ufw default deny incoming
$ sudo ufw default allow outgoing
$ sudo ufw allow 22 comment 'дозволити SSH з локальної мережі'
$ sudo ufw allow 9735 comment 'дозволити Lightning'
$ sudo ufw allow 10009 comment 'Lightning gRPC'
$ sudo ufw enable
$ sudo systemctl enable ufw
$ sudo ufw status
$ sudo apt install fail2ban
```

```
10.- Ми встановлюємо go: якщо ви не використовуєте raspberry pi, завантажте go для вашої архітектури тут (https://golang.org/dl/)

```
$ wget https://golang.org/dl/go1.15.linux-armv6l.tar.gz
$ sudo tar -C /usr/local -xzf go1.15.linux-armv6l.tar.gz
$ echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc
$ echo "export GOPATH=$HOME/go" >> ~/.bashrc
$ echo "export PATH=$PATH:$GOPATH/bin" >> ~/.bashrc
$ source ~/.bashrc
$ go version # має відобразити наступне повідомлення 'go version go1.13.5 linux/arm'
```

11.- Ми компілюємо та встановлюємо lnd

```
$ git clone https://github.com/lightningnetwork/lnd.git
$ cd lnd
$ make
$ make install tags="autopilotrpc chainrpc experimental invoicesrpc routerrpc signrpc walletrpc watchtowerrpc wtclientrpc"
$ sudo cp $GOPATH/bin/lnd /usr/local/bin/
$ sudo cp $GOPATH/bin/lncli /usr/local/bin/
$ lncli --version
lncli version 0.11.0-beta commit=v0.11.0-beta-61-g6055b00dbbcedf45cd60f12e57dc5c1a7b97746f
```

12.- Ми створюємо файл конфігурації lnd, це слід зробити з користувачем 'bitcoin'

```
$ sudo su - bitcoin
$ mkdir .lnd
$ nano .lnd/lnd.conf
```

```
[Application Options]
# дозволити спонтанні платежі
accept-keysend=1

# Публічне ім'я вузла
alias=ВАШ_АЛІАС
# Публічний колір у шістнадцятковому форматі
color=#000000
debuglevel=info
maxpendingchannels=5
listen=localhost
# gRPC сокет
rpclisten=0.0.0.0:10009

[Bitcoin]
bitcoin.active=1
bitcoin.mainnet=1
bitcoin.node=neutrino

[neutrino]
neutrino.connect=bb2.breez.technology
```

13.- Щоб LND запускався після завантаження rpi, ми повинні створити файл .service в systemd.
Якщо ми залогінені як користувач bitcoin і хочемо повернутися до користувача pi, просто вводимо 'exit'

```
$ exit
$ sudo nano /etc/systemd/system/lnd.service
```

```
[Unit]
Description=LND Lightning Network Daemon
After=network.target

[Service]

# Виконання сервісу
###################

ExecStart=/usr/local/bin/lnd


# Управління процесом
####################

Type=simple
Restart=always
RestartSec=30
TimeoutSec=240
LimitNOFILE=128000

# Створення директорій та дозволи
####################################

# Виконувати як bitcoin:bitcoin
User=bitcoin
Group=bitcoin

# /run/lightningd
RuntimeDirectory=lightningd
RuntimeDirectoryMode=0710

# Заходи жорсткого обмеження
####################

# Забезпечити приватний /tmp та /var/tmp.
```
PrivateTmp=true
# Змонтувати /usr, /boot/ та /etc тільки для читання для процесу.
ProtectSystem=full

# Заборонити процесу та всім його дочірнім процесам отримувати
# нові привілеї через execve().
NoNewPrivileges=true

# Використовувати новий простір імен /dev, заповнений тільки API псевдо-пристроями
# такими як /dev/null, /dev/zero та /dev/random.
PrivateDevices=true

# Заборонити створення записуваних та виконуваних відображень пам'яті.
MemoryDenyWriteExecute=true

[Install]
WantedBy=multi-user.target
```

```
$ sudo systemctl enable lnd
$ sudo systemctl start lnd
$ systemctl status lnd
```

Ми можемо переглянути логи, виконавши команду journalctl

```
$ sudo journalctl -f -u lnd
```

14. Тепер ми запускаємо lnd

```
$ sudo su - bitcoin
$ lncli create
```

15. Додаємо кошти на наш вузол

```
$ lncli newaddress p2wkh
```

Надішліть btc на адресу, повернуту lnd

Щоб перевірити баланс

```
$ lncli walletbalance
{
    "total_balance": "500000",
    "confirmed_balance": "0",
    "unconfirmed_balance": "500000"
}
```

Після підтвердження транзакції, ми можемо відкрити канал. Якщо ви не знаєте, з яким вузлом відкрити канал, ви можете зайти на 1ml.com та вибрати вузол.

Відкрити з'єднання з вузлом:

```
$ lncli connect 031015a7839468a3c266d662d5bb21ea4cea24226936e2864a7ca4f2c3939836e0@212.129.58.219:9735
```

Потім відкрити канал

```
$ lncli openchannel 031015a7839468a3c266d662d5bb21ea4cea24226936e2864a7ca4f2c3939836e0 1000000 0
```

Перевірити наші кошти

```
$ lncli walletbalance
$ lncli channelbalance
```

Ми можемо переглянути очікуючі та активні канали

```
$ lncli pendingchannels
$ lncli listchannels
```

Щоб оплатити lightning інвойс

```
$ lncli payinvoice lnbc1p0kkhgwpp5sn9y6xe9hx7swrjj4057674vh73nwk6rxg8j8zedztkn3vdzgjafacqmud86h
```

Щоб отримати платіж, створіть інвойс на конкретну суму

```
$ lncli addinvoice --memo 'мій перший платіж в LN' --amt 100
```

Щоб переглянути інформацію про мій вузол

```
$ lncli getinfo
```

Повний список команд можна побачити, просто виконавши lncli

```
$ lncli
```

Нарешті, щоб робити виклики до API lnd

```
$ MACAROON_HEADER="Grpc-Metadata-macaroon: $(xxd -ps -u -c 1000 .lnd/data/chain/bitcoin/mainnet/admin.macaroon)"
$ curl -X GET --cacert .lnd/tls.cert --header "$MACAROON_HEADER" https://localhost:8080/v1/getinfo |jq
```

> КІНЕЦЬ