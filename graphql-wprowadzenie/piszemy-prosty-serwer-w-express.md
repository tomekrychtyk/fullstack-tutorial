# Piszemy prosty serwer w Express

### Niezbędne biblioteki

Do pracy z GraphQL będą nam potrzebne przede wszystkim trzy biblioteki: **graphql**, **express-graphql** i **express**. Dodatkowo zainstalujemy sobie jeszcze **lodash**, która może później okazać się przydatna do formatowania danych, które GraphQL nam zwróci. Instalujemy zależności za pomocą komendy:

```
yarn add express express-graphql graphql lodash
```

{% hint style="info" %}
W tym tutorialu używać będę **yarn** do zarządzania zależnościami, jednak jeśli używasz **npm** również nie będziesz mieć problemów z ukończeniem tego kursu.
{% endhint %}

### Prosty serwer w Express

Ok, jeśli instalacja przebiegła pomyślnie, tworzymy sobie nowy plik o nazwie server.js w /backend/graphql/server.js:

{% code-tabs %}
{% code-tabs-item title="/backend/graphql/server.js" %}
```javascript
const express = require('express');
const expressGraphQL = require('express-graphql');

const app = express();
app.listen(4000, () => {
    console.log('Listening at 4000');
});
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Na razie mamy jak widać bardzo prosty serwer w Express, który zreszta nie ma jeszcze pojęcia o naszym zamiarze wykorzystania w aplikacji GraphQL. Do tego potrzeba jest nam biblioteka express-graphql, którą importujemy w drugiej linijce. Jest to niejako pośrednik pomiędzy Expresse-m, a GraphQL-em.

Aby użyć express-graphql musimy dodać do serwera poniższy kod:

{% code-tabs %}
{% code-tabs-item title="/backend/graphql/server.js" %}
```javascript
const express = require('express');
const expressGraphQL = require('express-graphql');

const app = express();

app.use('/graphql', expressGraphQL({
  graphiql: true,
}));

app.listen(4000, () => {
  console.log('Listening at 4000');
});
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Za pomocą `app.use()` dajemy instrukcję serwerowi w rodzaju: każde żądanie ścieżki `/graphql` obsługuj używając `expressGraphQL`. Tak naprawdę `expressGraphQL` w świecie Node.js jest to tzw. middleware czyli właśnie pośrednik, mówiąc po polsku. Express pozwala nam na zarejestrowanie wielu takich pośredników dla różnych żądań właśnie za pomocą `app.use()`. Więcej na ten temat można przeczytać [w dokumentacji](https://expressjs.com/en/api.html#app.use).

### Testujemy nasz serwer

Ok, w tym momencie jesteśmy już gotowi do testowego odpalenia naszego serwera za pomocą komendy:

`node server.js`

Powinniśmy zobaczyć nasz log, czyli "**Listening at 4000**".  
Sprawdźmy więc w przeglądarce jak zostanie przetwożone nasze żądanie: http://localhost:4000/graphql  
Po wejściu na podany adres zobaczymy... wiadomość z błędzie:

```javascript
{
    errors: [
        {
            message: "GraphQL middleware options must contain a schema."
        }
    ]
}
```

Jest to błąd wygenerowany przez GraphQL i mówi nam o jakimś tajemniczym bycie pod nazwą `schema`. Zajmiemy się tym w kolejnym rozdziale.

{% page-ref page="graphql-schema.md" %}



