---
title: Niestandardowa kolumna widoku przypisania w Aspose.Tasks
linktitle: Niestandardowa kolumna widoku przypisania w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak dodać niestandardowe kolumny widoku przypisań w Aspose.Tasks dla .NET, aby zwiększyć możliwości zarządzania projektami.
type: docs
weight: 16
url: /pl/net/advanced-features/assignment-view-column/
---
## Wstęp

tym samouczku omówimy, jak dodać niestandardowe kolumny do widoków przypisań za pomocą Aspose.Tasks dla .NET. Kolumny niestandardowe zapewniają elastyczność i pozwalają wyświetlać dodatkowe informacje istotne dla potrzeb zarządzania projektami.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Podstawowa znajomość języka programowania C#.
2.  Zainstalowana biblioteka Aspose.Tasks dla .NET. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
3. Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod wymaganych do tworzenia niestandardowych kolumn widoku przypisań:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Załaduj projekt

 Aby rozpocząć, załaduj plik projektu za pomocą`Project` klasa:

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Krok 2: Utwórz opcje zapisywania arkusza kalkulacyjnego

 Następnie utwórz instancję`Spreadsheet2003SaveOptions` co pozwala nam dostosować kolumny widoku przypisań:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Krok 3: Zdefiniuj kolumnę niestandardową

 Teraz zdefiniuj kolumnę niestandardową, tworząc instancję`AssignmentViewColumn`. Ta klasa wymaga nazwy kolumny, szerokości i funkcji delegowania, aby przekonwertować dane przypisania na tekst kolumny:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Krok 4: Dodaj niestandardową kolumnę do opcji

Dodaj kolumnę niestandardową do kolekcji kolumn widoku przypisania opcji zapisywania:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Krok 5: Iteruj po zadaniach

Wykonaj iterację po każdym przypisaniu zasobów w projekcie i wyświetl niestandardowy tekst kolumny:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Krok 6: Zapisz projekt z niestandardowymi kolumnami

Na koniec zapisz projekt z niestandardowymi kolumnami widoku przypisania:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Wniosek

W tym samouczku nauczyliśmy się dodawać niestandardowe kolumny widoku przypisań za pomocą Aspose.Tasks dla .NET. Kolumny niestandardowe zapewniają elastyczność wyświetlania dodatkowych informacji dostosowanych do wymagań projektu, zwiększając możliwości zarządzania projektami.

## Często zadawane pytania

### P1: Czy mogę dodać wiele kolumn niestandardowych do widoku przypisania?

 A1: Tak, możesz dodać wiele kolumn niestandardowych, tworząc dodatkowe instancje`AssignmentViewColumn` i dodanie ich do`Columns` kolekcja.

### P2: Czy dostępne są predefiniowane konwertery dla typowych pól przypisań?

O2: Tak, Aspose.Tasks udostępnia predefiniowane konwertery dla typowych pól przypisań, ułatwiając wyodrębnianie danych dla niestandardowych kolumn.

### P3: Czy mogę dostosować wygląd kolumn niestandardowych, na przykład formatując tekst lub stosując style?

O3: Tak, możesz dostosować wygląd niestandardowych kolumn, modyfikując właściwości, takie jak szerokość, czcionka i wyrównanie.

### P4: Czy można usunąć domyślne kolumny z widoku przypisania?

 O4: Tak, możesz usunąć domyślne kolumny, wykluczając je z`Columns` kolekcji lub ustawiając ich szerokość na zero.

### P5: Czy Aspose.Tasks obsługuje eksportowanie projektów do innych formatów oprócz arkuszy kalkulacyjnych z niestandardowymi kolumnami?

Odpowiedź 5: Tak, Aspose.Tasks obsługuje eksportowanie projektów do różnych formatów, takich jak PDF, HTML i XML, umożliwiając wszechstronne opcje raportowania projektów.