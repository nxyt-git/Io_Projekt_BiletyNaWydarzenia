Wymagania funkcjonalne:
|USER STORY| kryterium weryfikacji | Priorytet
Dla organizatora:
-  Organizator zakłada konto aby móc publikować wydarzenia | Rejstracja organizatora | MUST HAVE
- Organizator ma możliwość zalogowania się na swoje konto | Organizator loguje się do systemu | MUST HAVE
- Organizator tworzy wydarzenia | Wydarzenie zostaje przeslane do Bazy danych jako wydarzenie do weryfikacji | MUST HAVE
- Organizator edytuje szczegóły swojego wydarzenia | Rekord w bazie danych zostaje edytowany | MUST HAVE
- Organizator przegląda ilość sprzedanych biletów, zysk itd | Organizator ma dostęp do funkcji wyświetlania informacji  o przypisanych mu wydarzeniach | SHOULD HAVE
Dla Administratora:
- Administrator przegląda bądź odrzuca wydarzenia przesłane do weryfikacji | Zmiana statusu wydarzenia w bazie danych | MUST HAVE
- Organizator ma dostęp do metod edycji wydarzeń | Rekordy w bazie danych zostają edytowane|SHOULD HAVE 
- Organizator może przypisać bilet do użytkownika ręcznie | Pojawienie się nowego biletu w liście biletów użytkownika | SHOULD HAVE
- Organizator ma możlwiość kontaktu z klientem | Organizator widzi wysłane przez klienta zgłoszenia i może wysłać odpowiedź MUST HAVE
Dla klienta:
- Klient może utworzyć własne konto | Rejstracja konta klienckiego | MUST
- Klient ma możliwość zalogowania się na swoje konto | Klient loguje się do systemu | MUST HAVE
- Klinet może wyświetlić listę wydarzeń | Klient widzi  dostępne wydarzenia | MUST
- Klient może wybrać wydarzenie i kupić na nie bilet | Pojawia się nowy bilet w liście biletów klienta | MUST
- Klient może wyświetlić posiadane przez siebie bilety | Klient widzi listę swoich biletów w aplikacji | MUST
- Klient może wyszukiwać interesujące go wydarzenia po nazwie | Klient widzi wydarzenia o wpisanej nazwie | SHOULD
- Klient ma możliwość kontaktu z administracją | Administracja otrzymuje wiadomość od klienta | MUST
Dla systemu:
- System przypisuję bilety zakupione przez klienta, do listy ich biletów |Klient widzi zakupione przez siebie bilety |MUST
- System zapisuje utworzone przez organizatora, zatwierdzone przez administratora wydarzenia do bazy danych | Pojawienie sie nowych wpisów w bazie danych | MUST
Dla systemu płatności:
- Przesłanie informacji zwrotnej do systemu komputerowego | System komputerowy zapisuje zakup biletu bądź wyświetla komunikat błędu | MUST

Wymagania niefunkcjonalne:
- Bezpieczeństwo | Połączenie przez HTTPS; hasła przechowywane w postaci zahaszowanej; dane kart obsługuje wyłącznie system płatności. 
- Niezawodność | Automatyczna kopia zapasowa bazy danych raz na dobę, przechowywana min. 7 dni. 
- Wydajność | Lista wydarzeń ładuje się w mniej niż 3 s. 
- Responsywność | Interfejs nie blokuje się podczas przetwarzania płatności (użytkownik widzi wskaźnik postępu). 
- Spójność danych | Brak podwójnej sprzedaży tego samego biletu (transakcje w bazie). 
- Użyteczność | Interfejs działa na komputerze i telefonie. 