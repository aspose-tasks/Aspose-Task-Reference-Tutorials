---
title: Zbieraj statystyki pozycji ryzyka projektu MS w Aspose.Tasks
linktitle: Zbieranie statystyk pozycji ryzykownych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zbierać statystyki pozycji ryzyka z plików MS Project przy użyciu Aspose.Tasks dla .NET. Zwiększ swoje możliwości zarządzania projektami.
weight: 22
url: /pl/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zbieraj statystyki pozycji ryzyka projektu MS w Aspose.Tasks

## Wstęp
W tym samouczku omówimy, jak zbierać statystyki elementów ryzyka z plików MS Project przy użyciu Aspose.Tasks dla .NET. Ta biblioteka zapewnia zaawansowane funkcje do analizy danych projektowych, w tym oceny ryzyka i analizy statystycznej.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks. Można go zdobyć z[strona pobierania](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Skonfiguruj środowisko programistyczne do programowania w platformie .NET.

## Importuj przestrzenie nazw
Zanim zaczniesz kodować, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw do swojego projektu:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Krok 1: Załaduj plik projektu
Najpierw musisz załadować plik MS Project do swojej aplikacji. Oto jak możesz to osiągnąć:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Krok 2: Zdefiniuj ustawienia analizy ryzyka
Zainicjuj ustawienia analizy ryzyka, w tym liczbę iteracji, jak pokazano poniżej:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Krok 3: Zainicjuj wzorzec ryzyka
Ustaw wzór ryzyka do analizy, określając typ rozkładu, optymistyczne i pesymistyczne wartości procentowe oraz poziom ufności:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Krok 4: Wykonaj analizę ryzyka
 Utwórz instancję`RiskAnalyzer` klasy i analizy projektu:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Krok 5: Pobierz statystyki
Pobierz statystyki pozycji ryzyka, takie jak wcześniejsze zakończenie, z wyniku analizy:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Krok 6: Wydrukuj statystyki
Iteruj statystyki i wydrukuj szczegóły:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Drukuj inne istotne statystyki...
}
```

## Wniosek
W tym samouczku nauczyliśmy się, jak używać Aspose.Tasks dla .NET do zbierania statystyk pozycji ryzyka z plików MS Project. Wykonując poniższe kroki, możesz skutecznie analizować dane projektu i oceniać potencjalne ryzyko, pomagając w lepszym podejmowaniu decyzji i zarządzaniu projektem.

## Często zadawane pytania
### P: Czy Aspose.Tasks obsługuje duże pliki MS Project?
Odp.: Tak, Aspose.Tasks jest w stanie efektywnie obsługiwać duże pliki MS Project, oferując niezawodną wydajność i skalowalność.
### P: Czy Aspose.Tasks obsługuje inne formaty plików projektów oprócz .mpp?
O: Tak, Aspose.Tasks obsługuje różne formaty plików projektów, w tym XML i MPT.
### P: Czy Aspose.Tasks nadaje się do aplikacji do zarządzania projektami na poziomie przedsiębiorstwa?
O: Oczywiście, Aspose.Tasks został zaprojektowany, aby sprostać wymaganiom aplikacji do zarządzania projektami na poziomie przedsiębiorstwa, zapewniając solidne funkcje i obszerną dokumentację.
### P: Czy mogę dostosować ustawienia analizy ryzyka w Aspose.Tasks?
O: Tak, Aspose.Tasks oferuje elastyczność w konfigurowaniu ustawień analizy ryzyka tak, aby odpowiadały konkretnym wymaganiom i scenariuszom projektu.
### P: Czy dostępna jest pomoc techniczna dla użytkowników Aspose.Tasks?
 Odp.: Tak, użytkownicy Aspose.Tasks mogą uzyskać dostęp do pomocy technicznej poprzez Aspose[fora](https://forum.aspose.com/c/tasks/15), gdzie mogą zadawać pytania, zgłaszać problemy i wchodzić w interakcje ze społecznością.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
