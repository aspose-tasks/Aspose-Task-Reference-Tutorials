---
title: Skonfiguruj ustawienia strony MS Project za pomocą Aspose.Tasks
linktitle: Konfigurowanie ustawień strony w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skonfigurować ustawienia strony MS Project przy użyciu Aspose.Tasks dla .NET. Dostosuj orientację, rozmiar i inne parametry za pomocą prostych kroków.
type: docs
weight: 20
url: /pl/net/outline-code-page-settings/page-settings/
---
## Wstęp
W tym samouczku omówimy proces konfigurowania ustawień strony Microsoft Project przy użyciu Aspose.Tasks dla .NET. Aspose.Tasks to potężny interfejs API, który umożliwia programistom programowe manipulowanie plikami Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Aspose.Tasks dla .NET: Upewnij się, że zainstalowałeś Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Skonfiguruj środowisko programistyczne w programie Visual Studio lub innym preferowanym środowisku IDE do programowania w środowisku .NET.

## Importowanie przestrzeni nazw
Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Te przestrzenie nazw zapewniają dostęp do klas i metod Aspose.Tasks wymaganych do manipulowania plikami MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Krok 1: Załaduj plik projektu
Najpierw musisz załadować plik MS Project, dla którego chcesz skonfigurować ustawienia strony.
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Krok 2: Uzyskaj dostęp do ustawień strony
Następnie uzyskasz dostęp do ustawień strony pliku projektu.
```csharp
// Pobierz ustawienia
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Krok 3: Skonfiguruj ustawienia strony
Teraz skonfigurujmy różne właściwości ustawień strony zgodnie z Twoimi wymaganiami.
```csharp
// Ustaw orientację strony na pionową
settings.IsPortrait = true;
// Ustaw liczbę stron do wydrukowania na szerokość
settings.PagesInWidth = 5;
// Ustaw liczbę stron do wydrukowania na wysokość
settings.PagesInHeight = 7;
// Ustaw procent normalnego rozmiaru, do którego chcesz dostosować drukowanie
settings.PercentOfNormalSize = 200;
// Ustaw rozmiar papieru
settings.PaperSize = PrinterPaperSize.PaperB4;
// Ustaw numer pierwszej strony do wydrukowania
settings.FirstPageNumber = 3;
```
## Krok 4: Zapisz plik projektu
Na koniec zapisz plik projektu ze zaktualizowanymi ustawieniami strony.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Wniosek
W tym samouczku dowiedzieliśmy się, jak skonfigurować ustawienia strony Microsoft Project przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, można łatwo dostosować orientację strony, rozmiar i inne opcje drukowania zgodnie z własnymi wymaganiami.

## Często zadawane pytania
### P: Czy mogę skonfigurować ustawienia strony dla wielu plików MS Project jednocześnie?
O: Tak, możesz przeglądać wiele plików projektu i stosować do każdego z nich te same ustawienia strony.
### P: Czy można przywrócić domyślne ustawienia strony?
O: Oczywiście możesz po prostu pominąć kroki konfiguracji lub zresetować ustawienia do wartości domyślnych.
### P: Czy istnieją jakieś ograniczenia dotyczące obsługiwanych rozmiarów papieru?
Odp.: Aspose.Tasks obsługuje szeroką gamę rozmiarów papieru, w tym rozmiary standardowe i niestandardowe.
### P: Czy mogę zautomatyzować proces konfiguracji ustawień strony?
O: Oczywiście możesz zintegrować tę funkcjonalność z przepływem pracy swojej aplikacji, aby zautomatyzować konfigurację ustawień strony.
### P: Czy Aspose.Tasks oferuje obsługę innych formatów plików oprócz .mpp?
O: Tak, Aspose.Tasks obsługuje różne formaty plików, między innymi XML, MPT i HTML.