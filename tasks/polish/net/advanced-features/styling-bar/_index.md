---
date: 2026-04-06
description: Dowiedz się, jak zmienić styl pasków i dostosować ich kolory w Aspose.Tasks
  dla .NET, aby ulepszyć wizualizację projektu.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Pasek stylizacji w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak zmienić stylowanie pasków w Aspose.Tasks
url: /pl/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić styl pasków w Aspose.Tasks

## Wprowadzenie

Jeśli potrzebujesz **jak zmienić wygląd paska** w pliku Microsoft Project, Aspose.Tasks dla .NET daje pełną kontrolę nad kolorami pasków, ich kształtami oraz stylami tekstu. Dostosowując kolory pasków i inne atrybuty wizualne, możesz uczynić plany projektów znacznie czytelniejszymi i lepiej dopasowanymi do identyfikacji wizualnej Twojej organizacji. W tym samouczku przeprowadzimy Cię krok po kroku przez kompletny przykład, który pokaże, jak zmienić styl pasków – od wczytania projektu po wyeksportowanie go z nowymi regułami wizualnymi.

## Szybkie odpowiedzi
- **Co mogę stylizować?** Paski, kamienie milowe i tekst zadań w wykresach Gantta.  
- **Który format obsługuje stylizowane paski?** PDF, XLSX, HTML oraz natywny MPP przy zapisie z użyciem `PdfSaveOptions`.  
- **Czy potrzebna jest licencja?** Licencja komercyjna jest wymagana w środowisku produkcyjnym; darmowa wersja próbna wystarczy do testów.  
- **Czy mogę zastosować wiele stylów?** Tak – dodaj tyle obiektów `BarStyle`, ile potrzebujesz.  
- **Czy jest kompatybilny z .NET Core?** Absolutnie – działa z .NET Framework oraz .NET Core/5/6+.

## Co to jest stylizacja pasków w Aspose.Tasks?

Stylizacja pasków pozwala definiować reguły wizualne, które silnik Aspose.Tasks stosuje podczas renderowania wykresów Gantta. Każda reguła (obiekt **BarStyle**) dotyczy określonego typu elementu – zadań, kamieni milowych lub zadań podsumowujących – i umożliwia ustawienie kolorów, kształtów oraz własnego tekstu.

## Dlaczego warto dostosować kolory pasków?

Dostosowanie kolorów pasków pomaga interesariuszom natychmiast rozpoznać ścieżki krytyczne, opóźnione zadania lub kamienie milowe. Umożliwia także dopasowanie do firmowych schematów kolorystycznych, co sprawia, że raporty wyglądają profesjonalnie i zgodnie z marką.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

1. **Aspose.Tasks for .NET** – pobierz go ze [strony pobierania](https://releases.aspose.com/tasks/net/).  
2. Środowisko programistyczne obsługujące .NET (Framework 4.6+, .NET Core 3.1+ lub nowsze).  
3. Podstawową znajomość C# – przykłady używają prostego, samodzielnego kodu.

## Importowanie przestrzeni nazw

Najpierw zaimportuj przestrzenie nazw zawierające klasy, które będziemy używać:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Wczytaj projekt

Wczytaj istniejący plik MPP (lub utwórz nowy), aby uzyskać obiekt projektu do dalszej pracy:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Krok 2: Skonfiguruj opcje zapisu

Utwórz instancję `PdfSaveOptions` i zainicjuj kolekcję `BarStyles`, w której będziemy przechowywać własne style:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Krok 3: Zdefiniuj styl paska

Teraz tworzymy obiekt `BarStyle` i ustawiamy właściwości kontrolujące wygląd paska. To miejsce, w którym **dostosowujemy kolory pasków** i ich kształty:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Krok 4: Dostosuj konwerter tekstu (opcjonalnie)

Jeśli chcesz zmodyfikować tekst wyświetlany na pasku, możesz przypisać własny konwerter. Przykład dodaje prefiks do nazw zadań, które nie zaczynają się od „T”:

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

Dodaj w pełni skonfigurowany styl do kolekcji `BarStyles` w opcjach zapisu:

```csharp
options.BarStyles.Add(style);
```

## Krok 6: Zapisz projekt

Na koniec wyeksportuj projekt. PDF (lub inny format) wyrenderuje wykres Gantta przy użyciu zdefiniowanego stylu paska:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| **Styl paska nie został zastosowany** | Kolekcja `BarStyles` była pusta lub nie została podłączona do opcji zapisu. | Upewnij się, że dodałeś `BarStyle` do `options.BarStyles` przed wywołaniem `Save`. |
| **Kolory wyglądają inaczej w PDF** | Renderowanie PDF może używać innego profilu kolorów. | Użyj standardowych wartości `System.Drawing.Color` lub zdefiniuj własne kolory ARGB. |
| **Konwerter tekstu zgłasza błąd null reference** | Właściwość `Tsk.Name` jest null dla niektórych zadań. | Dodaj sprawdzenie null przed dostępem do `task.Get(Tsk.Name)`. |

## FAQ

### Q1: Czy mogę zastosować wiele stylów pasków w jednym projekcie?

A1: Tak, możesz definiować i stosować wiele stylów pasków dla różnych typów zadań w tym samym projekcie.

### Q2: Czy istnieje możliwość dynamicznej zmiany stylów pasków w czasie działania aplikacji?

A2: Tak, możesz dynamicznie modyfikować style pasków w zależności od określonych warunków lub preferencji użytkownika w aplikacji.

### Q3: Czy Aspose.Tasks obsługuje eksport projektów ze stylizowanymi paskami do różnych formatów plików?

A3: Tak, Aspose.Tasks umożliwia eksport projektów ze stylizowanymi paskami do różnych formatów, takich jak PDF, XLSX i HTML.

### Q4: Czy dostępne są predefiniowane style pasków w Aspose.Tasks?

A4: Choć Aspose.Tasks dostarcza domyślne style pasków, deweloperzy mogą także tworzyć własne style dostosowane do wymagań projektu.

### Q5: Czy mogę pobrać i zmodyfikować istniejące style pasków w projekcie za pomocą API?

A5: Tak, istnieje możliwość pobrania i modyfikacji istniejących stylów pasków programowo przy użyciu API Aspose.Tasks dla .NET.

## Najczęściej zadawane pytania

**P: Jak zmienić kolor paska dla zwykłych zadań, a nie kamieni milowych?**  
O: Ustaw `style.ItemType = BarItemType.Task;` i przypisz `style.BarColor` do żądanego `Color`.

**P: Czy mogę użyć tego podejścia do stylizacji pasków przy eksporcie do HTML?**  
O: Tak. Użyj `HtmlSaveOptions` i wypełnij jego kolekcję `BarStyles` w ten sam sposób.

**P: Czy istnieje limit liczby stylów pasków, które mogę zdefiniować?**  
O: Praktycznie nie; możesz dodać dowolną liczbę, ale pamiętaj o wydajności przy bardzo dużych kolekcjach.

**P: Czy muszę wywołać `project.Calculate()` po zmianie stylów?**  
O: Nie, style są stosowane podczas operacji zapisu; przeliczenie jest wymagane tylko przy zmianach harmonogramu.

---

**Ostatnia aktualizacja:** 2026-04-06  
**Testowano z:** Aspose.Tasks 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}