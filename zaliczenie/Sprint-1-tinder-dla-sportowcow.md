# Plan Sprintu nr 1

**Data:** 2026-01-21  
**Okres trwania:** 2025-08-30 – 2025-09-30  
**Uczestnicy:** Sebastian (Developer), Właściciel Produktu (symulowany)

---

## 1. Cel Sprintu (Sprint Goal)

Dostarczyć podstawową funkcjonalność rejestracji i logowania użytkownika wraz z konfiguracją bazy danych oraz modelem danych, aby umożliwić dalszy rozwój aplikacji SportConnect.

---

## 2. Wybrane Historyjki Użytkownika (Backlog Sprintu)

### Historyjka 1: US-01 – Rejestracja użytkownika

**Opis:**  
Jako *nowy użytkownik*, chcę *utworzyć konto w aplikacji*, aby *móc korzystać z funkcjonalności SportConnect*.

**Priorytet:** Wysoki  
**Estymacja:** 8 SP  

**Kryteria akceptacji:**
- Użytkownik może podać e-mail, hasło, imię i nazwisko.
- System zapisuje dane w bazie danych.
- System waliduje poprawność danych (np. unikalny e-mail).
- Po rejestracji użytkownik otrzymuje potwierdzenie.

---

### Historyjka 2: US-02 – Logowanie użytkownika

**Opis:**  
Jako *zarejestrowany użytkownik*, chcę *zalogować się do aplikacji*, aby *uzyskać dostęp do swojego konta*.

**Priorytet:** Wysoki  
**Estymacja:** 5 SP  

**Kryteria akceptacji:**
- Użytkownik podaje e-mail i hasło.
- System weryfikuje dane i generuje token JWT.
- Niepoprawne dane zwracają komunikat błędu.
- Token jest zwracany w odpowiedzi i możliwy do użycia w kolejnych żądaniach.

---

### Historyjka 3: US-03 – Konfiguracja bazy danych

**Opis:**  
Jako *developer*, chcę *mieć poprawnie skonfigurowaną bazę danych i migracje*, aby *móc rozwijać kolejne funkcjonalności*.

**Priorytet:** Wysoki  
**Estymacja:** 3 SP  

**Kryteria akceptacji:**
- Projekt zawiera skonfigurowany `DbContext`.
- Migracje tworzą tabele użytkowników i powiązane encje.
- Po uruchomieniu aplikacji baza działa poprawnie.

---

### Historyjka 4: US-04 – Dokumentacja OpenAPI

**Opis:**  
Jako *developer*, chcę *mieć automatycznie generowaną dokumentację API*, aby *łatwo testować i prezentować funkcjonalności backendu*.

**Priorytet:** Średni  
**Estymacja:** 2 SP  

**Kryteria akceptacji:**
- Swagger jest dostępny pod `/swagger`.
- Dokumentacja OpenAPI generuje się automatycznie.
- Endpointy rejestracji i logowania są widoczne.

---

## Podsumowanie

**Łączna suma Story Points:** 18 SP  
**Pojemność zespołu:** 18 SP (symulowana, 1 osoba)

---

## 3. Podział na zadania

### Zadania dla Historyjki 1: Rejestracja użytkownika

- Zaprojektowanie modelu `User`
- Implementacja endpointu `POST /users/register`
- Walidacja danych wejściowych
- Zapis użytkownika w bazie danych
- Testy jednostkowe i integracyjne

### Zadania dla Historyjki 2: Logowanie użytkownika

- Implementacja serwisu autoryzacji
- Generowanie tokena JWT
- Endpoint `POST /auth/login`
- Obsługa błędów logowania
- Testy jednostkowe

### Zadania dla Historyjki 3: Konfiguracja bazy danych

- Utworzenie `ApplicationDbContext`
- Konfiguracja połączenia z PostgreSQL
- Dodanie migracji startowej
- Weryfikacja poprawności działania

### Zadania dla Historyjki 4: Dokumentacja OpenAPI

- Dodanie `AddSwaggerGen()`
- Konfiguracja Swagger UI
- Włączenie dokumentacji XML
- Test w przeglądarce

---

## 4. Definicja Ukończenia (Definition of Done)

- Kod został napisany i działa zgodnie z kryteriami akceptacji.
- Testy jednostkowe i integracyjne zostały napisane i przechodzą pomyślnie.
- Kod został sprawdzony i zatwierdzony w procesie Code Review.
- Funkcjonalność została wdrożona na środowisko testowe.
- Właściciel Produktu zaakceptował działanie funkcjonalności.
- Dokumentacja została zaktualizowana (jeśli to konieczne).
