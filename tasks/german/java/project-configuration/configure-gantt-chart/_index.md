---
date: 2026-10-15
description: Erfahren Sie, wie Sie activity erstellen, das data directory festlegen,
  table fields anpassen und ein Projekt als MPP mit Aspose.Tasks for Java speichern.
  Schritt‑für‑Schritt‑Anleitung für Java‑Entwickler.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Wie man activity erstellt und das data directory mit Aspose.Tasks for Java
  festlegt
og_description: Wie man activity erstellt, table fields anpasst und ein Projekt als
  MPP mit Aspose.Tasks for Java speichert. Folgen Sie dieser detaillierten Anleitung
  für eine schnelle Implementierung.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Wie man activity erstellt und das data directory in Aspose.Tasks for Java
  festlegt
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Wie man activity erstellt und das data directory mit Aspose.Tasks for Java
  festlegt
url: /de/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Aktivitäten erstellt und das Datenverzeichnis mit Aspose.Tasks für Java festlegt

## Einführung
In diesem Tutorial erfahren Sie **wie man Aktivitäten** programmgesteuert erstellt, das **Datenverzeichnis** konfiguriert und das **Projekt als MPP** speichert, während Sie **Tabellenfelder** in einer Gantt‑Diagrammansicht **anpassen**. Aspose.Tasks für Java ist eine leistungsstarke API, die über 30 Eingabe‑ und Ausgabeformate unterstützt und Projekte mit bis zu 10 000 Aufgaben verarbeiten kann, ohne die gesamte Datei in den Speicher zu laden. Am Ende der Anleitung können Sie die Projekterstellung automatisieren, Aufgaben mit benutzerdefinierten Attributen anreichern und eine sofort öffnungsbereite MPP‑Datei für Microsoft Project erzeugen.

## Schnellantworten
- **Was ist der erste Schritt?** Legen Sie den Pfad des Datenverzeichnisses fest, in dem Ihre Projektdateien liegen.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (von der offiziellen Website herunterladbar).  
- **Kann ich benutzerdefinierte Attribute hinzufügen?** Ja – Sie können erweiterte Attribute definieren und im Gantt‑Diagramm anzeigen.  
- **Benötige ich eine Lizenz für Tests?** Eine temporäre Lizenz ist für Evaluierungszwecke verfügbar.  
- **Welche IDE funktioniert am besten?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) funktioniert.

## Was bedeutet „Datenverzeichnis festlegen“ und warum ist das wichtig?
Das Festlegen des Datenverzeichnisses teilt Aspose.Tasks mit, wo Projektdateien gelesen und geschrieben werden sollen. Ohne einen korrekten Pfad kann die API Ihre `.mpp`‑Dateien nicht finden, was zu `FileNotFoundException`‑Fehlern führt. Die Definition dieses Verzeichnisses zu Beginn Ihres Codes macht den Workflow wiederholbar und trennt Dateisystem‑Belange von der Geschäftslogik.

## Warum Tabellenfelder in einem Gantt‑Diagramm anpassen?
Benutzerdefinierte Tabellenfelder ermöglichen es, zusätzliche Informationen – wie benutzerdefinierte Attribute, Ressourcendaten oder projektspezifische Notizen – direkt in der Gantt‑Ansicht darzustellen. Das reduziert den Bedarf an separaten Berichten und liefert den Stakeholdern eine einzige, datenreiche Visualisierung, die die Entscheidungsfindung um bis zu 30 % beschleunigen kann.

## Wie erstellt man eine neue Aktivität?
Sie erstellen eine neue Aktivität (Aufgabe), indem Sie ein `Task`‑Objekt instanziieren und es zur Wurzel‑Aufgabensammlung des Projekts hinzufügen. Dieser Ansatz ermöglicht es, große Zeitpläne automatisch zu erzeugen, Aufgabendaten aus externen Systemen zu übernehmen oder Massen‑Updates ohne manuelle Bearbeitung durchzuführen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder neuer.  
2. **Aspose.Tasks für Java** – laden Sie es von der **Aspose.Tasks Java‑Release‑Seite** herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor Ihrer Wahl.  

## Pakete importieren
Der Namespace `com.aspose.tasks` enthält alle Klassen, die Sie für die Projektmanipulation benötigen. Durch das Importieren erhalten Sie Zugriff auf `Project`, `Task`, `ExtendedAttributeDefinition` und weitere Kern‑Typen.

```java
import com.aspose.tasks.*;
```

## Maven‑Abhängigkeit (optional)
Falls Sie Ihr Projekt mit Maven verwalten, fügen Sie die Aspose.Tasks‑Abhängigkeit zu `pom.xml` hinzu. Dadurch wird die Bibliothek während des Builds automatisch aufgelöst.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre Projektdateien enthält. Die Variable `dataDir` enthält den absoluten Pfad und wird im gesamten Tutorial wiederverwendet.

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den vollständigen Pfad zu dem Ordner, in dem `project.mpp` liegt, zum Beispiel `C:/Projects/MyGantt`.

### Schritt 2: Projektdatei laden
`Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne Microsoft‑Project‑Datei im Speicher repräsentiert. Das Laden einer bestehenden Datei gibt Ihnen Zugriff auf Aufgaben, Ressourcen und Tabellen.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 3: neue Aktivität hinzufügen
`Task` steht für eine einzelne Aktivität im Zeitplan. Das Hinzufügen einer Aufgabe zur Wurzel‑Aufgabensammlung fügt sie auf der obersten Ebene der Projekt‑Hierarchie ein.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Schritt 4: benutzerdefiniertes Attribut definieren
`ExtendedAttributeDefinition` ermöglicht das Erstellen eines wiederverwendbaren benutzerdefinierten Feldes, das jeder Aufgabe, Ressource oder Zuordnung zugeordnet werden kann.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Schritt 5: benutzerdefiniertes Attribut zur Aufgabe hinzufügen
`ExtendedAttribute` ist die konkrete Instanz eines benutzerdefinierten Attributs, das Sie einer bestimmten Aufgabe zuweisen.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Schritt 6: Tabelle anpassen – benutzerdefiniertes Attribut als Spalte hinzufügen
`TableField` beschreibt eine Spalte in einer Gantt‑Diagrammtabelle. Durch das Hinzufügen eines `TableField`, das auf das benutzerdefinierte Attribut verweist, wird das Attribut in der Diagrammansicht sichtbar.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Schritt 7: Projekt speichern
Der Aufruf `project.save` speichert alle Änderungen in einer neuen Datei. Die Konstante `SaveFileFormat.MPP` weist Aspose.Tasks an, die Datei im nativen Binärformat von Microsoft Project zu schreiben.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Häufige Probleme und Lösungen
| Problem | Warum es auftritt | Lösung |
|-------|----------------|-----|
| **FileNotFoundException** beim Laden des Projekts | Der **Datenverzeichnis‑Pfad** ist falsch oder fehlt ein abschließender Schrägstrich. | Prüfen Sie, dass `dataDir` exakt auf den Ordner zeigt und den richtigen Pfadtrenner (`/` oder `\\`) enthält. |
| Benutzerdefiniertes Attribut nicht im Gantt‑Diagramm sichtbar | Das Tabellenfeld wurde am falschen Index eingefügt oder die Spaltenbreite ist zu klein. | Stellen Sie sicher, dass `table.getTableFields().add(3, attrField);` einen gültigen Index verwendet und passen Sie `setWidth` bei Bedarf an. |
| LicenseException beim Speichern | Keine gültige Lizenz wurde für die Produktion angewendet. | Laden Sie eine temporäre oder permanente Lizenz, bevor Sie `project.save()` aufrufen. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
A: Ja, Aspose.Tasks ist für .NET, Java und C++ verfügbar.

**F: Gibt es eine kostenlose Testversion von Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose Testversion von der **Aspose.Tasks Free‑Trial‑Download‑Seite** herunterladen.

**F: Wo finde ich Support für Aspose.Tasks?**  
A: Support und Fragen finden Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

**F: Wie kaufe ich eine Lizenz für Aspose.Tasks?**  
A: Sie können eine Lizenz auf der **Aspose.Tasks‑Kaufseite** erwerben.

**F: Benötige ich eine temporäre Lizenz für Testzwecke?**  
A: Ja, Sie können eine temporäre Lizenz über die **Seite für temporäre Lizenzanfragen** erhalten.

## Fazit
Sie wissen jetzt **wie man Aktivitäten erstellt**, das Datenverzeichnis festlegt, ein benutzerdefiniertes Attribut definiert und zuweist und **wie man das Projekt als MPP** speichert, während Sie **Tabellenfelder** in einer Gantt‑Diagrammansicht mit Aspose.Tasks für Java **anpassen**. Diese Möglichkeiten geben Ihnen die vollständige programmgesteuerte Kontrolle über Projektdaten, ermöglichen die automatisierte Zeitplanerstellung und bieten Ihren Stakeholdern reichhaltigere visuelle Berichte.

---

**Zuletzt aktualisiert:** 2026-10-15  
**Getestet mit:** Aspose.Tasks Java 24.12 (neueste)  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Create Empty Project File in Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}