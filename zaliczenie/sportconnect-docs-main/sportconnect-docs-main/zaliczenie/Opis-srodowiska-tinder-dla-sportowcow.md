# Opis środowiska i technologii – SportConnect

Dokument opisuje środowisko uruchomieniowe oraz technologie wykorzystane w projekcie SportConnect. Celem jest przedstawienie pełnego stosu technologicznego oraz uzasadnienie wyboru poszczególnych narzędzi.

---

## 1. Środowisko uruchomieniowe

### • Środowisko lokalne (development)
- .NET 8 SDK  
- Node.js 18+  
- PostgreSQL 14+  
- Vite (serwer deweloperski frontendu)  
- Swagger UI  
- EF Core CLI  

### • Środowisko testowe / produkcyjne
- Serwer obsługujący .NET 8  
- PostgreSQL jako baza danych  
- Zmienne środowiskowe dla connection stringów  
- Możliwość wdrożenia w Dockerze (opcjonalnie)

---

## 2. Technologie backendu

### • ASP.NET Core (.NET 8)
- Wysoka wydajność i stabilność.  
- Wbudowane DI, middleware, routing.  
- Idealny do budowy REST API.

### • C#
- Silne typowanie.  
- Nowoczesne funkcje języka (pattern matching, records).  
- Obsługa async/await.

### • Entity Framework Core
- ORM z podejściem Code‑First.  
- Migracje bazy danych.  
- LINQ do zapytań.

### • PostgreSQL
- Stabilna relacyjna baza danych.  
- Indeksy i transakcje ACID.  
- Wysoka wydajność przy dużej liczbie zapytań.

### • JWT Authentication
- Standardowy sposób autoryzacji.  
- Tokeny przechowywane po stronie klienta.  
- Middleware weryfikujące tokeny.

### • Swagger / OpenAPI
- Automatyczna dokumentacja API.  
- Podgląd endpointów i modeli danych.

### • Dodatkowe narzędzia backendowe
- AutoMapper – mapowanie encji na DTO.  
- Serilog – logowanie zdarzeń.  
- xUnit / NUnit – testy jednostkowe.  
- Moq – mockowanie zależności.  
- Biblioteki geolokalizacyjne – obliczanie odległości (Haversine).

---

## 3. Technologie frontendu

### • Vue 3
- Composition API  
- `<script setup>`  
- Modularna architektura komponentów  

### • TypeScript
- Silne typowanie.  
- Interfejsy dla DTO i modeli.  
- Łatwiejsza refaktoryzacja.

### • Pinia
- Zarządzanie stanem aplikacji.  
- Store dla autoryzacji, motywów i powiadomień.

### • Vue Router
- Nawigacja między widokami.  
- Route Guards dla ochrony tras.

### • Axios
- Interceptory tokenów JWT.  
- Globalna obsługa błędów.

### • Tailwind CSS
- Utility‑first CSS.  
- Szybkie prototypowanie UI.  
- Spójny design.

### • Vite
- Błyskawiczny serwer deweloperski.  
- Optymalizacja buildów.

### • Dodatkowe biblioteki
- Leaflet / @vue-leaflet – mapy.  
- FontAwesome – ikony.  
- date‑fns – operacje na datach.

---

## 4. Uzasadnienie wyboru technologii

- **.NET 8 + Vue 3** – nowoczesny, szybki i stabilny duet.  
- **PostgreSQL** – darmowa, wydajna i niezawodna baza danych.  
- **TypeScript** – zmniejsza liczbę błędów i poprawia jakość kodu.  
- **Tailwind CSS** – przyspiesza tworzenie UI.  
- **Pinia + Axios** – prosta i czytelna architektura frontendu.  
- **Swagger** – ułatwia testowanie i dokumentowanie API.

---

