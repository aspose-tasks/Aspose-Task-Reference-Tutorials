---
date: 2026-03-19
description: Dowiedz się, jak dodać wiele niestandardowych kolumn i sformatować szerokość
  niestandardowych kolumn podczas eksportowania projektu do XML przy użyciu Aspose.Tasks
  dla .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Dodaj wiele niestandardowych kolumn do widoku przydziałów w Aspose.Tasks
url: /pl/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj wiele niestandardowych kolumn do widoku przydziałów w Aspose.Tasks

## Wprowadzenie

W tym samouczku dowiesz się **jak dodać wiele niestandardowych kolumn** do widoku przydziałów przy użyciu Aspose.Tasks dla .NET. Niestandardowe kolumny pozwalają wyświetlać dodatkowe dane — takie jak notatki, koszty lub własne flagi — bezpośrednio w eksportowanych raportach. Po zakończeniu przewodnika będziesz w stanie ustawić szerokość niestandardowej kolumny, wyeksportować projekt do XML i dostosować widok do potrzeb zarządzania projektem.

## Szybkie odpowiedzi
- **Co mogę osiągnąć?** Wyświetlanie dowolnych danych przydziału w niestandardowych kolumnach i kontrolowanie ich wyglądu.  
- **Jakie formaty to obsługują?** Eksport projektu do XML (lub innych formatów) przy użyciu `Spreadsheet2003SaveOptions`.  
- **Czy potrzebna jest licencja?** Tak, wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego.  
- **Jakie wersje .NET działają?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ile kolumn mogę dodać?** Nieograniczoną liczbę – wystarczy utworzyć dodatkowe instancje `AssignmentViewColumn`.

## Czym są wiele niestandardowych kolumn?
Wiele niestandardowych kolumn to pola definiowane przez użytkownika, które pojawiają się obok domyślnych kolumn przydziału, gdy projekt jest zapisywany lub eksportowany. Dają one możliwość wyświetlenia dowolnej właściwości obiektu `ResourceAssignment`, takiej jak własne notatki, kody kosztów czy wartości obliczeniowe.

## Dlaczego dodać wiele niestandardowych kolumn do widoku przydziałów?
- **Ulepszone raportowanie:** Dodaj informacje specyficzne dla projektu, które nie są objęte wbudowanymi kolumnami.  
- **Lepsze podejmowanie decyzji:** Interesariusze mogą zobaczyć dokładnie te dane, których potrzebują, bez przeszukiwania surowych plików.  
- **Spójne formatowanie:** Kontroluj szerokość kolumny i konwersję tekstu, aby uzyskać czysty, czytelny wynik.  

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

1. Podstawową wiedzę o języku programowania C#.  
2. Zainstalowaną bibliotekę Aspose.Tasks for .NET. Jeśli nie, możesz ją pobrać **[tutaj](https://releases.aspose.com/tasks/net/)**.  
3. Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.  

## Przewodnik krok po kroku

### Krok 1: Importowanie przestrzeni nazw
Najpierw zaimportuj przestrzenie nazw, które udostępniają klasy potrzebne do pracy z projektami i wizualizacjami.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Krok 2: Załaduj projekt
Utwórz instancję `Project` i załaduj istniejący plik MPP.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Krok 3: Utwórz opcje zapisu arkusza kalkulacyjnego
Zainicjuj `Spreadsheet2003SaveOptions` – ten obiekt pozwala dostosować widok przydziału przed eksportem.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Krok 4: Zdefiniuj niestandardową kolumnę
Utwórz `AssignmentViewColumn` dla każdego elementu danych, który chcesz wyświetlić. Poniżej dodajemy kolumnę **Notatki** o szerokości 200 punktów.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Wskazówka:** Aby dodać *wiele* niestandardowych kolumn, powtórz ten krok z różnymi nazwami pól i logiką delegata, a następnie dodaj każdą instancję do `options.AssignmentView.Columns`.

### Krok 5: Dodaj niestandardową kolumnę do opcji
Dodaj kolumnę (lub kolumny) do kolekcji `Columns` widoku przydziału.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Krok 6: Iteruj przez przydziały (opcjonalne debugowanie)
Możesz przejść przez przydziały, aby zweryfikować, że tekst niestandardowej kolumny jest generowany prawidłowo.

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

### Krok 7: Zapisz projekt z niestandardowymi kolumnami
Na koniec zapisz projekt. Przykład zapisuje do XML, ale możesz wybrać dowolny obsługiwany format.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Jak wyeksportować projekt do XML z niestandardowymi kolumnami?
Gdy wywołasz `project.Save` z skonfigurowanymi `Spreadsheet2003SaveOptions`, Aspose.Tasks zapisuje dane projektu — w tym wszystkie **wiele niestandardowych kolumn** — do wybranego pliku XML. Ułatwia to udostępnianie wzbogaconych informacji o projekcie innym systemom lub interesariuszom.

## Formatuj szerokość niestandardowej kolumny dla lepszej czytelności
Drugi parametr konstruktora `AssignmentViewColumn` kontroluje szerokość kolumny (mierzoną w punktach). Dostosuj tę wartość do oczekiwanej ilości tekstu. Na przykład szerokość **300** sprawdza się przy dłuższych notatkach, natomiast **100** wystarcza dla krótkich flag.

## Typowe problemy i rozwiązania
- **Tekst w kolumnie jest pusty:** Upewnij się, że delegat zwraca ciąg znaków i że właściwość przydziału (np. `Asn.NotesText`) jest wypełniona.  
- **Kolumny nie są widoczne w wyeksportowanym pliku:** Sprawdź, czy `options.AssignmentView.Columns` zawiera Twoje niestandardowe kolumny przed wywołaniem `Save`.  
- **Szerokość jest ignorowana:** Niektóre formaty eksportu mają własne zasady układu; XML respektuje szerokość, ale PDF/HTML mogą wymagać dodatkowego stylowania.

## Najczęściej zadawane pytania

### Q1: Czy mogę dodać wiele niestandardowych kolumn do widoku przydziałów?
**A:** Tak, po prostu utwórz dodatkowe obiekty `AssignmentViewColumn` i dodaj każdy do `options.AssignmentView.Columns`.

### Q2: Czy dostępne są wbudowane konwertery dla typowych pól przydziału?
**A:** Tak, Aspose.Tasks udostępnia wbudowane konwertery dla wielu standardowych pól, co ułatwia pobieranie danych bez pisania własnych delegatów.

### Q3: Czy mogę dostosować wygląd niestandardowych kolumn, np. formatowanie tekstu lub stosowanie stylów?
**A:** Oczywiście. Oprócz ustawiania szerokości możesz modyfikować czcionkę, wyrównanie i inne właściwości wizualne poprzez opcje stylizacji kolumny.

### Q4: Czy można usunąć domyślne kolumny z widoku przydziałów?
**A:** Możesz wykluczyć domyślne kolumny, usuwając je z kolekcji `Columns` lub ustawiając ich szerokość na zero.

### Q5: Czy Aspose.Tasks obsługuje eksport projektów do innych formatów poza arkuszami z niestandardowymi kolumnami?
**A:** Tak, Aspose.Tasks może eksportować do PDF, HTML, XML i wielu innych formatów, zachowując definicje niestandardowych kolumn.

---

**Ostatnia aktualizacja:** 2026-03-19  
**Testowano z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}