---
date: 2026-07-05
description: Dowiedz się, jak śledzić budżet projektu i zarządzać kosztami projektu
  przy użyciu Aspose.Tasks dla .NET. Zdefiniuj Cost Accrual Types dla dokładnego śledzenia
  kosztów.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Śledź budżet projektu przy użyciu Cost Accrual Types w Aspose.Tasks
url: /pl/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Śledź budżet projektu przy użyciu typów naliczania kosztów w Aspose.Tasks

## Wprowadzenie

Precyzyjne **śledzenie budżetu projektu** jest podstawą udanej realizacji projektu. Gdy informacje o kosztach są rejestrowane w odpowiednich momentach, można prognozować przekroczenia, dostosowywać zasoby i informować interesariuszy. Aspose.Tasks dla .NET daje programistom szczegółową kontrolę nad naliczaniem kosztów, pozwalając określić *kiedy* koszt jest zapisywany — czy to na początku pracy, ciągle, czy tylko po jej zakończeniu. Ten samouczek przeprowadzi Cię przez koncepcje, pokaże, jak ustawić typ naliczania, i przedstawi najlepsze praktyki zapewniające rzetelne śledzenie budżetu.

## Szybkie odpowiedzi
- **Jaki jest główny cel typów naliczania kosztów?** Określają one moment w cyklu życia zadania, w którym koszt jest uznawany, umożliwiając precyzyjne śledzenie budżetu.  
- **Która wartość wyliczenia opóźnia koszt do zakończenia pracy?** `CostAccrualType.End`.  
- **Czy potrzebuję licencji, aby uruchomić kod?** Tak, ważna licencja Aspose.Tasks jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić typy naliczania dla wielu zasobów jednocześnie?** Tak — przeiteruj kolekcję `Resources` i przypisz żądany typ.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest typ naliczania kosztów?
**Typ naliczania kosztów** informuje Aspose.Tasks, kiedy zastosować koszt zasobu do budżetu projektu. Jest reprezentowany przez wyliczenie `CostAccrualType` i może być ustawiany per‑zasób lub per‑zadanie. Wybranie właściwego typu zapewnia, że dane kosztowe są zgodne z polityką rozliczeniową Twojej organizacji, niezależnie od tego, czy potrzebujesz kosztów rejestrowanych na początku pracy, proporcjonalnie w czasie trwania, czy tylko po zakończeniu.

## Dlaczego śledzić budżet projektu przy użyciu typów naliczania kosztów?
Aspose.Tasks obsługuje **cztery** opcje naliczania — `Start`, `Prorated`, `Duration` i `End` — obejmujące pełen zakres typowych scenariuszy księgowości projektowej. Wybranie odpowiedniej opcji pozwala dopasować rozpoznawanie kosztów do cykli rozliczeniowych w umowach, zmniejszyć odchylenia w raportach finansowych oraz generować zestawienia kosztów, które płynnie integrują się z systemami ERP, przy jednoczesnym niskim zużyciu pamięci w dużych projektach.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:

### 1. Zainstaluj Aspose.Tasks dla .NET
Aby rozpocząć, musisz mieć zainstalowany Aspose.Tasks dla .NET w swoim środowisku programistycznym. Możesz pobrać bibliotekę ze [strony pobierania](https://releases.aspose.com/tasks/net/) i postępować zgodnie z dostarczonymi instrukcjami instalacji.

### 2. Znajomość .NET Framework
Podstawowa znajomość frameworka .NET oraz języka programowania C# jest wymagana, aby podążać za przykładami w tym samouczku.

## Jak ustawić typ naliczania kosztów dla zasobu?

Załaduj projekt, zlokalizuj docelowy zasób i przypisz żądany `CostAccrualType`. Poniższy dwuliniowy wzorzec jest standardowym podejściem: utwórz instancję `Project`, pobierz zasób po jego ID, a następnie ustaw `CostAccrualType`. Ta zwięzła sekwencja zapewnia, że **śledzisz budżet projektu** dokładnie od momentu dodania zasobu.

### Krok 1: Importuj przestrzenie nazw
Zacznijmy od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks w naszym projekcie .NET:

```csharp

```

Teraz, gdy mamy już zaimportowane przestrzenie nazw, możemy przejść do ładowania pliku projektu.

### Krok 2: Załaduj plik projektu
Klasa `Project` reprezentuje plik Microsoft Project i zapewnia dostęp do jego zadań, zasobów oraz innych danych.

```csharp
var project = new Project("Project2.mpp");
```

Najpierw musimy załadować plik projektu do naszej aplikacji. Tworzymy nowy obiekt `Project` i inicjalizujemy go ścieżką do naszego pliku projektu.

### Krok 3: Uzyskaj dostęp do zasobu
Kolekcja `Resources` zawiera wszystkie zasoby zdefiniowane w projekcie. Metoda `GetById` pobiera zasób po jego unikalnym identyfikatorze.

```csharp
var resource = project.Resources.GetById(1);
```

Następnie uzyskujemy dostęp do zasobu, któremu chcemy zastosować typ naliczania kosztów. Używamy metody `GetById` z kolekcji `Resources` i przekazujemy identyfikator zasobu jako argument. To demonstruje **dostęp do zasobu po ID**, typowe wymaganie przy automatyzacji aktualizacji kosztów.

### Krok 4: Ustaw typ naliczania kosztów
Metoda `Set` przypisuje wartość do pola zasobu.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Tutaj ustawiamy typ naliczania kosztów dla zasobu. W tym przykładzie ustawiamy go na `CostAccrualType.End`, co oznacza, że koszty nie będą naliczane, dopóki pozostała praca nie będzie równa zero. Wybór `End` jest idealny, gdy chcesz **śledzić budżet projektu** dopiero po pełnym zakończeniu zadania.

### Krok 5: Kontynuuj pracę z projektem
Po ustawieniu typu naliczania kosztów możesz kontynuować pracę z projektem według potrzeb, wykonując dodatkowe operacje lub obliczenia, takie jak generowanie raportów kosztowych, aktualizacja przydziałów czy eksportowanie pliku.

## Częste pułapki i wskazówki profesjonalne
- **Wskazówka:** Zawsze wywołuj `project.Save` po modyfikacji typów naliczania, aby zachować zmiany.  
- **Pułapka:** Ustawienie `CostAccrualType.Start` na zasobie, który nigdy nie rozpoczyna pracy, spowoduje zawyżenie raportów budżetowych — najpierw zweryfikuj harmonogramy zadań.  
- **Wskazówka:** Użyj `project.Resources.ToList()` gdy potrzebujesz masowo zaktualizować wiele zasobów; unika to wielokrotnych wyszukiwań w kolekcji i poprawia wydajność w dużych projektach.

## Najczęściej zadawane pytania

**P:** Czy mogę zmienić typ naliczania kosztów dla wielu zasobów jednocześnie?  
**O:** Tak, iteruj przez `project.Resources` i przypisz żądany `CostAccrualType` każdemu zasobowi w pętli `foreach`.

**P:** Jakie są inne dostępne typy naliczania kosztów oprócz `End`?  
**O:** Aspose.Tasks udostępnia `Start`, `Prorated` i `Duration` — każdy odpowiada innej strategii rozliczeniowej.

**P:** Jak mogę określić bieżący typ naliczania kosztów dla konkretnego zasobu?  
**O:** Pobierz wartość za pomocą `resource.Get(TskResource.CostAccrualType)`; zwraca ona wyliczenie reprezentujące bieżące ustawienie.

**P:** Czy można zastosować różne typy naliczania kosztów do różnych zadań w tym samym projekcie?  
**O:** Oczywiście. Zarówno zadania, jak i zasoby udostępniają właściwość `CostAccrualType`, co pozwala na niezależną konfigurację dla każdej jednostki.

**P:** Czy Aspose.Tasks obsługuje niestandardowe typy naliczania kosztów?  
**O:** Nie, biblioteka obecnie obsługuje tylko cztery wbudowane typy; niestandardową logikę należy zaimplementować zewnętrznie, jeśli jest wymagana.

**Ostatnia aktualizacja:** 2026-07-05  
**Testowano z:** Aspose.Tasks 24.8 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Kalendarz i harmonogramowanie w Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Obsługa stawek w MS Project przy użyciu Aspose.Tasks dla .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Łatwe zarządzanie zasobami w MS Project przy użyciu Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}