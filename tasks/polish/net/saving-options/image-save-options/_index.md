---
title: Obraz Zapisz opcje MS Project dla Aspose.Tasks
linktitle: Opcje zapisywania obrazu dla Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zapisywać opcje MS Project jako obrazy przy użyciu Aspose.Tasks dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
type: docs
weight: 11
url: /pl/net/saving-options/image-save-options/
---

## Wstęp
W świecie tworzenia oprogramowania wydajna realizacja zadań projektowych ma kluczowe znaczenie dla skutecznego zarządzania projektami. Aspose.Tasks dla .NET oferuje potężne rozwiązanie dla programistów pracujących z plikami Microsoft Project, umożliwiając im płynne manipulowanie, konwertowanie i zarządzanie zadaniami projektowymi w aplikacjach .NET.
## Warunki wstępne
Zanim zaczniesz używać Aspose.Tasks dla .NET do zapisywania opcji MS Project jako obrazów, upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Zainstaluj Aspose.Tasks dla .NET
Aby rozpocząć, musisz mieć zainstalowany Aspose.Tasks dla .NET w swoim środowisku programistycznym. Bibliotekę można pobrać ze strony[strona internetowa](https://releases.aspose.com/tasks/net/) i postępuj zgodnie z dostarczonymi instrukcjami instalacji.
### 2. Uzyskaj licencję (opcjonalnie)
 Chociaż Aspose.Tasks dla .NET może być używany bez licencji w trybie ewaluacyjnym, zaleca się uzyskanie licencji w celu uzyskania pełnej funkcjonalności i usunięcia ograniczeń ewaluacyjnych. Licencję można nabyć w witrynie[strona zakupu](https://purchase.aspose.com/buy) lub zdecyduj się na[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) do celów testowych.
### 3. Podstawowa znajomość programowania w C# i .NET
Aby postępować zgodnie z przykładami i skutecznie integrować funkcjonalności Aspose.Tasks z aplikacjami, niezbędna jest podstawowa znajomość języka programowania C# i frameworku .NET.
## Importuj przestrzenie nazw
Zanim zaczniemy zapisywać opcje MS Project jako obrazy przy użyciu Aspose.Tasks dla .NET, upewnijmy się, że zaimportowaliśmy niezbędne przestrzenie nazw do naszego projektu C#:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Skonfiguruj ścieżkę katalogu dokumentów
Upewnij się, że masz wyznaczony katalog na swoje dokumenty i odpowiednio ustaw ścieżkę:
```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Załaduj plik MS Project
 Zainicjuj nowy`Project` obiekt poprzez załadowanie pliku MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Krok 3: Zdefiniuj opcje zapisywania obrazu
 Utwórz instancję`ImageSaveOptions` określ żądane ustawienia:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Krok 4: Określ strony do zapisania
W razie potrzeby określ strony, które mają zostać zapisane. W tym przykładzie dodajemy stronę 2:
```csharp
options.Pages.Add(2);
```
## Krok 5: Zapisz obraz
Na koniec zapisz wybrane strony jako obraz z określonymi opcjami:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Wniosek
Aspose.Tasks dla .NET upraszcza proces pracy z plikami MS Project, umożliwiając programistom bezproblemowe manipulowanie zadaniami projektowymi. Wykonując kroki opisane w tym samouczku, możesz efektywnie zapisywać opcje MS Project jako obrazy w aplikacjach .NET.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Tasks dla .NET bez licencji?
O: Tak, możesz używać Aspose.Tasks dla .NET bez licencji w trybie ewaluacyjnym. Zaleca się jednak uzyskanie licencji na pełną funkcjonalność i usunięcie ograniczeń ewaluacyjnych.
### P2: Jak mogę uzyskać tymczasową licencję na testowanie?
 Odpowiedź: Możesz uzyskać tymczasową licencję do celów testowych z[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).
### P3: Czy Aspose.Tasks for .NET jest kompatybilny z innymi frameworkami .NET?
Odp.: Tak, Aspose.Tasks dla .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET Standard.
### P4: Czy mogę bardziej dostosować opcje zapisywania obrazu?
O: Tak, możesz dostosować opcje zapisywania obrazu zgodnie ze swoimi specyficznymi wymaganiami, takimi jak rozmiar strony, rozdzielczość lub format wyjściowy.
### P5: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks dla .NET?
 Odp.: Możesz znaleźć wsparcie i pomoc dla Aspose.Tasks dla .NET na[forum](https://forum.aspose.com/c/tasks/15).