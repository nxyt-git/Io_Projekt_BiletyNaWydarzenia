# Stos technologiczny

Architektura systemu opiera się na podziale na niezależną warstwę kliencką (Frontend) oraz serwerową (Backend) komunikujące się za pomocą REST API.

| Warstwa | Technologia | Wersja / Narzędzia |
| :--- | :--- | :--- |
| **Frontend** | React + TypeScript | Vite, Tailwind CSS |
| **Backend** | C# + ASP.NET Core Web API | .NET 8 (LTS), REST API |
| **Baza danych** | PostgreSQL + Entity Framework Core | Npgsql, podejście Code First, LINQ |
| **Autoryzacja i bezpieczeństwo** | JSON Web Token (JWT) | BCrypt.Net (hashowanie haseł) |
| **Integracje i funkcje dodatkowe** | Stripe API, Biblioteka `QRCoder` | MailKit (powiadomienia e-mail) |
| **Środowisko i wdrożenie** | Docker, GitHub Actions | Docker Compose, Git |

---

## Uzasadnienie wyboru technologii

### 1. Frontend: React + TypeScript + Tailwind CSS
* **Komponentowa architektura:** Pozwala na łatwe wydzielenie powtarzalnych elementów interfejsu, takich jak karty wydarzeń, koszyk, formularze zakupu czy panel organizatora.
* **TypeScript:** Zapewnia statyczne typowanie, co minimalizuje ryzyko błędów w trakcie pracy zespołowej i ułatwia refaktoryzację kodu.
* **Tailwind CSS:** Umożliwia szybkie stworzenie responsywnego interfejsu (RWD), co jest kluczowe dla użytkowników kupujących i okazujących bilety na urządzeniach mobilnych.

### 2. Backend: C# + ASP.NET Core Web API
* **Silne typowanie i bezpieczeństwo kodu:** Język C# wymusza ścisłą kontrolę typów już na etapie kompilacji, co ułatwia utrzymanie porządku w kodzie przy pracy zespołowej i minimalizuje ryzyko błędów w logice biznesowej.
* **Wysoka wydajność:** Platforma .NET oraz asynchroniczny model przetwarzania zapytań (`async/await`) zapewniają bardzo dobrą wydajność przy jednoczesnej obsłudze wielu użytkowników (np. podczas startu sprzedaży biletów na popularne wydarzenie).
* **Bogaty wbudowany ekosystem:** ASP.NET Core oferuje gotowe mechanizmy wstrzykiwania zależności (Dependency Injection), walidacji modeli, obsługi błędów oraz integracji ze Swaggerem (OpenAPI) do automatycznego dokumentowania endpointów.

### 3. Baza danych: PostgreSQL + Entity Framework Core
* **Gwarancja ACID i transakcyjność:** W systemie biletowym kluczowe jest uniknięcie sytuacji podwójnej rezerwacji tego samego miejsca (*race condition*). Relacyjna baza PostgreSQL zapewnia silną spójność danych oraz mechanizmy blokowania wierszy podczas transakcji zakupu.
* **Złożone relacje:** Struktura danych (Użytkownicy, Role, Wydarzenia, Miejsca/Pule biletów, Zamówienia, Bilety) ma charakter ściśle relacyjny.
* **Entity Framework Core:** Dojrzały ORM dla .NET, który ułatwia pracę z bazą danych w podejściu *Code First*, upraszcza zarządzanie migracjami w zespole oraz zapewnia bezpieczeństwo typów przy budowaniu zapytań za pomocą LINQ.

### 4. Bezpieczeństwo i autoryzacja: JWT + BCrypt.Net
* **Kontrola dostępu oparta na rolach (RBAC):** Tokeny JWT w połączeniu z wbudowanym middleware autoryzacji ASP.NET Core pozwalają na bezstanowe uwierzytelnianie i łatwe rozdzielenie uprawnień pomiędzy **Uczestnika**, **Organizatora** (tworzenie wydarzeń, skanowanie biletów) oraz **Administratora**.
* **Ochrona haseł:** Biblioteka `BCrypt.Net` zabezpiecza hasła użytkowników w bazie danych przed wyciekiem za pomocą bezpiecznego hashowania z solą.

### 5. Narzędzia wspierające proces biletowy
* **Generowanie kodów QR (`QRCoder`):** Biblioteka dla .NET umożliwiająca szybkie wygenerowanie unikalnego kodu QR dla każdego zakupionego biletu w celu jego późniejszej weryfikacji na wejściu.
* **Płatności (Stripe API – tryb testowy):** Oficjalne SDK `Stripe.net` pozwala na bezpieczne zasymulowanie procesu płatności bez konieczności samodzielnego przetwarzania wrażliwych danych kart płatniczych.

### 6. Konteneryzacja i praca zespołowa: Docker + GitHub
* **Docker i Docker Compose:** Gwarantują identyczne środowisko uruchomieniowe (baza danych + backend) na komputerze każdego członka zespołu, eliminując problem „u mnie działa”.
* **GitHub (PR + Code Review):** Umożliwia kontrolę wersji, śledzenie postępów za pomocą *Issues* oraz weryfikację kodu przed włączeniem zmian do głównej gałęzi projektu.