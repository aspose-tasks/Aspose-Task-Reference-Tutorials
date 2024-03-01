---
title: Zarządzanie kolekcją zasobów projektu w Aspose.Tasks
linktitle: Zarządzanie kolekcją zasobów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać zbiorami zasobów Microsoft Project w .NET przy użyciu interfejsu API Aspose.Tasks. Zwiększ produktywność i elastyczność.
type: docs
weight: 13
url: /pl/net/resource-risk-analysis/managing-resource-collection/
---
## Wstęp
W tym samouczku przyjrzymy się, jak efektywnie zarządzać kolekcjami zasobów programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Aspose.Tasks to potężny interfejs API, który umożliwia programistom programową pracę z plikami Microsoft Project, umożliwiając bezproblemową integrację i manipulowanie danymi projektu.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
1. Znajomość C# i .NET Framework: W tym samouczku założono znajomość języka programowania C# i .NET Framework.
2. Instalacja Aspose.Tasks dla .NET: Upewnij się, że zainstalowałeś Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Konfiguracja środowiska programistycznego: Skonfiguruj środowisko programistyczne za pomocą programu Visual Studio lub innego preferowanego środowiska IDE.

## Importuj przestrzenie nazw
Zanim zaczniemy, zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Krok 1: Załaduj plik projektu
Najpierw załaduj plik Microsoft Project do obiektu projektu Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Krok 2: Dodaj pusty zasób
Następnie dodajmy do projektu pusty zasób:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Krok 3: Dodaj zasób z nazwą
Teraz dodaj do projektu zasób o określonej nazwie:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Krok 4: Dodaj zasób przed innym zasobem
Dodaj zasób o określonej nazwie przed innym zasobem na podstawie jego identyfikatora:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Krok 5: Dostęp do zasobów według identyfikatora lub UID
Dostęp do zasobów można uzyskać po ich identyfikatorze lub UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Krok 6: Drukowanie informacji o zasobach
Drukuj informacje o zasobach projektu:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Krok 7: Usuwanie zasobów
Usuń zasoby z projektu:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Wniosek
Zarządzanie kolekcjami zasobów Microsoft Project za pomocą Aspose.Tasks dla .NET zapewnia programistom solidny zestaw narzędzi do wydajnej programowej obsługi zasobów projektu. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo manipulować zasobami w swoich projektach, zwiększając produktywność i elastyczność zadań związanych z zarządzaniem projektami.
## Często zadawane pytania
### P: Czy Aspose.Tasks obsługuje pliki projektów na dużą skalę?

Odp.: Tak, Aspose.Tasks został zaprojektowany do wydajnej obsługi plików projektów na dużą skalę, oferując wysoką wydajność i niezawodność.

### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Microsoft Project?

Odp.: Aspose.Tasks obsługuje różne wersje Microsoft Project, zapewniając kompatybilność w różnych środowiskach.

### P: Czy mogę dostosować właściwości zasobów za pomocą Aspose.Tasks?

O: Oczywiście, Aspose.Tasks zapewnia szerokie możliwości dostosowywania właściwości zasobów zgodnie z konkretnymi wymaganiami projektu.

### P: Czy Aspose.Tasks obsługuje wielowątkowość dla współbieżnych operacji?

O: Tak, Aspose.Tasks obsługuje wielowątkowość, umożliwiając jednoczesne operacje na danych projektu w celu poprawy wydajności.

### P: Czy dostępna jest pomoc techniczna dla użytkowników Aspose.Tasks?

 O: Tak, użytkownicy Aspose.Tasks mogą uzyskać dostęp do pomocy technicznej za pośrednictwem forum[Tutaj](https://forum.aspose.com/c/tasks/15).