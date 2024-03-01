---
title: Zapisywanie plików MS Project w różnych formatach w Aspose.Tasks
linktitle: Zapisywanie plików w różnych formatach w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zapisywać pliki MS Project w różnych formatach przy użyciu Aspose.Tasks dla .NET. Proste kroki do skutecznego zarządzania projektami.
type: docs
weight: 17
url: /pl/net/rate-recurring-tasks/save-file-formats/
---
## Wstęp
W tym samouczku omówimy, jak zapisywać pliki Microsoft Project w różnych formatach przy użyciu Aspose.Tasks dla .NET. Aspose.Tasks to potężny interfejs API, który pozwala programistom programowo manipulować plikami projektu i zarządzać nimi.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET, takie jak Visual Studio.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importuj przestrzenie nazw
Pamiętaj, aby zaimportować niezbędne przestrzenie nazw na początku pliku C#:
```csharp

using Aspose.Tasks.Saving;
```
## Krok 1: Utwórz obiekt projektu
Najpierw utwórz obiekt Project i załaduj plik Microsoft Project.
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Krok 2: Zapisz projekt w formacie CSV
Teraz zapiszmy projekt w formacie CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Krok 3: Poznaj inne formaty
 Aspose.Tasks obsługuje różne formaty zapisywania plików projektów, takie jak XML, PDF, XLSX i inne. Możesz eksplorować te formaty, po prostu zmieniając plik`SaveFileFormat` parametr w`Save` metoda.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Wykonując poniższe kroki, możesz łatwo zapisać pliki Microsoft Project w różnych formatach przy użyciu Aspose.Tasks dla .NET.

## Wniosek
W tym samouczku nauczyliśmy się, jak zapisywać pliki MS Project w różnych formatach przy użyciu Aspose.Tasks dla .NET. Aspose.Tasks upraszcza proces programowego manipulowania plikami projektu, oferując programistom elastyczność i wydajność.
## Często zadawane pytania
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Odp.: Aspose.Tasks obsługuje formaty Microsoft Project 2003 XML, Microsoft Project 2007 MPP i Microsoft Project 2010 MPP.
### P: Czy mogę wypróbować Aspose.Tasks przed zakupem?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks?
Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy dostępne są licencje tymczasowe dla Aspose.Tasks?
 Odpowiedź: Tak, licencje tymczasowe są dostępne do celów próbnych. Możesz taki otrzymać[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Jaka jest cena Aspose.Tasks?
 Odp.: Informacje o cenach można znaleźć na stronie zakupu Aspose.Tasks[Tutaj](https://purchase.aspose.com/buy).