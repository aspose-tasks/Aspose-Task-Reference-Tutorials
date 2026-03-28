---
date: 2026-01-28
description: Erfahren Sie, wie Sie erweiterte Aufgabenattribute mit Aspose.Tasks für
  Java lesen und den Typ benutzerdefinierter Felder effizient umschalten.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Erweiterte Aufgabenattribute mit Aspose.Tasks für Java lesen
url: /de/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erweiterte Aufgabenattribute mit Aspose.Tasks für Java lesen

## Einführung
In diesem umfassenden Tutorial erfahren Sie, wie Sie **erweiterte Aufgabenattribute** aus Microsoft‑Project‑Dateien mithilfe der Aspose‑Tasks‑Bibliothek für Java auslesen. Egal, ob Sie ein Reporting‑Tool bauen, Daten synchronisieren oder einfach tiefere Einblicke in benutzerdefinierte Felder benötigen – das Beherrschen dieser Funktion ermöglicht Ihnen, jede im Projekt gespeicherte Information zu extrahieren. Wir führen Sie durch die erforderliche Einrichtung, zeigen Ihnen, wie Sie den Typ des benutzerdefinierten Feldes beim Verarbeiten von Attributen umschalten, und geben praktische Tipps, um häufige Stolperfallen zu vermeiden.

## Schnellantworten
- **Was bedeutet „erweiterte Aufgabenattribute lesen“?** Es bezieht sich auf das Extrahieren von benutzerdefinierten Feldwerten, die über die Standard‑Aufgabeneigenschaften einer Project‑Datei hinausgehen.  
- **Welche Klasse bietet Zugriff auf diese Attribute?** Die `ExtendedAttribute`‑Klasse in Aspose.Tasks.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich den Attributtyp zur Laufzeit ändern?** Ja – verwenden Sie die `switch`‑Anweisung, um **den benutzerdefinierten Feldtyp** basierend auf `CustomFieldType` zu **wechseln**.  
- **Ist das mit Java 8 und neuer kompatibel?** Absolut, die API unterstützt JDK 8+.

## Was sind erweiterte Aufgabenattribute?
Erweiterte Aufgabenattribute sind vom Benutzer definierte Felder (Text, Datum, Zahl, Flagge usw.), die die Standard‑Aufgabeneigenschaften in Microsoft Project ergänzen. Aspose.Tasks stellt sie über die `ExtendedAttribute`‑Sammlung bereit, die jedem `Task`‑Objekt zugeordnet ist, sodass Sie deren Werte programmgesteuert lesen oder ändern können.

## Warum erweiterte Aufgabenattribute lesen?
- **Vollständige Sichtbarkeit:** Gewinnen Sie Einblick in benutzerdefinierte Daten, die Stakeholder dem Zeitplan hinzugefügt haben.  
- **Automatisierung:** Befüllen Sie Dashboards, erstellen Sie benutzerdefinierte Berichte oder migrieren Sie Daten in andere Systeme, ohne manuelle Exporte.  
- **Flexibilität:** Arbeiten Sie mit jedem benutzerdefinierten Feldtyp – Text, Datum, Dauer, Kosten, Flagge – indem Sie jeden Fall angemessen behandeln.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:
- Grundkenntnisse in der Java‑Programmierung.  
- Das Java Development Kit (JDK) ist auf Ihrem Rechner installiert.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  

## Pakete importieren
Importieren Sie die notwendigen Klassen für das Aspose‑Tasks‑Projekt:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Schritt 1: Zugriff auf Aufgabe und erweiterte Attribute
Laden Sie eine Projektdatei und iterieren Sie über jede Aufgabe, um zu deren erweiterten Attributen zu gelangen:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Schritt 2: Feld‑ID und Wert‑GUID abrufen
Geben Sie die internen Bezeichner aus, die Ihnen helfen zu verstehen, welches benutzerdefinierte Feld Sie gerade bearbeiten:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Schritt 3: Wie man den benutzerdefinierten Feldtyp beim Lesen erweiterter Aufgabenattribute wechselt
Verwenden Sie eine `switch`‑Anweisung auf `CustomFieldType`, um jeden möglichen Datentyp korrekt zu verarbeiten:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Wiederholen Sie diese Schritte für jede Aufgabe in Ihrem Projekt, um jedes erweiterte Aufgabenattribut zu untersuchen und zu manipulieren.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Null‑Werte zurückgegeben** | Stellen Sie sicher, dass das benutzerdefinierte Feld in der Quell‑*.mpp‑Datei tatsächlich befüllt ist. |
| **Falscher Typ angezeigt** | Vergewissern Sie sich, dass den korrekten `CustomFieldType` in der `switch`‑Anweisung verwenden; nicht übereinstimmende Typen führen zu Standardwerten. |
| **Leistungsabfall bei großen Projekten** | Verarbeiten Sie Aufgaben in Batches oder filtern Sie nur die benötigten Aufgaben, indem Sie `project.getRootTask().getChildren().stream()` mit geeigneten Prädikaten verwenden. |

## Häufig gestellte Fragen
### Kann ich erweiterte Aufgabenattribute programmgesteuert ändern?
Ja, Sie können erweiterte Aufgabenattribute mit Aspose.Tasks für Java ändern. Weitere Details finden Sie in der Dokumentation.

### Gibt es eine Testversion?
Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Wo finde ich Support für Aspose.Tasks für Java?
Für Support besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

### Wie kann ich eine temporäre Lizenz erhalten?
Eine temporäre Lizenz erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich die Vollversion von Aspose.Tasks für Java kaufen?
Die Vollversion können Sie [hier](https://purchase.aspose.com/buy) erwerben.

---

**Zuletzt aktualisiert:** 2026-01-28  
**Getestet mit:** Aspose.Tasks Java API (neueste stabile Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}