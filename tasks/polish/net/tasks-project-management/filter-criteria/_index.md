---
title: Opanowanie kryteriów filtrowania projektów MS za pomocą Aspose.Tasks
linktitle: Kryteria filtrowania w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zaimplementować kryteria filtrów w MS Project przy użyciu Aspose.Tasks dla .NET. Zwiększ efektywność zarządzania projektami dzięki ukierunkowanej analizie danych.
type: docs
weight: 18
url: /pl/net/tasks-project-management/filter-criteria/
---
## Wstęp
W dziedzinie zarządzania projektami Microsoft Project jest niezawodnym narzędziem oferującym mnóstwo funkcji ułatwiających planistom i menedżerom projektów. Wśród wielu funkcjonalności znajduje się możliwość filtrowania danych projektowych, dzięki czemu użytkownicy mogą skupić się na konkretnych aspektach zadań projektowych. Jednakże opanowanie tych możliwości filtrowania może być trudnym zadaniem bez odpowiednich wskazówek. Ten samouczek ma na celu objaśnienie tego procesu poprzez przedstawienie przewodnika krok po kroku dotyczącego wdrażania kryteriów filtrowania w MS Project przy użyciu Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest konieczna, aby zrozumieć koncepcje omówione w tym samouczku.
2.  Instalacja Aspose.Tasks dla .NET: Upewnij się, że masz zainstalowany Aspose.Tasks dla .NET w swoim środowisku programistycznym. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
3. Plik Microsoft Project: Przygotuj plik Microsoft Project (np. Project2003.mpp), którego użyjesz do wdrożenia kryteriów filtrowania.

## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw do pracy z Aspose.Tasks dla .NET. Wykonaj następujące kroki:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Krok 1: Załaduj plik projektu
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Objaśnienie: Ten wiersz kodu inicjuje nową instancję klasy`Project` class i ładuje plik Microsoft Project określony w jego ścieżce.
## Krok 2: Pobierz filtr zadań
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Objaśnienie: Tutaj pobieramy filtr zadań z projektu. Dostosuj indeks (`[1]`) zgodnie z wymaganiami dotyczącymi wyboru żądanego filtra.
## Krok 3: Wyświetl wiersze kryteriów
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Objaśnienie: Ta sekcja przegląda każdy wiersz kryteriów filtru i wyświetla jego pole, operację, test i wartości (jeśli istnieją).
## Krok 4: Wydrukuj kryteria filtra
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Objaśnienie: Drukuje działanie kryteriów filtru.
## Krok 5: Wyświetl szczegóły kryteriów
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Objaśnienie: Ta część pobiera i wyświetla szczegółowe informacje o każdym wierszu kryteriów, zapewniając wgląd w konfigurację filtra.

## Wniosek
Opanowanie kryteriów filtrów w MS Project przy użyciu Aspose.Tasks for .NET to cenna umiejętność, która może znacząco zwiększyć efektywność zarządzania projektami. Wykonując ten samouczek, nauczyłeś się programowo manipulować kryteriami filtrów, co pozwala dostosować widoki projektu do konkretnych potrzeb.
## Często zadawane pytania
### P: Czy mogę zastosować wiele filtrów jednocześnie w MS Project?
Odp.: Tak, możesz połączyć wiele filtrów, aby jeszcze bardziej udoskonalić dane projektu.
### P: Czy Aspose.Tasks obsługuje starsze wersje plików Microsoft Project?
Odp.: Tak, Aspose.Tasks zapewnia kompatybilność wsteczną, umożliwiając pracę z różnymi wersjami plików Microsoft Project.
### P: Czy Aspose.Tasks jest kompatybilny z innymi frameworkami .NET?
Odp.: Aspose.Tasks obsługuje .NET Framework, .NET Core i .NET Standard, zapewniając elastyczność w różnych środowiskach programistycznych.
### P: Czy mogę dostosować kryteria filtrowania w oparciu o warunki dynamiczne?
Odp.: Oczywiście można programowo dostosować kryteria filtrowania w oparciu o parametry dynamiczne, umożliwiając adaptacyjną analizę danych projektu.
### P: Gdzie mogę szukać pomocy, jeśli napotkam problemy z Aspose.Tasks?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) aby uzyskać wsparcie od społeczności lub bezpośrednio skontaktować się z obsługą Aspose.Tasks w celu uzyskania spersonalizowanej pomocy.