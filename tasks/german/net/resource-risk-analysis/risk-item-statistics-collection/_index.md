---
title: Sammeln Sie MS Project-Risikoelementstatistiken in Aspose.Tasks
linktitle: Sammlung von Risikoelementstatistiken in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Risikoelementstatistiken aus MS Project-Dateien sammeln. Erweitern Sie Ihre Projektmanagementfähigkeiten.
weight: 22
url: /de/net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sammeln Sie MS Project-Risikoelementstatistiken in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für .NET Risikoelementstatistiken aus MS Project-Dateien sammeln. Diese Bibliothek bietet leistungsstarke Funktionen zur Analyse von Projektdaten, einschließlich Risikobewertung und statistischer Analyse.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie. Sie erhalten es von der[Download-Seite](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung für die .NET-Programmierung ein.

## Namespaces importieren
Bevor Sie mit dem Codieren beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Schritt 1: Laden Sie die Projektdatei
Zuerst müssen Sie die MS Project-Datei in Ihre Anwendung laden. So können Sie es erreichen:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Schritt 2: Definieren Sie die Risikoanalyseeinstellungen
Initialisieren Sie die Risikoanalyseeinstellungen, einschließlich der Anzahl der Iterationen, wie unten gezeigt:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Schritt 3: Initialisieren Sie ein Risikomuster
Richten Sie ein Risikomuster für die Analyse ein und geben Sie dabei den Verteilungstyp, optimistische und pessimistische Prozentsätze sowie das Konfidenzniveau an:
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
## Schritt 4: Führen Sie eine Risikoanalyse durch
 Instanziieren Sie die`RiskAnalyzer` Unterrichten und analysieren Sie das Projekt:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Schritt 5: Statistiken abrufen
Rufen Sie die Risikoelementstatistiken, z. B. vorzeitiges Ende, aus dem Analyseergebnis ab:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Schritt 6: Statistiken drucken
Durchlaufen Sie die Statistiken und drucken Sie die Details aus:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Weitere relevante Statistiken drucken...
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Aspose.Tasks für .NET verwendet, um Risikoelementstatistiken aus MS Project-Dateien zu sammeln. Wenn Sie diese Schritte befolgen, können Sie Projektdaten effektiv analysieren und potenzielle Risiken bewerten, was zu einer besseren Entscheidungsfindung und einem besseren Projektmanagement beiträgt.

## FAQs
### F: Kann Aspose.Tasks große MS Project-Dateien verarbeiten?
A: Ja, Aspose.Tasks ist in der Lage, große MS Project-Dateien effizient zu verarbeiten und bietet zuverlässige Leistung und Skalierbarkeit.
### F: Unterstützt Aspose.Tasks neben .mpp auch andere Projektdateiformate?
A: Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate, einschließlich XML und MPT.
### F: Ist Aspose.Tasks für Projektmanagementanwendungen auf Unternehmensebene geeignet?
A: Absolut, Aspose.Tasks ist darauf ausgelegt, die Anforderungen von Projektmanagementanwendungen auf Unternehmensebene zu erfüllen und robuste Funktionen und umfangreiche Dokumentation bereitzustellen.
### F: Kann ich die Risikoanalyseeinstellungen in Aspose.Tasks anpassen?
A: Ja, Aspose.Tasks bietet Flexibilität bei der Konfiguration von Risikoanalyseeinstellungen, um sie an Ihre spezifischen Projektanforderungen und -szenarien anzupassen.
### F: Ist technischer Support für Aspose.Tasks-Benutzer verfügbar?
 A: Ja, Aspose.Tasks-Benutzer können über Aspose auf technischen Support zugreifen[Foren](https://forum.aspose.com/c/tasks/15), wo sie Fragen stellen, Probleme melden und mit der Community interagieren können.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
