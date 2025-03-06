---
title: Zarządzaj kolekcją atrybutów MS Project w Aspose.Tasks
linktitle: Zarządzanie rozszerzoną kolekcją atrybutów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać rozszerzonymi atrybutami MS Project przy użyciu Aspose.Tasks dla .NET. Bezproblemowo manipuluj atrybutami zadań, korzystając ze wskazówek krok po kroku.
weight: 12
url: /pl/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj kolekcją atrybutów MS Project w Aspose.Tasks

## Wstęp
Czy chcesz efektywnie zarządzać rozszerzonymi atrybutami MS Project za pomocą Aspose.Tasks dla .NET? W tym samouczku przeprowadzimy Cię krok po kroku przez ten proces. Zanurzmy się!
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Visual Studio: Zainstaluj Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Załaduj plik projektu
Najpierw załaduj plik MS Project, używając następującego fragmentu kodu:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Krok 2: Zadanie dostępu i atrybuty rozszerzone
Uzyskaj dostęp do określonego zadania i jego rozszerzonych atrybutów:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Krok 3: Wyczyść atrybuty rozszerzone
W razie potrzeby wyczyść istniejące rozszerzone atrybuty:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Krok 4: Utwórz rozszerzone definicje atrybutów
Utwórz definicje nowych rozszerzonych atrybutów:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Krok 5: Iteruj po rozszerzonych atrybutach zadania
Iteruj po rozszerzonych atrybutach zadania:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Krok 6: Dodaj rozszerzone atrybuty
Dodaj nowe rozszerzone atrybuty do zadania:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Krok 7: Pracuj z rozszerzonymi atrybutami
W razie potrzeby wykonaj operacje na atrybutach rozszerzonych.
## Krok 8: Usuń atrybuty rozszerzone
Usuń rozszerzone atrybuty według indeksu lub warunkowo:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Krok 9: Skopiuj atrybuty do innego zadania
Skopiuj atrybuty do innego zadania w tym samym lub innym projekcie:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Wniosek
Zarządzanie rozszerzonymi kolekcjami atrybutów MS Project staje się bezproblemowe dzięki Aspose.Tasks dla .NET. Wykonując kroki opisane w tym samouczku, możesz efektywnie obsługiwać rozszerzone atrybuty, zwiększając możliwości zarządzania projektami.
## Często zadawane pytania
### P: Czy mogę manipulować rozszerzonymi atrybutami w wielu projektach?
O: Tak, możesz kopiować rozszerzone atrybuty pomiędzy zadaniami w różnych projektach przy użyciu Aspose.Tasks dla .NET.
### P: Czy istnieją ograniczenia dotyczące liczby rozszerzonych atrybutów na zadanie?
Odp.: Aspose.Tasks dla .NET nie nakłada żadnych nieodłącznych ograniczeń na liczbę rozszerzonych atrybutów na zadanie.
### P: Czy mogę utworzyć niestandardowe rozszerzone pola atrybutów?
Odp.: Absolutnie! Aspose.Tasks dla .NET umożliwia definiowanie niestandardowych rozszerzonych pól atrybutów dostosowanych do wymagań Twojego projektu.
### P: Czy Aspose.Tasks dla .NET obsługuje odczytywanie i zapisywanie plików MS Project w różnych wersjach?
O: Tak, Aspose.Tasks dla .NET obsługuje formaty plików MS Project w różnych wersjach.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
