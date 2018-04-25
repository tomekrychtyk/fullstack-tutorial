# Dodajemy repozytorium do AWS CodeCommit

### AWS CodeCommit czy GitHub?

Przy starcie praktycznie każdego nowego projektu dobrą praktyką jest konfiguracja systemu kontroli wersji kodu. Ja postanowiłem używać do tego celu Git, a jako repozytorium wybrałem jeden z serwisów AWS, a mianowicie **AWS CodeCommit**. Dlaczego nie **GitHub**? Po pierwsze, prawie każdy zna GitHub, a w końcu tutorial polega na tym, żeby nauczyć się czegoś nowego. Po drugie i tak duża część naszej aplikacji będzie zależeć właśnie od różnych serwisów AWS więc uznałem, że kod projektu także chcę mieć zarządzany przez AWS - dzięki temu praktycznie cała aplikacja jest w jednym miejscu.

### Amazon Web Services Free Tier

{% hint style="warning" %}
Aby skorzystać z jakiegokolwiek serwisu AWS, należy zapisać się na tzw. Free Tier - jest to roczny okres, w którym większość usług oferowanych przez AWS mamy zupełnie za darmo. Zaznaczam jednak, że nie wszystko jest darmowe. I tak np. żeby ukończyć ten kurs, **nie mogę zagwarantować, że nie zapłacisz ani grosza**, jednak gwarantuję, że jeśli coś wyjdzie, to będą to sprawy właśnie groszowe, typu $0.5 - $1.0 miesięcznie. Więcej o Free Tier można znaleźć [tutaj](https://aws.amazon.com/free).
{% endhint %}



Nie będę opisywał tutaj jak zapisać się do Free Tier, bo naprawdę wystarczy wejść w podanego powyżej linka i proces rejectracji jest bardzo prosty.

### Tworzymy repozytorium w CodeCommit

Zakładam zatem, że masz już zarejestrowane i aktywne konto na AWS. Po zalogowaniu się do konsoli AWS po prostu wpisz w wyszukiwarce znajdującej się nad listą serwisów odpowiednią frazę:

![Pic 1. Wyszukiwarka serwis&#xF3;w AWS](../.gitbook/assets/screenshot-from-2018-04-25-14-26-43.png)

Natępnie klikamy przycisk '**Create Repository**' i wypełniamy prosty formularz:

![](../.gitbook/assets/screenshot-from-2018-04-25-14-31-01.png)

Pojawi nam się prośba o konfigurację SNS-a, czyli notyfikacji e-mailowych. Nie potrzebujemy tego na razie więc klikamy tutaj '**Skip**'. Po tym kroku nasze repozytorium powinno zostać utworzone pomyślnie.

{% page-ref page="dodajemy-nowego-uzytkownika-w-aws.md" %}



