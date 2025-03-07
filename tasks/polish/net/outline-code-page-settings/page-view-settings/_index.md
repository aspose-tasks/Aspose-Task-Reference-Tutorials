---
title: Dostosuj ustawienia widoku strony MS Project w Aspose.Tasks
linktitle: Konfigurowanie ustawień widoku strony w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skonfigurować ustawienia widoku strony w Aspose.Tasks dla .NET, aby dostosować format drukowania dokumentów Microsoft Project.
weight: 21
url: /pl/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dostosuj ustawienia widoku strony MS Project w Aspose.Tasks

## Wstęp
Microsoft Project to potężne narzędzie do zarządzania projektami, ale czasami trzeba dostosować sposób przeglądania i drukowania projektu. Dzięki Aspose.Tasks dla .NET możesz łatwo skonfigurować ustawienia widoku strony, aby spełnić Twoje specyficzne wymagania. W tym samouczku przeprowadzimy Cię krok po kroku przez ten proces.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Aspose.Tasks dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Plik Microsoft Project: Przygotuj plik Microsoft Project, dla którego chcesz skonfigurować ustawienia widoku strony.

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby móc pracować z Aspose.Tasks w projekcie .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Krok 1: Załaduj plik projektu
 Zacznij od załadowania pliku Microsoft Project do instancji`Project` klasa.
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Krok 2: Ustaw liczbę pierwszych kolumn
Określ liczbę pierwszych kolumn, które mają zostać wydrukowane na wszystkich stronach.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Krok 3: Wydrukuj notatki
Wybierz, czy chcesz drukować notatki wraz z projektem.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Krok 4: Dopasuj skalę czasu do końca strony
Zdecyduj, czy podczas drukowania skala czasu ma być dopasowana do końca strony.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Krok 5: Wydrukuj wszystkie kolumny arkusza
Określ, czy drukować wszystkie kolumny arkusza widoku.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Krok 6: Wydrukuj puste strony
Wybierz, czy drukować puste strony widoku.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Krok 7: Wydrukuj pierwsze kolumny na wszystkich stronach
Ustaw, czy drukować określoną liczbę pierwszych kolumn na wszystkich stronach.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Krok 8: Zapisz projekt ze skonfigurowanymi ustawieniami
Na koniec zapisz projekt ze skonfigurowanymi ustawieniami widoku strony, określając format wyjściowy, np. PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Wniosek
Konfigurowanie ustawień widoku strony Microsoft Project w Aspose.Tasks dla .NET jest proste i pozwala dostosować format wydruku do Twoich dokładnych potrzeb. Wykonując kroki opisane w tym samouczku, możesz mieć pewność, że dokumenty projektu są prezentowane dokładnie zgodnie z wymaganiami.
## Często zadawane pytania
### P: Czy mogę skonfigurować ustawienia widoku strony dla innych formatów plików oprócz PDF?
O: Tak, Aspose.Tasks obsługuje różne formaty plików do zapisywania projektów, w tym XLSX, MPP i HTML.
### P: Czy istnieją jakieś ograniczenia dotyczące liczby kolumn, które mogę wydrukować?
Odp.: Aspose.Tasks umożliwia dostosowanie liczby drukowanych kolumn w zależności od wymagań.
### P: Czy mogę zastosować różne ustawienia widoku strony dla różnych projektów?
O: Tak, możesz dostosować ustawienia widoku strony niezależnie dla każdego pliku projektu, z którym pracujesz.
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Odp.: Aspose.Tasks zapewnia kompatybilność z Microsoft Project 2003 i nowszymi wersjami.
### P: Gdzie mogę znaleźć dalszą pomoc lub wsparcie dla Aspose.Tasks?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w przypadku jakichkolwiek pytań lub problemów napotkanych podczas użytkowania.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
