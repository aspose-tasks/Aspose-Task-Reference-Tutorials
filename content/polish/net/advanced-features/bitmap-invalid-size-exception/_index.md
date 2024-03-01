---
title: Obsługa wyjątku nieprawidłowego rozmiaru mapy bitowej w Aspose.Tasks
linktitle: Obsługa wyjątku nieprawidłowego rozmiaru mapy bitowej w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak obsługiwać wyjątek BitmapInvalidSizeException w Aspose.Tasks dla .NET podczas zapisywania projektów jako obrazów. Obszerny samouczek ze wskazówkami krok po kroku.
type: docs
weight: 22
url: /pl/net/advanced-features/bitmap-invalid-size-exception/
---
## Wstęp

 W tym samouczku zajmiemy się obsługą plików`BitmapInvalidSizeException` podczas pracy z Aspose.Tasks dla .NET. Aspose.Tasks to potężna biblioteka, która umożliwia programistom programowe manipulowanie plikami Microsoft Project, umożliwiając wykonywanie takich zadań, jak zapisywanie projektów jako obrazów. Jednak czasami podczas próby zapisania projektu jako obrazu możemy napotkać błąd`Invalid Size Exception`związane z bitmapą. Ten samouczek ma na celu poprowadzić Cię przez proces skutecznego wychwytywania i obsługi tego wyjątku.

## Warunki wstępne

Przed kontynuowaniem tego samouczka upewnij się, że spełnione są następujące wymagania wstępne:
1. Podstawowa znajomość języka programowania C#.
2. Zainstalowano Aspose.Tasks dla .NET.
3. Znajomość pracy z plikami Microsoft Project.

## Importuj przestrzenie nazw

Przed rozpoczęciem pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Zainicjuj projekt i zdefiniuj widok

 Po pierwsze, zainicjuj a`Project` obiekt i zdefiniuj widok, taki jak`GanttChartView`.

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## Krok 2: Określ opcje zapisywania obrazu

Następnie określ opcje zapisu obrazu, w tym format i skalę czasową.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## Krok 3: Ustaw jednostkę skali czasu i liczbę

Dostosuj jednostkę skali czasu i policz zgodnie ze swoimi wymaganiami. W tym przykładzie ustawiliśmy skalę czasu na minuty.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## Krok 4: Zapisz projekt jako obraz

Spróbuj zapisać projekt jako obraz, korzystając z określonych opcji.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## Krok 5: Złap i obsłuż wyjątek

 Zaimplementuj obsługę wyjątków, aby przechwycić plik`BitmapInvalidSizeException` jeśli nastąpi to podczas procesu zapisywania obrazu.

```csharp
try
{
    // Spróbuj zapisać projekt jako obraz
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Obsługuj wyjątek
    Console.WriteLine(ex.Message);
}
```

## Wniosek

 Podsumowując, obsługa`BitmapInvalidSizeException` podczas zapisywania projektów jako obrazów w Aspose.Tasks dla .NET ma kluczowe znaczenie dla zapewnienia płynnego wykonywania aplikacji. Wykonując kroki opisane w tym samouczku, możesz skutecznie wychwycić i obsłużyć ten wyjątek, zwiększając w ten sposób niezawodność rozwiązań do zarządzania projektami.

## Często zadawane pytania

### P1: Co powoduje wyjątek BitmapInvalidSizeException w Aspose.Tasks?

A1: Ten wyjątek występuje podczas próby zapisania projektu jako obrazu z nieprawidłowymi parametrami rozmiaru mapy bitowej.

### P2: Czy mogę dostosować skalę czasu podczas zapisywania projektu jako obrazu?

Odpowiedź 2: Tak, możesz dostosować jednostkę skali czasu i liczbę zgodnie ze swoimi wymaganiami, jak pokazano w samouczku.

### P3: Gdzie mogę znaleźć więcej zasobów do pracy z Aspose.Tasks dla .NET?

O3: Możesz zapoznać się z dokumentacją i forami wsparcia dostarczonymi przez Aspose.Tasks, aby uzyskać kompleksowe wskazówki i pomoc.

### P4: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?

O4: Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, umożliwiając bezproblemową interoperacyjność.

### P5: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?

Odpowiedź 5: Możesz nabyć tymczasową licencję do celów próbnych, korzystając z łącza podanego w artykule.