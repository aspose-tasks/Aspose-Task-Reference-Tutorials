---
title: Schreiben Sie eine MPP-Projektzusammenfassung in Aspose.Tasks
linktitle: Schreiben Sie eine MPP-Projektzusammenfassung in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks MPP-Projektzusammenfassungen in Java schreiben. Projektinformationen mühelos festlegen und abrufen.
weight: 27
url: /de/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schreiben Sie eine MPP-Projektzusammenfassung in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Aspose.Tasks für Java verwenden, um MPP-Projektzusammenfassungen zu schreiben. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek für die Arbeit mit Microsoft Project-Dateien. Wenn Sie die unten beschriebenen Schritte ausführen, können Sie mithilfe dieser Bibliothek verschiedene zusammenfassende Informationen zu einem Projekt festlegen und abrufen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java: Laden Sie die Aspose.Tasks für Java-Bibliothek herunter und installieren Sie sie. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie Ihre bevorzugte IDE für die Java-Entwicklung, z. B. IntelliJ IDEA, Eclipse oder NetBeans.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihre Java-Klasse:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Schritt 1: Projekt einrichten und Zusammenfassungsinformationen definieren
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
//Initialisieren Sie ein neues Projektobjekt mit dem Pfad zu Ihrer Projektdatei
Project project = new Project(dataDir + "project.mpp");
// Legen Sie zusammenfassende Informationen zum Projekt fest
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Legen Sie das Erstellungsdatum des Projekts fest
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Legen Sie Schlüsselwörter für das Projekt fest
project.set(Prj.KEYWORDS, "MPP Aspose");
// Legen Sie das letzte gedruckte Datum des Projekts fest
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Schritt 2: Projektzusammenfassungsinformationen speichern
```java
// Speichern Sie das Projekt wieder im MPP-Format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Zeigt eine Erfolgsmeldung an
System.out.println("Process completed Successfully");
```
## Schritt 3: Lesen Sie die Informationen zur Projektzusammenfassung
```java
// Lesen von Projektzusammenfassungsinformationen
project = new Project(dataDir + "MppAspose.xml");
// Druckautor des Projekts
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Letzten Autor des Projekts drucken
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Revisionsnummer des Projekts drucken
System.out.println("Revision: " + project.get(Prj.REVISION));
// Schlüsselwörter des Projekts drucken
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Kommentare zum Projekt drucken
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Druckerstellungsdatum des Projekts
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Schlüsselwörter des Projekts (erneut) drucken
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Letztes gedrucktes Datum des Projekts drucken
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Abschluss
In diesem Tutorial haben wir behandelt, wie man MPP-Projektzusammenfassungen mit Aspose.Tasks für Java schreibt. Wenn Sie diese Schritte befolgen, können Sie verschiedene zusammenfassende Informationen zu Ihren Projektdateien effizient festlegen und abrufen. Aspose.Tasks vereinfacht die Arbeit mit Microsoft Project-Dateien in Java-Anwendungen und bietet robuste Funktionalität und Benutzerfreundlichkeit.
## FAQs
### F: Kann ich Aspose.Tasks für Java mit anderen Java-Bibliotheken verwenden?
A: Ja, Aspose.Tasks für Java kann nahtlos in andere Java-Bibliotheken integriert werden, um Ihre Projektmanagementfunktionen zu verbessern.
### F: Gibt es eine Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### F: Wie oft wird Aspose.Tasks für Java aktualisiert?
A: Aspose.Tasks für Java wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Versionen von Java und Microsoft Project-Dateien sicherzustellen.
### F: Kann ich die Projektzusammenfassungsinformationen weiter anpassen?
A: Absolut, Aspose.Tasks für Java bietet umfangreiche Optionen zum Anpassen von Projektzusammenfassungsinformationen entsprechend Ihren spezifischen Anforderungen.
### F: Wo erhalte ich Unterstützung für Aspose.Tasks für Java?
A: Sie können Unterstützung vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
