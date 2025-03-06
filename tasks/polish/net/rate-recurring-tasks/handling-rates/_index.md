---
title: Obsługa stawek za projekty MS za pomocą Aspose.Tasks dla .NET
linktitle: Obsługa stawek w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Opanuj z łatwością zarządzanie stawkami projektów MS za pomocą Aspose.Tasks dla .NET. Efektywnie automatyzuj zadania, aby zapewnić płynniejszy przebieg prac nad projektami.
weight: 10
url: /pl/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa stawek za projekty MS za pomocą Aspose.Tasks dla .NET

## Wstęp
Witamy w naszym samouczku dotyczącym obsługi stawek MS Project przy użyciu Aspose.Tasks dla .NET! W tym przewodniku przeprowadzimy Cię krok po kroku przez proces, zapewniając efektywne zarządzanie stawkami w dokumentach MS Project. Aspose.Tasks dla .NET zapewnia zaawansowane funkcje do programowego manipulowania plikami MS Project, umożliwiając bezproblemowe usprawnienie zadań związanych z zarządzaniem projektami.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. Zainstalowany program Visual Studio: Upewnij się, że w systemie zainstalowano program Visual Studio.
2.  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.
## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Te przestrzenie nazw zapewnią dostęp do klas i metod wymaganych do obsługi stawek MS Project.
## Krok 1: Zaimportuj przestrzeń nazw Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Podzielmy teraz podany przykład na wiele kroków i dokładnie zrozummy każdy krok.
## Krok 1: Załaduj plik projektu
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 W tym kroku ładujemy istniejący plik MS Project o nazwie „Project1.mpp” przy użyciu rozszerzenia`Project` klasa dostarczona przez Aspose.Tasks.
## Krok 2: Dodaj zasób i ustaw pracę
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Tutaj dodajemy do projektu nowy zasób o nazwie „Zasób 1” i ustawiamy jego typ na „Praca”. Określamy także czas pracy tego zasobu.
## Krok 3: Ustaw stawkę standardową
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Na tym etapie ustalamy standardową stawkę za zasób na 20 USD za godzinę.
## Krok 4: Zdefiniuj okresy cenowe
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Tutaj definiujemy okresy taryfowe dla zasobu. Stawka 1 ustalana jest od 1 stycznia 2019 r. do 11 listopada 2019 r. z określonymi stawkami standardowymi i za nadgodziny.
## Krok 5: Dodaj kolejny okres taryfowy
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Na tym ostatnim etapie dodajemy kolejny okres cenowy rozpoczynający się 12 listopada 2019 r. do 31 grudnia 2019 r., z inną zdefiniowaną stawką standardową i kosztem wykorzystania.
Gratulacje! Pomyślnie poradziłeś sobie ze stawkami MS Project przy użyciu Aspose.Tasks dla .NET.
## Wniosek
Programowe zarządzanie stawkami MS Project może znacznie usprawnić przepływ pracy w zarządzaniu projektami. Dzięki Aspose.Tasks dla .NET masz możliwość wydajnej automatyzacji zadań obsługi stawek, oszczędzając czas i zasoby.
## Często zadawane pytania
### P: Czy Aspose.Tasks obsługuje złożone struktury projektu?
Odp.: Tak, Aspose.Tasks zapewnia solidne funkcje umożliwiające łatwą obsługę złożonych struktur projektów.
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami plików MS Project?
Odp.: Aspose.Tasks obsługuje różne wersje plików MS Project, zapewniając kompatybilność na różnych platformach.
### P: Czy mogę modyfikować istniejące stawki w pliku MS Project przy użyciu Aspose.Tasks?
Odp.: Absolutnie! Aspose.Tasks pozwala modyfikować istniejące stawki, dodawać nowe i dynamicznie nimi zarządzać.
### P: Czy Aspose.Tasks oferuje wsparcie dla niestandardowych obliczeń stawek?
Odp.: Tak, możesz wdrożyć niestandardowe obliczenia stawek za pomocą Aspose.Tasks, aby spełnić określone wymagania projektu.
### P: Czy dostępne jest forum społecznościowe lub wsparcie dla użytkowników Aspose.Tasks?
 Odpowiedź: Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)do szukania pomocy i interakcji z innymi użytkownikami.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
