# Instalujemy Nodemon

Zanim ruszymy dalej z bardziej zaawansowanym użyciem GraphQL, chciałbym zrobić jeszcze jedną drobną zmianę w konfiguracji naszego projektu. Jak pewnie sam zauważyłeś, za każdym razem kiedy zrobimy jakąś zmianę w kodzie naszej aplikacji, musimy ręcznie restartować serwer. Nie jest to najlepszy układ na dłuższą metę, poza tym dość częstym powodem frustracji, zwłaszcza dla początkujących, może być fakt, że właśnie po prostu zapomnieli zrestartować serwer.  
Żeby rozwiazać ten problem zainstalujemy małą bibliotekę o nazwie nodemon. Nodemon ma za zadanie obserwować wszelkie zmiany wprowadzone w naszych plikach i reagować na nie właśnie poprzez restart serwera, tak abyśmy sami nie musieli o tym pamiętać.

Instalujemy go komendą:

```
yarn add --dev nodemon
```

{% hint style="info" %}
 Jeśli używasz **npm** do zarządzania zależnościami musisz zamienić **--dev** na **--save-dev** w powyższej komendzie.
{% endhint %}

Musimy jeszcze zauktualizować nasz package.json dodając odpowiedni skrypt w sekcji `scripts`:

```javascript
{
    "scripts": {
        "server:dev": "nodemon server.js",
        // reszta skrytpów
    }
}
```

Teraz w terminalu możemy użyć powyższego do odpalenia naszego serwera, a nodemon będzie zajmował się automatycznym restartowaniem go przy każdej zmianie w pliku.

