1. Opis/wizja projektu:
Projekt jest systemem sprzedaży biletów online.
Organizatorzy tworzą wydarzenia z daną pulą biletów.
Następnie zainteresowani klienci mają możliwość kupna biletów na wydarzenia z puli.
System przypisuje dane bilety do użytkownika.
Administrator posiada uprawienia pozwalające na zarządzanie całym systemem. Aby operację były zgodne.
W przypadku nieprzewidzianych problemów z serwisem użytkownik ma możliwość kontaktu z administracją,
a administracja ma możliwość rozwiązania problemów.
Płatność odbywa się przez zewnętrzny system. (Jako ze jest to projekt naukowy platnosci nie beda rzeczywiste)
2. Zakres systemu:
Rejstracja i logowanie użytkownika, zakup biletów wraz z płatnością, przeglądanie dostępnych wydarzeń,
przeglądanie posiadanych biletów. Tworzenie wydarzeń przez konta organizatorskie.
Administracja systemu
3.  Aktorzy:
3.1 Klient - reprezentuje pojedyńczą osobę, ma możliwości przeglądania wydarzeń, kupna biletów, wykonanina płatnści i kontaktu z administracją.
3.2 Organizator - reprezentuje człowieka bądź firmę, ma możliwość dodania i edycji wydarzenia, konto organizatora powinno byc zatwierdzone przez administację
3.3 Admin - weryfikuje konta organizatorskie, ma możliwość przypisania użytkonikowi biletu, przykładowo w sytuacji otrzymania płatności gdy system uległ awarii i bilet nie został przypisany. Zatwierdza lub usuwa wydarzenia
3.4 System płatności - zewnętrzny system płatności (w tym przypadku powinna zostać uruchomiona nowa strona reprezentująca płatność, zwracająca informacje czy płatność się powiodła.)