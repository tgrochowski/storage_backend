Readme

Napisz dwie aplikacje, które będą komunikować się ze sobą przy pomocy REST. Pierwsza aplikacja będzie źródłem danych, z którego druga aplikacja (aplikacja kliencka) będzie korzystać. Dostęp do bazy ma tylko pierwsza aplikacja.
Aplikacja kliencka ma umożliwić pobranie listy produktów, które:

    • Znajdują się na składzie
    • Nie znajdują się na składzie
    • Znajdują się na składzie w ilości większej niż 5
    
Aplikacja kliencka powinna także umożliwiać edycję produktu, dodanie nowego i usunięcie.
Zadanie powinno być zrealizowane w formie bundle’a Symfony lub paczki do Laravela, które będą dociągane przez Composera.

Technologie, na których powinno opierać się zadanie:

    • Symfony lub Laravel
    • baza SQL
    
    
Struktura bazy:
Tabela items
id
name
amount
1
Produkt 1
4
2
Produkt 2
12
3
Produkt 5
0
4
Produkt 7
6
5
Produkt 8
2




Oceniane będą:
    • wykorzystanie i znajomość języka php i OOP,
    • wykorzystanie i znajomość wybranego frameworka,
    • wykorzystanie i znajomość dobrych praktyk pisania kodu
    • wykorzystanie i znajomość wzorców projektowych,
    • wykorzystanie i znajomość standardów REST Api,
    • wykorzystanie i znajomość systemu kontroli wersji GIT
