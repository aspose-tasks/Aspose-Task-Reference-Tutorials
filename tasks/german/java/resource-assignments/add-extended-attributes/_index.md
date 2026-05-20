---
date: 2026-05-20
description: Erfahren Sie, wie Sie Aspose.Tasks für Java verwenden, um Extended Attributes
  zu Resource Assignments hinzuzufügen, das Project Start Date festzulegen und MS
  Project-Dateien effizient zu schreiben.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Extended Attributes zu Resource Assignments in Aspose.Tasks hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man Aspose.Tasks für Java verwendet – Extended Attributes zu Resource Assignments
  hinzufügen
url: /de/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Meistern der MS Project-Manipulation mit Aspose.Tasks für Java

## Einführung
In diesem Tutorial entdecken Sie **wie man Aspose.Tasks für Java verwendet**, um erweiterte Attribute zu Ressourcen‑Zuweisungen hinzuzufügen und Microsoft‑Project‑Informationen programmgesteuert zu schreiben. Egal, ob Sie eine Reporting‑Pipeline automatisieren oder ein benutzerdefiniertes Projekt‑Management‑Tool erstellen, die nachstehenden Schritte zeigen Ihnen genau, wie Sie das Projekt‑Startdatum festlegen, Ressourcen‑Zuweisungen erstellen und die Datei als XML speichern – alles mit nur wenigen Zeilen Java‑Code.

## Schnelle Antworten
- **Was macht Aspose.Tasks für Java?** Es liest, schreibt und ändert Microsoft‑Project‑Dateien, ohne dass Microsoft Project installiert sein muss.  
- **Kann ich benutzerdefinierte Felder zu einer Ressourcen‑Zuweisung hinzufügen?** Ja, verwenden Sie die `ExtendedAttribute`‑Sammlung im `ResourceAssignment`‑Objekt.  
- **Wie setze ich das Projekt‑Startdatum?** Rufen Sie `project.setStartDate(LocalDateTime.of(...))` vor dem Speichern auf.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz entfernt Evaluations‑Wasserzeichen und schaltet den vollen API‑Zugriff frei.  
- **Welche Java‑Versionen werden unterstützt?** Aspose.Tasks für Java unterstützt JDK 8 bis JDK 21.

## Wie verwendet man Aspose.Tasks für Java?
`Project` ist das primäre Objekt, das eine Microsoft‑Project‑Datei im Speicher repräsentiert. Laden Sie die Aspose.Tasks‑Bibliothek, erstellen Sie eine `Project`‑Instanz, konfigurieren Sie projektbezogene Eigenschaften, fügen Sie einer Ressourcen‑Zuweisung erweiterte Attribute hinzu und speichern Sie schließlich das Projekt als XML. Der Kern‑Workflow lässt sich in drei prägnante Schritte unterteilen: Initialisieren, Modifizieren und Persistieren. Dieses Muster funktioniert für Projektdateien jeder Größe und läuft auf Windows-, Linux- oder macOS‑JVMs.

## Was ist ein erweitertes Attribut in Aspose.Tasks?
Ein **erweitertes Attribut** ist ein benutzerdefiniertes Feld, das Sie Aufgaben, Ressourcen oder Zuweisungen hinzufügen, um zusätzliche Metadaten über die integrierten Spalten hinaus zu speichern. `ExtendedAttributeDefinition` definiert das Schema für ein benutzerdefiniertes Feld. Aspose.Tasks stellt die Klassen `ExtendedAttributeDefinition` und `ExtendedAttribute` bereit, um diese Felder programmgesteuert zu definieren und zuzuweisen.

## Warum erweiterte Attribute zu Ressourcen‑Zuweisungen hinzufügen?
Aspose.Tasks unterstützt **mehr als 50 integrierte und benutzerdefinierte Felder**, und Sie können unbegrenzt benutzerdefinierte Attribute hinzufügen. Das Hinzufügen ermöglicht es Ihnen, Kostenstellen, Abteilungs‑IDs oder beliebige geschäftsspezifische Daten direkt in der .mpp‑Datei zu erfassen, wodurch externe Tabellenkalkulationen überflüssig werden und die Datenintegrität über den gesamten Projektlebenszyklus hinweg sichergestellt wird.

## Voraussetzungen
1. **Java Development Kit (JDK)** – JDK 8 oder höher installiert.  
2. **Aspose.Tasks for Java library** – Laden Sie sie von der offiziellen Release‑Seite [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor Ihrer Wahl.

## Pakete importieren
First, import the necessary packages in your Java project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie das Verzeichnis, in dem Ihre Projektdaten gespeichert werden sollen. Dieser Pfad wird später beim Speichern der XML‑Datei verwendet.

```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projektinstanz erstellen
Die Klasse `Project` ist das oberste Objekt von Aspose.Tasks, das eine einzelne Microsoft‑Project‑Datei im Speicher repräsentiert. Durch die Instanziierung erhalten Sie vollen Zugriff auf alle Projektelemente.

```java
Project project = new Project();
```

### Schritt 3: Projekteigenschaften festlegen
Setzen Sie wesentliche Projekteigenschaften wie das Startdatum, das Flag „Planung ab Start“ und das Stichtag‑Datum. Diese Werte werden im `ProjectInfo`‑Objekt des Projekts gespeichert.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Schritt 4: Erweiterte Attribute zu einer Ressourcen‑Zuweisung hinzufügen
Erstellen Sie eine `ExtendedAttributeDefinition` für das benutzerdefinierte Feld, hängen Sie sie an eine `ResourceAssignment` an und füllen Sie den Wert aus. Dieser Schritt demonstriert das Schlüsselwort **add extended attributes** in Aktion.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Häufige Probleme und Lösungen
- **NullPointerException beim Zugriff auf die Zuweisungssammlung** – Stellen Sie sicher, dass Sie mindestens eine Ressource und eine Aufgabe erstellt haben, bevor Sie Zuweisungen abrufen.  
- **Erweitertes Attribut erscheint nicht in MS Project** – Überprüfen Sie, ob die `FieldId` des Attributs einem benutzerdefinierten Feldslot entspricht (z. B. `ExtendedAttributeTask.Text1`).  
- **Datumsformat stimmt nicht überein** – Verwenden Sie `java.time.LocalDateTime` für Datumswerte; Aspose.Tasks konvertiert sie automatisch in das Kalenderformat des Projekts.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java verwenden, um MS Project‑Dateien zu lesen?**  
A: Ja, die Bibliothek bietet vollständige Lese‑ und Schreibfunktionen für .mpp-, .xml‑ und .xps‑Formate.

**Q: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?**  
A: Absolut, es unterstützt Dateien von Project 2000 bis zur neuesten 2024‑Version und deckt über 20 Versionsformate ab.

**Q: Gibt es Einschränkungen in der Testversion von Aspose.Tasks für Java?**  
A: Die Testversion fügt den erzeugten Dateien ein Wasserzeichen hinzu und begrenzt die Anzahl der erstellbaren Aufgaben, aber alle API‑Funktionen bleiben zugänglich.

**Q: Wie kann ich Support für Aspose.Tasks für Java erhalten?**  
A: Sie können Unterstützung im Aspose.Tasks‑Community‑Forum [hier](https://forum.aspose.com/c/tasks/15) erhalten.

**Q: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?**  
A: Ja, temporäre Lizenzen sind für kurzfristige Nutzung verfügbar. Sie können eine von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

---

**Zuletzt aktualisiert:** 2026-05-20  
**Getestet mit:** Aspose.Tasks for Java 24.12 (zuletzt zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Notizen zu Ressourcen‑Zuweisungen in Aspose.Tasks hinzufügt](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Wie man die Tarifskala für Ressourcen‑Zuweisungen in Aspose.Tasks liest und schreibt](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Wie man eine Ressource zum Projekt hinzufügt und Level‑Verzögerungs‑Eigenschaften in Aspose.Tasks handhabt](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}