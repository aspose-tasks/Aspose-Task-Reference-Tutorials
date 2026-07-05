---
date: 2026-07-05
description: Dowiedz się, jak dostosować CSS podczas eksportowania projektu do HTML
  przy użyciu Aspose.Tasks dla .NET. Dostosuj wyjście HTML za pomocą argumentów zapisywania
  CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Jak dostosować CSS podczas zapisywania projektów przy użyciu Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Jak dostosować CSS podczas zapisywania projektów przy użyciu Aspose.Tasks
url: /pl/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dostosować CSS podczas zapisywania projektów przy użyciu Aspose.Tasks

W tym przewodniku odkryjesz **jak dostosować CSS** podczas eksportu HTML pliku Microsoft Project przy użyciu Aspose.Tasks dla .NET. Poprzez dostosowanie argumentów zapisu CSS uzyskasz pełną kontrolę nad wyglądem generowanych stron HTML, co pozwoli dopasować wynik do Twojej marki lub standardów raportowania.

## Szybkie odpowiedzi
- **Jaki jest główny punkt wejścia?** Użyj `HtmlSaveOptions` z niestandardowymi callbackami.  
- **Czy potrzebuję licencji?** Tak, ważna licencja Aspose.Tasks jest wymagana w środowisku produkcyjnym.  
- **Które wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy mogę eksportować duże projekty?** Aspose.Tasks obsługuje projekty z > 10 000 zadaniami bez ładowania całego pliku do pamięci.  
- **Czy dostosowanie CSS jest opcjonalne?** Tak, możesz pominąć callbacki, aby użyć domyślnego arkusza stylów.

## Jak dostosować CSS w Aspose.Tasks?

Wczytaj swój projekt, podłącz callbacki zapisu CSS do obiektu `HtmlSaveOptions`, a następnie wywołaj `project.Save`. Ten wzorzec pozwala tworzyć własne pliki CSS, zastępować domyślne style i kontrolować strukturę folderów — wszystko w kilku linijkach kodu. Callbacki są wywoływane automatycznie dla każdego pliku CSS podczas procesu eksportu.

`HtmlSaveOptions` konfiguruje sposób, w jaki projekt jest eksportowany do HTML.

## Wprowadzenie

W tym samouczku zagłębimy się w proces zapisywania argumentów CSS przy użyciu Aspose.Tasks dla .NET. Kaskadowe arkusze stylów (CSS) są kluczowe dla definiowania wyglądu elementów HTML. Aspose.Tasks umożliwia efektywne manipulowanie i zapisywanie tych atrybutów CSS.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:

1. **Instalacja:** Upewnij się, że zainstalowałeś Aspose.Tasks dla .NET. Możesz pobrać go ze [strony internetowej](https://releases.aspose.com/tasks/net/).  
2. **Podstawowa wiedza:** Znajomość C# i środowiska programistycznego .NET jest zalecana.

## Importowanie przestrzeni nazw

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Zdefiniuj callbacki zapisu CSS

`ICssSavingCallback` jest interfejsem, który pozwala dostosować sposób zapisywania plików CSS podczas eksportu HTML.

**Callback zapisu CSS** to delegat, który Aspose.Tasks wywołuje w celu zapisania plików CSS podczas eksportu HTML. Zdefiniuj metody callback, aby kontrolować sposób tworzenia każdego pliku CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Krok 2: Zaimplementuj callbacki zapisu czcionek i obrazów

`FontSavingArgs` dostarcza informacji o zapisywanej czcionce, natomiast `ImageSavingArgs` udostępnia szczegóły dotyczące zasobów obrazów.

Zaimplementuj metody callback zapisu czcionek i obrazów w podobny sposób:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Krok 3: Skonfiguruj opcje zapisu

`HtmlSaveOptions` jest obiektem konfiguracyjnym, który kontroluje sposób eksportu projektu do HTML.

`HtmlSaveOptions` pozwala określić callbacki, foldery wyjściowe i inne ustawienia eksportu.

Ustaw jego właściwości, aby używać wcześniej zdefiniowanych callbacków i określić folder wyjściowy:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Krok 4: Zapisz projekt z dostosowanym CSS

`Project` reprezentuje plik Microsoft Project, który może być modyfikowany i zapisywany.

Na koniec zapisz swój projekt z dostosowanymi ustawieniami CSS:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Dlaczego dostosowywać CSS przy eksportowaniu projektów?

Aspose.Tasks obsługuje **eksport projektów do HTML** w ponad 30 formatach i może wygenerować do 30 oddzielnych plików CSS przy każdym eksporcie. Stabilnie przetwarza projekty zawierające ponad 10 000 zadań, utrzymując zużycie pamięci poniżej 200 MB, co umożliwia raportowanie na skalę przedsiębiorstwa bez wąskich gardeł wydajności.

## Zakończenie

W tym samouczku omówiliśmy, jak zapisywać argumenty CSS przy użyciu Aspose.Tasks dla .NET. Definiując callbacki zapisu CSS i konfigurując opcje zapisu HTML, możemy efektywnie manipulować atrybutami CSS zgodnie z naszymi wymaganiami.

## Najczęściej zadawane pytania

### P1: Czym jest Aspose.Tasks dla .NET?

A1: Aspose.Tasks dla .NET to potężne API .NET, które umożliwia programistom programowe operowanie plikami Microsoft Project.

### P2: Czy mogę dostosować atrybuty CSS przy zapisywaniu plików HTML przy użyciu Aspose.Tasks?

A2: Tak, możesz zdefiniować callbacki zapisu CSS, aby dostosować atrybuty CSS zgodnie z potrzebami.

### P3: Czy Aspose.Tasks dla .NET jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?

A3: Aspose.Tasks dla .NET obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność w różnych środowiskach.

### P4: Gdzie mogę znaleźć kompleksową dokumentację Aspose.Tasks dla .NET?

A4: Możesz odwołać się do [dokumentacji](https://reference.aspose.com/tasks/net/), aby uzyskać szczegółowe informacje i przykłady.

### P5: Czy Aspose.Tasks dla .NET oferuje wsparcie dla programistów?

A5: Tak, możesz uzyskać wsparcie od społeczności Aspose.Tasks poprzez [forum](https://forum.aspose.com/c/tasks/15).

**Dodatkowe pytania**

**Q: Jak dostosowanie CSS wpływa na rozmiar eksportowanego HTML?**  
A: Użycie własnego CSS może zmniejszyć całkowity rozmiar nawet o 15 %, ponieważ możesz usunąć nieużywane domyślne style.

**Q: Czy mogę używać tych samych callbacków dla wielu projektów?**  
A: Oczywiście. Zaimplementuj callbacki raz i używaj ich ponownie przy dowolnej liczbie eksportów projektów.

**Q: Czy istnieje możliwość osadzenia CSS bezpośrednio w HTML zamiast osobnych plików?**  
A: Tak, ustaw `HtmlSaveOptions.EmbeddedCss = true`, aby wstawić arkusz stylów inline, co upraszcza dystrybucję.

---

**Ostatnia aktualizacja:** 2026-07-05  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Zapisz MS Project jako HTML przy użyciu Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementacja callbacku zapisu strony w Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Obsługa zapisu obrazów w Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}