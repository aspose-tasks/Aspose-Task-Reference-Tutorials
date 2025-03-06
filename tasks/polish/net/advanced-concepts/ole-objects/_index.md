---
title: Praca z obiektami OLE w Aspose.Tasks
linktitle: Praca z obiektami OLE w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak wydajnie pracować z obiektami OLE w aplikacjach .NET przy użyciu Aspose.Tasks, zwiększając możliwości zarządzania projektami.
type: docs
weight: 22
url: /pl/net/advanced-concepts/ole-objects/
---
## Wstęp

Aspose.Tasks dla .NET zapewnia wszechstronną funkcjonalność do pracy z obiektami OLE (łączenie i osadzanie obiektów) w plikach projektu. Ten samouczek poprowadzi Cię przez proces efektywnego zarządzania obiektami OLE przy użyciu Aspose.Tasks w aplikacjach .NET.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Instalacja: Upewnij się, że masz zainstalowany Aspose.Tasks for .NET w swoim środowisku programistycznym. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).

2. Podstawowa wiedza: Zapoznaj się z koncepcjami języka programowania C# i platformy .NET.

3. Środowisko programistyczne: Skonfiguruj odpowiednie środowisko programistyczne, takie jak Visual Studio.

## Importuj przestrzenie nazw

Najpierw zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;


```

Podzielmy teraz każdy przykład na wiele kroków w formie przewodnika krok po kroku:

## Praca z obiektami OLE

### Krok 1: Załaduj plik projektu
```csharp
var project = new Project("TaskImage2010.mpp");
```

### Krok 2: Uzyskaj dostęp do obiektów OLE
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

### Krok 3: Iteracja po obiektach OLE
```csharp
foreach (var oleObject in oleObjects)
{
    // Uzyskaj dostęp i wydrukuj właściwości obiektu OLE
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Kontynuuj dla innych właściwości
}
```

### Krok 4: Pobierz bajty zawartości
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

## Czyszczenie obiektów OLE

### Krok 1: Załaduj plik projektu
```csharp
var project = new Project("TaskImage2010.mpp");
```

### Krok 2: Wyczyść obiekty OLE
```csharp
project.OleObjects.Clear();
```

### Krok 3: Zapisz projekt
```csharp
project.Save("ClearedProject.mpp");
```

## Uzyskiwanie właściwości rozmieszczenia obiektów wizualnych

### Krok 1: Załaduj plik projektu
```csharp
var project = new Project("TaskImage2010.mpp");
```

### Krok 2: Uzyskaj dostęp do obiektu OLE i wizualnego rozmieszczenia obiektów
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

### Krok 3: Pobierz właściwości
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Wniosek

W tym samouczku omówiliśmy, jak efektywnie pracować z obiektami OLE w Aspose.Tasks dla .NET. Postępując zgodnie z tymi przykładami krok po kroku, możesz bezproblemowo zintegrować możliwości zarządzania obiektami OLE z aplikacjami .NET, zwiększając ich funkcjonalność i użyteczność.

## Często zadawane pytania

### P1: Czy Aspose.Tasks obsługuje różne formaty obiektów OLE?

O1: Tak, Aspose.Tasks obsługuje szeroką gamę formatów obiektów OLE, w tym obrazy, dokumenty i pliki multimedialne.

### P2: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?

Odpowiedź 2: Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność i bezproblemową integrację.

### P3: Czy mogę manipulować rozmieszczeniem obiektów OLE w widokach projektu?

Odpowiedź 3: Oczywiście, Aspose.Tasks udostępnia interfejsy API do zarządzania właściwościami rozmieszczenia i wyglądu obiektów OLE w widokach projektu.

### P4: Czy Aspose.Tasks nadaje się do projektów na poziomie przedsiębiorstwa?

Odpowiedź 4: Tak, Aspose.Tasks doskonale nadaje się zarówno do projektów na małą skalę, jak i na poziomie przedsiębiorstwa, oferując solidne funkcje i niezawodną wydajność.

### P5: Czy Aspose.Tasks oferuje wsparcie klienta i zasoby dokumentacji?

Odpowiedź 5: Tak, Aspose.Tasks zapewnia obszerną dokumentację, fora i obsługę klienta, aby pomóc programistom w efektywnym wykorzystaniu jego funkcji.