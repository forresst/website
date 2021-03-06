# ✨ Работа в продакшене

Когда придет время выпустить ваше приложение в продакшен, используйте режим `production`.

```bash
parcel build entry.js
```

Эта команда запускает оптимизированную релизную сборку приложения. Сборка будет осуществлена без наблюдения за изменением файлов и горячей замены модулей, но с минимизацией всех выходных бандлов для уменьшения итогового размера файлов. Минификаторы, используемые Parcel: [terser](https://github.com/fabiosantoscode/terser) для JavaScript, [cssnano](http://cssnano.co) для CSS и [htmlnano](https://github.com/posthtml/htmlnano) для HTML.

Запуск сборки в режиме продакшена также устанавливает переменную окружения `NODE_ENV=production`. Большие библиотеки, такие как React, имеют дополнительную функциональность для отладки, которую можно отключить путем установки этой переменной окружения. Это позволяет получить более компактные и быстрые сборки для продакшена.
