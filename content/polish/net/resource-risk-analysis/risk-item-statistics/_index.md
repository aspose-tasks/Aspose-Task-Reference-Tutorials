---
title: Statystyki dla pozycji ryzyka w Aspose.Tasks
linktitle: Statystyki dla pozycji ryzyka w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odblokuj moc analizy ryzyka w plikach MS Project za pomocą Aspose.Tasks dla .NET. Zdobądź wiedzę, łagodź niepewność i bez wysiłku prowadź do sukcesu projektu.
type: docs
weight: 21
url: /pl/net/resource-risk-analysis/risk-item-statistics/
---
## Wstęp
Czy chcesz poprawić swoje umiejętności zarządzania projektami za pomocą Aspose.Tasks dla .NET? Wejdź w dziedzinę analizy ryzyka dzięki naszemu tutorialowi krok po kroku na temat uzyskiwania statystyk dla pozycji ryzyka w plikach MS Project. Wykorzystując potężne możliwości Aspose.Tasks, możesz uzyskać bezcenny wgląd w niepewności projektu i podejmować świadome decyzje w celu skutecznego ograniczania ryzyka.
## Warunki wstępne
Zanim wyruszymy w tę podróż, upewnijmy się, że spełniliśmy następujące wymagania wstępne:
1.  Aspose.Tasks dla biblioteki .NET: Pobierz i zainstaluj bibliotekę z[Aspose.Tasks dla dokumentacji .NET](https://reference.aspose.com/tasks/net/). Ta biblioteka zapewnia solidne narzędzia do programowego manipulowania plikami MS Project.
2. Środowisko programistyczne .NET: Skonfiguruj środowisko programistyczne .NET, w tym Visual Studio lub dowolne inne wybrane IDE, aby ułatwić bezproblemową integrację Aspose.Tasks z Twoimi projektami.

## Importuj przestrzenie nazw
Włącz niezbędne przestrzenie nazw do swojego projektu, aby wykorzystać funkcjonalności Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Krok 1: Zdefiniuj katalog danych
```csharp
String DataDir = "Your Document Directory";
```
 Pamiętaj o wymianie`"Your Document Directory"` ze ścieżką do katalogu dokumentów, w którym znajdują się pliki MS Project.
## Krok 2: Skonfiguruj ustawienia analizy ryzyka
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Poprawić`IterationsCount`parametr w oparciu o wymagania projektu, aby kontrolować precyzję analizy ryzyka.
## Krok 3: Załaduj plik projektu MS
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Załaduj żądany plik MS Project do`project` obiekt do dalszej analizy.
## Krok 4: Zdefiniuj zadanie i zainicjuj wzorzec ryzyka
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Określ zadanie analizy ryzyka i skonfiguruj wzór ryzyka z odpowiednimi parametrami, takimi jak typ rozkładu, optymistyczny i pesymistyczny czas trwania oraz poziom ufności.
## Krok 5: Analiza ryzyka projektu
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Rozpocznij proces analizy ryzyka, korzystając ze zdefiniowanych ustawień i danych projektu.
## Krok 6: Pobierz i wyświetl statystyki
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Pobieraj i wyświetlaj różne metryki statystyczne związane z pozycjami ryzyka w pliku MS Project, w tym wartość oczekiwaną, odchylenie standardowe, percentyle, wartości minimalne i maksymalne.

## Wniosek
Podsumowując, opanowanie analizy ryzyka w plikach MS Project przy użyciu Aspose.Tasks dla .NET otwiera sferę możliwości dla kierowników projektów i interesariuszy. Postępując zgodnie z naszym obszernym samouczkiem, możesz śmiało pokonać niepewności, zapewniając pomyślne wyniki projektu.
## Często zadawane pytania
### Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami .NET w celu uzyskania rozszerzonej funkcjonalności?
Absolutnie! Aspose.Tasks bezproblemowo integruje się z różnymi bibliotekami .NET, umożliwiając zwiększenie jego możliwości zgodnie z wymaganiami projektu.
### Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?
 Tak, możesz poznać funkcje Aspose.Tasks, uzyskując dostęp do[bezpłatna wersja próbna](https://releases.aspose.com/) dostępne na naszej stronie internetowej.
### Jak często są wydawane aktualizacje i ulepszenia dla Aspose.Tasks?
Staramy się stale ulepszać Aspose.Tasks, okresowo publikując aktualizacje i ulepszenia, zapewniając, że zawsze masz dostęp do najnowszych funkcji i optymalizacji.
### Czy mogę uzyskać pomoc techniczną dla Aspose.Tasks?
 pewnością! Nasz oddany zespół wsparcia jest łatwo dostępny na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) aby pomóc Ci w przypadku jakichkolwiek pytań i wyzwań, które możesz napotkać na swojej drodze do wdrożenia.
### Czy oferujecie licencje tymczasowe na projekty krótkoterminowe?
 Tak, jeśli potrzebujesz Aspose.Tasks do krótkoterminowego projektu, możesz skorzystać z naszego wygodnego[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) możliwość zaspokojenia potrzeb licencyjnych bez żadnych długoterminowych zobowiązań.