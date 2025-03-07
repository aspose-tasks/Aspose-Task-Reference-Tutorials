---
title: Bestimmen Sie die MS Project-Version mit Aspose.Tasks
linktitle: Bestimmen Sie die Projektversion mit Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie die Version von MS Project-Dateien programmgesteuert mit Aspose.Tasks für Java ermitteln. Schritt-für-Schritt-Anleitung mit Codebeispielen.
weight: 12
url: /de/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestimmen Sie die MS Project-Version mit Aspose.Tasks

## Einführung
Dieses Tutorial führt Sie Schritt für Schritt durch die Verwendung von Aspose.Tasks für Java, um die Version einer MS Project-Datei zu ermitteln. Aspose.Tasks ist eine leistungsstarke Java-API, die es Entwicklern ermöglicht, Microsoft Project-Dateien zu bearbeiten, ohne dass Microsoft Project installiert sein muss.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks for Java JAR-Datei: Laden Sie die Aspose.Tasks for Java-Bibliothek von herunter[Webseite](https://releases.aspose.com/tasks/java/) und fügen Sie es Ihrem Java-Projekt hinzu.
3. MS Project-Datei: Bereiten Sie eine MS Project-Datei (XML-Format) zum Testen vor.

## Pakete importieren
Bevor wir uns mit dem Code befassen, importieren wir die erforderlichen Pakete:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Schritt 1: Richten Sie das Projekt ein
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu dem Verzeichnis, das Ihre MS Project-Datei enthält.
## Schritt 2: Laden Sie das Projekt
```java
Project project = new Project(dataDir + "input.xml");
```
 Ersetzen`"input.xml"` mit dem Namen Ihrer MS Project-Datei.
## Schritt 3: Projektversion ermitteln
```java
//Projektversionseigenschaft anzeigen
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Dieser Codeausschnitt ruft die Version und das letzte Speicherdatum der MS Project-Datei ab und druckt sie aus.
## Schritt 4: Ergebnis anzeigen
```java
//Ergebnis der Konvertierung anzeigen.
System.out.println("Process completed Successfully");
```
Diese Zeile zeigt den Abschluss des Prozesses an.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Tasks für Java die Version einer MS Project-Datei ermitteln. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie effizient und problemlos mit MS Project-Dateien in Ihren Java-Anwendungen arbeiten.

## FAQs
### F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
A: Ja, Aspose.Tasks unterstützt mehrere Programmiersprachen, darunter .NET, Java und C++.
### F: Ist Aspose.Tasks für Großprojekte geeignet?
A: Absolut, Aspose.Tasks ist für die problemlose Abwicklung von Projekten jeder Größe konzipiert.
### F: Kann ich Projektdaten mit Aspose.Tasks anpassen?
A: Ja, Sie können mit Aspose.Tasks Projektdaten bearbeiten, Aufgaben, Ressourcen ändern und vieles mehr.
### F: Erfordert Aspose.Tasks die Installation von Microsoft Project?
A: Nein, Aspose.Tasks funktioniert unabhängig und erfordert keine Installation von Microsoft Project.
### F: Ist technischer Support für Aspose.Tasks verfügbar?
 A: Ja, Sie können technischen Support im Aspose.Tasks-Forum unter erhalten[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
