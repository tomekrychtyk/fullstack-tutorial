# Konfiguracja package.json

Zanim przejdziemy do `package.json` skonfigurujmy sobie jeszcze na szybko **Babel-a**. W tym celu bezpośrednio w katalogu **client** stwórz plik o nazwie `.babelrc` i dodaj do niego następującą zawartość:

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

Musimy jeszcze odpowiednio skonfigurować **ESLint**. W tym celu dodajemy również dwie poniższe sekcje:

```javascript
  "eslintIgnore": [
    "dist"
  ],
  "eslintConfig": {
    "extends": "airbnb",
    "parser": "babel-eslint",
    "env": {
      "browser": true
    },
    "plugins": [
      "react"
    ],
    "rules": {
      "jsx-a11y/anchor-is-valid": [
        "error",
        {
          "components": [
            "Link"
          ],
          "specialLink": [
            "to"
          ]
        }
      ],
      "import/no-extraneous-dependencies": [
        "off",
        {
          "devDependencies": [
            "*.test.js"
          ]
        }
      ],
      "padded-blocks": 0,
      "react/jsx-filename-extension": [
        1,
        {
          "extensions": [
            ".js",
            ".jsx"
          ]
        }
      ],
      "react/no-danger": "off",
      "jsx-a11y/label-has-for": [
        2,
        {
          "components": [
            "Label"
          ],
          "required": {
            "every": [
              "id"
            ]
          }
        }
      ]
    }
  },
```

Generalnie jest to konfiguracja jakiej ja używam mniej więcej w każdym React-owym projekcie, aczkolwiek potraktuj ją bardziej jako punkt wyjścia. Naprawdę zachęcam cię do zapoznania się z opcjami konfiguracyjnymi ESLint-a i do modyfikowania powyższego wedle uznania. W ten sposób najszybciej zrozumiesz poszczególne opcje.

Ostatnia rzecz jaką musimy zrobić to stworzyć katalog **src**, a w nim dwa pliki **index.js** oraz **index.html**. index.js na razie zostaw pusty - będzie on służył jako punkt wejściowy naszej aplikacji, więc jest on bardzo ważny, ale na razie potrzebujemy tylko **index.html:**

{% code-tabs %}
{% code-tabs-item title="src/index.html" %}
```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>FullStack Unsplashed</title>
    <link href="https://fonts.googleapis.com/css?family=Muli:700i" rel="stylesheet">
</head>
<body>
  <div id="root">It works!</div>
</body>


```
{% endcode-tabs-item %}
{% endcode-tabs %}

Teraz możemy odpalić nasze środowisko developerskie za pomocą komendy:

`yarn start`

Jeśli wszystko poszło ok, powinna otworzyć się nowa karta w przeglądarce z \(z typowo Apache-like ;\) \) napisem "**It works!**".

Super! W końcu możemy przejść do rzeczy naprawdę ciekawych, czyli do **React.js**!

