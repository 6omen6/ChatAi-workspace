# Plan realizacji projektu prototypu chatbota AI

## 1. Przygotowanie i konfiguracja (2h)

### Backend:
- [done] 1.1. Utworzenie projektu ASP.NET Core Web API
- [done] 1.2. Konfiguracja Entity Framework Core i połączenia z SQL Server
- [done] 1.3. Dodanie wymaganych pakietów NuGet (EF Core, MediatR, Newtonsoft.Json)

### Frontend:
- [done] 1.4. Utworzenie projektu Angular z Angular CLI
- [done] 1.5. Instalacja Angular Material i innych zależności
- [done] 1.6. Konfiguracja proxy dla połączenia z API

## 2. Implementacja modeli i bazy danych (2h)

### Backend:
- [done] 2.1. Utworzenie modeli danych (Message, Rating)
- [done] 2.2. Konfiguracja DbContext
- [done] 2.3. Utworzenie i uruchomienie migracji
- [done] 2.4. Implementacja interfejsów repozytoriów

### Frontend:
- [done] 2.5. Utworzenie odpowiednich modeli danych (Message, Rating)
- [done] 2.6. Konfiguracja modułów i komponentów

## 3. Implementacja podstawowej funkcjonalności API (3h)
- [done] 3.1. Implementacja repozytoriów dla encji
- [done] 3.2. Utworzenie serwisu chatbota z podstawowymi metodami
- [done] 3.3. Implementacja kontrolera API z endpointami:
  - [done] 3.3.1. Pobieranie historii czatu
  - [done] 3.3.2. Wysyłanie wiadomości
  - [done] 3.3.3. Ocenianie odpowiedzi
- [done] 3.4. Testowanie endpointów w Postmanie/Swaggerze

## 4. Implementacja streamowania odpowiedzi (2.5h)
- [done] 4.1. Utworzenie mechanizmu streamowania odpowiedzi (SSE)
- [done] 4.2. Implementacja symulacji "pisania" odpowiedzi
- [done] 4.3. Dodanie endpointów do anulowania generowania odpowiedzi
- [done] 4.4. Implementacja zapisywania częściowych odpowiedzi

## 5. Implementacja podstawowego interfejsu użytkownika (3h)
- [done] 5.1. Utworzenie komponentu historii czatu
- [done] 5.2. Implementacja formularza wysyłania wiadomości
- [done] 5.3. Wyświetlanie wiadomości z rozróżnieniem użytkownika/bota
- [done] 5.4. Podstawowa stylizacja interfejsu

## 6. Implementacja wyświetlania streamowanych odpowiedzi (2h)
- [done] 6.1. Utworzenie serwisu do obsługi Server-Sent Events
- [done] 6.2. Implementacja wyświetlania odpowiedzi znak po znaku
- [done] 6.3. Dodanie wizualnych wskaźników generowania odpowiedzi
- [done] 6.4. Implementacja przycisku anulowania odpowiedzi

## 7. Implementacja oceniania odpowiedzi (1h)
- [done] 7.1. Dodanie przycisków oceny (👍/👎) do odpowiedzi bota
- [done] 7.2. Implementacja mechanizmu zmiany oceny
- [done] 7.3. Wizualne oznaczanie ocenionych odpowiedzi

## 8. Integracja i testy (2.5h)
- [done] 8.1. Integracja wszystkich komponentów
- [] 8.2. Testowanie pełnego flow aplikacji
- [] 8.3. Identyfikacja i naprawa błędów
               - znika ocena po przejsciu miedzy watkami
- [] 8.4. Optymalizacja wydajności

## 9. Finalizacja (1h)
- [ ] 9.1. Końcowe poprawki UI
- [InProgress] 9.2. Czyszczenie kodu
- [done] 9.3. Dodanie podstawowej dokumentacji
- [ ] 9.4. Przygotowanie środowiska demonstracyjnego

---

## Priorytetyzacja zadań:

1. **Najpierw zbuduj podstawową strukturę** - modele, baza danych, podstawowe API
   - Zadania: 1.1-1.3, 2.1-2.4, 3.1-3.4
2. **Następnie zaimplementuj główne funkcjonalności** - historia czatu, wysyłanie wiadomości
   - Zadania: 1.4-1.6, 2.5-2.6, 5.1-5.4
3. **Później dodaj zaawansowane funkcje** - streamowanie odpowiedzi, ocenianie
   - Zadania: 4.1-4.4, 6.1-6.4, 7.1-7.3
4. **Na końcu dopracuj UI i UX** - stylizacja, wskaźniki ładowania, poprawki
   - Zadania: 8.1-8.4, 9.1-9.4

## Kamienie milowe:

1. **Działająca baza danych i API** (koniec kroku 3)
2. **Podstawowy interfejs czatu** (koniec kroku 5)
3. **Streamowanie odpowiedzi i anulowanie** (koniec kroku 6)
4. **Pełna funkcjonalność z ocenianiem** (koniec kroku 7)
5. **Gotowy prototyp** (koniec kroku 9)

**Całkowity szacowany czas: 17h**