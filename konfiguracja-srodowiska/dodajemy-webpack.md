# Dodajemy Webpack

Instalacja **Webpacka** jest prosta jak instalacja każdej innej paczki. Będąc cały czas w katalogu **client**, po prostu wpisz:

`yarn add webpack webpack-cli`

Później na etapie konfiguracji webpack-a do celów produkcyjnych, będziemy także potrzebowali kilku pluginów, więc możemy równie dobrze zainstalować je teraz:

`yarn add --dev clean-webpack-plugin optimize-css-assets-webpack-plugin uglifyjs-webpack-plugin webpack-bundle-analyzer webpack-dev-server webpack-merge style-loader css-loader`

Jako że będziemy używać React-a, chcemy korzystać ze wszystkich jego dobrodziejstw, między innymi [**JSX**](https://reactjs.org/docs/introducing-jsx.html). Jako że JSX nie jest \(i nie będzie\) w żaden sposób częścią ECMAScriptu, nie możemy po prostu sobie zacząć w nim pisać licząc na to, że przeglądarki jakoś się domyślą o co nam chodzi. Potrzebujemy narzędzie, które w jakiś sposób przetłumaczy kod z wyższego poziomu \(czyli wspomniany JSX, ale także np. ES6\), na kod, który zrozumie przeglądarka. W tym celu użyjemy bardzo popularnego transpilera jakim jest [**Babel**](https://babeljs.io/docs/en/next/babel-core.html):

`yarn add --dev @babel/cli @babel/core @babel/plugin-syntax-dynamic-import @babel/preset-env @babel/preset-react babel-loader`

Bardzo pomocny przy pisaniu aplikacji w JS będzie również tzw. [**code linter** ](https://en.wikipedia.org/wiki/Lint_%28software%29)czyli narzędzie do statycznej analizy naszego kodu - ostrzeże nas ono w razie popełnienia błędów składniowych, literówek, użycia niezadeklarowanych zmiennych, czy też w poważniejszych sytuacjach jak np. przy importowaniu nieistniejących bibliotek, a nawet próbie użycia cyrkularnych referencji! Ja na codzień używam [**ESLint**](https://eslint.org/) więc i w tym projekcie mam zamiar go zainstalować:

`yarn add --dev eslint babel-eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react`

Tak uzbrojeni w Webpacka i resztę, możemy w końcu przejść do ich konfiguracji.

