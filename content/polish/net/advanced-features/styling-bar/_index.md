---
title: Pasek stylizacji w Aspose.Tasks
linktitle: Pasek stylizacji w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak stylizować paski w Aspose.Tasks dla .NET, aby ulepszyć wizualizację projektu.
type: docs
weight: 19
url: /pl/net/advanced-features/styling-bar/
---
## Wstęp

Stylizowanie pasków w Aspose.Tasks jest istotnym aspektem tworzenia atrakcyjnych wizualnie planów projektów. Dzięki elastyczności oferowanej przez interfejs API Aspose.Tasks programiści mogą dostosowywać różne aspekty pasków, takie jak kolor, kształt i styl tekstu, w celu ulepszenia wizualizacji projektu. W tym samouczku omówimy, jak stylizować paski za pomocą Aspose.Tasks dla .NET, dzieląc każdy przykład na łatwe do wykonania kroki.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[strona pobierania](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: skonfiguruj środowisko programistyczne z obsługą platformy .NET.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Załaduj projekt

Aby rozpocząć, załaduj plik projektu za pomocą interfejsu API Aspose.Tasks:

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Krok 2: Skonfiguruj opcje zapisywania

Zdefiniuj opcje zapisu, określając style prętów, które mają zostać zastosowane:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Krok 3: Zdefiniuj styl paska

Utwórz nowy styl paska i dostosuj jego właściwości:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Ustaw typ elementu paska
style.BarColor = Color.Green; // Ustaw kolor paska
style.BarShape = BarShape.HalfHeight; // Ustaw kształt paska
style.StartShape = Shape.LeftBracket; // Ustaw kształt na początku paska
style.StartShapeColor = Color.Aqua; // Ustaw kolor kształtu początkowego
style.EndShape = Shape.RightBracket; // Ustaw kształt na końcu paska
style.EndShapeColor = Color.Aquamarine; // Ustaw kolor kształtu końcowego
style.TextStyle = new TextStyle(); // Ustaw styl tekstu
style.TextStyle.BackgroundColor = Color.Black; // Ustaw kolor tła dla tekstu
```

## Krok 4: Dostosuj konwerter tekstu

Opcjonalnie dostosuj konwerter tekstu, aby zmodyfikować renderowanie tekstu:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Krok 5: Dodaj styl paska do opcji

Dodaj skonfigurowany styl paska do opcji zapisu:

```csharp
options.BarStyles.Add(style);
```

## Krok 6: Zapisz projekt

Na koniec zapisz projekt z zastosowanymi stylami pasków:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Wniosek

Dostosowywanie stylów pasków w Aspose.Tasks dla .NET zapewnia programistom możliwość tworzenia atrakcyjnych wizualnie planów projektów. Wykonując kroki opisane w tym samouczku, możesz efektywnie stylizować paski, aby spełniały określone wymagania dotyczące wizualizacji projektu.

## Często zadawane pytania

### P1: Czy mogę zastosować wiele stylów pasków w jednym projekcie?

Odpowiedź 1: Tak, możesz zdefiniować i zastosować wiele stylów pasków do różnych typów zadań w tym samym projekcie.
   
### P2: Czy można dynamicznie zmieniać style pasków w czasie wykonywania?

Odpowiedź 2: Tak, możesz dynamicznie modyfikować style pasków w oparciu o określone warunki lub preferencje użytkownika w swojej aplikacji.
   
### P3: Czy Aspose.Tasks obsługuje eksportowanie projektów ze stylizowanymi paskami do różnych formatów plików?

O3: Tak, Aspose.Tasks obsługuje eksportowanie projektów ze stylizowanymi paskami do różnych formatów, takich jak PDF, XLSX i HTML.
   
### P4: Czy w Aspose.Tasks dostępne są predefiniowane style pasków?

Odpowiedź 4: Chociaż Aspose.Tasks zapewnia domyślne style pasków, programiści mogą również tworzyć niestandardowe style pasków dostosowane do wymagań ich projektu.
   
### P5: Czy mogę pobrać i zmodyfikować istniejące style prętów w projekcie za pomocą interfejsu API?

O5: Tak, możesz programowo pobierać i modyfikować istniejące style pasków za pomocą Aspose.Tasks for .NET API.