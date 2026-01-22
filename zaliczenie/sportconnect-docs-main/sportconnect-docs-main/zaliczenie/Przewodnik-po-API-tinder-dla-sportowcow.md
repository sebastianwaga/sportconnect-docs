# Przewodnik po API (API Guide) – SportConnect

Dokument opisuje sposób korzystania z API aplikacji SportConnect. Zawiera informacje o autoryzacji, podstawowych operacjach oraz kolejności korzystania z dostępnych zasobów.

---

## 1. Autoryzacja

API korzysta z mechanizmu JWT (JSON Web Token).  
Aby uzyskać dostęp do zasobów wymagających uwierzytelnienia, użytkownik musi najpierw założyć konto, a następnie zalogować się.  
Po poprawnym logowaniu system zwraca token, który należy przesyłać w nagłówku autoryzacji przy każdym kolejnym zapytaniu.  
Token potwierdza tożsamość użytkownika i umożliwia dostęp do jego danych.

---

## 2. Rejestracja użytkownika

Rejestracja polega na przekazaniu podstawowych danych użytkownika, takich jak adres e‑mail, hasło oraz dane osobowe.  
Po poprawnym utworzeniu konta system zwraca informację o nowym użytkowniku.  
Rejestracja nie wymaga wcześniejszej autoryzacji.

---

## 3. Logowanie użytkownika

Logowanie odbywa się poprzez podanie adresu e‑mail oraz hasła.  
Jeśli dane są poprawne, system zwraca token JWT.  
Token ten należy zapisać i wykorzystywać przy wszystkich operacjach wymagających uwierzytelnienia.  
Bez ważnego tokena dostęp do zasobów użytkownika jest zablokowany.

---

## 4. Pobieranie profilu użytkownika

Po zalogowaniu użytkownik może pobrać swój profil.  
Profil zawiera podstawowe dane, takie jak imię, nazwisko, adres e‑mail, lista wybranych sportów oraz ustawienia lokalizacji.  
Dostęp do profilu wymaga przesłania tokena autoryzacyjnego.

---

## 5. Edycja profilu użytkownika

Użytkownik może edytować swoje dane, takie jak imię, nazwisko czy opis profilu.  
Zmiany są zapisywane w systemie i widoczne przy kolejnym pobraniu profilu.  
Operacja wymaga autoryzacji.

---

## 6. Ustawienie lokalizacji użytkownika

Użytkownik może ustawić swoją lokalizację geograficzną oraz promień wyszukiwania.  
Dane te są wykorzystywane do dopasowywania użytkowników znajdujących się w pobliżu.  
Zmiana lokalizacji wymaga autoryzacji.

---

## 7. Zarządzanie sportami użytkownika

Użytkownik może dodawać lub usuwać sporty, które uprawia.  
Lista sportów jest przechowywana w systemie i wykorzystywana do dopasowywania partnerów treningowych.  
Operacje te wymagają autoryzacji.

---

## 8. Lista dostępnych sportów

System udostępnia listę wszystkich sportów, które mogą zostać przypisane do użytkownika.  
Lista ta jest publiczna i nie wymaga autoryzacji.

---

## 9. Najczęstsze błędy

- **Brak autoryzacji** – występuje, gdy użytkownik nie przekaże tokena lub token jest niepoprawny.  
- **Niepoprawne dane wejściowe** – pojawia się, gdy przesłane dane nie spełniają wymagań walidacyjnych.  
- **Brak zasobu** – zwracany, gdy użytkownik lub inny zasób nie istnieje.

---

## 10. Kolejność korzystania z API

1. Rejestracja nowego użytkownika.  
2. Logowanie i pobranie tokena.  
3. Edycja profilu użytkownika.  
4. Dodanie sportów do profilu.  
5. Ustawienie lokalizacji.  
6. Pobieranie profilu i dalsze operacje.

---

## 11. Pełna specyfikacja OpenAPI

Pełna specyfikacja API dostępna jest w formacie OpenAPI pod adresem generowanym przez Swagger.  
Można ją wyświetlić w przeglądarce lub wyrenderować w zewnętrznych narzędziach.

---
