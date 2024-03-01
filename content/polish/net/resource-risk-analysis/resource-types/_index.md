---
title: Rodzaje zasobów w Aspose.Tasks
linktitle: Rodzaje zasobów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak pracować z różnymi typami zasobów w Aspose.Tasks dla .NET, w tym zasobami pracy, materiałami i kosztami, poprzez samouczek krok po kroku.
type: docs
weight: 14
url: /pl/net/resource-risk-analysis/resource-types/
---
## Wstęp
Aspose.Tasks dla .NET to potężna biblioteka, która umożliwia programistom programową pracę z plikami Microsoft Project. Niezależnie od tego, czy zarządzasz zadaniami, zasobami czy harmonogramami, Aspose.Tasks upraszcza ten proces, udostępniając kompleksowy zestaw interfejsów API. W tym samouczku zagłębimy się w różne typy zasobów, które możesz wykorzystać w swoich projektach za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Visual Studio: Zainstaluj Visual Studio, potężne zintegrowane środowisko programistyczne (IDE) do programowania w .NET.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość C#: Zapoznaj się z C#, językiem programowania używanym do programowania .NET.

## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks dla .NET:
```csharp
    
```

## Krok 1: Utwórz nową instancję projektu
```csharp
var project = new Project();
```
Ta linia inicjuje nowy obiekt Project, który służy jako kontener dla wszystkich danych i operacji związanych z projektem.
## Krok 2: Dodaj zasób pracy
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Tutaj tworzymy nowy zasób pracy o nazwie „Zasób pracy” i określamy jego typ jako ResourceType.Work.
## Krok 3: Dodaj zasób materiałowy
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
W tym kroku dodaje się zasób materiałowy o nazwie „Zasób materiałowy” z typem ustawionym na ResourceType.Material. Dodatkowo na etykiecie materiału podajemy „kg”, aby wskazać jednostkę miary.
## Krok 4: Dodaj zasób kosztowy
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Na koniec dodajemy zasób kosztowy o nazwie „Zasób kosztowy” i ustawiamy jego typ jako ResourceType.Cost. Dodatkowo ustaliliśmy wartość kosztu na 59,99, reprezentującą wartość pieniężną powiązaną z tym zasobem.

## Wniosek
W tym samouczku omówiliśmy, jak pracować z różnymi typami zasobów w Aspose.Tasks dla .NET, w tym zasobami pracy, materiałów i kosztów. Postępując zgodnie z przewodnikiem krok po kroku, możesz efektywnie i programowo zarządzać zasobami w swoich projektach.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla .NET z innymi formatami oprogramowania do zarządzania projektami?
O: Tak, Aspose.Tasks obsługuje różne formaty, w tym Microsoft Project (MPP), Primavera P6 i inne.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać pomoc techniczną dla Aspose.Tasks dla .NET?
 O: Możesz odwiedzić forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15) za pomoc techniczną.
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla .NET?
 Odpowiedź: Tak, możesz kupić licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Czy Aspose.Tasks dla .NET udostępnia dokumentację w celach informacyjnych?
 Odp.: Tak, możesz znaleźć dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).