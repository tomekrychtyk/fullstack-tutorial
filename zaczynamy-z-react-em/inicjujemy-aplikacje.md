# Inicjujemy aplikację

## Instalacja React-a

Zanim zaczniemy cokolwiek robić w **React.js**, musimy go oczywiście najpierw zainstalować. Oprócz tego będziemy jeszcze używać **React-Router** więc warto również zadbać już teraz, by i ta paczka była obecna w naszym projekcie. Z linii poleceń wykonaj następującą komendę:

```
yarn add react react-dom react-router react-router-dom
```

Możemy teraz sprawdzić, czy instalacja React-a i React-Router przebiegła pomyślnie. Jeśli masz uruchomiony serwer developerski \(poprzez komendę `yarn start` którą zdefiniowaliśmy w poprzednim rozdziale\), zatrzymaj go za pomocą `ctrl+c`, a następnie uruchom ponownie.

{% hint style="info" %}
Serwer developerski wbudowany w Webpack-a posiada mechanizm zwany **Hot Module Replacement** \(w skrócie często po prostu HMR\), który jest świetnym usprawnieniem pracy developera, ponieważ zmiany wprowadzone w plikach naszego projektu widzimy praktycznie od razu po ich zapisaniu, nawet bez odświeżania strony. HMR ma jednak swoje limitacje i jedną z nich jest przypadek, kiedy instalujemy nowe biblioteki w naszym projekcie. Wówczas musimy zrestartować serwer, aby aplikacja móc ich użyć. Więcej na ten temat można znaleźć oczywiście w [dokumentacji](https://webpack.js.org/concepts/hot-module-replacement/).
{% endhint %}

Teraz możemy dodać React do naszego projektu. 

Na początek otwórz plik `src/index.html` i usuń z niego nasz testowy tekst "**It works!**".

Następnie otwórz plik `src/index.js` \(jeśli go jeszcze nie stworzyłeś w jednym z poprzednich kroków, po prostu stwórz go teraz\) oraz wklej do niego poniższy kod:

{% code-tabs %}
{% code-tabs-item title="src/index.js" %}
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(
  <BrowserRouter>
    <div>I am a React.js app now!</div>
  </BrowserRouter>,
  document.getElementById('root'),
);

```
{% endcode-tabs-item %}
{% endcode-tabs %}

Pierwsze dwie linijki służą generalnie rzecz biorąc do importu samego React-a. Trzecia importuje tzw. `BrowserRouter`. Jest to komponent będący częścią React-Router i daje on nam możliwość definiowania **routingu**.

{% hint style="info" %}
Routing to najprościej mówiąc sposób zdefiniowania, jak ma się zachowywać aplikacja przy zmianie adresu URL strony, na jakiej się znajdujemy. Jako że budujemy tutaj tzw. **SPA** \(**Single Page Application**\), musimy w pewien sposób obejść konwencjonalne zachowanie przeglądarki przy zmianie URL - czyli nie dopuścić do przeładowania strony, a jednocześnie jakoś na to zdarzenie zareagować, czyli zaktualizować treść, którą widzi użytkownik. I to będzie właśnie zadaniem [BrowserRouter](https://reacttraining.com/react-router/web/api).
{% endhint %}

Druga część pliku to po prostu "wstrzyknięcie" naszej aplikacji do odpowiedniego elementu HTML na stronie \(czyli w tym przypadku `div`-a o ID `root`. Generalnie idea React-a polega na tym, że cała aplikacja będzie żyć właśnie w tym jednym elemencie, który tutaj podaliśmy.

Jeśli na chwilę obecną wygląda to wszystko niejasno, nie przejmuj się. Po pierwsze, tak naprawdę tutaj nadal jeszcze w pewnym sensie konfigurujemy naszą aplikację \(inicujejmy routing, pokazujemy gdzie wyrenderować aplikację etc.\), a po drugie ta "właściwa" część React-a jak i ogólnie tego tutoriala jest dużo lżejsza w odbiorze.

