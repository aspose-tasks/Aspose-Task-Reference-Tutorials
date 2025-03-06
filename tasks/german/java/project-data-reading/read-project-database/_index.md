---
title: Lesen von Projektdaten aus der MS Project-Datenbank in Aspose.Tasks
linktitle: Lesen von Projektdaten aus der Microsoft Project-Datenbank in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Projektdaten aus der Microsoft Project-Datenbank lesen. Schritt-für-Schritt-Anleitung mit Codebeispielen.
weight: 12
url: /de/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lesen von Projektdaten aus der MS Project-Datenbank in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java Projektdaten aus einer Microsoft Project-Datenbank lesen. Aspose.Tasks ist eine leistungsstarke Java-API, die es Entwicklern ermöglicht, Microsoft Project-Dokumente zu bearbeiten, ohne dass Microsoft Project installiert sein muss. Indem Sie die in diesem Leitfaden beschriebenen Schritte befolgen, erfahren Sie, wie Sie Projektdaten effizient aus einer Datenbank extrahieren und im gewünschten Format speichern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundkenntnisse der Java-Programmierung.
2. Java Development Kit (JDK) auf Ihrem System installiert.
3. Aspose.Tasks für Java-Bibliothek heruntergeladen und in Ihrem Projekt konfiguriert.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## Schritt 1: Datenbankverbindung einrichten
Zunächst müssen Sie die Verbindung zur Microsoft Project-Datenbank einrichten. Dazu gehört die Angabe der Datenbank-URL, des Servernamens, der Portnummer, des Datenbanknamens, des Benutzernamens und des Passworts.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Schritt 2: JDBC-Treiber hinzufügen
Als Nächstes müssen Sie den JDBC-Treiber zu Ihrem Projekt hinzufügen. Dieser Treiber erleichtert die Kommunikation zwischen Java-Anwendungen und der Microsoft SQL Server-Datenbank.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Schritt 3: Projektdaten lesen
 Erstellen Sie nun eine`Project` Objekt und laden Sie Projektdaten aus der Datenbank mit den zuvor definierten Einstellungen.
```java
Project project = new Project(settings);
```
## Schritt 4: Projektdaten speichern
Abschließend speichern Sie die Projektdaten im gewünschten Format. In diesem Beispiel speichern wir es als XML-Datei.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Glückwunsch! Sie haben mit Aspose.Tasks für Java erfolgreich Projektdaten aus einer Microsoft Project-Datenbank gelesen.

## Abschluss
In diesem Tutorial haben wir den Prozess des Lesens von Projektdaten aus einer Microsoft Project-Datenbank mit Aspose.Tasks für Java behandelt. Indem Sie die beschriebenen Schritte befolgen, können Sie Projektinformationen nahtlos extrahieren und entsprechend Ihren Anforderungen bearbeiten. Aspose.Tasks vereinfacht die Handhabung von Microsoft Project-Dokumenten und ermöglicht eine effiziente Datenextraktion und -bearbeitung.
## FAQs
### F: Kann Aspose.Tasks zum Lesen von Projektdaten aus anderen Datenbanken als Microsoft Project verwendet werden?
A: Ja, Aspose.Tasks unterstützt das Lesen von Projektdaten aus verschiedenen Quellen, einschließlich XML-Dateien, Primavera und Microsoft Project-Datenbanken.
### F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?
A: Ja, Aspose.Tasks ist für die Zusammenarbeit mit verschiedenen Versionen von Microsoft Project konzipiert und gewährleistet so Kompatibilität und nahtlose Integration.
### F: Kann ich die Projektdaten bearbeiten, bevor ich sie speichere?
A: Absolut, Aspose.Tasks bietet eine breite Palette von Funktionen zum Bearbeiten von Projektdaten, wie zum Beispiel das Hinzufügen von Aufgaben, das Aktualisieren von Ressourcen und das Festlegen von Projekteigenschaften.
### F: Unterstützt Aspose.Tasks mehrere Ausgabeformate?
A: Ja, Aspose.Tasks unterstützt verschiedene Ausgabeformate, darunter XML, PDF, HTML und Bildformate wie PNG und JPEG.
### F: Wo finde ich weitere Unterstützung oder Hilfe zu Aspose.Tasks?
 A: Für zusätzliche Unterstützung oder Unterstützung können Sie das Aspose.Tasks-Forum besuchen oder die auf der Website verfügbare Dokumentation durchsuchen[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
