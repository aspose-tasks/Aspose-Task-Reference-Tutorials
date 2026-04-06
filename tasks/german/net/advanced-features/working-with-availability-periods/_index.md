---
date: 2026-04-06
description: Erfahren Sie, wie Sie Ressourcen zum Projekt hinzufügen und die Verfügbarkeitszeiträume
  von Ressourcen mit Aspose.Tasks für .NET festlegen. Schritt‑für‑Schritt‑Anleitung
  zur Verwaltung von Ressourcen‑Kalendern.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Arbeiten mit Verfügbarkeitszeiträumen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ressource zum Projekt hinzufügen und Verfügbarkeit in Aspose.Tasks festlegen
url: /de/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ressource zum Projekt hinzufügen und Verfügbarkeit in Aspose.Tasks festlegen

## Einführung

In diesem Tutorial lernen Sie **wie man eine Ressource zum Projekt hinzufügt** und anschließend deren Verfügbarkeitszeiträume mit der Aspose.Tasks .NET-Bibliothek definiert. Das Verwalten von Ressourcenkalendern ist entscheidend für realistische Projektpläne, und die nachstehenden Schritte führen Sie durch den gesamten Prozess – vom Erstellen einer Projektinstanz bis zum Ausgeben der Details jedes Zeitraums.

## Schnelle Antworten
- **Was ist das Hauptziel?** Eine Ressource zu einem Projekt hinzuzufügen und ihre Verfügbarkeitszeiträume zu konfigurieren.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für .NET.  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine kommerzielle Lizenz ist erforderlich.  
- **Unterstützte .NET-Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementierungszeit?** In der Regel unter 15 Minuten für einfache Szenarien.

## Was bedeutet „Ressource zum Projekt hinzufügen“?

Das Hinzufügen einer Ressource zu einem Projekt erstellt einen Platzhalter für eine Person, Ausrüstung oder Material, das Aufgaben zugewiesen werden kann. Sobald die Ressource existiert, können Sie **die Ressourcenkapazität festlegen**, ihren Arbeitskalender definieren und den Scheduler diese Einschränkungen berücksichtigen lassen.

## Warum Arbeitsplan und Verfügbarkeitszeiträume konfigurieren?

- **Genauere Planung:** Aufgaben werden nur dann geplant, wenn die Ressource tatsächlich frei ist.  
- **Kostenkontrolle:** Verfügbarkeitseinheiten spiegeln Teilzeitarbeit wider und helfen, Arbeitskosten korrekt zu berechnen.  
- **Ressourcenabgleich:** Die Engine kann Überbuchungen automatisch ausgleichen, wenn sie den Kalender jeder Ressource kennt.

## Voraussetzungen

1. Visual Studio (oder jede .NET‑kompatible IDE).  
2. Aspose.Tasks für .NET – Download von [hier](https://releases.aspose.com/tasks/net/).  
3. Grundkenntnisse in C#.

## Namespaces importieren

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Wie fügt man eine Ressource zum Projekt hinzu?

### Schritt 1: Erstellen einer neuen `Project`-Instanz

```csharp
var project = new Project();
```

Dieses Objekt repräsentiert die gesamte Projektdatei im Speicher.

### Schritt 2: Eine Ressource zum Projekt hinzufügen

```csharp
var resource = project.Resources.Add("Work Resource");
```

Der Aufruf erstellt eine **Ressource** mit dem Namen *Work Resource*, die Sie später Aufgaben zuweisen können.

### Schritt 3: Verfügbarkeitszeiträume definieren

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` ist eine Hilfsmethode (Implementierung nicht gezeigt), die eine Sammlung von `AvailabilityPeriod`-Objekten zurückgibt. Jeder Zeitraum gibt ein Startdatum, ein Enddatum und die Einheiten (Prozentsatz der Vollzeitkapazität) an, zu denen die Ressource verfügbar ist.

### Schritt 4: Die Zeiträume zur Ressource hinzufügen

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Hier legen wir die **Ressourcenverfügbarkeit** fest, indem wir die Sammlung durchlaufen und jeden Zeitraum zum Kalender der Ressource hinzufügen.

### Schritt 5: Verfügbarkeitsdetails anzeigen

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Die Konsolenausgabe ermöglicht es Ihnen zu überprüfen, dass die Zeiträume korrekt gespeichert wurden.

## Häufige Fallstricke & Tipps

- **Datumspräzision:** `AvailableFrom` und `AvailableTo` sind `DateTime`-Werte; stellen Sie sicher, dass sie auf Mitternacht gesetzt sind, wenn Sie ganztägige Zeiträume wünschen.  
- **Einheitenbereich:** Gültige Werte sind 0‑100 %; Werte außerhalb dieses Bereichs werfen eine Ausnahme.  
- **Überlappende Zeiträume:** Überlappende Zeiträume werden automatisch zusammengeführt, aber es ist übersichtlicher, sie getrennt zu halten.

## Häufig gestellte Fragen

### Q1: Kann ich Aspose.Tasks für .NET in kommerziellen Projekten verwenden?
A1: Ja, Aspose.Tasks für .NET kann in kommerziellen Projekten verwendet werden. Sie können eine Lizenz [hier](https://purchase.aspose.com/buy) erwerben.

### Q2: Ist ein kostenloser Testzeitraum für Aspose.Tasks für .NET verfügbar?
A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET [hier](https://releases.aspose.com/) erhalten.

### Q3: Wo finde ich die Dokumentation für Aspose.Tasks für .NET?
A3: Die Dokumentation finden Sie [hier](https://reference.aspose.com/tasks/net/).

### Q4: Wie kann ich Support für Aspose.Tasks für .NET erhalten?
A4: Sie können Support im Community-Forum [hier](https://forum.aspose.com/c/tasks/15) erhalten.

### Q5: Bieten Sie temporäre Lizenzen für Aspose.Tasks für .NET an?
A5: Ja, temporäre Lizenzen sind [hier](https://purchase.aspose.com/temporary-license/) verfügbar.

---

**Zuletzt aktualisiert:** 2026-04-06  
**Getestet mit:** Aspose.Tasks für .NET (neueste stabile Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}