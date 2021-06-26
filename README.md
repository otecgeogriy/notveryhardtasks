# notveryhardtasks

## Первоначальная установка

0. Форкануть
1. Очевидно `git clone [ссылка_на_этот_репозиторий]`
2. Прописать `npm install` в папке проекта, чтобы автоматически установить нужные зависимости (node_modules)

### На вкладке "Wiki" репозитория есть чуток гайдов

## Задания

Порядок:

1. cars.js
2. creatures.js

Задания представлены в следующем виде

```javascript
...
// Задание
// название_функции(аргументы)  -> ожидаемый результат
const название_функции = undefined;
...
```

Для выполнения задания необходимо сделать одно из двух

- Заменить `undefined` на стрелочную функцию:
  `const название_функции = (аргументы) => { ... }`
- Полностью заменить строку на традиционную запись:
  `function название_функции(аргументы) { ... }`

**Для проверки выполнения задания необходимо прописать `npm test`**

Возможные результаты:

- сообщение об ошибке при выполнении/несоответсвии результата ожиданиями
- `passed`, означающее что тест пройден успешно
- статус `skipped`, если отправляемая на проверку функция (сама она, не её результат выполнения) равна `undefined`

Для того чтобы присылать успехи сюда нужно сделать форк (гуглим) и откуда уже жмякать по pull request (гуглим).

## Структура файла

Само содержимое файла с заданием имеет следующую конструкцию (на примере cars.js):

```javascript
const db = require("../data/cars_db.json");

/* задания */

module.exports = {
  getOwnersWithG10kFine,
  getPaulsFerrari,
  getAllWantedCarsOwnerNames,
};
```

- `db` - переменная с данными, её нужно использовать в процессе написания функции. Запрещено ссылаться на неё **изнутри** фукнции, только через **аргумент**, поскольку для тестирования туда будут подаваться другие базы.
- `cars_db.json` - json-файл с данными, их _можно_ смотреть чтобы понять структуру с которой надо работать, однако вот _более предпочительные_ способы (тк в реальных условиях исходные файлы не всегда даны в явном виде):
  - `console.log(db)`
  - `console.log(JSON.stringify(db, null, 4))`
  - Отправить в браузер и посмотреть в тамошней консоли (да, для этого надо сделать серверное приложение)
- `module.exports = { fun }` - экспорт функций/обьектов/переменных. Таким образом их можно использовать в другом файле `const { fun } = require("./источник");` В данном случае их затем импортируют тесты для проведения тестирования
