# Пример проекта локального

Создать локальный пакет в любом месте.

В `index.js` добавить код:
```ts
function randomNoGenerator(min, max) {
  if(typeof(max) !== 'number' && typeof(min) !== 'number') {
    min = 0;  max = 1;
  }
 return (Math.random() * (max-min)) + min;
}

module.exports = randomNoGenerator;
```

Пример `package.json`:

```json
{
  "name": "test-local-package-ui",
  "version": "0.0.10001",
  "main": "index.js",
  "license": "MIT",
  "author": "",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  }
}
```
---
# Установка локального проекта

1 Установка локального пакета

> yarn add /Users/nikita/dev/test/test-local-package-ui

2 после этого появлется строка в `package.json`

```json
"dependencies": {
  "viking": "file:../../oresoftware/viking",
},
```

---

# Использование локального пакета
```ts
const randomGen = require('test-local-package-ui');

console.log(randomGen(5, 10));
```