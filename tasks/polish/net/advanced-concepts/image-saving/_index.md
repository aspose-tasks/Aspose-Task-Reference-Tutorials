---
date: 2026-03-05
description: Dowiedz się, jak zapisywać obrazy, generować HTML z obrazami i dostosowywać
  eksport obrazów przy użyciu Aspose.Tasks dla .NET. Przewodnik krok po kroku, jak
  zapisać projekt jako HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Jak zapisać obrazy przy użyciu Aspose.Tasks dla .NET
url: /pl/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zapisywać obrazy przy użyciu Aspose.Tasks dla .NET

## Wprowadzenie

W tym samouczku dowiesz się **jak zapisywać obrazy** z plików Microsoft Project przy użyciu API Aspose.Tasks dla .NET. Niezależnie od tego, czy potrzebujesz osadzić wykresy w raportach, generować strony HTML zawierające wizualizacje projektu, czy po prostu wyeksportować zasoby diagramowe, poniższe kroki poprowadzą Cię przez cały proces – od skonfigurowania obiektu projektu po dostosowanie wywołań zwrotnych eksportu obrazu.

## Szybkie odpowiedzi
- **Co oznacza „jak zapisywać obrazy” w Aspose.Tasks?**  
  Odnosi się to do użycia interfejsu `IImageSavingCallback`, który pozwala kontrolować, gdzie i w jaki sposób zasoby wizualne są zapisywane na dysku.
- **Czy mogę zapisać projekt jako HTML z osadzonymi obrazami?**  
  Tak, używając `HtmlSaveOptions` razem z wywołaniami zwrotnymi zapisu obrazu możesz **zapisać projekt jako HTML**, który zawiera wszystkie wygenerowane obrazy.
- **Czy do eksportu obrazów potrzebna jest licencja?**  
  Tymczasowa licencja ewaluacyjna działa w trybie testowym; pełna licencja jest wymagana w środowisku produkcyjnym.
- **Jakie wersje .NET są obsługiwane?**  
  Aspose.Tasks dla .NET obsługuje .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6+.
- **Czy można dostosować eksport obrazu (format, folder, nazewnictwo)?**  
  Zdecydowanie – wywołanie zwrotne daje pełną kontrolę nad nazwą pliku, formatem i miejscem docelowym.

## Co oznacza „jak zapisywać obrazy” w kontekście Aspose.Tasks?
Zapisywanie obrazów oznacza wyodrębnianie elementów wizualnych (wykresy, paski Gantta, grafiki zasobów) z pliku Project i zapisywanie ich jako pliki graficzne (PNG, JPEG itp.). Aspose.Tasks udostępnia elastyczny mechanizm wywołań zwrotnych, który pozwala określić dokładną lokalizację, konwencję nazewnictwa oraz format obrazu.

## Dlaczego warto używać Aspose.Tasks do zapisywania obrazów?
- **Pełna kontrola programistyczna** – nie wymaga ręcznej interakcji z interfejsem UI.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS dzięki .NET Core.  
- **Renderowanie wysokiej jakości** – obrazy zachowują taką samą jakość jak oryginalny widok projektu.  
- **Łatwa generacja HTML** – połącz `HtmlSaveOptions` z wywołaniami zwrotnymi obrazów, aby **automatycznie generować HTML z obrazami**.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

1. Zainstalowane Visual Studio na maszynie deweloperskiej.  
2. Aspose.Tasks dla .NET pobrane z [tutaj](https://releases.aspose.com/tasks/net/).  
3. Podstawową znajomość C# oraz struktury projektu .NET.

## Importowanie przestrzeni nazw

Najpierw dodaj wymagane przestrzenie nazw do swojego pliku źródłowego:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Utworzenie obiektu Project

Wczytaj plik Microsoft Project, z którym chcesz pracować:

```csharp
var project = new Project("Project1.mpp");
```

## Krok 2: Definiowanie opcji zapisu

Utwórz opcje zapisu HTML, które będą również przechowywać nasze wywołania zwrotne zapisu obrazu:

```csharp
var options = GetSaveOptions(1);
```

## Krok 3: Zapis projektu jako HTML (save project as html)

Teraz wyeksportuj projekt do pliku HTML. Obrazy odwoływane w HTML zostaną wygenerowane przez wywołanie zwrotne, które zdefiniujemy w następnym kroku:

```csharp
project.Save("document_out.html", options);
```

## Krok 4: Implementacja wywołania zwrotnego zapisu obrazu (customize image export)

Zaimplementuj interfejs `IImageSavingCallback`. To miejsce, w którym **dostosowujesz zachowanie eksportu obrazu**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Krok 5: Zapis obrazów do określonego katalogu

W metodzie `ImageSaving` zdecyduj, gdzie każdy obraz ma być przechowywany. Poniższy przykład rozróżnia zasoby PNG od innych formatów:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Krok 6: Określenie opcji zapisu (w tym wywołań zwrotnych)

Podłącz wywołania zwrotne dla czcionek, CSS i obrazów. Dzięki temu każdy element wizualny będzie obsługiwany konsekwentnie:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Obrazy nie pojawiają się w wygenerowanym HTML | Wywołanie zwrotne nie przypisuje prawidłowej ścieżki pliku | Upewnij się, że `args.Path` wskazuje na folder z prawami zapisu i prawidłowo ustaw `args.ImageStream`. |
| Pliki PNG zapisywane z niewłaściwym rozszerzeniem | Logika warunkowa sprawdza tylko przyrostek „png” | Użyj `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` dla solidnego wykrywania. |
| Odwołania w HTML są zepsute po przeniesieniu plików | Zmieniły się ścieżki względne po przeniesieniu folderu wyjściowego | Trzymaj foldery HTML i obrazów razem lub zaktualizuj `options.ImageFolder` odpowiednio. |

## Zakończenie

Postępując zgodnie z tymi krokami, teraz wiesz **jak zapisywać obrazy** z pliku Project, **jak zapisać projekt jako HTML** oraz **jak dostosować eksport obrazów** do struktury folderów Twojej aplikacji. To podejście umożliwia **generowanie HTML z obrazami**, które można osadzać w raportach, portalach dokumentacji lub pulpitach internetowych bezproblemowo.

## Najczęściej zadawane pytania

**P1: Czy mogę używać Aspose.Tasks do manipulacji plikami projektu w formatach innych niż HTML?**  
Odp: Tak, Aspose.Tasks obsługuje różne formaty, takie jak PDF, XLSX i MPP.

**P2: Czy Aspose.Tasks zapewnia wsparcie dla integracji z przechowywaniem w chmurze?**  
Odp: Tak, Aspose.Tasks oferuje API do pracy z popularnymi usługami chmurowymi, takimi jak Amazon S3 i Google Drive.

**P3: Czy Aspose.Tasks jest kompatybilny z .NET Core?**  
Odp: Tak, Aspose.Tasks jest kompatybilny z .NET Core, co pozwala na tworzenie aplikacji wieloplatformowych.

**P4: Czy mogę dostosować wygląd zapisywanych obrazów?**  
Odp: Tak, możesz modyfikować wygląd zapisywanych obrazów, zmieniając logikę zapisu w metodach wywołań zwrotnych.

**P5: Czy Aspose.Tasks oferuje wersje próbne do oceny?**  
Odp: Tak, darmową wersję próbną Aspose.Tasks można uzyskać [tutaj](https://releases.aspose.com/).

---

**Ostatnia aktualizacja:** 2026-03-05  
**Testowano z:** Aspose.Tasks 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}