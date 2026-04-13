---
date: 2026-04-13
description: Dowiedz się, jak stworzyć kolektor zadań podrzędnych przy użyciu Aspose.Tasks
  dla .NET. Popraw zarządzanie projektami w swoich aplikacjach .NET.
keywords:
- create child tasks collector
- Aspose.Tasks child tasks
- .NET project management
- collect child tasks
- Aspose.Tasks API
linktitle: Utwórz kolektor zadań podrzędnych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak utworzyć kolektor zadań podrzędnych w Aspose.Tasks
url: /pl/net/calendar-scheduling/child-tasks-collector/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kolektor zadań podrzędnych w Aspose.Tasks

## Wprowadzenie

Jeśli potrzebujesz **utworzyć kolektor zadań podrzędnych** dla pliku Microsoft Project, Aspose.Tasks for .NET ułatwia to. W tym samouczku przeprowadzimy Cię przez dokładne kroki potrzebne do zebrania każdego zadania podrzędnego pod rodzicem, abyś mógł je przetwarzać, analizować lub eksportować z pewnością. Po zakończeniu przewodnika będziesz mieć wielokrotnego użytku fragment kodu, który naturalnie wpasowuje się w każde rozwiązanie do zarządzania projektami oparte na .NET.

## Szybkie odpowiedzi
- **Co robi ChildTasksCollector?** Przegląda hierarchię zadań i zbiera wszystkie zadania potomne do kolekcji.  
- **Która biblioteka zapewnia tę funkcję?** Aspose.Tasks for .NET.  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna działa w celach oceny; licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak długo trwa implementacja?** Około 5‑10 minut po zainstalowaniu biblioteki.

## Co to jest kolektor zadań podrzędnych?

**Kolektor zadań podrzędnych** to obiekt narzędziowy, który przegląda drzewo zadań pliku Project, zaczynając od określonego zadania głównego, i agreguje każde napotkane zadanie podrzędne (sub‑task). Jest to szczególnie przydatne, gdy chcesz zastosować operacje masowe — takie jak aktualizacja pól, eksport danych lub generowanie raportów — bez ręcznego iterowania po każdym poziomie hierarchii.

## Dlaczego tworzyć kolektor zadań podrzędnych?

- **Uprość rekurencję:** Kolektor obsługuje wewnętrznie przeglądanie w głąb, więc nie musisz pisać własnych pętli rekurencyjnych.  
- **Zwiększ produktywność:** Pobierz wszystkie zadania potomne w jednej kolekcji, co sprawia, że masowe edycje lub analizy są proste.  
- **Utrzymaj czysty kod:** Oddziela logikę biznesową od niskopoziomowej nawigacji po strukturze projektu.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

1. **Podstawowa znajomość C#** – powinieneś swobodnie pisać i uruchamiać proste aplikacje konsolowe.  
2. **Aspose.Tasks for .NET zainstalowany** – pobierz go z [download link](https://releases.aspose.com/tasks/net/).  
3. **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
4. **Dostęp do oficjalnej dokumentacji** – miej pod ręką [Aspose.Tasks for .NET documentation](https://reference.aspose.com/tasks/net/) do odniesienia.

Teraz, gdy podstawa jest gotowa, zanurzmy się w kod.

## Importowanie przestrzeni nazw

Najpierw wprowadź wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć klasy, których będziemy używać.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## Przewodnik krok po kroku

### Krok 1: Zainicjalizuj obiekt Project

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

Ten wiersz ładuje istniejący plik Microsoft Project (`ParentChildTasks.mpp`) z folderu `DataDir` do obiektu `Project`, dając nam programowy dostęp do jego zadań.

### Krok 2: Utwórz instancję ChildTasksCollector

```csharp
var collector = new ChildTasksCollector();
```

Tutaj **tworzymy kolektor zadań podrzędnych** – instancję `ChildTasksCollector`, która będzie przechowywać każde napotkane zadanie podrzędne.

### Krok 3: Zastosuj kolektor do zadania głównego

```csharp
TaskUtils.Apply(project.RootTask, collector, 0);
```

Mówimy Aspose.Tasks, aby rozpoczął zbieranie od zadania głównego projektu. Metoda `Apply` przegląda hierarchię rekurencyjnie, wypełniając `collector.Tasks` wszystkimi zadaniami potomnymi.

### Krok 4: Iteruj po zebranych zadaniach

```csharp
foreach (var task in collector.Tasks)
{
    Console.WriteLine(task.Get(Tsk.Name));
}
```

Na koniec iterujemy po zebranych zadaniach i wypisujemy nazwę każdego zadania na konsolę. W rzeczywistym scenariuszu możesz zamienić `Console.WriteLine` na dowolne własne przetwarzanie (np. eksport do CSV, aktualizacja pól itp.).

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| **Brak zwróconych zadań** | Kolektor został zastosowany do niewłaściwego zadania (np. węzła liścia). | Zastosuj `TaskUtils.Apply` do `project.RootTask` lub konkretnego rodzica, od którego chcesz rozpocząć. |
| **NullReferenceException** | `DataDir` lub ścieżka do pliku jest nieprawidłowa. | Sprawdź, czy `DataDir` wskazuje na folder zawierający `ParentChildTasks.mpp`. |
| **Licencja nie ustawiona** | Aspose.Tasks wyświetla ostrzeżenie o licencji w trybie próbnym. | Załaduj licencję przy użyciu `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` przed utworzeniem obiektu `Project`. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks for .NET jest kompatybilny ze wszystkimi wersjami .NET?**  
A: Tak, Aspose.Tasks for .NET działa z .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6+.

**Q: Czy mogę używać Aspose.Tasks for .NET do tworzenia nowych plików projektów?**  
A: Oczywiście! Biblioteka pozwala tworzyć, odczytywać i modyfikować pliki projektów programowo.

**Q: Czy Aspose.Tasks for .NET obsługuje wiele platform?**  
A: Choć jest przeznaczony dla .NET, możesz go uruchamiać na każdej platformie obsługującej środowisko .NET, w tym Windows, Linux i macOS.

**Q: Czy dostępne jest wsparcie techniczne dla Aspose.Tasks for .NET?**  
A: Tak, pomoc możesz uzyskać na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Czy mogę wypróbować Aspose.Tasks for .NET przed zakupem?**  
A: Oczywiście! Darmowa wersja próbna jest dostępna na [release page](https://releases.aspose.com/).

---

**Ostatnia aktualizacja:** 2026-04-13  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}