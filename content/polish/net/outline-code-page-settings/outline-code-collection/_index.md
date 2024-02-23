---
title: Kolekcja MS Project kodów konspektu w Aspose.Tasks
linktitle: Zbiór kodów konspektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zbierać kody konspektu programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Ten obszerny samouczek zawiera instrukcje krok po kroku.
type: docs
weight: 11
url: /pl/net/outline-code-page-settings/outline-code-collection/
---
## Wstęp
W tym samouczku przyjrzymy się, jak zbierać kody konspektu programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Aby zapewnić przejrzystość i zrozumienie, podzielimy proces na instrukcje krok po kroku.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Visual Studio: Zainstaluj Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość programowania w języku C#: Znajomość języka C# będzie korzystna.

## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks w projekcie C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Krok 1: Załaduj plik projektu
 Rozpocznij od załadowania pliku Microsoft Project za pomocą`Project` klasa.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Krok 2: Zbierz kody konspektu
Utwórz moduł zbierający, aby zebrać kody konspektu z zadań projektu.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Krok 3: Iteruj po zadaniach i kodach konspektu
Iteruj po zebranych zadaniach i kodach konspektu, drukując ich szczegóły.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Krok 4: Dodaj niestandardową definicję kodu konspektu
Dodaj do projektu niestandardową definicję kodu konspektu.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Krok 5: Utwórz i wstaw kod konspektu
Utwórz kod konspektu i wstaw go do zadania.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Krok 6: Manipuluj kodami konspektu
W razie potrzeby manipuluj kodami konspektu, na przykład wstawiając, usuwając lub czyszcząc.
```csharp
// Przykład manipulacji
// ,
// Wstaw kod z cyfrą 2 na właściwej pozycji
task.OutlineCodes.Insert(2, code2);
// Sprawdź, czy kod został wpisany
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Wniosek
tym samouczku nauczyliśmy się zbierać kody konspektu programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz skutecznie zarządzać kodami konspektu w swoich projektach, poprawiając organizację i przejrzystość.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla .NET z innymi językami programowania?
O: Tak, Aspose.Tasks for .NET jest skierowany przede wszystkim na platformę .NET, ale zapewnia także obsługę innych języków programowania poprzez Aspose.Tasks for Cloud.
### P: Czy istnieją jakieś ograniczenia dotyczące rozmiaru plików projektu, które może obsłużyć Aspose.Tasks dla .NET?
Odp.: Aspose.Tasks dla .NET może wydajnie obsługiwać duże pliki projektu, ale wydajność może się różnić w zależności od złożoności i rozmiaru pliku.
### P: Czy Aspose.Tasks for .NET jest kompatybilny z najnowszymi wersjami Microsoft Project?
Odp.: Tak, Aspose.Tasks for .NET obsługuje różne wersje Microsoft Project, w tym najnowsze.
### P: Czy mogę dostosować format wyjściowy podczas pracy z Aspose.Tasks dla .NET?
O: Oczywiście, Aspose.Tasks dla .NET zapewnia szerokie możliwości dostosowywania formatu wyjściowego zgodnie z Twoimi wymaganiami.
### P: Gdzie mogę znaleźć dodatkowe wsparcie lub zasoby dla Aspose.Tasks dla .NET?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub zapytań dotyczących Aspose.Tasks dla .NET.