---
title: Drucken Sie Seiten, um Bilder in Aspose.Tasks zu trennen
linktitle: Drucken Sie Seiten, um Bilder in Aspose.Tasks zu trennen
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie in Aspose.Tasks für Java Seiten drucken, um Bilder zu trennen. Verbessern Sie die Projektvisualisierung mit dieser Schritt-für-Schritt-Anleitung.
weight: 22
url: /de/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Drucken Sie Seiten, um Bilder in Aspose.Tasks zu trennen

## Einführung
In diesem Tutorial führen wir Sie durch den Prozess des Druckens von Seiten zum Trennen von Bildern mit Aspose.Tasks für Java. Diese Funktionalität kann besonders nützlich sein, wenn Sie Projektlayouts oder kritische Aufgaben separat visualisieren müssen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es herunterladen unter[Hier](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java-Bibliothek: Laden Sie die Aspose.Tasks for Java-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein. Sie können es von bekommen[Hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Pakete am Anfang Ihrer Java-Datei importieren:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Schritt 1: Projektdaten laden
Laden Sie zunächst die Projektdaten aus Ihrer MPP-Datei:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Schritt 2: Legen Sie die Optionen zum Speichern von Bildern fest
Definieren Sie die Optionen zum Speichern des Bildes, einschließlich Startdatum, Enddatum, kritische Aufgaben, Legende und Gitternetzlinien:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Schritt 3: Gitterlinien anpassen
Passen Sie die Gitterlinien für das Bild an, indem Sie Typ, Farbe und Muster angeben:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Schritt 4: Bilder speichern
Speichern Sie das Projektlayout als Bilder, sowohl als einzelne Datei als auch als separate Dateien:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Abschluss
In diesem Tutorial haben wir gezeigt, wie man mit Aspose.Tasks für Java Seiten druckt, um Bilder zu trennen. Indem Sie die oben beschriebenen Schritte befolgen, können Sie Projektlayouts und kritische Aufgaben entsprechend Ihren Anforderungen effizient visualisieren.
## FAQs
### F: Kann ich das Bildformat beim Speichern von Projektlayouts anpassen?
 A: Ja, Aspose.Tasks für Java unterstützt verschiedene Bildformate wie PNG, JPEG, BMP usw. Sie können das gewünschte Format im angeben`ImageSaveOptions` Klasse.
### F: Ist Aspose.Tasks für Java mit verschiedenen Java-Entwicklungsumgebungen kompatibel?
A: Ja, Aspose.Tasks für Java ist mit den meisten Java-Entwicklungsumgebungen kompatibel, einschließlich Eclipse, IntelliJ IDEA und NetBeans.
### F: Kann ich Aspose.Tasks für Java in mein Maven- oder Gradle-Projekt integrieren?
A: Ja, Sie können Aspose.Tasks für Java problemlos in Ihr Maven- oder Gradle-Projekt integrieren, indem Sie die entsprechende Abhängigkeit in Ihrem Projekt hinzufügen`pom.xml` oder`build.gradle` Datei.
### F: Unterstützt Aspose.Tasks für Java den Export von Projektdaten in andere Formate als Bilder?
A: Ja, Aspose.Tasks für Java unterstützt den Export von Projektdaten in verschiedene Formate wie PDF, HTML, XLSX usw. und bietet so Flexibilität bei der Datenvisualisierung und Berichterstellung.
### F: Gibt es Community-Support für Aspose.Tasks für Java?
 A: Ja, Sie können auf der Community-Unterstützung finden, Fragen stellen und mit anderen Benutzern in Kontakt treten[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
