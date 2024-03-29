Laboratorium nr 5 - Języki Programowania - 3. semestr

Podczas laboratorium należy zbudować aplikację, w której dojdzie do synchronizacji wielu wątków. Aplikacja pozwala na uruchamianie tych wątków i obserwowanie ich stanów. Aplikacja jest parametryzowana (wyjaśnienie znajduje się dalej). Aplikacja pełni rolę symulatora gry (z graficznym interfejsem), w której chodzi o obronę końcowych pól boiska przed nadlatującymi piłkami przez znajdujących się na tym boisku graczy dwóch przeciwnych drużyn. Niech boisko będzie planszą o zadanym rozmiarze, np. 9x10 lub więcej - przy czym liczba kolumn jest nieparzysta (rozmiar planszy to parametr).

W drugiej i przedostatniej kolumnie planszy poruszają się gracze, odpowiednio, jednej z dwóch drużyn. W każdej drużynie może być 2 lub więcej graczy (liczba graczy to parametr). Gracze poruszają się góra-dół, nie wchodząc na siebie. Każdy z graczy to osobny wątek.

W środkowej kolumnie, w wylosowanych miejscach, pojawiają się piłki. Piłki poruszają się lewa-prawo, przy czym kierunek poruszania się piłki na samym początku jest losowy. Piłki dolatując do drugiej lub przedostatniej kolumny odbijają się od graczy i zmieniają kierunek ruchu, jeśli gracze tam są. Jeśli w przedostatniej lub ostatniej kolumnie pole jest puste, piłki dolatują do pierwszej lub ostatniej kolumny i tam kończą swój ruch. Każda piłka to osobny wątek.

Na planszy nie może być więcej poruszających się piłek niż zadana liczba, minimum to 3, maksimum to liczba wierszy siatki (liczba piłek to parametr). Ponadto w jednym wierszu nie może pojawić się więcej niż jedna piłka.
Piłki generowane są przez osobny wątek, który jest aktywny gdy liczba poruszających się piłek jest niższa od zadanego parametru (dezaktywuje się, gdy liczba poruszających się piłek zrówna się z tym parametrem, aktywuje się ponownie, gdy liczba poruszających się piłek spadnie poniżej tego parametru).

W wierszach pierwszej i ostatniej kolumny pojawiają się liczby mówiące o tym, ile piłek skończyło tam swój ruch. Im więcej piłek dotrze na daną stronę planszy, tym gorszy jest wynik broniącej jej drużyny.
Gracze jednej drużyny są wątkami realizującymi tę samą metodę run(). Piłki są wątkami realizującymi tę samą metodę run(). Wątek generujący piłki posiada własną metodę run(). Należy zapewnić synchronizację pomiędzy wątkami.
Liczby po bokach, tutaj na dwóch pozycjach, informują o liczbie piłek, które doleciały do końca danego wiersza; symbol # reprezentuje piłkę; literki reprezentują graczy.
