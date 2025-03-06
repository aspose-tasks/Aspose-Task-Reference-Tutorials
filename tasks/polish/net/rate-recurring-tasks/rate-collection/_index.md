---
title: Opanuj stawki za projekty MS za pomocą Aspose.Tasks
linktitle: Zbiór stawek w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać stawkami w plikach MS Project przy użyciu Aspose.Tasks dla .NET. Samouczek krok po kroku dotyczący efektywnego zarządzania zasobami.
weight: 11
url: /pl/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanuj stawki za projekty MS za pomocą Aspose.Tasks

## Wstęp
Witamy w naszym samouczku dotyczącym zarządzania stawkami w MS Project przy użyciu Aspose.Tasks dla .NET! W tym przewodniku przeprowadzimy Cię przez proces pracy ze stawkami w plikach MS Project przy użyciu Aspose.Tasks. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz przygodę z programowaniem .NET, w tym samouczku znajdziesz instrukcje krok po kroku, jak skutecznie zarządzać stawkami w swoich projektach.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Zainstalowany program Visual Studio
Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie. Możesz go pobrać ze strony internetowej, jeśli jeszcze tego nie zrobiłeś.
### 2. Aspose.Tasks dla .NET
 Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[strona internetowa](https://releases.aspose.com/tasks/net/).
### 3. Podstawowa znajomość C# i .NET
Zapoznaj się z językiem programowania C# i podstawami platformy .NET, aby lepiej zrozumieć przykłady kodu podane w tym samouczku.
## Importuj przestrzenie nazw
swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Teraz podzielmy każdy przykład na wiele kroków:
## Krok 1: Załaduj plik projektu MS
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Tutaj tworzymy nowy`Project` obiekt poprzez załadowanie istniejącego pliku MS Project.
## Krok 2: Dodaj zasób i ustaw pracę oraz stawki
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Dodajemy do projektu nowy zasób, ustalamy jego typ jako pracę, ilość pracy i stawkę standardową.
## Krok 3: Dodaj stawki do zasobu
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Do zasobu dodajemy stawki określając daty rozpoczęcia i zakończenia, stawkę standardową i format stawki.
## Krok 4: Informacje o cenach wydruku
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
W tym kroku drukowane są informacje o stawkach powiązanych z zasobem.
## Krok 5: Zaktualizuj stawkę
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Aktualizujemy datę końcową określonej stawki.
## Krok 6: Usuń stawki
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Ten krok usuwa wszystkie stawki określonego typu.
## Krok 7: Iteruj po pozostałych stawkach
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Na koniec iterujemy po pozostałych stawkach po usunięciu.
## Wniosek
Podsumowując, ten samouczek dostarczył kompleksowego przewodnika na temat zarządzania stawkami w plikach MS Project przy użyciu Aspose.Tasks dla .NET. Postępując zgodnie ze szczegółowymi instrukcjami opisanymi w tym samouczku, możesz efektywnie zarządzać stawkami w swoich projektach, zapewniając dokładne zarządzanie zasobami.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks for .NET z innym oprogramowaniem do zarządzania projektami?
Odp.: Tak, Aspose.Tasks dla .NET obsługuje integrację z różnymi programami do zarządzania projektami, w tym MS Project, Primavera i innymi.
### P: Czy Aspose.Tasks dla .NET jest kompatybilny z różnymi wersjami plików MS Project?
O: Oczywiście, Aspose.Tasks dla .NET obsługuje pracę z plikami MS Project w różnych wersjach, zapewniając elastyczność i kompatybilność.
### P: Czy Aspose.Tasks dla .NET oferuje dokumentację i wsparcie?
 Odp.: Tak, obszerną dokumentację i dostęp do forów wsparcia można znaleźć w Aspose.Tasks[strona internetowa](https://reference.aspose.com/tasks/net/).
### P: Czy przed zakupem mogę wypróbować Aspose.Tasks dla .NET?
Odp.: Tak, możesz skorzystać z bezpłatnej wersji próbnej Aspose.Tasks dla .NET, aby ocenić jego funkcje i zgodność z własnymi wymaganiami.
### P: Jak mogę kupić licencję na Aspose.Tasks dla .NET?
 Odp.: Możesz kupić licencję na Aspose.Tasks dla .NET w witrynie[strona internetowa](https://purchase.aspose.com/temporary-license/)która zapewnia elastyczne opcje licencjonowania dostosowane do Twoich potrzeb.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
