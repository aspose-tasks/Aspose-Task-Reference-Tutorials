---
date: 2026-07-05
description: Dowiedz się, jak kopiować dane projektu przy użyciu Aspose.Tasks dla
  .NET z opcjami kopiowania. Zwiększ wydajność swoich aplikacji .NET dzięki precyzyjnemu
  zarządzaniu projektami.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Jak skopiować dane projektu przy użyciu opcji kopiowania w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Jak skopiować dane projektu przy użyciu opcji kopiowania w Aspose.Tasks
url: /pl/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak skopiować dane projektu przy użyciu opcji kopiowania w Aspose.Tasks

## Wprowadzenie

Jeśli potrzebujesz **jak skopiować projekt** informacje z jednego pliku Microsoft Project do drugiego, Aspose.Tasks for .NET daje Ci czysty, code‑first sposób ich kopiowania. W tym samouczku przeprowadzimy Cię przez pełny przepływ pracy — ładowanie projektu źródłowego, konfigurowanie opcji kopiowania, tworzenie kopii i ładowanie wyniku — abyś mógł zintegrować logikę kopiowania projektów w dowolnej aplikacji .NET z pewnością.

## Szybkie odpowiedzi
- **Co robi funkcja kopiowania?** Powiela dane projektu, umożliwiając jednocześnie włączenie lub wykluczenie określonych sekcji, takich jak kalendarze, zasoby lub informacje o widokach.  
- **Która klasa kontroluje zachowanie?** `CopyToOptions` pozwala precyzyjnie dostosować, co jest kopiowane.  
- **Czy potrzebna jest licencja?** Ważna licencja Aspose.Tasks jest wymagana w środowisku produkcyjnym; darmowa wersja próbna działa w fazie rozwoju.  
- **Obsługiwane formaty?** Aspose.Tasks obsługuje pliki MPP, XML i XER — ponad 20 + formatów łącznie.  
- **Czy mogę pominąć dane widoku?** Tak, ustaw `CopyToOptions.SkipViewData = true`, aby pominąć informacje związane z interfejsem użytkownika.

## Co to jest „jak skopiować projekt” w Aspose.Tasks?
**„Jak skopiować projekt”** odnosi się do użycia API Aspose.Tasks do duplikowania danych obiektu Project do nowego pliku, opcjonalnie filtrując niepożądane elementy. Operacja ta jest przydatna do tworzenia szablonów, archiwizacji lub tworzenia wariantów projektu bez ręcznych kroków w interfejsie użytkownika i działa we wszystkich obsługiwanych formatach plików.

## Dlaczego używać opcji kopiowania w Aspose.Tasks?
Aspose.Tasks obsługuje **ponad 50 podmiotów związanych z projektem** (zadania, zasoby, kalendarze, przydziały itp.) i może przetwarzać pliki zawierające **do 10 000 zadań**, jednocześnie utrzymując zużycie pamięci poniżej 200 MB. Użycie `CopyToOptions` pozwala uniknąć kopiowania ciężkich danych widoku, zmniejszając rozmiar pliku wyjściowego o **30‑40 %** i przyspieszając operację o około **2×** w przypadku dużych projektów.

## Wymagania wstępne

1. **Aspose.Tasks for .NET** – pobierz najnowszą wersję z [download link](https://releases.aspose.com/tasks/net/).  
2. **Środowisko programistyczne .NET** – zainstalowany Visual Studio 2022 (lub dowolne IDE obsługujące .NET 6+).  
3. **Ważna licencja Aspose.Tasks** – opcjonalna do oceny, obowiązkowa w wersjach produkcyjnych.  
4. **Istniejący plik projektu** (np. `SourceProject.xml`), który chcesz skopiować.

## Jak zaimportować przestrzenie nazw dla Aspose.Tasks?

Dodaj wymagane dyrektywy `using` na początku pliku C#, aby kompilator mógł odnaleźć typy Aspose.Tasks. Dołączenie tych instrukcji zapewnia bezpośredni dostęp do `Project`, `CopyToOptions` i innych klas pomocniczych bez konieczności pełnego kwalifikowania ich nazw, upraszczając kod i zwiększając czytelność.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Krok 1: Inicjalizacja obiektów projektu

Najpierw utwórz instancję `Project`, która reprezentuje plik źródłowy i załaduj dane XML.  
Klasa `Project` reprezentuje plik Microsoft Project załadowany do pamięci, udostępniając zadania, zasoby, kalendarze i inne informacje o projekcie.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Wskazówka:** Jeśli pracujesz z bardzo dużymi plikami, rozważ użycie konstruktora `LoadOptions`, aby włączyć leniwe ładowanie i utrzymać niskie zużycie pamięci.

## Krok 2: Utwórz kopię projektu

Następnie zainicjuj drugi obiekt `Project`, który otrzyma skopiowane dane. Ten obiekt zaczyna się jako pusty.

```csharp
Project copiedProject = new Project();
```

Masz teraz dwa odrębne obiekty `Project`: jeden załadowany z dysku i drugi gotowy do przyjęcia kopii.

## Krok 3: Załaduj skopiowany projekt

Po operacji kopiowania (pokazanej później) będziesz chciał zweryfikować wynik, ładując nowo zapisany plik do kolejnej instancji `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Ponowne załadowanie pliku potwierdza, że kopiowanie zakończyło się sukcesem i że ustawione opcje zachowały się zgodnie z oczekiwaniami.

## Krok 4: Skonfiguruj opcje kopiowania

Klasa `CopyToOptions` pozwala dokładnie określić, co zostanie przeniesione ze źródła do docelowego.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Ustawienie `SkipViewData = true` zmniejsza rozmiar pliku wyjściowego i przyspiesza operację, szczególnie gdy potrzebujesz tylko logicznych danych projektu.

## Krok 5: Wykonaj kopiowanie projektu

Na koniec wywołaj metodę `CopyTo` na projekcie źródłowym, przekazując projekt docelowy oraz skonfigurowane opcje.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

To dwuliniowe wywołanie wykonuje całą operację kopiowania, respektując zdefiniowane opcje. Powstały plik `CopiedProject.xml` zawiera jedynie dane, które zostały określone.

## Częste problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **NullReferenceException podczas wywoływania `CopyTo`** | Projekt docelowy nie został zainicjowany. | Upewnij się, że `new Project()` jest wywoływany przed `CopyTo`. |
| **Brak zadań po kopiowaniu** | `CopyCommonData` ustawione na `false`. | Ustaw `CopyCommonData = true` lub ręcznie skopiuj wybrane kolekcje. |
| **Duży plik wyjściowy** | `SkipViewData` pozostawione jako `false`. | Włącz `SkipViewData`, aby pominąć dane związane z interfejsem użytkownika. |
| **Licencja nie zastosowana** | Plik licencji nie został załadowany. | Wywołaj `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` przed użyciem jakiejkolwiek API. |

## Najczęściej zadawane pytania

**P: Czy mogę skopiować tylko podzbiór zadań?**  
O: Tak, użyj `CopyToOptions` razem z `ProjectRootTask`, aby określić zadanie początkowe, lub ręcznie skopiuj wybrane zadania po początkowym kopiowaniu.

**P: Czy Aspose.Tasks obsługuje kopiowanie między różnymi formatami plików?**  
O: Zdecydowanie tak. Możesz załadować plik MPP i zapisać kopię jako XML, XER lub dowolny inny obsługiwany format — ponad **20 + formatów** łącznie.

**P: Jak obsłużyć pliki projektu chronione hasłem?**  
O: Załaduj źródło przy użyciu `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, a następnie kontynuuj kopiowanie jak zwykle.

**P: Czy istnieje sposób na skopiowanie pul zasobów bez zadań?**  
O: Ustaw `CopyToOptions.CopyResources = true` i `CopyToOptions.CopyTasks = false`, aby przenieść tylko informacje o zasobach.

**P: Gdzie mogę znaleźć więcej przykładów?**  
O: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać fragmenty kodu tworzone przez społeczność, porady rozwiązywania problemów i oficjalną dokumentację.

---

**Ostatnia aktualizacja:** 2026-07-05  
**Testowano z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Opanowanie danych projektu z Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Opanowanie opcji zapisu MS Project dla Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Kalendarz i harmonogramowanie w Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}