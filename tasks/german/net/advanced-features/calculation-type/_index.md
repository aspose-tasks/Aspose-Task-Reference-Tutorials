---
date: 2026-03-24
description: Lernen Sie, wie Sie die Berechnung in Aspose.Tasks für .NET festlegen,
  mit Beispielen zur Berechnung von Summenwerten, zur Definition von Berechnungsformeln
  und zur Konfiguration von Rollup‑Zusammenfassungen.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man den Berechnungstyp in Aspose.Tasks festlegt
url: /de/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Berechnungstyp in Aspose.Tasks festlegt

## Einführung

Wenn Sie **wie man Berechnungsregeln** für Aufgaben und Zusammenfassungszeilen in einer Microsoft Project‑Datei festlegen müssen, zeigt Ihnen dieses Tutorial genau das mit Aspose.Tasks für .NET. Wir gehen ein komplettes **Beispiel für den Berechnungstyp** durch, demonstrieren, wie **Zusammenfassungswerte berechnet** werden, und erklären, wie man **eine Berechnungsformel definiert** und **Rollup‑Zusammenfassung konfiguriert** für erweiterte Attribute. Am Ende können Sie einer Projektdatei eine Aufgabe hinzufügen, benutzerdefinierte Berechnungslogik festlegen und das Roll‑up‑Verhalten sicher steuern.

## Schnelle Antworten
- **Was ist der Hauptzweck?** Die Berechnung von Aufgaben‑ und Zusammenfassungswerten in einer Projektdatei zu steuern.  
- **Welche API‑Klasse wird verwendet?** `ExtendedAttributeDefinition` zusammen mit `CalculationType` und `SummaryRowsCalculationType`.  
- **Kann ich eine Formel verwenden?** Ja – setzen Sie `CalculationType = CalculationType.Formula` und geben Sie einen Formelausdruck an.  
- **Wie rolle ich Zusammenfassungswerte zusammen?** Verwenden Sie `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` und geben Sie einen `RollupType` wie `Average` an.  
- **Benötige ich eine Lizenz?** Eine gültige Aspose.Tasks‑Lizenz ist für den Produktionseinsatz erforderlich.

## Was ist Berechnungstyp und wie legt man die Berechnung fest?

`CalculationType` gibt Aspose.Tasks an, wie der Wert eines erweiterten Attributs berechnet wird. Sie können einen statischen Wert, eine Formel wählen oder die Bibliothek die Werte aus Unteraufgaben zusammenfassen lassen. Die korrekte Einstellung der Berechnung ist entscheidend, wenn das Projekt benutzerdefinierte Geschäftsregeln ohne manuelle Updates widerspiegeln soll.

## Warum den Berechnungstyp verwenden, um Zusammenfassungswerte zu berechnen?

Enthält ein Projekt Zusammenfassungsaufgaben, müssen die Zusammenfassungszeilen häufig aggregierte Daten anzeigen (z. B. Gesamtkosten, durchschnittliche Dauer). Durch die Konfiguration von **calculate summary values** über `SummaryRowsCalculationType` und `RollupType` kann Aspose.Tasks diese Aggregationen automatisch synchron halten, wenn einzelne Aufgaben geändert werden.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Grundkenntnisse in C# und dem .NET‑Framework.  
2. Visual Studio (eine aktuelle Version) auf Ihrem Rechner installiert.  
3. Aspose.Tasks für .NET‑Bibliothek installiert – Sie können sie von [hier](https://releases.aspose.com/tasks/net/) herunterladen.  
4. Zugriff auf die offizielle Aspose.Tasks für .NET‑Dokumentation zum Nachschlagen, verfügbar [hier](https://reference.aspose.com/tasks/net/).

## Namespaces importieren

Bevor Sie mit dem Beispiel beginnen, importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Schritt 1: Ein neues Projekt erstellen

Zuerst erstellen wir ein leeres `Project`‑Objekt, das unsere Aufgaben und benutzerdefinierten Attribute enthält.

```csharp
var project = new Project();
```

## Schritt 2: Eine Aufgabe zum Projekt hinzufügen

Jetzt **fügen wir Aufgabendaten** hinzu, indem wir eine einfache Aufgabe erstellen, ihr Startdatum festlegen und eine eintägige Dauer zuweisen.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Schritt 3: Berechnungstyp für ein erweitertes Attribut definieren (Formelbeispiel)

Hier erstellen wir eine erweiterte Attributdefinition, deren Wert aus einer Formel berechnet wird. Dies demonstriert ein **Beispiel für den Berechnungstyp** und zeigt, wie man **eine Berechnungsformel definiert**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Schritt 4: Berechnungstyp für Zusammenfassungszeilen definieren (Rollup‑Zusammenfassung konfigurieren)

Als Nächstes erstellen wir eine weitere erweiterte Attributdefinition, die Aspose.Tasks anweist, **Rollup‑Zusammenfassung** mit dem *Average*‑Rollup‑Typ zu **konfigurieren**. Dies ist der typische Weg, um **Zusammenfassungswerte zu berechnen** für Kosten, Arbeit oder benutzerdefinierte Felder.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Häufige Probleme & Fehlerbehebung

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Formel gibt `null` zurück | Falsche Feldreferenz in der Formel | Überprüfen Sie den Feldnamen in Klammern (z. B. `[Start]` nicht `[stARt]`). |
| Zusammenfassungszeilen zeigen 0 | `SummaryRowsCalculationType` nicht gesetzt oder falscher `RollupType` | Stellen Sie sicher, dass `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` und wählen Sie einen geeigneten `RollupType`. |
| Projekt lässt sich nach dem Hinzufügen von Attributen nicht laden | Diskrepanz zwischen Attributdefinition und Aufgabenverwendung | Fügen Sie die Attributdefinition **vorher** hinzu, bevor Sie sie einer Aufgabe zuweisen. |

## Fazit

In diesem Tutorial haben wir **wie man Berechnungsregeln** in Aspose.Tasks für .NET festlegt, von der Erstellung einer einfachen Aufgabe bis zur Definition sowohl formelbasierter als auch rollup‑basierter Berechnungstypen. Durch das Beherrschen dieser Einstellungen erhalten Sie eine feinkörnige Kontrolle über **calculate summary values** und ermöglichen umfangreichere Projektanalysen ohne manuelle Tabellenkalkulation.

## FAQ

### Q1: Was ist der Berechnungstyp in Aspose.Tasks?

A1: Der Berechnungstyp in Aspose.Tasks bestimmt, wie Werte für Aufgaben und Zusammenfassungsaufgaben innerhalb eines Projekts berechnet werden, mit Optionen wie Formel und Rollup.

### Q2: Wie lege ich den Berechnungstyp für ein erweitertes Attribut fest?

A2: Sie können den Berechnungstyp für ein erweitertes Attribut festlegen, indem Sie dessen `CalculationType`‑Eigenschaft entsprechend definieren.

### Q3: Kann ich den Berechnungstyp für Zusammenfassungszeilen in einem Projekt anpassen?

A3: Ja, Aspose.Tasks ermöglicht es Ihnen, den Berechnungstyp für Zusammenfassungszeilen anzugeben, sodass Sie die Wertberechnung an Ihre Anforderungen anpassen können.

### Q4: Gibt es verschiedene Rollup‑Typen für Berechnungen von Zusammenfassungsaufgaben?

A4: Ja, Aspose.Tasks bietet verschiedene Rollup‑Typen wie Average, Sum und Count für die Berechnung von Werten in Zusammenfassungsaufgaben.

### Q5: Wo finde ich weitere Ressourcen zu Aspose.Tasks für .NET?

A5: Sie können die Dokumentation und Community‑Support‑Foren auf der Seite [Aspose.Tasks für .NET](https://reference.aspose.com/tasks/net/) für umfassende Anleitungen und Unterstützung durchsuchen.

---

**Zuletzt aktualisiert:** 2026-03-24  
**Getestet mit:** Aspose.Tasks für .NET (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}