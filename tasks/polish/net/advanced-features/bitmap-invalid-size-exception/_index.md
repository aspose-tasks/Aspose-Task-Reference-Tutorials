---
date: 2026-03-21
description: Naucz się eksportować obraz i obsługiwać wyjątek BitmapInvalidSizeException
  podczas zapisywania projektu jako obrazu w Aspose.Tasks dla .NET. Zawiera kroki
  zapisu projektu jako obrazu oraz eksportu projektu do formatu PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak wyeksportować obraz i obsłużyć wyjątek nieprawidłowego rozmiaru
url: /pl/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wyeksportować obraz – obsługa wyjątku nieprawidłowego rozmiaru bitmapy w Aspose.Tasks

W tym samouczku dowiesz się **jak wyeksportować obraz** z pliku Microsoft Project przy użyciu Aspose.Tasks dla .NET oraz, co ważniejsze, jak przechwycić `BitmapInvalidSizeException`, który może wystąpić w trakcie tego procesu. Eksportowanie projektu jako obrazu jest częstym wymaganiem przy tworzeniu pulpitów raportowych, dokumentacji lub po prostu udostępnianiu wizualnego podglądu harmonogramu. Po zakończeniu tego przewodnika będziesz w stanie **zapisować projekt jako obraz** niezawodnie i nawet **eksportować projekt do formatu PNG** bez nieoczekiwanych awarii.

## Szybkie odpowiedzi
- **Jaki wyjątek może wystąpić podczas eksportu obrazu?** `BitmapInvalidSizeException`  
- **Jaki format jest użyty w przykładzie?** PNG (`SaveFileFormat.Png`)  
- **Czy potrzebna jest specjalna licencja?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego.  
- **Czy mogę zmienić skalę czasu?** Tak – możesz ustawić jednostkę skali czasu (minuty, godziny, dni itp.).  
- **Czy kod jest kompatybilny z .NET Core?** Absolutnie – to samo API działa w .NET Framework i .NET Core.

## Co to jest BitmapInvalidSizeException?
`BitmapInvalidSizeException` jest rzucany, gdy wymiary bitmapy obliczone dla obrazu znajdują się poza obsługiwanym zakresem (np. szerokość lub wysokość wynosi zero lub przekracza wewnętrzne limity). Zwykle dzieje się tak, gdy ustawienia skali czasu lub widoku generują obraz zbyt duży lub zbyt mały.

## Dlaczego eksportować projekt jako obraz?
- **Raportowanie wizualne** – osadź wykres Gantta w plikach PDF, dokumentach Word lub stronach internetowych.  
- **Udostępnianie międzyplatformowe** – pliki PNG mogą być wyświetlane na dowolnym urządzeniu bez potrzeby posiadania Microsoft Project.  
- **Wydajność** – obrazy są lżejsze niż pełne pliki projektów, co przyspiesza podglądy.

## Wymagania wstępne
1. Podstawowa znajomość C# i programowania w .NET.  
2. Zainstalowany Aspose.Tasks dla .NET (pakiet NuGet `Aspose.Tasks`).  
3. Przykładowy plik Microsoft Project (np. `Blank2010.mpp`).  

## Importowanie przestrzeni nazw
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Przewodnik krok po kroku

### Krok 1: Inicjalizacja projektu i wybór widoku
Najpierw utwórz instancję `Project` i wybierz widok, który chcesz wyrenderować (tutaj używamy pierwszego widoku wykresu Gantta).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Krok 2: Konfiguracja opcji zapisu obrazu (Eksport projektu do PNG)
Ustaw żądany format obrazu i poinstruuj Aspose.Tasks, aby użył skali czasu zdefiniowanej w widoku.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Krok 3: Dostosowanie jednostki skali czasu (Kontrola rozmiaru obrazu)
Zmiana skali czasu wpływa na wymiary bitmapy. W tym przykładzie używamy **minut**, aby utrzymać rozmiar obrazu w rozsądnych granicach.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Krok 4: Próba zapisania projektu jako obrazu
Ten wiersz wykonuje rzeczywistą operację **zapisz projekt jako obraz**.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Krok 5: Przechwycenie i obsługa BitmapInvalidSizeException
Otocz wywołanie zapisu w bloku `try / catch`, aby aplikacja mogła reagować łagodnie, jeśli rozmiar bitmapy jest nieprawidłowy.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Nadal występuje wyjątek po dostosowaniu skali czasu | Skala czasu wciąż generuje zbyt dużą bitmapę | Zmniejsz `view.MiddleTimescaleTier.Count` lub przełącz na grubszą jednostkę `TimescaleUnit` (np. godziny). |
| Plik wyjściowy jest pusty | Nieprawidłowa ścieżka pliku lub brak uprawnień do zapisu | Sprawdź, czy `DataDir` wskazuje na folder z prawami zapisu oraz czy nazwa pliku kończy się na `.png`, jeśli zmieniasz format. |
| Jakość obrazu jest słaba | Domyślne DPI może być niskie | Ustaw `options.DpiX` i `options.DpiY` na wyższe wartości (np. 300). |

## Najczęściej zadawane pytania

**P: Co powoduje BitmapInvalidSizeException w Aspose.Tasks?**  
O: Występuje, gdy obliczone wymiary bitmapy są nieprawidłowe — najczęściej dlatego, że skala czasu tworzy obraz zbyt duży lub o zerowej szerokości/wysokości.

**P: Czy mogę dostosować skalę czasu przy eksporcie obrazu?**  
O: Tak. Możesz modyfikować `view.MiddleTimescaleTier.Unit` i `Count`, aby dopasować je do swoich potrzeb, jak pokazano w samouczku.

**P: Czy Aspose.Tasks obsługuje inne formaty obrazu poza PNG?**  
O: Absolutnie. `SaveFileFormat` zawiera także JPEG, BMP, GIF i TIFF. Wystarczy zmienić wartość wyliczenia w `ImageSaveOptions`.

**P: Czy licencja jest wymagana do eksportowania obrazów w środowisku produkcyjnym?**  
O: Tak. Biblioteka działa w trybie ewaluacyjnym, ale komercyjna licencja usuwa ograniczenia ewaluacyjne i zapewnia pełne wsparcie.

**P: Jak mogę poprawić jakość eksportowanego PNG?**  
O: Zwiększ ustawienia DPI (`options.DpiX` i `options.DpiY`) lub dostosuj skalę czasu widoku, aby uzyskać większą bitmapę.

## Podsumowanie
Postępując zgodnie z powyższymi krokami, teraz wiesz **jak wyeksportować obraz** z pliku Project, **jak zapisać projekt jako obraz** oraz jak elegancko obsłużyć `BitmapInvalidSizeException`. Te techniki sprawiają, że Twoje procesy raportowania są bardziej odporne i zapewniają niezawodne eksporty wizualne niezależnie od rozmiaru projektu i wybranej skali czasu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-21  
**Testowano z:** Aspose.Tasks 24.12 dla .NET  
**Autor:** Aspose  

---