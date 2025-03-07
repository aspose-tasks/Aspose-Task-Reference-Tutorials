---
title: Pobierz informacje o pliku projektu MS w Aspose.Tasks
linktitle: Pobieranie informacji o pliku projektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak odzyskać informacje o pliku Microsoft Project za pomocą Aspose.Tasks dla .NET. Przewodnik krok po kroku z przykładami kodu.
weight: 19
url: /pl/net/project-management-integration/project-file-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz informacje o pliku projektu MS w Aspose.Tasks

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym odzyskiwania informacji o plikach Microsoft Project przy użyciu Aspose.Tasks dla .NET. Aspose.Tasks to potężna biblioteka, która umożliwia programistom .NET programową pracę z plikami Microsoft Project, umożliwiając wykonywanie takich zadań, jak czytanie, pisanie i manipulowanie danymi projektu.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. Podstawowa znajomość języków C# i .NET: W tym samouczku założono, że masz podstawową wiedzę na temat języka programowania C# i platformy .NET.
2. Visual Studio: Zainstaluj Visual Studio lub dowolne inne IDE kompatybilne z programowaniem .NET.
3.  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/tasks/net/).
4. Plik Microsoft Project: Przygotuj plik Microsoft Project (w tym przykładzie w formacie XML) do celów testowych.

## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#, aby móc pracować z Aspose.Tasks:
## Krok 1: Zaimportuj przestrzeń nazw Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
## Pobieranie informacji o pliku MS Project
Podzielmy teraz dostarczony przykładowy kod na kilka kroków:
## Krok 2: Ustaw katalog dokumentów
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` ze ścieżką do katalogu zawierającego plik MS Project.
## Krok 3: Pobierz informacje o pliku projektu
```csharp
var info = Project.GetProjectFileInfo(dataDir + "Project.xml");
```
 Ten wiersz kodu pobiera informacje o określonym pliku projektu. Zastępować`"Project.xml"` z nazwą pliku MS Project.
## Krok 4: Wyświetl informacje o projekcie
```csharp
Console.WriteLine("CanRead: " + info.CanRead);
Console.WriteLine("ProjectApplicationInfo: " + info.ProjectApplicationInfo);
Console.WriteLine("ProjectFileFormat: " + info.ProjectFileFormat);
```
Te linie kodu wyświetlają różne informacje o pliku MS Project, takie jak jego czytelność, informacje o aplikacji i format pliku.

## Wniosek
tym samouczku dowiedzieliśmy się, jak odzyskać informacje o pliku Microsoft Project za pomocą Aspose.Tasks dla .NET. Wykonując te proste kroki, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami .NET, umożliwiając wydajną pracę z plikami MS Project.
## Często zadawane pytania
### Czy Aspose.Tasks może obsługiwać różne wersje plików Microsoft Project?
Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, w tym formaty MPP i XML.
### Czy Aspose.Tasks jest kompatybilny z .NET Core?
Tak, Aspose.Tasks jest kompatybilny zarówno z .NET Framework, jak i .NET Core.
### Czy mogę manipulować danymi projektu za pomocą Aspose.Tasks?
Absolutnie Aspose.Tasks zapewnia szerokie możliwości programowego odczytu, zapisu i manipulowania danymi projektu.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Tasks[Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks?
 Możesz uzyskać wsparcie dla Aspose.Tasks poprzez[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Kompletny kod źródłowy
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
