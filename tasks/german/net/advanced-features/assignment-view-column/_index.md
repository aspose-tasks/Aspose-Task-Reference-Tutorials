---
date: 2026-03-19
description: Erfahren Sie, wie Sie mehrere benutzerdefinierte Spalten hinzufügen und
  die Breite benutzerdefinierter Spalten formatieren, wenn Sie ein Projekt mit Aspose.Tasks
  für .NET in XML exportieren.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Mehrere benutzerdefinierte Spalten zur Zuweisungsansicht in Aspose.Tasks hinzufügen
url: /de/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mehrere benutzerdefinierte Spalten zur Zuordnungsansicht in Aspose.Tasks hinzufügen

## Einleitung

In diesem Tutorial erfahren Sie **wie Sie mehrere benutzerdefinierte Spalten** zu einer Zuordnungsansicht mit Aspose.Tasks für .NET hinzufügen können. Benutzerdefinierte Spalten ermöglichen es, zusätzliche Daten – wie Notizen, Kosten oder benutzerdefinierte Kennzeichen – direkt in exportierten Berichten anzuzeigen. Am Ende der Anleitung können Sie die Breite benutzerdefinierter Spalten formatieren, das Projekt nach XML exportieren und die Ansicht an Ihre Projektmanagement‑Bedürfnisse anpassen.

## Schnelle Antworten
- **Was kann ich erreichen?** Anzeigen beliebiger Zuordnungsdaten in benutzerdefinierten Spalten und Steuerung ihres Erscheinungsbildes.  
- **Welches Format unterstützt das?** Exportieren des Projekts nach XML (oder anderen Formaten) mit `Spreadsheet2003SaveOptions`.  
- **Benötige ich eine Lizenz?** Ja, für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Welche .NET‑Versionen funktionieren?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie viele Spalten kann ich hinzufügen?** Unbegrenzt – einfach weitere `AssignmentViewColumn`‑Instanzen erstellen.

## Was sind mehrere benutzerdefinierte Spalten?
Mehrere benutzerdefinierte Spalten sind vom Benutzer definierte Felder, die neben den Standard‑Zuordnungsspalten erscheinen, wenn ein Projekt gespeichert oder exportiert wird. Sie geben Ihnen die Flexibilität, jede Eigenschaft eines `ResourceAssignment`‑Objekts anzuzeigen, z. B. benutzerdefinierte Notizen, Kostenstellen oder berechnete Werte.

## Warum mehrere benutzerdefinierte Spalten zur Zuordnungsansicht hinzufügen?
- **Erweiterte Berichterstellung:** Projektbezogene Informationen einbeziehen, die von den integrierten Spalten nicht abgedeckt werden.  
- **Bessere Entscheidungsfindung:** Stakeholder können die genauen Daten sehen, die sie benötigen, ohne in Rohdateien zu graben.  
- **Konsistente Formatierung:** Spaltenbreite und Textumwandlung steuern für eine saubere, lesbare Ausgabe.  

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Grundkenntnisse der Programmiersprache C#.  
2. Aspose.Tasks für .NET‑Bibliothek installiert. Falls nicht, können Sie sie **[hier](https://releases.aspose.com/tasks/net/)** herunterladen.  
3. Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio.  

## Schritt-für-Schritt-Anleitung

### Schritt 1: Namespaces importieren
Importieren Sie zunächst die Namespaces, die die Klassen bereitstellen, die wir für die Arbeit mit Projekten und Visualisierungen benötigen.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Schritt 2: Projekt laden
Erstellen Sie eine `Project`‑Instanz und laden Sie eine vorhandene MPP‑Datei.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Schritt 3: Spreadsheet‑Speicheroptionen erstellen
Instanziieren Sie `Spreadsheet2003SaveOptions` – dieses Objekt ermöglicht es uns, die Zuordnungsansicht vor dem Export anzupassen.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Schritt 4: Benutzerdefinierte Spalte definieren
Erstellen Sie für jedes anzuzeigende Datenelement ein `AssignmentViewColumn`. Unten fügen wir eine **Notes**‑Spalte mit einer Breite von 200 Punkten hinzu.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tipp:** Um *mehrere* benutzerdefinierte Spalten hinzuzufügen, wiederholen Sie diesen Schritt mit unterschiedlichen Feldnamen und Delegatenlogik und fügen Sie jede Instanz zu `options.AssignmentView.Columns` hinzu.

### Schritt 5: Benutzerdefinierte Spalte zu den Optionen hinzufügen
Fügen Sie die Spalte (oder Spalten) zur `Columns`‑Sammlung der Zuordnungsansicht hinzu.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Schritt 6: Durch Zuordnungen iterieren (optional Debugging)
Sie können durch die Zuordnungen iterieren, um zu überprüfen, ob der Text der benutzerdefinierten Spalte korrekt erzeugt wird.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Schritt 7: Projekt mit benutzerdefinierten Spalten speichern
Speichern Sie schließlich das Projekt. Das Beispiel speichert nach XML, Sie können jedoch jedes unterstützte Format wählen.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Wie exportiere ich ein Projekt mit benutzerdefinierten Spalten nach XML?
Wenn Sie `project.Save` mit den konfigurierten `Spreadsheet2003SaveOptions` aufrufen, schreibt Aspose.Tasks die Projektdaten – einschließlich aller **mehreren benutzerdefinierten Spalten** – in die ausgewählte XML‑Datei. So lässt sich angereicherte Projektinformation leicht mit anderen Systemen oder Stakeholdern teilen.

## Spaltenbreite benutzerdefinierter Spalten für bessere Lesbarkeit formatieren
Der zweite Parameter des `AssignmentViewColumn`‑Konstruktors steuert die Spaltenbreite (gemessen in Punkten). Passen Sie diesen Wert an die erwartete Textmenge an. Zum Beispiel funktioniert eine Breite von **300** gut für längere Notizen, während **100** für kurze Kennzeichen ausreicht.

## Häufige Probleme und Lösungen
- **Spaltentext erscheint leer:** Stellen Sie sicher, dass der Delegat einen String zurückgibt und dass die zugrunde liegende Zuordnungseigenschaft (z. B. `Asn.NotesText`) befüllt ist.  
- **Spalten sind in der exportierten Datei nicht sichtbar:** Vergewissern Sie sich, dass `options.AssignmentView.Columns` Ihre benutzerdefinierten Spalten enthält, bevor Sie `Save` aufrufen.  
- **Breite scheint ignoriert zu werden:** Einige Exportformate haben eigene Layoutregeln; XML respektiert die Breite, aber PDF/HTML benötigen möglicherweise zusätzliche Formatierung.  

## Häufig gestellte Fragen

### F1: Kann ich mehrere benutzerdefinierte Spalten zur Zuordnungsansicht hinzufügen?
**A:** Ja, erstellen Sie einfach zusätzliche `AssignmentViewColumn`‑Objekte und fügen Sie jedes zu `options.AssignmentView.Columns` hinzu.

### F2: Gibt es vordefinierte Konverter für gängige Zuordnungsfelder?
**A:** Ja, Aspose.Tasks stellt integrierte Konverter für viele Standardfelder bereit, sodass Sie Daten leicht abrufen können, ohne eigene Delegaten zu schreiben.

### F3: Kann ich das Aussehen benutzerdefinierter Spalten anpassen, z. B. Text formatieren oder Stile anwenden?
**A:** Absolut. Neben dem Festlegen der Breite können Sie Schriftart, Ausrichtung und weitere visuelle Eigenschaften über die Stiloptionen der Spalte ändern.

### F4: Ist es möglich, Standardspalten aus der Zuordnungsansicht zu entfernen?
**A:** Sie können Standardspalten ausschließen, indem Sie sie aus der `Columns`‑Sammlung entfernen oder ihre Breite auf Null setzen.

### F5: Unterstützt Aspose.Tasks den Export von Projekten in andere Formate neben Tabellenkalkulationen mit benutzerdefinierten Spalten?
**A:** Ja, Aspose.Tasks kann in PDF, HTML, XML und viele andere Formate exportieren und dabei benutzerdefinierte Spaltendefinitionen beibehalten.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}