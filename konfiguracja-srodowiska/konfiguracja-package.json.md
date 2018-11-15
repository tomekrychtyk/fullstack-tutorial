# Konfiguracja package.json

Zanim przejdziemy do `package.json` skonfigurujmy sobie jeszcze na szybko Babel-a. W tym celu bezpośrednio w katalogu client stwórz plik o nazwie `.babelrc` i dodaj do niego następującą zawartość:

```javascript
{
  "presets": ["@babel/preset-env", "@babel/preset-react"],
  "plugins": [
    "@babel/plugin-syntax-dynamic-import"
  ]
}
```

Teraz otwieramy `package.json` i dodajemy do niego sekcję `scripts`, a w niej dwa skrypty:

```javascript
  "scripts": {
    "start": "webpack-dev-server --open --config webpack.dev.js",
    "eslint": "eslint ."
  }
```



