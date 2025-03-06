---
title: Statistiken für Risikoelemente in Aspose.Tasks
linktitle: Statistiken für Risikoelemente in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Nutzen Sie die Möglichkeiten der Risikoanalyse in MS Project-Dateien mit Aspose.Tasks für .NET. Gewinnen Sie Erkenntnisse, mindern Sie Unsicherheiten und steigern Sie mühelos den Projekterfolg.
type: docs
weight: 21
url: /de/net/resource-risk-analysis/risk-item-statistics/
---
## Einführung
Möchten Sie Ihre Projektmanagementfähigkeiten mit Aspose.Tasks für .NET verbessern? Tauchen Sie mit unserem Schritt-für-Schritt-Tutorial zum Erhalten von Statistiken für Risikoelemente in MS Project-Dateien in die Welt der Risikoanalyse ein. Durch die Nutzung der leistungsstarken Funktionen von Aspose.Tasks können Sie wertvolle Einblicke in Projektunsicherheiten gewinnen und fundierte Entscheidungen treffen, um Risiken effektiv zu mindern.
## Voraussetzungen
Bevor wir uns auf diese Reise begeben, stellen Sie sicher, dass Sie über die folgenden Voraussetzungen verfügen:
1.  Aspose.Tasks für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Aspose.Tasks für .NET-Dokumentation](https://reference.aspose.com/tasks/net/). Diese Bibliothek stattet Sie mit robusten Tools für die programmgesteuerte Bearbeitung von MS Project-Dateien aus.
2. .NET-Entwicklungsumgebung: Richten Sie Ihre .NET-Entwicklungsumgebung ein, einschließlich Visual Studio oder einer anderen IDE Ihrer Wahl, um die nahtlose Integration von Aspose.Tasks in Ihre Projekte zu ermöglichen.

## Namespaces importieren
Integrieren Sie die erforderlichen Namespaces in Ihr Projekt, um die Funktionalitäten von Aspose.Tasks zu nutzen:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Schritt 1: Datenverzeichnis definieren
```csharp
String DataDir = "Your Document Directory";
```
 Stellen Sie sicher, dass Sie es ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrem Dokumentverzeichnis, in dem sich Ihre MS Project-Dateien befinden.
## Schritt 2: Konfigurieren Sie die Risikoanalyseeinstellungen
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Verstelle die`IterationsCount`Parameter basierend auf Ihren Projektanforderungen, um die Präzision der Risikoanalyse zu steuern.
## Schritt 3: MS Project-Datei laden
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Laden Sie die gewünschte MS Project-Datei in das`project` Objekt zur weiteren Analyse.
## Schritt 4: Aufgabe definieren und Risikomuster initialisieren
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
Geben Sie die Aufgabe für die Risikoanalyse an und konfigurieren Sie das Risikomuster mit geeigneten Parametern wie Verteilungstyp, optimistischer und pessimistischer Dauer und Konfidenzniveau.
## Schritt 5: Projektrisiken analysieren
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Starten Sie den Risikoanalyseprozess anhand der definierten Einstellungen und Projektdaten.
## Schritt 6: Statistiken abrufen und anzeigen
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
Rufen Sie verschiedene statistische Metriken im Zusammenhang mit Risikoelementen in der MS Project-Datei ab und zeigen Sie sie an, einschließlich Erwartungswert, Standardabweichung, Perzentilen, Mindest- und Höchstwerten.

## Abschluss
Zusammenfassend lässt sich sagen, dass die Beherrschung der Risikoanalyse in MS Project-Dateien mit Aspose.Tasks für .NET Projektmanagern und Stakeholdern eine Fülle von Möglichkeiten eröffnet. Wenn Sie unserem umfassenden Tutorial folgen, können Sie sicher durch Unsicherheiten navigieren und erfolgreiche Projektergebnisse sicherstellen.
## FAQs
### Kann ich Aspose.Tasks für erweiterte Funktionalität in andere .NET-Bibliotheken integrieren?
Absolut! Aspose.Tasks lässt sich nahtlos in verschiedene .NET-Bibliotheken integrieren, sodass Sie seine Funktionen entsprechend Ihren Projektanforderungen erweitern können.
### Gibt es eine Testversion für Aspose.Tasks für .NET?
 Ja, Sie können die Funktionen von Aspose.Tasks erkunden, indem Sie auf zugreifen[Kostenlose Testphase](https://releases.aspose.com/) auf unserer Website verfügbar.
### Wie oft werden Updates und Verbesserungen für Aspose.Tasks veröffentlicht?
Wir sind bestrebt, Aspose.Tasks kontinuierlich zu verbessern, indem wir regelmäßig Updates und Erweiterungen veröffentlichen, um sicherzustellen, dass Sie immer Zugriff auf die neuesten Funktionen und Optimierungen haben.
### Kann ich technischen Support für Aspose.Tasks erhalten?
Sicherlich! Unser engagiertes Support-Team steht Ihnen jederzeit zur Verfügung[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um Sie bei allen Fragen oder Herausforderungen zu unterstützen, auf die Sie während Ihrer Implementierungsreise stoßen könnten.
### Bieten Sie temporäre Lizenzen für kurzfristige Projekte an?
 Ja, wenn Sie Aspose.Tasks für ein kurzfristiges Projekt benötigen, können Sie unser praktisches Tool nutzen[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) Möglichkeit, Ihren Lizenzbedarf ohne langfristige Verpflichtungen zu decken.