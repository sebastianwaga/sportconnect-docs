# Opis architektury systemu – SportConnect

Aplikacja SportConnect została zaprojektowana jako system składający się z dwóch głównych modułów: backendu (REST API) oraz frontendu (SPA). Architektura systemu została oparta na zasadach modularności, skalowalności oraz separacji odpowiedzialności.

---

## 1. Architektura ogólna

System składa się z dwóch niezależnych warstw:

- **Backend (API)** – odpowiedzialny za logikę biznesową, autoryzację, przetwarzanie danych oraz komunikację z bazą danych.
- **Frontend (SPA)** – odpowiedzialny za interfejs użytkownika, komunikację z API oraz prezentację danych.

Komunikacja między warstwami odbywa się poprzez protokół **HTTPS** oraz format danych **JSON**.

---

## 2. Architektura backendu

Backend został zbudowany w oparciu o architekturę warstwową:

### • Warstwa prezentacji (Controllers)
- Odbiera żądania HTTP.
- Waliduje dane wejściowe.
- Przekazuje dane do warstwy logiki biznesowej.
- Zwraca odpowiedzi w formacie JSON.

### • Warstwa logiki biznesowej (Services)
- Zawiera zasady działania aplikacji.
- Przetwarza dane i wykonuje operacje biznesowe.
- Komunikuje się z repozytoriami.

### • Warstwa dostępu do danych (Repositories)
- Odpowiada za komunikację z bazą danych.
- Wykonuje zapytania i zapisuje dane.
- Mapuje encje na modele domenowe.

### • Warstwa danych (Entities / Models)
- Definicje encji odwzorowujących strukturę tabel w bazie danych.

### • Dokumentacja API
- Generowana automatycznie za pomocą Swagger / OpenAPI.

---

## 3. Architektura frontendu

Frontend został zbudowany jako aplikacja **SPA (Single Page Application)** oparta na Vue 3.

### Główne elementy architektury:

### • Warstwa prezentacji (Views / Components)
- Odpowiada za renderowanie interfejsu użytkownika.
- Komponenty są modularne i wielokrotnego użytku.

### • Warstwa logiki aplikacji (Composables / Stores)
- Zarządzanie stanem aplikacji (Pinia).
- Logika autoryzacji, motywów, powiadomień.

### • Warstwa komunikacji z API (Axios)
- Interceptory obsługujące tokeny JWT.
- Globalna obsługa błędów HTTP.

### • Routing (Vue Router)
- Nawigacja między widokami.
- Ochrona tras (Route Guards).

---

## 4. Architektura bazy danych

System korzysta z relacyjnej bazy danych PostgreSQL.

### Najważniejsze tabele:

- **Users** – dane użytkowników.
- **Sports** – lista dyscyplin sportowych.
- **UserSports** – relacja wiele‑do‑wielu.
- **UserLocation** – lokalizacja użytkownika.
- **Invitations** – zaproszenia do wspólnych treningów.
- **Matches** – system dopasowywania użytkowników.

### Relacje:

- User 1‑N UserLocation  
- User N‑N Sports (UserSports)  
- User 1‑N Invitations  
- User 1‑N Matches  

---

## 5. Przepływ danych w systemie

### Przykład: logowanie użytkownika

1. Użytkownik wysyła dane logowania z frontendu.  
2. Backend weryfikuje dane i generuje token JWT.  
3. Token jest zwracany do frontendu.  
4. Frontend zapisuje token w localStorage.  
5. Każde kolejne zapytanie do API zawiera token w nagłówku `Authorization`.  
6. Backend weryfikuje token i zwraca dane użytkownika.

---

## 6. Możliwości rozbudowy architektury

- Integracja z aplikacją mobilną.  
- Konteneryzacja (Docker).  
- Wprowadzenie mikroserwisów.  
- System powiadomień push.  
- Integracja z zewnętrznymi API sportowymi.

---
