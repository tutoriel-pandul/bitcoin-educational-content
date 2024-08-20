---
term: ПРОБЛЕМА ВИЗАНТИЙСКИХ ГЕНЕРАЛОВ
---

Проблема была впервые сформулирована Лесли Лэмпортом, Робертом Шостаком и Маршаллом Пизом в специализированном журнале *ACM Transactions on Programming Languages and Systems, vol 4, n° 3* ["Проблема византийских генералов"](https://lamport.azurewebsites.net/pubs/byz.pdf) в июле 1982 года. Сегодня она используется для иллюстрации вызовов в плане принятия решений, когда распределенная система не может доверять ни одному участнику.

В этой метафоре группа византийских генералов и их соответствующие армии расположены вокруг города, который они хотят атаковать или осадить. Генералы географически разделены друг от друга и должны общаться через посредников, чтобы координировать свою стратегию. Неважно, атакуют они или отступают, главное, чтобы все генералы достигли консенсуса.

Таким образом, мы можем выделить следующие требования:
* Каждый генерал должен принять решение: атаковать или отступать (да или нет);
* Как только решение принято, его нельзя изменить;
* Все генералы должны согласиться с одним и тем же решением и выполнить его синхронно.

Более того, генерал может общаться с другим только через сообщения, передаваемые курьером, которые могут быть задержаны, уничтожены, изменены или потеряны. И даже если сообщение успешно доставлено, один или несколько генералов могут выбрать (по какой-либо причине) предать установленное доверие и отправить мошенническое сообщение, сея хаос.

Применяя дилемму к контексту блокчейна Bitcoin, каждый генерал представляет собой узел в сети, который должен достичь консенсуса относительно состояния системы. Другими словами, большинство участников в распределенной сети должны согласиться и выполнить одно и то же действие, чтобы избежать полного провала. Единственный способ достичь консенсуса в такой распределенной системе - иметь по крайней мере 2/3 надежных и честных узлов сети. Следовательно, если большинство сети решит действовать злонамеренно, система уязвима.

> ► *Эта дилемма иногда также называется "Проблема надежной трансляции".*