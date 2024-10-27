---
name: LAPP bitcoin
description: Посібник з розробки вашого першого LApp
---

Навчіться програмувати свій перший додаток Lightning

Вимоги:

- NodeJs >= 8
- LND >= 9

NodeJs можна завантажити з офіційного сайту

Замість завантаження та налаштування вузла LND, ми використаємо інструмент polar, який виконає це завдання за нас.

Для створення нашого додатку Lightning ми будемо використовувати наступні технології:

- Express для нашого веб-сервера
- Шаблони Pug + bootstrap для нашого фронтенду

## Операційна система

Рекомендується використовувати Linux, якщо ви користуєтеся Windows 10, ви можете мати консоль Linux, слідуючи цим кільком крокам.
Підготовка бази

Використовуйте інструмент генератора додатків, express, для швидкого створення скелета додатку.

```
$ sudo npm install express-generator -g
```

За допомогою наступної інструкції ми створюємо додаток Express під назвою lnapp. Додаток буде створено в директорії під назвою lnapp у поточному робочому каталозі, і двигун перегляду буде призначено Pug.

```
$ express --view=pug lnapp
```

Потім ми заходимо в директорію та встановлюємо необхідні пакети для роботи веб-сервера.

```
$ cd myapp
$ npm install
```

Тепер просто запускаємо сервер

```
$ npm start
```

Далі, перейдіть за цією адресою http://localhost:3000 у браузері, щоб отримати доступ до додатку.

Створений додаток має наступну структуру директорій:

```
.
├── app.js
├── bin
│ └── www
├── package.json
├── public
│ ├── images
│ ├── javascripts
│ └── stylesheets
│ └── style.css
├── routes
│ ├── index.js
│ └── users.js
└── views
├── error.pug
├── index.pug
└── layout.pug
```

## Polar

Завантажте Polar, встановіть його та створіть мережу з 2 вузлами LND (Alice та Bob) та 1 bitcoind. Як тільки ми побачимо граф у додатку, що показує наші вузли, натисніть кнопку Start і зачекайте кілька секунд, поки індикатор кожного вузла не змінить колір на зелений.

Для відправлення платежів у Lightning необхідно, щоб вузли були з'єднані через канали. Створення каналів за допомогою Polar дуже просте, нам просто потрібно натиснути мишкою на одне з вушок вузла Alice та перетягнути його до одного з вушок вузла Bob. Відразу з'явиться модальне вікно з назвою Open new channel, ми залишаємо значення за замовчуванням і натискаємо кнопку відкриття каналу. Тепер ми повторюємо дію, але цього разу від Bob до Alice, таким чином обидва вузли можуть відправляти та отримувати гроші.

## Nodemon

Щоб не доводилося перезапускати nodejs кожного разу, коли ми робимо зміну в коді, ми встановимо nodemon

```
$ npm install nodemon -D
```

Ми повинні створити запис у секції scripts файлу package.json, додайте цей рядок "dev": "nodemon ./bin/www", секція scripts повинна виглядати так:

```
"scripts": {
"start": "node ./bin/www",
"dev": "nodemon ./bin/www"
},
```

Перейдіть до консолі, де запущено npm start, натисніть ctrl + c і знову запустіть nodejs, але цього разу використовуючи nodemon

```
$ npm run dev
```

## Підключення до LND

Для підключення до вузла Lightning з nodejs ми будемо використовувати бібліотеку ln-service, також ми встановимо dotenv для управління змінними середовища.

```
$ npm install ln-service dotenv
У нашій директорії lnapp створіть файл під назвою .env, він повинен містити такі змінні:

```
LND_GRPC_HOST=''
LND_CERT_BASE64=''
LND_MACAROON_BASE64=''
```

Поверніться до Polar, виберіть Bob, вузол, до якого ми хочемо підключитися, перейдіть на вкладку "Підключення", скопіюйте вміст GRPC Host і помістіть його у змінну LND_GRPC_HOST, у нижній частині вкладки підключення виберіть base64 і скопіюйте вміст TLS Cert та помістіть його у змінну LND_CERT_BASE64, а також зробіть те саме з адміністративним macaroon у LND_MACAROON_BASE64.

Тепер додайте цей рядок до файлу app.js, розташованого в корені робочого каталогу, ми повинні скопіювати його на перший рядок файлу.

```
require('dotenv').config();
```

Щоб перевірити, чи може nodejs підключитися до нашого вузла, відкрийте файл routes/index.js, цей файл маршрутів було створено за допомогою генератора express, спочатку ми вимагаємо бібліотеку ln-service, тому ми додаємо її на перший рядок

```
const lnservice = require('ln-service');
```

Ми додаємо новий маршрут, який надасть нам інформацію про наш вузол.

```
router.get('/info', async function(req, res, next) {
try {
// аутентифікація з lnd
const { lnd } = lnservice.authenticatedLndGrpc({
cert: process.env.LND_CERT_BASE64,
macaroon: process.env.LND_MACAROON_BASE64,
socket: process.env.LND_GRPC_HOST,
});
// отримання інформації про вузол
const info = await lnservice.getWalletInfo({ lnd });

    // відображення інформації у форматі json
    res.send(`
      <h1>Інформація про вузол</h1>
      <pre>${JSON.stringify(info, null, 2)}</pre>
    `);
    next();

} catch (e) {
console.log(e);
}
});
```

Тепер перейдіть за цією адресою http://localhost:3000/info

Якщо ви бачите json з інформацією про вузол LND, вітаємо!!! ваш додаток тепер може взаємодіяти з Lightning Network.
Створення фіктивної моделі

Щоб симулювати базу даних, нам потрібно створити фіктивну модель, це дозволить нам використовувати додаток без встановлення та налаштування бази даних.

Спочатку встановіть пакет uuid

```
$ npm install uuid
```

Створіть директорію models і всередині неї створіть файл Post.js з наступним вмістом:

```
const { v4: uuidv4 } = require('uuid');'
class Post {
  constructor() {
    this.posts = [];
  }
  add({ time, name, content, paid, hash, preimage, request }) {
    const post = {
      id: uuidv4(),
      time: time || new Date(),
      name,
      content,
      paid: paid || false,
      hash: hash || null,
      preimage: preimage || null,
      request: request || null,
    };
    this.posts.push(post);

    return post;
  }

  find(id) {
    return this.posts.find(p => p.id === id);
  }

  findByHash(hash) {
    return this.posts.find(p => p.hash === hash);
  }

  findAll() {
    return this.posts;
  }

  findAllPaid() {
    return this.posts
      .filter(p => !!p.paid)
      .sort((a, b) => b.time - a.time);
  }

  paid(hash) {
    let updatedPost;
    this.posts = this.posts.map(p => {
      if (p.hash === hash) {
```markdown
const router = express.Router();
const posts = require('../models/posts');

router.post('/post', async (req, res) => {
  try {
    const { name, content } = req.body;
    const newPost = await posts.addPost({ name, content, paid: false });
    if (newPost) {
      res.json({ success: true, data: newPost });
    } else {
      res.json({ success: false });
    }
  } catch (error) {
    res.status(500).send(error.toString());
  }
});

module.exports = router;
```

## Підготуйте вигляд

Нам потрібен bootstrap, щоб наш html виглядав краще, тому ми змінюємо файл layout.pug, який знаходиться в директорії views, щоб він виглядав так:

```
doctype html
html
  head
    title= title
    link(rel='stylesheet', href='https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css')
    link(rel='stylesheet', href='/stylesheets/style.css')
  body
    block content
    block scripts
      script(src="https://code.jquery.com/jquery-3.4.1.min.js")
      script(src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js")
      script(src="/javascripts/main.js")
```

## Створення посту

Щоб створити пост, нам потрібна форма. У директорії views створіть файл під назвою form.pug з наступним вмістом:

```
.collapse#post-form
  form
    h2 Напишіть статтю
    .form-group
      label(for="name") Ім'я
      input(id="name").form-control
    .form-group
      label(for="content") Зміст
      textarea(id="content").form-control
    button.btn.btn-primary#send-btn(type="button") Відправити
```

## Javascript на фронтенді

Найпряміший спосіб взаємодії з користувачем - це використання javascript у веб-браузері. Для цього створіть файл під назвою main.js у директорії javascript, який ми вже викликаємо з layout.pug. Початковий вміст main.js має вигляд:

```
const App = {
  endpoint: 'http://localhost:3000/api',
  interval: null,
};

App.init = () => {
  $('#post-form').collapse('show');
  $('#send-btn').click(App.sendBtn);
}

App.sendBtn = () => {
  console.log('!привіт');
};

$(() => App.init());
```

Натисніть кнопку "Відправити", і якщо все добре, в консолі має з'явитися повідомлення "!привіт". Тепер ми можемо змінити метод App.sendBtn(), щоб відправити інформацію на наш API.

```
App.sendBtn = async () => {
  const name = $('#name').val();
  const content = $('#content').val();
  const response = await App.makeRequest({
    api: "post",
    post: { name, content },
  });
  if (!response) console.error('Помилка отримання даних!');
  if (response.success) {
    // Робіть щось з відповіддю
  }
};
```

```markdown
// Виведіть дані, які приходять з API, в консоль
console.log(response.data);
}
};
```

Ми також створюємо метод App.makeRequest() і додаємо його до main.js

```markdown
App.makeRequest = ({api, post}) => {
const type = !post ? 'GET' : 'POST';
const data = !!post ? JSON.stringify(post) : null;
return $.ajax(`${App.endpoint}/${api}`, {
type,
data,
contentType: 'application/json',
dataType: 'json',
});
};
```

## Створіть API

Для цього нам потрібно створити новий файл у routes/api.js і написати метод, який відповідає на запит, зроблений у App.sendBtn().

```markdown
const express = require('express');
```
```markdown
const lnservice = require('ln-service');
const router = express.Router();
const post = require('../models/Post');

router.post('/post', (req, res) => {
const { name, content } = req.body;
return res.json({
success: true,
data: { name, content },
});
});

module.exports = router;
```

Цей файл має бути включений до app.js, тому ми додаємо наступні рядки:

```markdown
const apiRouter = require('./routes/api');
app.use('/api', apiRouter);
```

Натиснімо кнопку відправлення знову, і вона має відповісти тими самими даними, що ми ввели у форму.

## Створення інвойсу

Метод, який виконується, коли користувач створює пост, має генерувати інвойс, потім створювати запис у базі даних, пов'язуючи його з інвойсом, і повертати інвойс користувачу, щоб він міг його оплатити.

```markdown
router.post('/post', async (req, res) => {
// Аутентифікація з lnd
const { lnd } = lnservice.authenticatedLndGrpc({
cert: process.env.LND_CERT_BASE64,
macaroon: process.env.LND_MACAROON_BASE64,
socket: process.env.LND_GRPC_HOST,
});

const { name, content } = req.body;
try {
const invoice = await lnservice.createInvoice({
lnd,
tokens: 1000,
description: name,
});
if (!!invoice) {
const p = post.add({
name,
content,
hash: invoice.id,
request: invoice.request,
preimage: invoice.secret,
});
return res.json({
success: true,
data: p,
});
}
} catch (e) {
console.log(e);
}
});
```

Якщо ми отримаємо об'єкт поста у відповідь після натискання відправлення, як тут, все пройшло правильно. Тепер нам потрібно відобразити текст, щоб користувач міг його оплатити.

```markdown
{
"success":true,
"data":{
"id":"0fb1544a-d7f9-487d-961a-d0004ecc515c",
"time":"2020-09-02T21:29:53.747Z",
"name":"epale",
"content":"contenido bla bla",
"paid":false,
"hash":"0e3c7a1151d8f8f202bc7264db83e554c9009f9bd32c0fcb0412772b310b520e",
"preimage":null,
}
```

## Новий вигляд інвойсу

У директорії views нам потрібно створити файл під назвою invoice.pug з наступним вмістом:

```
.collapse#invoice-form
form
.h2 Оплатіть цей інвойс
.form-group
textarea(
id="invoice",
readonly,
rows="5"
).form-control
```

І включити його до index.pug

```
extends layout

block content
h1 Lightning App
include form.pug
include invoice.pug
```

## Модифікація App.sendBtn()

Тепер ми модифікуємо App.sendBtn(), щоб відображати отримані дані:

```
App.sendBtn = async () => {
const name = $('#name').val();
const content = $('#content').val();
const response = await App.makeRequest({
api: "post",
post: { name, content },
});
if (!response) console.error('Помилка отримання даних!');
if (response.success) {
$('#post-form').collapse('hide');
$('#invoice-form').collapse('show');
$('#invoice').val(response.data.request);
}
};
```

## Отримання платежу
Нам потрібно знати, коли ми отримуємо платіж, для цього ми будемо використовувати метод subscribeToInvoices() з lnservice, цей метод дозволяє нам виконувати код, коли статус інвойсу було оновлено, для його використання ми додаємо ці рядки в app.js.
```
// підключаємо lnservice та нашу таблицю постів
const lnservice = require('ln-service');
const post = require('./models/Post');

// автентифікація з lnd
const { lnd } = lnservice.authenticatedLndGrpc({
cert: process.env.LND_CERT_BASE64,
macaroon: process.env.LND_MACAROON_BASE64,
socket: process.env.LND_GRPC_HOST,
});

// перевіряємо, чи був інвойс оплачений кожного разу, коли інвойс оновлюється
const subscribeInvoices = async () => {
try {
const sub = lnservice.subscribeToInvoices({lnd});
sub.on('invoice_updated', async invoice => {
if (!invoice.is_confirmed) return;

      // позначаємо інвойс як 'оплачений'
      const paid = post.paid(invoice.id);
      if (paid) console.log('Інвойс оплачений!');
    });

} catch (e) {
console.log(e);
return e;
}
};
// запускаємо підписку на інвойси
subscribeInvoices();
```

Створюємо HTTP GET метод в нашому API, щоб користувач міг перевірити, чи був хеш оплачений.

````
router.get('/post/:hash', (req, res) => {
const { hash } = req.params;
```javascript
const data = post.findByHash(hash);
if (!!data) {
  return res.json({
    success: true,
    data,
  });
} else {
  return res.json({
    success: false,
    data: null,
  });
}
});
````

Тепер, з main.js, ми створюємо функцію під назвою App.waitPayment(), яка запитує API, чи був платіж здійснений.

```javascript
App.waitPayment = async (hash) => {
  const response = await App.makeRequest({
    api: `post/${hash}`,
  });
  if (response.success && response.data.paid) {
    console.log("Платіж здійснений");
  }
};
```

Тепер ми стикаємося з проблемою, функція App.waitPayment() виконується лише один раз, користувач може здійснити платіж, і ми не змогли повідомити, що їх платіж було отримано. Для цього ми використовуємо функцію JavaScript під назвою setInterval(), яка дозволяє нам виконувати функцію нескінченно через вказаний інтервал часу.

Давайте модифікуємо функції App.waitPayment() та App.sendBtn(), включаючи setInterval() та clearInterval()

```javascript
App.waitPayment = async (hash) => {
  const response = await App.makeRequest({
    api: `post/${hash}`,
  });
  if (response.success && response.data.paid) {
    clearInterval(App.interval);
    App.interval = null;
    $("#invoice-form").collapse("hide");
    $("#preimage").text(response.data.preimage);
    $("#success").collapse("show");
  }
};

App.sendBtn = async () => {
  const name = $("#name").val();
  const content = $("#content").val();
  const response = await App.makeRequest({
    api: "post",
    post: { name, content },
  });
  if (!response) console.error("Помилка отримання даних!");
  if (response.success) {
    $("#post-form").collapse("hide");
    $("#invoice-form").collapse("show");
    $("#invoice").val(response.data.request);
    App.interval = setInterval(App.waitPayment, 1000, response.data.hash);
  }
};
```
І ми створюємо вигляд, щоб вказати, що платіж було успішно отримано, ми створюємо файл success.pug у папці views з наступним вмістом:
```pug
.collapse#success
  h2 Платіж успішний
  div Доказ платежу:
    #preimage
```

Ми включаємо його в index.pug.

```pug
extends layout

block content
  h1 Lightning App
  include form.pug
  include invoice.pug
  include success.pug
```

Якщо після оплати рахунку ви можете побачити повідомлення "Платіж успішний" та доказ платежу, вітаємо!!! Ви це зробили, ви завершили свій перший LApp.