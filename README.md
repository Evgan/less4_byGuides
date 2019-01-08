Собираем среду по официальным guides

1 Webpack: основы настройки проекта на JavaScript и Sass
===============================================================================
https://tproger.ru/translations/webpack-basics/

!!!!! extract-text-webpack-plugin не заработал
Потому используем MiniCssExtractPlugin
ссылка на описалово https://tproger.ru/translations/configure-webpack4/

Но у Димы Апакина по другому, похоже как в официальном :
https://webpack.js.org/plugins/mini-css-extract-plugin/#src/components/Sidebar/Sidebar.jsx
Minimal example но с небольшими изменениями

Сделл как у Димы Апакина


2 BABEL
===============================================================================
по https://babeljs.io/setup#installation
1)npm install --save-dev babel-cli
Идёт ссылка на: https://blog.jetbrains.com/webstorm/2015/05/ecmascript-6-in-webstorm-transpiling/#babelfilewatcher
2) babel.config.js: https://babeljs.io/docs/en/configuration
НЕ РАЗОБРАЛСЯ КАК НАСТРОИТЬ ЭТОТ КОНФИГ

ПО ВИДОСУ https://www.youtube.com/watch?v=FX8uKB9vO0s
1)npm install --save-dev babel-cli
2) Бабелу нужны плагины, что бы не устанавливать каждый плагин в отдельности есть пакеты плагинов для каждой версии es: 2015 и 2016 и так далее и react:
npm i babel-preset-es2015 -D
Подключить установлнные пакеты можно в файле конфигураторе .babelrc или же в package.json
  "babel":{
    "presets":["es2015"] //чтобы бебел знал какие пакеты использовать при транспиляции
  },
  
Транспиляции:
"babel src/js --out-file dist/es5.js" - бебел высе js файлы из папки js переведёт в нативный js форма и запишит в файл es5.js
С минимизацией:
babel src/js --out-file dist/es5min.js --minified или же указать "minified": true в package.json
Так же в package.json можно указать файлы которые бабел будет игнорировать


Babel для React:
npm i babel-preset-react -D
+ добавляем в presets "react" и теперь транспилтор будет обрабатывать jsx файлы








ПОЛЕЗНОЧТИ
===============================================================================
Статья 2018-11
React + Webpack 4 + Babel 7 Setup Tutorial
https://www.robinwieruch.de/minimal-react-webpack-babel-setup/