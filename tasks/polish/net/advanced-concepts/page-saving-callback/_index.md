---
date: 2026-03-16
description: Dowiedz się, jak zaimplementować wywołanie zwrotne zapisywania stron
  w Aspose.Tasks dla .NET, umożliwiając spersonalizowaną obsługę strumieni wyjściowych
  dokumentów wielostronicowych.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Zaimplementuj wywołanie zwrotne zapisywania strony w Aspose.Tasks
url: /pl/net/advanced-concepts/page-saving-callback/
weight: 12
---

ne

List items.

## Importowanie przestrzeni nazw

Then code block placeholder.

## Krok 1: Utwórz obiekt Project

...

## Krok 2: Skonfiguruj opcje zapisu obrazu

...

> **Pro tip:** ... translate.

## Krok 3: Zapisz projekt z wywołaniem zwrotnym

...

## Krok 4: Przetwarzaj zapisane strumienie stron

...

## Krok 5: Zaimplementuj własne wywołanie zwrotne zapisu strony

...

## Typowe problemy i rozwiązywanie

Table.

Translate column headers: Issue -> Problem, Reason -> Przyczyna, Solution -> Rozwiązanie.

Rows: "No pages are returned" -> "Nie zwrócono żadnych stron". etc.

## Najczęściej zadawane pytania

Then Q&A.

Translate Q1 etc.

Make sure to keep bold formatting.

Also keep links.

At the end, "Last Updated", "Tested With", "Author" translate.

Probably "Ostatnia aktualizacja", "Testowane z", "Autor".

But we must keep the same format: **Last Updated:** 2026-03-16 etc. Should translate the label.

Let's translate.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementacja wywołania zwrotnego zapisu strony w Aspose.Tasks

## Wprowadzenie

W tym samouczku dowiesz się, jak **zaimplementować wywołanie zwrotne zapisu strony** w Aspose.Tasks dla .NET. Ta potężna funkcja pozwala skierować każdą stronę wielostronicowego dokumentu do wybranego strumienia, dając pełną kontrolę nad tym, jak wynik jest przechowywany lub dalej przetwarzany.

## Szybkie odpowiedzi
- **Co robi wywołanie zwrotne zapisu strony?** Przechwytuje każdą wyrenderowaną stronę w osobnym strumieniu, aby można było obsłużyć je indywidualnie.  
- **Do jakiego formatu mogę eksportować?** Do dowolnego formatu obsługiwanego przez `ImageSaveOptions`, np. PNG, JPEG, PDF.  
- **Czy potrzebna jest licencja?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego.  
- **Czy mogę używać tego z .NET Core?** Tak, Aspose.Tasks w pełni wspiera .NET Core oraz .NET 5/6+.  
- **Czy wywołanie zwrotne jest bezpieczne wątkowo?** Wywołanie zwrotne działa w tym samym wątku, w którym odbywa się renderowanie, więc obowiązują standardowe zasady bezpieczeństwa wątkowego.

## Co to jest **implement page saving callback**?
Wzorzec **implement page saving callback** pozwala podłączyć własną logikę do potoku zapisu w Aspose.Tasks. Zamiast zapisywać bezpośrednio do pliku, otrzymujesz obiekt `Stream` dla każdej strony, co umożliwia przechowywanie go w pamięci, przesyłanie do chmury lub dodatkowe przetwarzanie.

## Dlaczego eksportować projekt jako PNG z wywołaniem zwrotnym?
Eksport projektu jako PNG daje rastrowy obraz każdej strony wykresu Gantta, co jest idealne do raportów, e‑maili lub osadzania w stronach internetowych. Użycie wywołania zwrotnego pozwala trzymać każdą stronę w osobnym `MemoryStream` bez tworzenia tymczasowych plików na dysku.

## Wymagania wstępne

1. **Znajomość C#** – podstawowa znajomość klas, interfejsów i strumieni.  
2. **Aspose.Tasks for .NET** – pobierz i zainstaluj z [tutaj](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider lub dowolny edytor kompatybilny z .NET.

## Importowanie przestrzeni nazw

Aby rozpocząć, zaimportuj wymagane przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Krok 1: Utwórz obiekt Project

Wczytaj istniejący plik MPP do instancji `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Krok 2: Skonfiguruj opcje zapisu obrazu

Ustaw `ImageSaveOptions` dla wyjścia PNG i podłącz własne wywołanie zwrotne:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Pro tip:** Ustawienie `RenderToSinglePage = false` zapewnia, że każda strona wykresu Gantta jest renderowana osobno, co jest niezbędne, aby wywołanie zwrotne otrzymało odrębne strumienie.

## Krok 3: Zapisz projekt z wywołaniem zwrotnym

Wywołaj metodę `Save`, przekazując `Stream.Null`, ponieważ rzeczywiste strumienie są dostarczane przez wywołanie zwrotne:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Krok 4: Przetwarzaj zapisane strumienie stron

Po zakończeniu operacji zapisu wywołanie zwrotne przechowuje kolekcję obiektów `MemoryStream` — po jednej na stronę. Możesz teraz iterować po nich:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Krok 5: Zaimplementuj własne wywołanie zwrotne zapisu strony

Utwórz klasę sealed, która implementuje `IPageSavingCallback`. Klasa ta przechwytuje strumień każdej strony i zapisuje go w liście do późniejszego użycia.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Typowe problemy i rozwiązywanie

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Nie zwrócono żadnych stron** | `RenderToSinglePage` pozostawiono jako `true`. | Ustaw `RenderToSinglePage = false`, aby generować oddzielne strony. |
| **Strumienie są puste** | `KeepStreamOpen` ustawiono na `true` bez późniejszego zwalniania. | Pozostaw `false` (wartość domyślna) i pozwól wywołaniu zwrotnemu automatycznie zamykać strumienie. |
| **Błędy pamięci (Out‑of‑memory)** | Bardzo duże projekty generują wiele wysokiej rozdzielczości PNG. | Przetwarzaj strumienie pojedynczo lub zwiększ limity pamięci wirtualnej. |

## Najczęściej zadawane pytania

**Q1: Co to jest wywołanie zwrotne zapisu strony w Aspose.Tasks?**  
A: Wywołanie zwrotne zapisu strony pozwala przechwycić proces zapisu każdej strony wielostronicowego dokumentu, udostępniając własny `Stream` dla tej strony.

**Q2: Czy mogę używać różnych formatów do zapisu stron przy użyciu tego wywołania zwrotnego?**  
A: Tak. Zmieniając `SaveFileFormat`, możesz eksportować do PNG, JPEG, PDF, SVG itp.

**Q3: Czy Aspose.Tasks jest kompatybilny z .NET Core?**  
A: Absolutnie. Aspose.Tasks obsługuje .NET Core, .NET 5 oraz .NET 6.

**Q4: Jak mogę obsłużyć błędy podczas procesu zapisu stron?**  
A: Otocz logikę wywołania zwrotnego blokami try/catch i loguj wyjątki. Metoda `OnFinish` jest dobrym miejscem na końcowe czyszczenie.

**Q5: Gdzie mogę znaleźć więcej zasobów i wsparcie dla Aspose.Tasks?**  
A: Możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy, dostęp do dokumentacji znajdziesz [tutaj](https://reference.aspose.com/tasks/net/), a dodatkowe funkcje i opcje licencjonowania – na stronie [Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-03-16  
**Testowane z:** Aspose.Tasks 24.12 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}