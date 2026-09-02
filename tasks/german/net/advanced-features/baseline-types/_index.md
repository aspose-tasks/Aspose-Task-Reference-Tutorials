---
date: 2026-04-30
description: Erfahren Sie, wie Sie Baselines festlegen und Projektbaselines effizient
  mit Aspose.Tasks für .NET manipulieren.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Verschiedene Arten von Baselines in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man eine Basislinie in Aspose.Tasks festlegt – Verschiedene Basistypen
url: /de/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verschiedene Arten von Baselines in Aspose.Tasks

## Einführung

Im Projektmanagement kann **wie man eine Baseline setzt** den Unterschied zwischen einem Projekt, das im Zeitplan bleibt, und einem, das aus dem Ruder läuft, ausmachen. Aspose.Tasks für .NET bietet eine voll ausgestattete API zum Erstellen, Aktualisieren und Vergleichen von Baselines, sodass Sie **den Projektfortschritt** gegenüber dem ursprünglichen Plan **verfolgen** können. In diesem Tutorial lernen Sie, wie Sie eine Baseline setzen, mit mehreren Baseline‑Typen arbeiten und die Daten nutzen, um den **Baseline‑vs‑Ist‑Zeitplan** Ihres Projekts zu analysieren.

## Schnelle Antworten
- **Was ist eine Baseline?** Ein Schnappschuss von Zeitplan-, Kosten‑ und Arbeitsdaten, der zu einem bestimmten Zeitpunkt im Projekt aufgenommen wird.  
- **Wie viele Baselines kann Aspose.Tasks speichern?** Bis zu 11 verschiedene Baselines pro Projekt.  
- **Warum eine Baseline setzen?** Um die tatsächliche Leistung mit dem ursprünglichen Plan zu vergleichen und Abweichungen zu identifizieren.  
- **Benötige ich eine Lizenz, um dies zu testen?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet „how to set baseline“ in Aspose.Tasks?
Eine Baseline zu setzen bedeutet, die `SetBaseline`‑Methode auf einem `Project`‑Objekt aufzurufen. Die API lässt Sie aus mehreren `BaselineType`‑Werten (Baseline, Baseline1 … Baseline10) wählen, sodass Sie historische Schnappschüsse speichern können, während das Projekt fortschreitet.

## Warum Projektbaselines verwalten?
- **Varianz messen:** Schnell erkennen, ob Aufgaben vor oder hinter dem Zeitplan liegen.  
- **Kostenkontrolle:** Baseline‑Kosten mit tatsächlichen Ausgaben vergleichen.  
- **Berichterstattung an Stakeholder:** Baseline‑Daten in PDF, XLSX oder andere Formate exportieren für klare Kommunikation.  
- **Szenario‑Planung:** Mehrere Baselines speichern, um „Was‑wenn“‑Zeitpläne zu bewerten.

## Voraussetzungen

### 1. Vertrautheit mit C# und .NET Framework
Ein grundlegendes Verständnis von C#‑Klassen, Methoden und objektorientierten Konzepten ist erforderlich.

### 2. Installation von Aspose.Tasks für .NET
Stellen Sie sicher, dass die Bibliothek zu Ihrem Projekt hinzugefügt wurde. Sie können sie von der [Aspose.Tasks‑Website](https://releases.aspose.com/tasks/net/) herunterladen oder über NuGet installieren.

### 3. Integrierte Entwicklungsumgebung (IDE)
Visual Studio (oder jede kompatible IDE) wird empfohlen, um C#‑Code zu schreiben, zu kompilieren und zu debuggen.

## Namespaces importieren

Bevor wir mit Aspose.Tasks in unserem C#‑Projekt arbeiten, müssen wir die erforderlichen Namespaces importieren, um Zugriff auf die benötigten Klassen und Methoden zu erhalten. Folgen Sie diesen Schritten:

```csharp

```

Jetzt, wo wir die Voraussetzungen eingerichtet und die notwendigen Namespaces importiert haben, tauchen wir ein in das Setzen verschiedener Baseline‑Typen mit Aspose.Tasks für .NET. Wir werden jedes Beispiel in mehrere Schritte aufteilen, um Klarheit und Verständlichkeit zu gewährleisten.

## Wie man eine Baseline in Aspose.Tasks setzt

### Schritt 1: Projektdatei laden
Zunächst müssen wir die Projektdatei laden, für die wir die Baseline setzen wollen. Dieser Schritt beinhaltet die Initialisierung eines `Project`‑Objekts und das Laden der Projektdatei. So geht's:

```csharp
var project = new Project("Project2.mpp");
```

### Schritt 2: Baseline setzen
Nachdem das Projekt geladen ist, können wir die Baseline setzen. Baselines liefern einen Schnappschuss des ursprünglichen Projektzeitplans, der als Referenzpunkt für Vergleiche dient, während das Projekt voranschreitet. Verwenden Sie die `SetBaseline`‑Methode, um die Baseline zu setzen. Zum Beispiel, um die Baseline für das gesamte Projekt zu setzen, verwenden Sie die Aufzählung `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Schritt 3: Mit Projektbaselines arbeiten
Nach dem Setzen der Baseline können Sie verschiedene Projektbaseline‑Felder nutzen, um den Projektfortschritt genau zu analysieren und zu verfolgen. Dieser Schritt beinhaltet den Zugriff auf Baseline‑Daten wie Start‑ und Enddaten, Dauer und Kosten. Hier können Sie die umfangreichen Funktionen von Aspose.Tasks nutzen, um Baseline‑Daten nach Ihren Anforderungen zu manipulieren.

## Häufige Probleme und Lösungen
- **Baseline nicht angewendet:** Stellen Sie sicher, dass die Projektdatei nach dem Aufruf von `SetBaseline` gespeichert wird. Verwenden Sie `project.Save("output.mpp");`, wenn Sie die Änderungen persistieren müssen.  
- **Konflikt bei mehreren Baselines:** Wenn Sie mehr als eine Baseline setzen, geben Sie den korrekten `BaselineType` an (z. B. `Baseline1`, `Baseline2`).  
- **Versionskonflikt:** Vergewissern Sie sich, dass die Aspose.Tasks‑DLL-Version mit der Ziel‑.NET‑Runtime übereinstimmt.

## Häufig gestellte Fragen

**F: Kann ich mehrere Baselines für ein einzelnes Projekt mit Aspose.Tasks für .NET setzen?**  
A: Ja, Aspose.Tasks ermöglicht es, bis zu 11 Baselines für ein Projekt zu setzen, was umfassende Tracking‑Möglichkeiten bietet.

**F: Ist Aspose.Tasks mit verschiedenen Projektdateiformaten kompatibel?**  
A: Absolut! Aspose.Tasks unterstützt verschiedene Projektdateiformate wie MPP, XML und MPX und sorgt so für Kompatibilität über unterschiedliche Plattformen hinweg.

**F: Wie kann ich Baseline‑Daten in meinem Projekt visualisieren?**  
A: Sie können Aspose.Tasks nutzen, um Projektdaten in gängige Dateiformate wie PDF oder XLSX zu exportieren, wodurch eine einfache Visualisierung und Weitergabe von Baseline‑Informationen ermöglicht wird.

**F: Bietet Aspose.Tasks Unterstützung für die Integration mit Projektmanagement‑Tools?**  
A: Aspose.Tasks stellt umfangreiche Dokumentation und Support‑Foren bereit, um Entwicklern bei der nahtlosen Integration seiner Funktionen in gängige Projektmanagement‑Tools und Plattformen zu helfen.

**F: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Ja, Sie können Aspose.Tasks über eine kostenlose Testversion auf der Website ausprobieren, um die Fähigkeiten selbst zu erleben.

---

**Last Updated:** 2026-04-30  
**Tested With:** Aspose.Tasks for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}