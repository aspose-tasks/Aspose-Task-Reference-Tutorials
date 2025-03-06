---
title: Główne rozszerzone definicje atrybutów MS Project w Aspose.Tasks
linktitle: Zbiór rozszerzonych definicji atrybutów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać rozszerzonymi definicjami atrybutów w programie Microsoft Project przy użyciu Aspose.Tasks dla .NET. Bez wysiłku dostosowuj i ulepszaj dane projektu.
weight: 14
url: /pl/net/tasks-project-management/extended-attribute-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Główne rozszerzone definicje atrybutów MS Project w Aspose.Tasks

## Wstęp
W tym samouczku przyjrzymy się, jak pracować z rozszerzonymi definicjami atrybutów w programie Microsoft Project przy użyciu Aspose.Tasks dla .NET. Rozszerzone atrybuty oferują elastyczny sposób dostosowywania i ulepszania danych projektu, umożliwiając użytkownikom dodawanie dodatkowych pól poza standardowymi, udostępnianymi domyślnie. Dzięki Aspose.Tasks możesz bez wysiłku zarządzać tymi rozszerzonymi atrybutami, aby dostosować swoje potrzeby w zakresie zarządzania projektami.
## Warunki wstępne
Przed kontynuowaniem upewnij się, że masz zainstalowane następujące wymagania wstępne:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks dla biblioteki .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod Aspose.Tasks w projekcie .NET. Wykonaj następujące kroki:
## Krok 1: Otwórz swój projekt .NET
Otwórz projekt .NET w preferowanym środowisku IDE, takim jak Visual Studio.
## Krok 2: Dodaj przestrzeń nazw Aspose.Tasks
Dodaj następujący wiersz na początku pliku kodu, aby zaimportować przestrzeń nazw Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Podzielmy teraz podane przykłady kodu na wiele kroków, aby uzyskać kompleksowe zrozumienie:
## Krok 1: Załaduj plik projektu
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Krok 2: Wyczyść istniejące rozszerzone definicje atrybutów (opcjonalnie)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Krok 3: Utwórz i dodaj rozszerzoną definicję atrybutu dla zadania
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Krok 4: Iteruj po rozszerzonych atrybutach zadania
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Krok 5: Utwórz i dodaj rozszerzoną definicję atrybutu dla zasobu
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Krok 6: Wstaw definicję atrybutu rozszerzonego zasobu
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Krok 7: Usuń rozszerzony atrybut według indeksu
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Wniosek
tym samouczku omówiliśmy podstawy pracy z rozszerzonymi definicjami atrybutów w programie Microsoft Project przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz efektywnie zarządzać rozszerzonymi atrybutami i dostosowywać je do wymagań związanych z zarządzaniem projektami.
## Często zadawane pytania
### P: Czy mogę modyfikować istniejące rozszerzone definicje atrybutów?
O: Tak, możesz modyfikować istniejące rozszerzone definicje atrybutów lub tworzyć nowe, zgodnie ze swoimi potrzebami.
### P: Czy rozszerzone atrybuty są obsługiwane we wszystkich wersjach programu Microsoft Project?
O: Tak, rozszerzone atrybuty są obsługiwane w większości wersji programu Microsoft Project, łącznie z najnowszymi.
### P: Czy mogę używać atrybutów rozszerzonych do obliczania pól niestandardowych?
O: Oczywiście, atrybuty rozszerzone mogą być używane do obliczania pól niestandardowych w oparciu o określone kryteria.
### P: Czy Aspose.Tasks jest kompatybilny z innymi frameworkami .NET?
O: Aspose.Tasks jest kompatybilny z różnymi frameworkami .NET, zapewniając elastyczność i łatwość integracji.
### P: Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Tasks?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) uzyskać wsparcie i zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
