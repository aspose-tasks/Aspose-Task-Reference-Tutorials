---
date: 2026-09-30
description: Erfahren Sie, wie Sie eine erweiterte Aufgabeneigenschaft mit Aspose.Tasks
  für Java erstellen, der führenden Java-Projektmanagement-Bibliothek zum Hinzufügen
  benutzerdefinierter Aufgabenfelder.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Wie man eine erweiterte Aufgabeneigenschaft mit Aspose.Tasks Java erstellt
og_description: Erfahren Sie, wie Sie eine erweiterte Aufgabeneigenschaft mit Aspose.Tasks
  für Java erstellen, der führenden Java-Projektmanagement-Bibliothek zum Hinzufügen
  benutzerdefinierter Aufgabenfelder.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Wie man eine erweiterte Aufgabeneigenschaft mit Aspose.Tasks Java erstellt
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Wie man eine erweiterte Aufgabeneigenschaft mit Aspose.Tasks Java erstellt
url: /de/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man erweiterte Aufgabenattribute mit Aspose.Tasks Java erstellt

## Einführung
In diesem Tutorial lernen Sie, wie Sie **erweiterte Aufgabenattribute** in einer Microsoft Project‑Datei mit Aspose.Tasks für Java erstellen. Das Hinzufügen benutzerdefinierter Felder ermöglicht es Ihnen, projektspezifische Daten zu erfassen, die von den integrierten Spalten nicht abgedeckt werden, und bietet Ihnen eine feinere Kontrolle über Berichte und Ressourcenplanung. Am Ende der Anleitung können Sie Text‑, Lookup‑ und Dauern‑Attribute zu jeder Aufgabe hinzufügen.

## Schnelle Antworten
- **Was bedeutet „erweitertes Attribut“?** Es ist ein benutzerdefiniertes Feld, das Sie definieren und Aufgaben, Ressourcen oder Zuordnungen zuweisen.  
- **Welche Bibliothek fügt diese Fähigkeit hinzu?** Aspose.Tasks für Java, eine Java‑Projektmanagement‑Bibliothek.  
- **Benötige ich eine Lizenz, um es auszuprobieren?** Ja – eine kostenlose 30‑Tage‑Testversion ist auf der Aspose‑Website verfügbar.  
- **Kann ich Lookup‑Werte hinzufügen?** Absolut; Sie können eine Liste zulässiger Werte für Text‑ oder Dauern‑Felder bereitstellen.  
- **Ist die API mit Java 8 und höher kompatibel?** Ja, sie unterstützt Java 8+ und läuft auf allen gängigen Betriebssystemen.

## Was ist ein erweitertes Aufgabenattribut?
Ein erweitertes Aufgabenattribut ist eine benutzerdefinierte Spalte, die zusätzliche Informationen für jede Aufgabe in einer Projektdatei speichert. Es verhält sich wie ein integriertes Feld, kann jedoch jeden von Ihnen benötigten Datentyp aufnehmen, z. B. Text, Zahlen, Daten oder Dauern.

## Warum Aspose.Tasks für Java verwenden?
Aspose.Tasks unterstützt **mehr als 50 Dateiformate** und kann Projekte mit **über 10.000 Aufgaben** verarbeiten, ohne dass Microsoft Project installiert sein muss. Die Bibliothek arbeitet vollständig offline und garantiert Datenschutz sowie deterministische Leistung für Unternehmens‑Lösungen.

## Voraussetzungen
- Grundkenntnisse in Java‑Programmierung.  
- Die Aspose.Tasks für Java‑Bibliothek ist installiert. Sie können sie von der [Website](https://releases.aspose.com/tasks/java/) herunterladen.  
- Eine Java‑IDE (IntelliJ IDEA, Eclipse oder VS Code) ist auf Ihrem Rechner eingerichtet.

## Pakete importieren
Die `import`‑Anweisungen geben Ihnen Zugriff auf die Kernklassen, die Sie benötigen, wie `Project`, `ExtendedAttributeDefinition` und `ExtendedAttribute`.  

`Project` repräsentiert eine Microsoft Project‑Datei und stellt Methoden zum Lesen, Ändern und Speichern bereit.  
`ExtendedAttributeDefinition` definiert ein benutzerdefiniertes Feld, das Aufgaben, Ressourcen oder Zuordnungen zugeordnet werden kann.  
`ExtendedAttribute` ist eine Instanz einer Definition, die den tatsächlichen Wert für ein bestimmtes Objekt hält.

## Wie fügt man einem Task ein reinen Text‑erweitertes Attribut hinzu?
Um ein reines Text‑erweitertes Attribut hinzuzufügen, laden Sie zuerst das Projekt, erstellen dann eine Definition vom Typ Text, fügen sie der Projektsammlung hinzu, erstellen eine Aufgabe, instanziieren das Attribut aus der Definition, setzen dessen Textwert, binden es an die Aufgabe und speichern schließlich das Projekt.

### 1. Dokumentverzeichnis-Pfad festlegen
Specify where your source and output files live.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Neues Projekt erstellen
Instantiate a `Project` object, optionally loading an existing .mpp file.

```java
String dataDir = "Your Document Directory";
```

### 3. Erweiterte Attributdefinition vom Typ Text1 erstellen
Define the custom field as a plain‑text column named “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Definition zur Sammlung erweiterter Attribute des Projekts hinzufügen
Register the new definition so the project recognises it.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Aufgabe zum Projekt hinzufügen
Create a task that will receive the custom field.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Erweitertes Attribut aus der Attributdefinition erstellen
Generate an instance that you can bind to a specific task.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Wert dem erzeugten erweiterten Attribut zuweisen
Set the actual text you want to store, e.g., “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Erweitertes Attribut zur Aufgabe hinzufügen
Attach the attribute instance to the task’s `ExtendedAttributes` collection.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Projekt speichern
Write the updated project back to disk in the desired format.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Wie fügt man ein Text‑Attribut mit Lookup‑Option hinzu?
When adding a text attribute with a lookup, you follow the same steps as for a plain‑text attribute, but before adding the definition you populate its `LookupValues` collection with the permitted strings. These values appear as a drop‑down list in Microsoft Project, ensuring data consistency.

## Wie fügt man ein Dauern‑Attribut mit Lookup‑Option hinzu?
To add a duration attribute with a lookup, replace the `Text1` type with `Duration2` when creating the definition, then fill the `LookupValues` collection with duration strings such as “1 day”, “2 days”, etc. After the definition is added to the project, create the attribute instance, set a duration value, attach it to a task, and save the file.

## Häufige Probleme und Fehlersuche
- **Lookup‑Werte werden nicht angezeigt** – Stellen Sie sicher, dass Sie jeden Lookup‑Eintrag zur `LookupValues`‑Sammlung *vor* dem Aufruf von `project.getExtendedAttributes().add(definition)` hinzufügen.  
- **Attributwert wird nicht gespeichert** – Vergewissern Sie sich, dass Sie die `ExtendedAttribute`‑Instanz zur Aufgabe *nach* dem Setzen ihres Wertes hinzufügen.  
- **Dateigröße wächst unerwartet** – Bei sehr großen Projekten sollten Sie `project.setSaveOptions(new ProjectSaveOptions())` aufrufen, um inkrementelles Speichern zu aktivieren.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Tasks für Java lässt sich nahtlos in jedes Java‑Ökosystem integrieren, einschließlich Spring, Hibernate und Apache POI.

**Q: Ist Aspose.Tasks für Java geeignet für groß angelegte Projektmanagement‑Anwendungen?**  
A: Absolut. Die Bibliothek ist darauf ausgelegt, Projekte mit mehreren tausend Aufgaben zu verarbeiten und unterstützt Streaming, um den Speicherverbrauch gering zu halten.

**Q: Gibt es Lizenzüberlegungen bei der Verwendung von Aspose.Tasks für Java in einem kommerziellen Projekt?**  
A: Ja, Sie benötigen eine gültige kommerzielle Lizenz. Details finden Sie auf der [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: Wie kann ich Support oder Hilfe zu Aspose.Tasks für Java erhalten?**  
A: Besuchen Sie das [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) für Community‑Hilfe oder öffnen Sie ein Support‑Ticket über Ihr Aspose‑Konto.

**Q: Kann ich Aspose.Tasks für Java vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion auf der Seite [Aspose.Tasks free trial](https://releases.aspose.com/) nutzen.

---

**Zuletzt aktualisiert:** 2026-09-30  
**Getestet mit:** Aspose.Tasks für Java 24.10  
**Autor:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Verwandte Tutorials

- [Benutzerdefinierte Spalten und erweiterte Attribute im Java‑Projektmanagement](/tasks/java/project-management/extended-attributes/)
- [Erweiterte Aufgabenattribute mit Aspose.Tasks für Java lesen](/tasks/java/task-properties/extended-task-attributes/)
- [Wie man ein Projekt mit Aspose.Tasks erstellt – Neue Aufgabenattribute festlegen](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}