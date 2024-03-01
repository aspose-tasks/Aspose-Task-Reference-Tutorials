---
title: Lesen Sie Währungseigenschaften in Aspose.Tasks-Projekten
linktitle: Lesen Sie Währungseigenschaften in Aspose.Tasks-Projekten
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Währungsinformationen aus MS Project-Dateien extrahieren. Schritt-für-Schritt-Anleitung bereitgestellt.
type: docs
weight: 10
url: /de/java/currency-properties/read-properties/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie Aspose.Tasks für Java verwenden, um Währungseigenschaften aus Microsoft Project-Dateien zu lesen. Aspose.Tasks ist eine leistungsstarke Java-API, die es Entwicklern ermöglicht, Microsoft Project-Dokumente zu bearbeiten, ohne dass Microsoft Project installiert sein muss. Wenn Sie die unten beschriebenen Schritte befolgen, können Sie mühelos währungsbezogene Informationen extrahieren.
## Voraussetzungen
Bevor Sie mit diesem Tutorial fortfahren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java JAR: Laden Sie die Aspose.Tasks für Java-Bibliothek von herunter[Hier](https://releases.aspose.com/tasks/java/) und fügen Sie es in Ihr Java-Projekt ein.
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihre Java-Klasse:
```java
import com.aspose.tasks.*;
```
## Schritt 1: Richten Sie Ihr Projektverzeichnis ein
Richten Sie zunächst Ihr Projektverzeichnis ein, in dem sich Ihre Microsoft Project-Datei befindet. Sie können diesen Verzeichnispfad wie folgt definieren:
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem tatsächlichen Pfad zu Ihrem Projektverzeichnis.
## Schritt 2: Erstellen Sie eine Project Reader-Instanz
 Instanziieren Sie a`Project` Objekt, indem Sie den Pfad zu Ihrer Microsoft Project-Datei angeben:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Stellen Sie sicher, dass Sie es ersetzen`"project.mpp"` mit dem Namen Ihrer MS Project-Datei.
## Schritt 3: Währungseigenschaften anzeigen
Währungseigenschaften aus der Projektdatei abrufen und anzeigen:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Dieses Codesegment ruft Informationen wie Währungscode, Ziffern, Symbol und Symbolposition aus der MS Project-Datei ab und druckt sie auf der Konsole.
## Schritt 4: Prozessabschluss
Drucken Sie abschließend eine Meldung aus, die den erfolgreichen Abschluss des Vorgangs anzeigt:
```java
System.out.println("Process completed Successfully");
```
## Abschluss
In diesem Tutorial haben wir untersucht, wie man mit Aspose.Tasks für Java Währungseigenschaften aus Microsoft Project-Dateien liest. Wenn Sie die beschriebenen Schritte befolgen, können Sie mühelos programmgesteuert währungsbezogene Informationen aus Ihren Projektdateien extrahieren und so eine nahtlose Integration in Ihre Java-Anwendungen ermöglichen.
## FAQs
### F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?
A: Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project, einschließlich MPP-Dateien, die von MS Project 2003-2021 generiert wurden.
### F: Kann ich Währungseigenschaften mit Aspose.Tasks ändern?
A: Ja, mit Aspose.Tasks können Sie Währungseigenschaften in MS Project-Dateien programmgesteuert lesen und ändern.
### F: Ist Aspose.Tasks für die kommerzielle Nutzung geeignet?
 A: Ja, Aspose.Tasks ist eine kommerzielle Bibliothek für den professionellen Einsatz. Sie können eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy).
### F: Bietet Aspose.Tasks eine kostenlose Testversion an?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks nutzen[Hier](https://releases.aspose.com/).
### F: Wo kann ich Hilfe oder Unterstützung für Aspose.Tasks suchen?
 A: Sie können das Aspose.Tasks-Forum besuchen[Hier](https://forum.aspose.com/c/tasks/15) für jegliche Hilfe oder Fragen.