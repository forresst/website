# 🚀 Начало работы

Parcel&nbsp;&mdash; это упаковщик для веб-приложений для разработчиков с различным опытом. Он предлагает великолепную быструю работу с использованием многоядерной обработки и не требует настройки.

Сначала установите Parcel с помощью Yarn или npm:

Yarn:

```bash
yarn global add parcel-bundler
```

npm:

```bash
npm install -g parcel-bundler
```

Создайте файл package.json в папке вашего проекта, используя:

```bash
yarn init -y
```

или

```bash
npm init -y
```

Parcel может принимать любой тип файла в качестве точки входа, но лучше всего использовать файл HTML или JavaScript. Если вы подключили свой основной JavaScript-файл в HTML, используя относительный путь, Parcel также обработает его для вас и заменит ссылку URL-адресом на выходной файл.

Далее создайте файлы index.html и index.js.

```html
<html>
<body>
  <script src="./index.js"></script>
</body>
</html>
```

```javascript
console.log('Привет, Мир!')
```

Parcel имеет встроенный сервер разработки, который будет автоматически пересобирать ваше приложение, так как поддерживает [горячую замену модулей](hmr.html) для увеличения скорости разработки. Просто выполните команду:

```bash
parcel index.html
```

Теперь откройте http://localhost:1234/ в браузере. Если горячая заменя модулей не работает, возможно вам нужно [настроить ваш редактор кода](hmr.html#safe-write). Вы также можете переопределить порт по умолчанию, с помощью опции параметра `-p <port number>`.

Используйте сервер разработки, если у вас нет собственного сервера или ваше приложение полностью отрисовывается на клиенте. Если у вас есть собственный сервер, вы можете запустить Parcel в режиме `watch`. Этот режим по-прежнему будет автоматически пересобирать приложение при измении файлов и поддерживает горячую замену модулей, но не запускает веб-сервер.

```bash
parcel watch index.html
```

Вы так же можете воспользоваться сервисом [createapp.dev](https://createapp.dev/parcel) чтобы создать Parcel-проект в браузере. Выбирайте компоненты, которые вам нужны, например React, Vue, Typescript или CSS, и вы увидите сгенерированный в реальном времени шаблон проекта. Вы можете использовать этот сервис в качестве примера настройки нового проекта. Или даже загрузить ZIP-архив с готовым шаблоном и сразу начать работу. 

## Несколько точек входа

В случае, если в вашем приложении более одной точки входа, например `index.html` и `about.html`, у вас есть два варианта запуска Parcel:

Указать пути к файлам:

```bash
parcel index.html about.html
```

Использовать glob-правило:

```bash
parcel *.html
```

_Обратите внимание:_ В случае, если в вашем проекте структура директорий похожа на следующую:

```
- folder-1
-- index.html
- folder-2
-- index.html
```

То переход к http://localhost:1234/folder-1/ не будет работать. Вместо этого вы должны обращаться точно к html-файлу: http://localhost:1234/folder-1/index.html.

## Сборка для продакшена

Когда вы готовы для продакшен-сборки, команда Parcel `build` не будет отслеживать изменения файлов и просто соберет приложение только один раз. Смотрите подробности в разделе [Работа в продакшене](production.html).


## Добавление Parcel в ваш проект

Бывает, что установить Parcel глобально нет возможности - например, если у вас нет root-доступа к системе или вы используете CI для автоматической сборки вашего проекта. В таком случае вы можете установить и использовать Parcel как локальный пакет.

Чтобы установить с помощью Yarn:

```bash
yarn add parcel-bundler --dev
```

Чтобы установить с помощью NPM:

```bash
npm install parcel-bundler --save-dev
```

Далее, добавьте следующие скрипты в `package.json` вашего проекта:

```json
{
  "scripts": {
    "dev": "parcel <your entry file>",
    "build": "parcel build <your entry file>"
  }
}
```

Теперь вы можете запускать их из консоли:

```bash
# Для запуска в режиме разработки
yarn dev
# or
npm run dev

# Для запуска продакшен-сборки
yarn build
# or
npm run build
```
