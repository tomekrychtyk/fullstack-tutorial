# Po pierwsze: yarn init

Długo zastanawiałem się czy konfigurować środowisko od podstaw czy użyć generatora szkieletu aplikacji jak np. **create-react-app**. Postanowiłem jednak skonfigurować cały projekt własnoręcznie. Decyzja ta ma jednak cele czysto edukacyjne. W prawdziwym projekcie naprawdę polecam użycie "gotowca" takiego jak create-react-app. Po pierwsze zaoszczędzisz dużo czasu, a po drugie, pomimo że jest to generator, to nadal daje on możliwość pełnej konfiguracji i dostosowania aplikacji do własnych potrzeb.

#### Node i yarn

Generalnie żeby zapoczątkować nasz projekt będziemy potrzebować dwóch narzędzi - Node.js oraz managera paczek, czyli yarn-a. Zakładam, że nawet jeśli nie masz ich w swoim systemie, nie będziesz miał problemu z ich instalacją, bo ta jest naprawdę bardzo prosta.  
Odsyłam więc do konkretnych stron obu projektów: [node](https://nodejs.org/en/download/) oraz [yarn](https://yarnpkg.com/lang/en/docs/install).

Mając w naszym systemie yarn możemy w końcu zainicjować projekt. Przejdź do katalogu, w którym umieścisz pliki naszej aplikacji i stwórz w nim dwa katalogi: "**client**" oraz "**backend**". Na początem zajmiemy się kliencką aplikacją, a przynajmniej jej szkieletem, ~~więc~~ wejdź do katalogu client i z linii poleceń odpal komendę:

`yarn init -y`

Komenda ta stworzy plik `package.json` oraz zainicjuje projekt.  
Teraz możemy zacząć dodawać paczki do naszego projektu. Na pierszy ogień pójdzie oczywiście **Webpack**!

