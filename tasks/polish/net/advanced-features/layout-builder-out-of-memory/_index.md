---
date: 2026-03-24
description: Poznaj obsługę braku pamięci oraz sposób zapisywania obrazu projektu
  przy użyciu Aspose.Tasks Layout Builder w .NET. Przewodnik krok po kroku z przykładami
  kodu.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Obsługa braku pamięci w Aspose.Tasks Layout Builder (C#)
url: /pl/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa braku pamięci w Aspose.Tasks Layout Builder

## Introduction

Obsługa braku pamięci jest krytyczną częścią budowania niezawodnych aplikacji .NET pracujących z dużymi plikami projektów. Gdy generujesz wizualizacje przy użyciu Aspose.Tasks Layout Builder, możesz szybko napotkać wyjątki związane z pamięcią, szczególnie przy złożonych wykresach Gantta. W tym samouczku przeprowadzimy Cię przez to, jak **obsługiwać wyjątki pamięci**, **dostosować widok Gantta** i **bezpiecznie zapisać obraz projektu**, aby Twoja aplikacja pozostawała responsywna nawet przy masywnych harmonogramach.

## Quick Answers
- **Co to jest obsługa braku pamięci?** Zarządzanie zużyciem pamięci i przechwytywanie błędów typu `OutOfMemoryException` podczas przetwarzania dużych danych.
- **Które API pomaga?** Aspose.Tasks Layout Builder dla .NET.
- **Typowy scenariusz?** Renderowanie wykresu Gantta w wysokiej rozdzielczości do formatu PNG.
- **Kluczowy wymóg wstępny?** .NET (Framework 4.5+ lub .NET 6) z zainstalowanym Aspose.Tasks.
- **Jak przechwytywać błędy?** Użyj bloków `try…catch` dla `ApsLayoutBuilderOutOfMemoryException` i powiązanych wyjątków.

## Prerequisites

Zanim zagłębisz się w kod, upewnij się, że masz:

1. **Podstawy C#** – powinieneś być zaznajomiony ze standardową składnią C#.
2. **Aspose.Tasks for .NET** zainstalowane. Jeśli jeszcze go nie dodałeś, pobierz go z [tutaj](https://releases.aspose.com/tasks/net/).
3. **IDE**, takie jak Visual Studio (lub VS Code z rozszerzeniem C#) do kompilacji i uruchamiania przykładu.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Step‑by‑Step Guide

### Step 1: Load the Project

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Ten wiersz ładuje **Blank2010.mpp** do instancji `Project`, przygotowując ją do wizualizacji.

### Step 2: Customize Gantt Chart View

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Tutaj **dostosowujemy widok Gantta** poprzez zmianę środkowych i dolnych poziomów skali czasu. Zmiana tych poziomów zmniejsza ilość danych renderowanych jednocześnie, co może pomóc złagodzić obciążenie pamięci.

### Step 3: Configure Image Save Options

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` informuje Aspose.Tasks, jak renderować wykres. Wybieramy PNG jako format wyjściowy i wiążemy skalę czasu z widokiem, który właśnie dostosowaliśmy.

### Step 4: Save the Project as an Image

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

Wywołanie `Save` **zapisuje obraz projektu** przy użyciu powyższych opcji. Jeśli projekt jest bardzo duży, to jest moment, w którym najprawdopodobniej pojawi się warunek braku pamięci.

### Step 5: Handle Exceptions

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Przechwytując `ApsLayoutBuilderOutOfMemoryException` **obsługujesz wyjątek pamięci** w sposób elegancki, zapewniając czytelny komunikat zamiast awarii aplikacji. Drugi blok catch zajmuje się problemami z rozmiarem bitmapy, które mogą wystąpić przy renderowaniu ogromnych wykresów.

## Common Issues and Solutions

| Problem | Dlaczego się dzieje | Rozwiązanie |
|-------|----------------|-----|
| **OutOfMemoryException** | Renderowanie obrazu w bardzo wysokiej rozdzielczości zużywa więcej pamięci RAM niż proces może przydzielić. | Zmniejsz wymiary obrazu, uprość poziomy skali czasu lub podziel wykres na wiele obrazów. |
| **BitmapInvalidSizeException** | Żądany rozmiar bitmapy przekracza maksymalny dopuszczalny dla platformy. | Ogranicz szerokość/wysokość w `ImageSaveOptions` lub renderuj w segmentach. |
| **Slow performance** | Duże pliki projektów wymagają dużo przetwarzania. | Włącz `project.Set(Prj.SaveToCache, true)` przed renderowaniem lub użyj wątku w tle. |

## FAQ's

### Q1: What is Aspose.Tasks for .NET?

A1: Aspose.Tasks for .NET to potężne API, które umożliwia programistom programowe manipulowanie plikami Microsoft Project w aplikacjach .NET.

### Q2: How can I obtain a temporary license for Aspose.Tasks?

A2: Możesz uzyskać tymczasową licencję na Aspose.Tasks, odwiedzając [ten link](https://purchase.aspose.com/temporary-license/).

### Q3: Is Aspose.Tasks suitable for handling large project files?

A3: Tak, Aspose.Tasks oferuje funkcje i optymalizacje umożliwiające efektywną obsługę dużych plików projektów, jednak programiści powinni nadal rozważać strategie zarządzania pamięcią.

### Q4: Can I customize the appearance of Gantt charts using Aspose.Tasks?

A4: Oczywiście! Aspose.Tasks zapewnia rozbudowane możliwości dostosowywania wyglądu i układu wykresów Gantta zgodnie z Twoimi wymaganiami.

### Q5: Where can I find more help and support for Aspose.Tasks?

A5: Więcej pomocy i wsparcia, a także możliwość kontaktu ze społecznością, znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Frequently Asked Questions

**Q: How can I reduce memory usage when saving a project image?**  
A: Obniż rozdzielczość obrazu, ogranicz zakres skali czasu lub zapisz wykres w kilku mniejszych segmentach.

**Q: Is it possible to stream the image directly to a web response?**  
A: Tak, możesz użyć `project.Save(stream, options)` i zapisać strumień do odpowiedzi HTTP.

**Q: Does Aspose.Tasks support .NET Core and .NET 5/6?**  
A: Biblioteka jest w pełni kompatybilna z .NET Core, .NET 5 i .NET 6.

**Q: What should I do if I still hit an out‑of‑memory error after optimization?**  
A: Rozważ przetwarzanie projektu na maszynie z większą ilością RAM lub przenieś renderowanie do usługi w tle.

**Q: Can I export the Gantt chart to formats other than PNG?**  
A: Tak, `ImageSaveOptions` obsługuje JPEG, BMP i TIFF oprócz PNG.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}