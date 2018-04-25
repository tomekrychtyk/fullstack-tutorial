# Łączymy się z CodeCommit

Aby połączyć się i skolonować repozytorium utworzone w CodeCommit wykonujemy z linii poleceń następującą komendę:

```text
git clone ssh://git-codecommit.eu-central-1.amazonaws.com/v1/repos/home-budget
```

Oczywiście podając na końcu nazwę repozytorium, którą podaliśmy przy jego tworzeniu. Po wykonaniu tego polecenia nasze repozytorium powinno zostać zainicjowane na naszej lokalnej maszynie, do tego powinien zostać utworzony katalog home-budget oraz wyświetlona poniższa informacja:

![](../.gitbook/assets/screenshot-from-2018-04-25-15-57-05.png)

Przechodzimy teraz do katalogu /home-budget i tworzymy następującą strukturę katalogów:

![](../.gitbook/assets/screenshot-from-2018-04-25-13-00-14%20%281%29.png)

### Inicjujemy backend

Kolejną rzeczą, którą musimy zrobić to zainicjować nasz projekt za pomocą yarn, jako że będziemy na pewno dodawać do niego dużo zależnych bibliotek, więc narzędzie do obługi tych zależności jest tutaj niezbędne. Aby zainicjować projekt, przechodzimy w terminalu do katalogu **backend**/ i wpisujemy po prostu` yarn init`:

![](../.gitbook/assets/screenshot-from-2018-04-25-13-13-45.png)

