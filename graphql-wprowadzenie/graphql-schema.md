# GraphQL Schema

### Co to jest "schema"

W ostatnim rozdziale pomyślnie napisaliśmy prosty serwer w Express, ale przy próbie odpalenia GraphQL w przeglądarce, natrafiliśmy na błąd o treści: "**GraphQL middleware options must contain a schema**".  
GraphQL próbuje nam powiedzieć, że nie skonfigurowaliśmy odpowiednia naszego middleware-u. GraphQL wymaga od nas zdefiniowania tzw. "**schema**", czyli mówiąc po polsku schematu, który niejako definiuje zależności między danymi w naszej bazie danych. GraphQL potrzebuje go, aby wiedzieć jakie dokładnie atrybuty każdy z obiektów w bazie danych posiada, jak są zorganizowane itp.

### Definiujemy prosty schemat

Zacznijmy od utworzenia folderu **schema**, a następnie utwórzmy w nim plik **schema.js**.

