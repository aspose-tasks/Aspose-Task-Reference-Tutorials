---
title: Zarządzanie kolekcjami projektów w Aspose.Tasks
linktitle: Zarządzanie kolekcją grup w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać zbiorami MS Project za pomocą Aspose.Tasks dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku.
weight: 26
url: /pl/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzanie kolekcjami projektów w Aspose.Tasks

## Wstęp
tym samouczku przyjrzymy się, jak zarządzać zbiorami grupowymi MS Project za pomocą Aspose.Tasks dla .NET. Zarządzanie zbiorami grupowymi ma kluczowe znaczenie dla efektywnego organizowania zadań i zasobów oraz manipulowania nimi w ramach projektu.
## Warunki wstępne
Przed kontynuowaniem tego samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1.  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
2. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#, ponieważ ten samouczek dotyczy kodowania w języku C#.
3. Środowisko programistyczne: Skonfiguruj środowisko programistyczne, takie jak Visual Studio lub dowolne inne IDE obsługujące programowanie .NET.

## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw, aby móc pracować z funkcjonalnościami Aspose.Tasks w naszym kodzie C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Krok 1: Załaduj projekt
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Ten krok polega na wczytaniu pliku MS Project do obiektu projektu Aspose.Tasks, co pozwala na wykonanie na nim operacji.
## Krok 2: Iteruj po grupach zadań
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Tutaj iterujemy po grupach zadań w ramach projektu, drukując szczegóły, takie jak indeks, nazwa i widoczność w menu dla każdej grupy.
## Krok 3: Iteruj po grupach zasobów
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Podobnie ten krok wykonuje iterację po grupach zasobów, wyświetlając ich indeks, nazwę i widoczność w menu.
## Krok 4: Wyczyść i skopiuj grupy do innego projektu
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Wyczyść inne grupy projektu
otherProject.TaskGroups.Clear();
// Skopiuj grupy do innego projektu
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Tutaj usuwamy grupy innego projektu, a następnie kopiujemy do niego grupy z oryginalnego projektu.
## Krok 5: Dodaj niestandardową grupę zadań
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Na tym etapie tworzymy niestandardową grupę zadań i dodajemy ją do innego projektu, jeśli jeszcze jej nie ma.
## Krok 6: Usuń wszystkie grupy
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Na koniec usuwamy wszystkie grupy z drugiego projektu.

## Wniosek
Zarządzanie grupowymi zbiorami MS Project w Aspose.Tasks dla .NET jest niezbędne do efektywnego organizowania danych projektu i manipulowania nimi. Wykonując kroki opisane w tym samouczku, możesz skutecznie obsługiwać grupy zadań i zasobów w swoich projektach, poprawiając ogólne zarządzanie projektami.
## Często zadawane pytania
### Czy Aspose.Tasks for .NET jest kompatybilny ze wszystkimi wersjami MS Project?
Aspose.Tasks dla .NET obsługuje różne wersje Microsoft Project, w tym 2003, 2007, 2010, 2013, 2016 i 2019.
### Czy mogę dostosować właściwości grupy za pomocą Aspose.Tasks dla .NET?
Tak, możesz dostosować właściwości grupy, takie jak nazwa i widoczność, używając Aspose.Tasks dla .NET.
### Czy Aspose.Tasks dla .NET oferuje kompatybilność między platformami?
Aspose.Tasks dla .NET jest przeznaczony przede wszystkim dla platformy .NET, ale można go używać w scenariuszach międzyplatformowych z .NET Core i .NET Standard.
### Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?
 Możesz uzyskać wsparcie dla Aspose.Tasks dla .NET poprzez[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks dla .NET z[strona internetowa](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
