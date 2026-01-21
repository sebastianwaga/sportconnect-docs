# Instrukcja uruchomienia projektu – SportConnect

Poniższa instrukcja opisuje sposób uruchomienia backendu aplikacji SportConnect w środowisku deweloperskim. Zawiera wymagania, konfigurację oraz kroki potrzebne do poprawnego startu projektu.

---

## 1. Wymagania wstępne

Aby uruchomić projekt, należy mieć zainstalowane:

- .NET 8 SDK  
- PostgreSQL (zalecana wersja 14 lub nowsza)  
- Narzędzie do zarządzania bazą danych (np. pgAdmin, TablePlus)  
- Git (opcjonalnie, jeśli projekt jest klonowany z repozytorium)

---

## 2. Klonowanie projektu

Jeśli projekt znajduje się w repozytorium Git, sklonuj go poleceniem:

`git clone <adres-repozytorium>`

Następnie przejdź do katalogu projektu:

`cd SportConnect`

---

## 3. Konfiguracja bazy danych

1. Uruchom PostgreSQL.  
2. Utwórz nową bazę danych, np. **sportconnect**.  
3. Zanotuj dane dostępowe do bazy:

- host  
- port  
- nazwa bazy  
- użytkownik  
- hasło  

---

## 4. Konfiguracja pliku `appsettings.json`

W pliku `appsettings.json` ustaw poprawny connection string do PostgreSQL, np.:

`"Host=localhost;Port=5432;Database=sportconnect;Username=postgres;Password=twojehaslo"`

---

## 5. Wykonanie migracji bazy danych

Aby utworzyć strukturę tabel w bazie danych, wykonaj:

`dotnet ef database update`

Po tej operacji baza danych będzie gotowa do pracy.

---

## 6. Uruchomienie projektu

Aby uruchomić backend, użyj:

`dotnet run`

Po uruchomieniu aplikacja będzie dostępna pod adresem:

- HTTP: `http://localhost:5000`  
- HTTPS: `https://localhost:7000`

---

## 7. Dokumentacja API (Swagger)

Po uruchomieniu projektu dokumentacja API będzie dostępna pod adresem:

`/swagger`

Przykład:

`https://localhost:7000/swagger`

---

## 8. Zmienne środowiskowe (opcjonalnie)

W środowiskach testowych lub produkcyjnych można użyć zmiennych środowiskowych:

- `ASPNETCORE_ENVIRONMENT`  
- `ConnectionStrings__DefaultConnection`

---

## 9. Typowe problemy i rozwiązania

### Brak migracji

Jeśli pojawia się błąd dotyczący migracji, wykonaj:

- `dotnet ef migrations add Initial`  
- `dotnet ef database update`

### Brak połączenia z bazą

Sprawdź:

- czy PostgreSQL działa  
- czy connection string jest poprawny  
- czy użytkownik ma uprawnienia do bazy  

---

## 10. Struktura projektu (skrót)

- **Controllers** – obsługa endpointów  
- **Services** – logika biznesowa  
- **Repositories** – komunikacja z bazą danych  
- **Models/Entities** – modele danych  
- **DTOs** – obiekty transferowe  
- **Migrations** – migracje EF Core  

---

## 11. Uruchomienie w trybie developerskim

Możesz użyć:

`dotnet watch run`

Projekt będzie automatycznie przeładowywany po zmianach w kodzie.

---

## 12. Zakończenie

Po wykonaniu powyższych kroków projekt powinien działać poprawnie w środowisku lokalnym.  
Można korzystać z API poprzez Swagger lub narzędzia takie jak Postman czy Insomnia.

---
