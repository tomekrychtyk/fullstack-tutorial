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



