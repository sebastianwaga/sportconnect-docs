# Plan Sprintu nr 2

**Data:** 2026-02-05  
**Okres trwania:** 2025-09-30 – 2025-10-30  
**Uczestnicy:** Sebastian (Developer), Właściciel Produktu (symulowany)

---

## 1. Cel Sprintu (Sprint Goal)

Dostarczyć funkcjonalność profilu użytkownika, zarządzania sportami oraz lokalizacją, aby umożliwić dopasowywanie użytkowników i przygotować aplikację do obsługi zaproszeń treningowych.

---

## 2. Wybrane Historyjki Użytkownika (Backlog Sprintu)

### Historyjka 1: US-05 – Edycja profilu użytkownika

**Opis:**  
Jako *zalogowany użytkownik*, chcę *edytować swój profil (imię, nazwisko, opis, zdjęcie)*, aby *mój profil był aktualny i atrakcyjny dla innych użytkowników*.

**Priorytet:** Wysoki  
**Estymacja:** 8 SP  

**Kryteria akceptacji:**
- Użytkownik może edytować dane profilu.
- Zmiany są zapisywane w bazie danych.
- Walidacja danych (np. maksymalna długość opisu).
- Endpoint zwraca zaktualizowany profil.

---

### Historyjka 2: US-06 – Wybór i zarządzanie sportami użytkownika

**Opis:**  
Jako *użytkownik*, chcę *wybrać sporty, które uprawiam*, aby *system mógł dopasować mnie do odpowiednich partnerów treningowych*.

**Priorytet:** Wysoki  
**Estymacja:** 5 SP  

**Kryteria akceptacji:**
- Użytkownik może dodać i usunąć sporty.
- Lista sportów jest pobierana z bazy danych.
- Relacja wiele-do-wielu działa poprawnie.
- Endpoint zwraca aktualną listę sportów użytkownika.

---

### Historyjka 3: US-07 – Ustawienie lokalizacji użytkownika

**Opis:**  
Jako *użytkownik*, chcę *ustawić swoją lokalizację (latitude, longitude) oraz promień wyszukiwania*, aby *system mógł znaleźć osoby w mojej okolicy*.

**Priorytet:** Średni  
**Estymacja:** 5 SP  

**Kryteria akceptacji:**
- Użytkownik może ustawić współrzędne i promień wyszukiwania.
- Dane są zapisywane w bazie.
- Walidacja promienia (np. 1–50 km).
- Endpoint zwraca aktualne ustawienia lokalizacji.

---

### Historyjka 4: US-08 – Pobieranie profilu użytkownika

**Opis:**  
Jako *użytkownik*, chcę *pobrać swój profil*, aby *widzieć aktualne dane i ustawienia*.

**Priorytet:** Średni  
**Estymacja:** 3 SP  

**Kryteria akceptacji:**
- Endpoint zwraca pełne dane profilu.
- Zwracane są sporty, lokalizacja i dane podstawowe.
- Dostęp wymaga tokena JWT.

---

## Podsumowanie

**Łączna suma Story Points:** 21 SP  
**Pojemność zespołu:** 18–22 SP (symulowana, 1 osoba)

---

## 3. Podział na zadania

### Zadania dla Historyjki 1: Edycja profilu użytkownika
- Dodanie pól profilu w modelu `User`
- Implementacja endpointu `PUT /users/{id}`
- Walidacja danych wejściowych
- Obsługa uploadu zdjęcia (opcjonalnie)
- Testy jednostkowe i integracyjne

### Zadania dla Historyjki 2: Zarządzanie sportami użytkownika
- Implementacja relacji `UserSport`
- Endpoint `POST /users/{id}/sports`
- Endpoint `DELETE /users/{id}/sports/{sportId}`
- Pobieranie listy sportów
- Testy jednostkowe

### Zadania dla Historyjki 3: Lokalizacja użytkownika
- Dodanie pól `latitude`, `longitude`, `searchRadiusKm`
- Endpoint `PUT /users/{id}/location`
- Walidacja danych
- Testy jednostkowe

### Zadania dla Historyjki 4: Pobieranie profilu
- Endpoint `GET /users/{id}`
- Zwracanie danych profilu + sportów + lokalizacji
- Testy jednostkowe

---

## 4. Definicja Ukończenia (Definition of Done)

- Kod działa zgodnie z kryteriami akceptacji.
- Testy jednostkowe i integracyjne przechodzą pomyślnie.
- Kod został sprawdzony i zatwierdzony w procesie Code Review.
- Funkcjonalność wdrożona na środowisko testowe.
- Właściciel Produktu zaakceptował działanie funkcjonalności.
- Dokumentacja została zaktualizowana (Swagger + opis funkcji).
