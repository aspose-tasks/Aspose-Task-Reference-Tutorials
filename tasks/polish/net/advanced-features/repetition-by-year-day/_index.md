---
date: 2026-04-03
description: Naucz się planowania zadań w zarządzaniu projektami i jak dodać zadanie
  cykliczne przy użyciu Aspose.Tasks dla .NET, w tym zapisywanie projektu jako MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Powtarzanie według dnia roku w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Planowanie zadań w zarządzaniu projektami z rocznym powtarzaniem w Aspose.Tasks
url: /pl/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Planowanie zadań zarządzania projektem z powtarzaniem rocznym w Aspose.Tasks

## Wprowadzenie

Skuteczne **project management task scheduling** jest podstawą każdego udanego projektu. Gdy zadania powtarzają się co roku — takie jak coroczne audyty, okna konserwacyjne lub przeglądy sezonowe — ręczne zarządzanie tymi powtórzeniami może być podatne na błędy i czasochłonne. Aspose.Tasks dla .NET upraszcza to, umożliwiając programowe definiowanie wzorców rocznych, dzięki czemu możesz skupić się na tym, co najważniejsze: dostarczaniu wartości. W tym samouczku nauczysz się **jak dodać zadanie powtarzające się** logiki opartej na konkretnym dniu roku oraz zobaczysz dokładnie **jak zapisać projekt jako MPP** dla płynnej integracji z Microsoft Project.

## Szybkie odpowiedzi
- **Co oznacza „year day repetition”?** Harmonogramuje zadanie w konkretnym dniu określonego miesiąca każdego roku.  
- **Która klasa API tworzy powtarzanie?** `YearlyRecurrencePattern` połączona z `ByYearDayRepetition`.  
- **Czy mogę ustawić datę początkową i końcową?** Tak, przy użyciu `EndByRecurrenceRange`.  
- **Jaki format pliku jest tworzony?** Projekt jest zapisywany jako plik MPP (`SaveFileFormat.Mpp`).  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna do użytku nie‑ewaluacyjnego.

## Wymagania wstępne

Zanim zagłębisz się w samouczek, upewnij się, że masz następujące wymagania wstępne:

1. Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z [strony internetowej](https://releases.aspose.com/tasks/net/).  
2. Środowisko programistyczne: Skonfiguruj odpowiednie środowisko programistyczne z Visual Studio lub innym preferowanym IDE do programowania w .NET.  
3. Podstawowa znajomość C#: Zapoznaj się z podstawami języka programowania C#, aby móc śledzić przykłady kodu.  
4. Koncepcje zarządzania projektami: Zrozumienie koncepcji zarządzania projektami i planowania zadań pomoże w efektywnym przyswojeniu treści samouczka.

## Importowanie przestrzeni nazw

Zanim rozpoczniemy kodowanie, zaimportujmy niezbędne przestrzenie nazw, aby ułatwić manipulację zadaniami przy użyciu Aspose.Tasks dla .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Teraz rozbijmy podany przykład na kilka kroków i szczegółowo wyjaśnijmy każdy z nich.

## Jak dodać zadanie powtarzające się z wzorcem rocznym

### Krok 1: Załaduj plik projektu

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Tutaj inicjalizujemy nowy obiekt `Project` i ładujemy istniejący plik projektu o nazwie **Project1.mpp**.

### Krok 2: Zdefiniuj parametry zadania powtarzającego się

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

W tym kroku definiujemy parametry naszego zadania powtarzającego się. Określamy nazwę zadania, czas trwania i wzorzec powtarzania. Dla rocznego powtarzania używamy `YearlyRecurrencePattern` i ustawiamy powtórzenie na **1. dzień lipca** przy użyciu `ByYearDayRepetition`. Dodatkowo definiujemy zakres powtarzania od 1 lipca 2018 do 1 lipca 2019.

### Krok 3: Dodaj zadanie do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Tutaj dodajemy zdefiniowane parametry zadania powtarzającego się do zadania głównego projektu.

### Krok 4: Zapisz projekt jako MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Na koniec **zapisujemy projekt jako plik MPP**, co przygotowuje go do otwarcia w Microsoft Project lub dowolnym kompatybilnym przeglądarce.

## Dlaczego to ma znaczenie

- **Automatyzacja** – Eliminacja ręcznego wprowadzania rocznych zadań, zmniejszająca liczbę błędów ludzkich.  
- **Spójność** – Gwarantuje, że ten sam wzorzec dzień‑miesiąc jest stosowany w kolejnych latach.  
- **Integracja** – Powstały plik MPP może być udostępniany interesariuszom, którzy korzystają z Microsoft Project.  

## Częste pułapki i wskazówki

- **Precyzja DateTime** – Upewnij się, że czas rozpoczęcia jest zgodny z kalendarzem projektu; w przeciwnym razie zadanie może być przesunięte.  
- **Strefy czasowe** – API działa na obiektach `DateTime`; rozważ konwersję na UTC, jeśli Twoja aplikacja obejmuje wiele regionów.  
- **Egzekwowanie licencji** – W trybie ewaluacyjnym zapisany plik MPP może zawierać znak wodny; użyj ważnej licencji w produkcji.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks obsługuje złożone wzorce powtarzania?**  
A: Tak, Aspose.Tasks zapewnia kompleksowe wsparcie dla różnych wzorców powtarzania, w tym rocznych, miesięcznych, tygodniowych i dziennych.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi formatami plików projektów?**  
A: Zdecydowanie, Aspose.Tasks obsługuje popularne formaty plików projektów, takie jak MPP, XML i CSV, zapewniając kompatybilność z różnymi narzędziami do zarządzania projektami.

**Q: Czy Aspose.Tasks oferuje dokumentację i wsparcie dla programistów?**  
A: Tak, programiści mają dostęp do obszernej dokumentacji oraz mogą uzyskać pomoc na forach społeczności Aspose.Tasks w przypadku pytań lub problemów.

**Q: Czy mogę dostosować właściwości zadania, takie jak czas trwania i data rozpoczęcia, przy użyciu Aspose.Tasks?**  
A: Oczywiście, Aspose.Tasks udostępnia solidne API do dynamicznej manipulacji właściwościami zadań, umożliwiając programistom dostosowanie czasu trwania, dat rozpoczęcia, zależności i innych.

**Q: Czy Aspose.Tasks jest odpowiedni zarówno dla małych, jak i dużych projektów korporacyjnych?**  
A: Z pewnością, Aspose.Tasks został zaprojektowany tak, aby sprostać potrzebom programistów pracujących nad projektami o różnej skali, od pojedynczych zadań po duże projekty korporacyjne.

---

**Ostatnia aktualizacja:** 2026-04-03  
**Testowano z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}