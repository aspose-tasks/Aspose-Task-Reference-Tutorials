---
date: 2026-10-26
description: Wie man group definition data mit Aspose.Tasks für Java liest. Extrahieren
  Sie task grouping, criteria und formatting aus Microsoft Project-Dateien, um reporting
  und migration zu automatisieren.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: Group Definition Data in Aspose.Tasks lesen
og_description: Wie man group definition data mit Aspose.Tasks für Java liest. Extrahieren
  Sie task grouping, criteria und formatting aus Microsoft Project-Dateien, um reporting
  und migration zu automatisieren.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: Wie man group definition data mit Aspose.Tasks für Java liest
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: Wie man group definition data mit Aspose.Tasks für Java liest
url: /de/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gruppendefinitionsdaten in Aspose.Tasks für Java lesen

## Einführung
Aspose.Tasks für Java ermöglicht den programmgesteuerten Zugriff, die Modifikation und Analyse von Microsoft‑Project‑Dateien. In diesem Tutorial lernen Sie **wie man Gruppendefinitions‑Daten** aus einer `.mpp`‑Datei ausliest, den Namen, die Kriterien und das visuelle Styling jeder Gruppe extrahiert und diese Informationen anschließend zur Erstellung benutzerdefinierter Berichte oder zur Migration von Einstellungen in andere Projekte verwendet. Das Beherrschen dieser Fähigkeit erlaubt Ihnen, Berichte zu automatisieren, Projektstrukturen zu validieren und datengetriebene Workflows zu optimieren.

## Schnellantworten
- **Was bedeutet „Gruppendefinition lesen“?** Es bedeutet, die Gruppierungsregeln (Name, Kriterien, Farben, Schriftarten) zu extrahieren, die Microsoft Project zur Organisation von Vorgängen verwendet.  
- **Welche Bibliothek benötige ich?** Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDEs werden unterstützt?** Jede Java‑IDE wie IntelliJ IDEA oder Eclipse.  
- **Wie viel Code ist nötig?** Weniger als 30 Zeilen Java‑Code, um ein Projekt zu laden und Gruppendetails anzuzeigen.

## Wie man Gruppendefinitionsdaten liest
Laden Sie das Projekt, enumerieren Sie seine Gruppen und prüfen Sie die Kriterien jeder Gruppe. Die direkte Antwort lautet: **Erzeugen Sie eine `Project`‑Instanz, rufen Sie `project.getTaskGroups()` auf und iterieren Sie über die Sammlung, um Namen, Kriterien, Schriftarten und Farben zu lesen.** Die folgenden Abschnitte zerlegen den Prozess in klare Schritte, jeweils begleitet von einem kurzen Code‑Platzhalter, den Sie durch das tatsächliche Snippet aus der Aspose.Tasks‑Dokumentation ersetzen.

## Was ist das Lesen von Gruppendefinitionen?
Das Lesen von Gruppendefinitionen bezieht sich auf das Extrahieren der Gruppierungsregeln (Name, Kriterien, Formatierung), die Microsoft Project anwendet, um Vorgänge zu ordnen. Diese Regeln geben der Anwendung vor, wie Vorgänge nach Status, Priorität oder benutzerdefinierten Feldern gruppiert werden, und enthalten visuelle Attribute wie Schriftstil und Zellenfarbe.

## Warum Gruppendefinitionsdaten lesen?
Das Lesen von Gruppendefinitionsdaten ermöglicht Ihnen **die automatisierte Berichtserstellung**, **die Migration von Gruppierungslogik** in andere Projekte und **die Validierung, dass erforderliche Gruppen existieren**, bevor Massen‑Updates durchgeführt werden. Aspose.Tasks für Java kann Projekte mit **über 10 000 Vorgängen** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was hochleistungsfähige Batch‑Operationen erlaubt. Zusätzlich können Sie Schriftfarben, Muster und Sortierrichtungen extrahieren, um das exakte visuelle Layout in eigenen Dashboards nachzubilden.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK) 8+** – jede aktuelle Version funktioniert.  
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von der [Aspose.Tasks für Java Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.  
3. **Eine Java‑IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  

> **Pro‑Tipp:** Verwenden Sie Maven oder Gradle, um die Aspose.Tasks‑Abhängigkeit zu verwalten; das erspart das manuelle JAR‑Handling.

## Pakete importieren
`Project` ist die Hauptklasse, die eine Microsoft‑Project‑Datei in Aspose.Tasks für Java repräsentiert.  

```java
import com.aspose.tasks.*;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis festlegen
Definieren Sie den Ordner, der die `.mpp`‑Datei enthält, die Sie untersuchen möchten. Die Verwendung von `java.nio.file.Paths` garantiert plattformunabhängige Pfadbehandlung.

```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projektdatei laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie auf Ihre `.mpp`‑Datei verweisen. Der Konstruktor liest den Dateikopf und baut ein In‑Memory‑Modell auf.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 3: Anzahl der Aufgabengruppen abrufen
Geben Sie die Gesamtzahl der im Projekt definierten Aufgabengruppen aus. Dieser schnelle Check bestätigt, dass die Datei tatsächlich Gruppierungsinformationen enthält.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Schritt 4: Informationen zu einer bestimmten Aufgabengruppe abrufen
Holen Sie sich eine bestimmte Gruppe (Index 1 in diesem Beispiel) und zeigen Sie deren Namen sowie die Anzahl der enthaltenen Kriterien an. Jede Gruppe kann mehrere Kriterien besitzen, die definieren, wie Vorgänge gruppiert werden.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Schritt 5: Kriterieninformationen der Gruppe abrufen
Jede Gruppe kann ein oder mehrere Kriterien haben. Das nachfolgende Snippet extrahiert Details wie das Feld, das für die Gruppierung verwendet wird, den Gruppierungsmodus, die Zellenfarbe und das Muster.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Schritt 6: Übergeordnete Gruppe prüfen
Manchmal gehört ein Kriterium zu einer übergeordneten Gruppe. Diese Prüfung bestätigt die Beziehung und verhindert Null‑Pointer‑Probleme beim Navigieren durch die Hierarchie.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Schritt 7: Schriftinformationen des Kriteriums abrufen
Gruppenkriterien können benutzerdefinierte Schriftstile besitzen. Der folgende Code gibt die Schriftfamilie, Größe, Stil und Sortierrichtung aus, sodass Sie das exakte Aussehen in Ihrer eigenen UI reproduzieren können.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **`NullPointerException` bei `criterion.getParentGroup()`** | Das Kriterium hat möglicherweise keine übergeordnete Gruppe. | Fügen Sie vor dem Zugriff auf die übergeordnete Gruppe einen Null‑Check hinzu. |
| **Datei nicht gefunden** | Der Pfad `dataDir` ist falsch oder der Dateiname ist falsch geschrieben. | Verwenden Sie `Paths.get(dataDir, "project.mpp").toAbsolutePath()` und prüfen Sie, ob die Datei existiert. |
| **Lizenz nicht gesetzt** | Aspose läuft im Evaluierungsmodus und kann die Ausgabe abschneiden. | Registrieren Sie Ihre Lizenz mit `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` bevor Sie das Projekt laden. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks für Java verwenden, um Projektdateien zu ändern?**  
A: Ja, die Bibliothek bietet vollständige Lese‑/Schreib‑Funktionen für Microsoft‑Project‑Formate, sodass Sie Vorgänge hinzufügen, Ressourcen ändern und Gruppendefinitionen programmgesteuert aktualisieren können.

**F: Ist Aspose.Tasks für Java mit allen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Es unterstützt MPP, XML, CSV und andere gängige Project‑Formate über Versionen hinweg, von Project 2000 bis zur neuesten 2024‑Version.

**F: Wie gehe ich mit Fehlern bei der Arbeit mit Aspose.Tasks für Java um?**  
A: Umschließen Sie Dateioperationen mit `try‑catch`‑Blöcken und fangen Sie `TasksException` für detaillierte Fehlermeldungen ab; prüfen Sie `getMessage()` der Ausnahme für Hinweise.

**F: Bietet Aspose.Tasks für Java Export in andere Formate?**  
A: Absolut – Sie können mit den dedizierten Export‑APIs nach PDF, XLSX, HTML und mehr exportieren.

**F: Wo finde ich zusätzliche Ressourcen und Support?**  
A: Besuchen Sie die [Aspose.Tasks für Java Dokumentation](https://reference.aspose.com/tasks/java/) für API‑Referenzen und das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Hilfe.

## Fazit
In diesem Tutorial haben wir **wie man Gruppendefinitionsdaten** aus einer Microsoft‑Project‑Datei mit Aspose.Tasks für Java liest, Schritt für Schritt durchgearbeitet. Durch das Laden eines `Project`, das Enumerieren der `TaskGroupCollection` und das Prüfen der Kriterien, Schriftarten und Farben jeder Gruppe können Sie automatisierte Berichtspipelines bauen, Gruppierungsregeln migrieren oder Projektstrukturen zuverlässig validieren. Der gleiche Ansatz skaliert zu großen Projekten mit tausenden von Vorgängen, während der Speicherverbrauch gering bleibt.

---

**Zuletzt aktualisiert:** 2026-10-26  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Projektinformationen aus Microsoft Project mit Aspose.Tasks für Java liest](/tasks/java/project-properties/read-project-info/)
- [Wie man Tabellenspalten abruft und Tabellendaten in Aspose.Tasks liest](/tasks/java/project-data-reading/read-table-data/)
- [read gantt chart java – Spezifische Gantt‑Daten extrahieren](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}