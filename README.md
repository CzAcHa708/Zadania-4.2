# Zadania-4.2
Zadania
Ćwiczenie 4.1
a	b	a AND b	a OR b	NOT a	a XOR b	NOT (a AND b)
F	F		F	F	T	F	T				
F	T		F	T	T	T	T				
T	F		F	T	F	T	T			
T	T		T	T	F	F	F

Ćwiczenie 4.2
if (lista != null && lista.size() > 0) { ... }
a) Pierwszy warunek lista != null jest fałszywy, więc dzięki operatorowi && drugi warunek nie zostanie sprawdzony. 
b) Program spróbuje najpierw wykonać lista.size(). Jeśli lista == null, wystąpi NullPointerException, ponieważ lista nie istnieje.
c) if (lista == null || lista.size() == 0) { ... }

Ćwiczenie 4.3
a)  kod znaku 'D'          = __68____
b)  kod znaku 'z'          = ___122___
c)  znak o kodzie 74       = ___J___
d)  '7' - '0'              = ___7___
e)  (char)('a' - 32)       = ___A___

Ćwiczenie 4.4
FUNKCJA zamienNaMala(znak)
    JEŻELI znak >= 'A' ORAZ znak <= 'Z' WTEDY
        ZWRÓĆ znak + 32
    W PRZECIWNYM RAZIE
        ZWRÓĆ znak
    KONIEC JEŻELI
KONIEC FUNKCJI	

Ćwiczenie 4.5
a)  ASCII koduje znaki na 8 bitach.                          _F_ ASCII używa 7 bitów na znak i definiuje 128 znaków.
b)  Unicode to sposób zapisu znaków w bajtach.               _F_ Unicode to standard definiujący punkty kodowe znaków; sposoby zapisu tych punktów w bajtach to m.in. UTF-8, UTF-16 i UTF-32.
c)  UTF-8 jest zgodne wstecz z ASCII.                        _P_
d)  W UTF-8 każdy znak zajmuje dokładnie 2 bajty.            _F__ W UTF-8 znak może zajmować od 1 do 4 bajtów.
e)  U+0041 to punkt kodowy litery A.                         _P__
f)  Emoji nie da się zapisać w UTF-8.                        _F__ Emoji można zapisywać w UTF-8; wiele z nich zajmuje 4 bajty.

Ćwiczenie 4.6
a) To zjawisko nazywa się błędną interpretacją kodowania znaków.
b) Nie, dane w pliku nie musiały zostać uszkodzone.
Sam zapis w Windows-1250 nie zmienia bajtów. Problem polega na tym, że edytor odczytuje je jako UTF-8, czyli interpretuje bajty według innego kodowania.
Po ponownym otwarciu pliku z właściwym kodowaniem znaki mogą być wyświetlone poprawnie.
c) HTML 
Nagłówki HTTP serwera 
Pliki źródłowe projektu
 
Ćwiczenie 4.7
Tekst	Liczba znaków	Liczba bajtów
Ala	3		3
Zażółć	6		8
cześć 😀	7		10

Wyjaśnienie
W Pythonie len(tekst) liczy znaki, a nie bajty.

len(tekst.encode("utf-8")) liczy bajty potrzebne do zapisania tekstu w UTF-8.

Znaki ASCII, np. A, l, a, zajmują 1 bajt.

Polskie znaki, np. ż, ó, ć, zajmują w UTF-8 2 bajty każdy.

Emoji 😀 zajmuje 4 bajty w UTF-8.

Ćwiczenie 5.1
a)  len(s)      = __11____
b)  s[0]        = ___P___
c)  s[3]        = ___g___
d)  s[-1]       = ___a___
e)  s[0:6]      = ___Program___
f)  s.find("m") = ___4___

Ćwiczenie 5.2
a) Wystąpi błąd TypeError, ponieważ napisy (str) w Pythonie są niemodyfikowalne (immutable). Nie można zmienić pojedynczego znaku przez tekst[0] = "b".
b) Poprawna wersja:

tekst = "kot"
tekst = "b" + tekst[1:]
print(tekst)

Wynik:
bot
c) Po wykonaniu poprawnej wersji istnieją 2 obiekty typu str: "kot" oraz "bot". Zmienna tekst wskazuje na drugi z nich.

Ćwiczenie 5.3
a)
+-----+-----+-----+-----+
| 'A' | 'l' | 'a' | \0  |
+-----+-----+-----+-----+
  65    108   97     0

Bajt \0 oznacza koniec napisu.
b)
+----------+-----+-----+-----+
| długość  | 'A' | 'l' | 'a' |
+----------+-----+-----+-----+
|    3     | 65  | 108 | 97  |
+----------+-----+-----+-----+
Wersja z zapisaną długością, ponieważ długość jest przechowywana bezpośrednio w pamięci. Można ją odczytać od razu.

Ćwiczenie 5.4
a) Napisy (str) w Pythonie są niemodyfikowalne.
b) elementy = []

for i in range(100000):
    elementy.append(str(i))

wynik = "".join(elementy)
c) StringBuilder

Ćwiczenie 5.5
wiersz = "  Kowalski;Jan;2008-05-14;klasa 2p  "

wiersz = wiersz.strip()
pola = wiersz.split(";")

nazwisko = pola[0]
rok_urodzenia = pola[2][:4]

print(nazwisko)
print(rok_urodzenia)

Wynik:
Kowalski
2008

Ćwiczenie 5.6
1. Ananas
2. Banan
3. ananas
4. banan
5. zebra
6. Żaba

Nie, nie jest to zgodne z polskim porządkiem alfabetycznym.
Wynika to m.in. z tego, że wielkie i małe litery oraz znaki diakrytyczne mają różne kody.
Aby sortować zgodnie z polskimi regułami językowymi, należy zastosować sortowanie zależne od lokalizacji (locale/collation), np. odpowiednią regułę języka polskiego.

Ćwiczenie 6.1
Pole					Typ	Uzasadnienie
Imię					string	Imię jest tekstem i może zawierać litery oraz znaki diakrytyczne.
Wiek					int	Wiek podajemy jako całkowitą liczbę lat.
PESEL					string	PESEL należy przechowywać jako tekst, ponieważ może zaczynać się od zera i nie wykonujemy na nim obliczeń.
Numer telefonu				string	Numer telefonu powinien być tekstem, ponieważ może zawierać +, spacje lub zaczynać się od zera.
Adres e-mail				string	Adres e-mail jest ciągiem znaków, np. jan@example.com.
Zgoda na regulamin			bool	Zgoda może mieć tylko dwie wartości: wyrażona albo niewyrażona.
Wzrost w cm				int	Jeśli wzrost podajemy w pełnych centymetrach, wystarczy liczba całkowita.
Waga w kg (z dokładnością do 0,1)	float	Waga może mieć część ułamkową, np. 72,5 kg

Ćwiczenie 6.2
Kolumna	      	Typ w aplikacji	 Typ w bazie danych  Uzasadnienie
id_zamowienia	int		 INT	             Identyfikator jest liczbą całkowitą i powinien jednoznacznie wskazywać zamówienie.			
id_klienta	int	         INT	             Identyfikator klienta jest liczbą całkowitą i może być kluczem obcym.		
data_zlozenia	date 	         DATE 	             Data złożenia powinna być przechowywana jako typ daty, aby można było wykonywać operacje na datach.		
wartosc_brutto	Decimal	         DECIMAL	     Kwota pieniężna wymaga dokładnej reprezentacji z dwoma miejscami po przecinku.	
liczba_pozycji	int	         INT	             Liczba pozycji jest nieujemną liczbą całkowitą.		
czy_oplacone	bool	         BOOLEAN	     Informacja określa jeden z dwóch stanów: opłacone lub nieopłacone.		
kod_rabatowy	string	         VARCHAR(50)	     Kod rabatowy jest tekstem i może zawierać litery oraz cyfry.

Ćwiczenie 6.3

a)  float saldo_konta;   float może powodować błędy zaokrągleń przy przechowywaniu pieniędzy.	 decimal saldo_konta; – typ przeznaczony do dokładnych wartości finansowych
b)  int numer_telefonu = 501234567;  Numer telefonu nie jest liczbą, na której wykonujemy działania; może też zaczynać się od 0 lub zawierać +.	 string numer_telefonu = "501234567";
c)  byte liczba_uczniow_w_szkole;  byte ma ograniczony zakres (zależny od języka), więc może nie wystarczyć dla bardzo dużej szkoły lub zbioru szkół.	int liczba_uczniow_w_szkole;
d)  int identyfikator_uzytkownika;   // portal społecznościowy  Brak błędu  
e)  char plec;                        // wartości 'K' lub 'M'  char jest technicznie możliwy dla pojedynczego znaku 'K'/'M', ale jeśli wartości mają reprezentować kategorie, lepszy jest typ kategoryczny, np. enum.	enum Plec { K, M }
f)  int kod_pocztowy = 50137;         // dla kodu 50-137  	Kod pocztowy jest identyfikatorem tekstowym, a nie liczbą; może zaczynać się od zera.	string kod_pocztowy = "50-137";

Ćwiczenie 6.4
a) float – przechowuje wartości zmiennoprzecinkowe, np. 23,7 °C; zwykle zajmuje 4 bajty.
double – daje większą precyzję, ale zwykle zajmuje 8 bajtów; przy dokładności czujnika 0,1 °C jest to zazwyczaj niepotrzebne.
b) 365 × 24 × 60 = 525 600 odczytów
c) Typ	Rozmiar jednego odczytu	  Wszystkie odczyty
float	      4 B	          2 102 400 B ≈ 2,10 MB
double	      8 B	          4 204 800 B ≈ 4,20 MB	
d) Ponieważ temperatura ma dokładność 0,1 °C, można przechowywać ją jako liczbę całkowitą po pomnożeniu przez 10.
Zakres:
−40,0 °C → −400
+85,0 °C → 850
Wystarczy int16 (2 bajty), ponieważ jego zakres jest znacznie większy niż −400...850.
Wtedy: 525 600 × 2 B = 1 051 200 B ≈ 1,05 MB
Czyli rozwiązanie z int16 zajmuje połowę pamięci w porównaniu z float, a dokładność 0,1 °C zostaje zachowana.

Ćwiczenie 6.5
Nazwa danej	    Typ	         Zakres wartości	Uzasadnienie
id_ucznia	    int	         1–2 147 483 647	Identyfikator ucznia jest liczbą całkowitą.
imie	            string	 dowolny tekst	        Imię jest ciągiem znaków.
nazwisko	    string	 dowolny tekst	        Nazwisko może zawierać litery i znaki diakrytyczne.
wiek	            byte	 0–255	                Wiek jest niewielką liczbą całkowitą i nie wymaga dużego zakresu.
ocena	            decimal	 1,0–6,0	        Ocena może być zapisana jako liczba, np. 4,5.
obecnosc	    bool	 true / false	        Informacja określa, czy uczeń był obecny.
liczba_nieobecnosci int	         0–2 147 483 647	Liczba nieobecności jest liczbą całkowitą nieujemną.
procent_frekwencji  decimal	 0–100%	                Procent frekwencji może wymagać części ułamkowej, np. 92,5%.
data_urodzenia	    date	 daty kalendarzowe	Data urodzenia powinna być przechowywana jako typ daty.
data_wpisania_oceny datetime     data i czas	        Pozwala zapisać dokładny moment wpisania oceny.
przedmiot	    string	 dowolny tekst	        Nazwa przedmiotu jest tekstem, np. „Matematyka”.
numer_w_dzienniku   int	         1–100	                Numer ucznia w dzienniku jest liczbą całkowitą.
