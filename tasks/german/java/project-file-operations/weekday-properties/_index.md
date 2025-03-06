---
title: Wochentagseigenschaften in Aspose.Tasks
linktitle: Wochentagseigenschaften in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Wochentagseigenschaften in Aspose.Tasks für Java effizient verwalten. Passen Sie ganz einfach Wochenstartdaten, Tage pro Monat und mehr an.
weight: 25
url: /de/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wochentagseigenschaften in Aspose.Tasks

## Einführung
Aspose.Tasks für Java ist eine leistungsstarke API, die es Java-Entwicklern ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project auf dem Computer installiert ist. Eine der wichtigsten Funktionen ist die Verwaltung von Wochentagseigenschaften, die es Benutzern ermöglicht, Wochenstartdaten, Tage pro Monat, Minuten pro Tag und Minuten pro Woche anzupassen. Dieses Tutorial bietet eine detaillierte Anleitung zur effektiven Nutzung dieser Funktionen.
## Voraussetzungen
Bevor Sie sich mit Aspose.Tasks für Java befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### Java Development Kit (JDK)
Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können das neueste JDK von der Oracle-Website herunterladen und installieren.
### Aspose.Tasks für Java-Bibliothek
 Laden Sie die Aspose.Tasks für Java-Bibliothek von der Website herunter und installieren Sie sie. Sie können auf den Download-Link zugreifen[Hier](https://releases.aspose.com/tasks/java/).
### Integrierte Entwicklungsumgebung (IDE)
Wählen Sie eine IDE Ihrer Wahl für die Java-Entwicklung. Beliebte Optionen sind IntelliJ IDEA, Eclipse oder NetBeans.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Aspose.Tasks-Pakete in Ihr Java-Projekt. Hier ist wie:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Lassen Sie uns nun zum besseren Verständnis das bereitgestellte Beispiel in mehrere Schritte aufteilen.
## Schritt 1: Projektdatei laden
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Dieser Schritt beinhaltet das Laden einer Projektdatei mit dem Namen „project.mpp“ aus dem angegebenen Datenverzeichnis.
## Schritt 2: Wochentagseigenschaften anzeigen
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Hier rufen wir das Startdatum der Woche, die Tage pro Monat, die Minuten pro Tag und die Minuten pro Woche des geladenen Projekts ab und drucken sie aus.
## Schritt 3: Wochentagseigenschaften festlegen
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Dieser Schritt umfasst das Erstellen einer neuen Projektinstanz und das Festlegen benutzerdefinierter Wochentagseigenschaften wie Wochenstarttag, Tage pro Monat, Minuten pro Tag und Minuten pro Woche.
## Schritt 4: Projekt speichern
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Abschließend speichern wir das geänderte Projekt mit den aktualisierten Wochentagseigenschaften als XML-Datei.
## Schritt 5: Ergebnis anzeigen
```java
System.out.println("Process completed Successfully");
```
Dieser Schritt bestätigt den erfolgreichen Abschluss des Prozesses.
## Abschluss
Die Beherrschung der Wochentagseigenschaften in Aspose.Tasks für Java ist für ein effektives Projektmanagement von entscheidender Bedeutung. Durch die Befolgung dieses Tutorials haben Sie gelernt, wie Sie Wochentagseigenschaften mühelos bearbeiten und anpassen können. Entdecken Sie weitere Dokumentationen und Beispiele, um Ihre Projektmanagementfähigkeiten zu verbessern.
## FAQs
### F: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks für Java bietet umfassende Unterstützung für die einfache Handhabung komplexer Projektstrukturen.
### F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von Microsoft Project-Dateien kompatibel?
A: Absolut, Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft Project-Dateien und gewährleistet so die plattformübergreifende Kompatibilität.
### F: Kann ich Aspose.Tasks für Java in meine vorhandenen Java-Anwendungen integrieren?
A: Ja, Aspose.Tasks für Java bietet nahtlose Integrationsmöglichkeiten, sodass Sie Ihre Java-Anwendungen mit leistungsstarken Projektmanagementfunktionen erweitern können.
### F: Bietet Aspose.Tasks für Java Dokumentation und Support?
 A: Ja, Sie können auf der Website auf umfangreiche Dokumentation und Community-Support für Aspose.Tasks für Java zugreifen[Webseite](https://releases.aspose.com/).
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java herunterladen[Webseite](https://reference.aspose.com/tasks/java/) um die Funktionen zu erkunden, bevor Sie einen Kauf tätigen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
