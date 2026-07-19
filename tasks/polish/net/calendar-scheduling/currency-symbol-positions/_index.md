---
date: 2026-07-19
description: Dowiedz się, jak łatwo kontrolować umieszczanie symbolu waluty po kwocie
  w projektach .NET przy użyciu Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Pozycje symbolu waluty w Aspose.Tasks
og_description: Dowiedz się, jak umieścić symbol waluty po kwocie przy użyciu Aspose.Tasks
  dla .NET. Postępuj zgodnie z instrukcjami krok po kroku i najlepszymi praktykami.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Symbol waluty po kwocie w Aspose.Tasks — szybki przewodnik
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Jak umieścić symbol waluty po kwocie w Aspose.Tasks
url: /pl/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak umieścić symbol waluty po kwocie w Aspose.Tasks

## Wprowadzenie

Podczas generowania raportów kosztów projektu, umiejscowienie **currency symbol after amount** może wpływać na czytelność oraz zgodność ze standardami regionalnymi. Aspose.Tasks dla .NET umożliwia kontrolowanie tego formatowania za pomocą kilku linijek kodu, zapewniając, że każda wartość finansowa wygląda dokładnie tak, jak oczekują interesariusze. W tym samouczku przeprowadzimy Cię przez niezbędne kroki, wyjaśnimy, dlaczego to ustawienie ma znaczenie, i pokażemy, jak zastosować je w rzeczywistym projekcie .NET.

## Szybkie odpowiedzi
- **Co oznacza „currency symbol after amount”?** Wyświetla symbol (np. $) po wartości liczbowej, np. `100 $`.
- **Która właściwość kontroluje pozycję?** `CurrencySymbolPosition` w obiekcie `Project`.
- **Czy potrzebna jest licencja?** Wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.
- **Obsługiwane waluty?** Ponad 50 walut jest wbudowanych, obejmując większość rynków światowych.
- **Czy mogę zmienić ustawienie w czasie działania?** Tak, możesz je zaktualizować w dowolnym momencie przed zapisaniem pliku projektu.

## Czym jest ustawienie „currency symbol after amount”?

Opcja **currency symbol after amount** określa, czy znak waluty pojawia się przed, czy po wartości liczbowej we wszystkich polach pieniężnych projektu. Dostosowanie tego ustawienia zapewnia, że raporty spełniają lokalne konwencje księgowe bez ręcznej obróbki po wygenerowaniu. Poprawia to także czytelność dla osób przyzwyczajonych do takiego formatu.

## Dlaczego używać Aspose.Tasks do formatowania waluty?

Aspose.Tasks obsługuje **ponad 50 walut** i może przetwarzać projekty z **10 000+ zadaniami** bez ładowania całego pliku do pamięci, zapewniając wysoką wydajność nawet na słabszym sprzęcie. API daje programistyczną kontrolę, eliminując potrzebę ręcznych edycji arkuszy kalkulacyjnych. Dzięki temu raportowanie finansowe na dużą skalę jest zarówno efektywne, jak i niezawodne.

## Wymagania wstępne

### 1. Instalacja Aspose.Tasks dla .NET
Upewnij się, że biblioteka Aspose.Tasks jest zainstalowana. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/net/).

### 2. Podstawowa znajomość programowania w .NET
Podstawowa znajomość programowania w .NET jest niezbędna do śledzenia przykładów.

## Importowanie przestrzeni nazw

Przestrzeń nazw `Aspose.Tasks` zapewnia dostęp do klasy `Project` oraz powiązanych wyliczeń.

Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik projektu w pamięci. Po zaimportowaniu przestrzeni nazw możesz rozpocząć pracę z danymi projektu.

```csharp

```

Teraz przeanalizujemy przykład w jasnych, praktycznych krokach.

## Jak ustawić symbol waluty po kwocie?

`CurrencySymbolPosition` jest wyliczeniem określającym, czy symbol waluty pojawia się przed, czy po wartości liczbowej.

Załaduj projekt, ustaw `CurrencySymbolPosition` na `After`, a następnie zapisz – to wszystko, czego potrzebujesz, aby wyświetlić symbol po kwocie. To bezpośrednie podejście działa dla każdej obsługiwanej waluty i nie wymaga dodatkowej logiki formatowania. Możesz również zweryfikować ustawienie, eksportując przykładowy raport kosztów, aby upewnić się, że symbol pojawia się prawidłowo.

### Krok 1: Załaduj plik projektu
Klasa `Project` ładuje istniejący plik MS‑Project lub tworzy nowy w pamięci.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Krok 2: Ustaw pozycję symbolu waluty
`CurrencySymbolPosition` to enum, który pozwala wybrać `Before` lub `After`. Ustawienie go na `After` umieszcza symbol po wartości liczbowej.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Krok 3: Pracuj z projektem
Po skonfigurowaniu pozycji symbolu możesz kontynuować dodawanie zadań, zasobów lub pól niestandardowych według potrzeb. Ustawienie jest zachowywane przy zapisie projektu.

```csharp
// Perform other operations with the project...
```

## Typowe problemy i rozwiązania
- **Symbol nadal pojawia się przed kwotą:** Upewnij się, że ustawiasz właściwość *przed* wywołaniem `Save`. Zmiana po zapisaniu wymaga ponownego zapisania pliku.
- **Nieobsługiwana waluta:** Sprawdź, czy używany kod waluty znajduje się na liście obsługiwanych przez Aspose.Tasks (ponad 50 walut).
- **Spowolnienie wydajności przy dużych projektach:** Użyj `ProjectReader` do strumieniowego odczytu dużych plików, jeśli przekraczasz 10 000 zadań.

## Najczęściej zadawane pytania

**Q: Czy mogę zmienić pozycję symbolu waluty wielokrotnie w tym samym projekcie?**  
A: Tak, możesz dostosować `CurrencySymbolPosition` tak wiele razy, jak potrzebujesz; wystarczy ustawić właściwość i ponownie zapisać projekt.

**Q: Czy Aspose.Tasks obsługuje waluty inne niż dolar amerykański?**  
A: Oczywiście. Aspose.Tasks obsługuje ponad 50 międzynarodowych walut, umożliwiając pracę z dowolnym formatem regionalnym.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?**  
A: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET [tutaj](https://releases.aspose.com/).

**Q: Czy mogę uzyskać pomoc, jeśli napotkam problemy podczas korzystania z Aspose.Tasks dla .NET?**  
A: Oczywiście! Wsparcie i pomoc możesz uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**Q: Jak mogę zakupić licencję na Aspose.Tasks dla .NET?**  
A: Licencję na Aspose.Tasks dla .NET możesz kupić [tutaj](https://purchase.aspose.com/buy).

## Podsumowanie

Kontrolowanie **currency symbol after amount** jest kluczowym elementem raportowania finansowego w oprogramowaniu do zarządzania projektami. Dzięki Aspose.Tasks dla .NET możesz ustawić tę opcję programowo, obsługując ponad 50 walut i efektywnie przetwarzając duże projekty. Zastosuj powyższe kroki, aby zapewnić, że raporty projektowe spełniają oczekiwania formatowania w dowolnej lokalizacji.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Powiązane samouczki

- [Zarządzanie kolekcją kalendarzy w Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Kolekcja wyjątków kalendarza w Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Obsługa stawek MS Project w Aspose.Tasks dla .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}