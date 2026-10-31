---
date: 2026-10-31
description: Erfahren Sie, wie Sie ein Projekt als PDF speichern und die Microsoft
  Project-Datenbank mit Aspose.Tasks für Java lesen, sowie eine Verbindung zu Project
  Server herstellen, das Projekt in HTML konvertieren und das Projekt nach XML exportieren.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Projekt-Daten aus Microsoft Project-Datenbank in Aspose.Tasks lesen
og_description: Projekt als PDF speichern und Microsoft Project-Datenbank mit Aspose.Tasks
  für Java lesen. Erfahren Sie, wie Sie eine Verbindung zu Project Server herstellen,
  nach HTML, XML und CSV exportieren.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Projekt als PDF speichern und Microsoft Project-Datenbank mit Aspose.Tasks
  für Java lesen
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Projekt als PDF speichern und Microsoft Project-Datenbank mit Aspose.Tasks
  für Java lesen
url: /de/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt als PDF speichern und Microsoft Project‑Datenbank mit Aspose.Tasks für Java lesen

## Einführung
In diesem Tutorial erfahren Sie, wie Sie die **Microsoft Project‑Datenbank** direkt von einem Microsoft Project Server **auslesen** und das Projekt anschließend **als PDF** mithilfe der Aspose.Tasks Java‑API **speichern**. Egal, ob Sie druckbare Berichte erstellen, Altdaten migrieren oder Projektinformationen in ein benutzerdefiniertes Portal einbetten möchten – diese Anleitung führt Sie Schritt für Schritt von der Konfiguration der JDBC‑Verbindung bis zum Export des Projekts nach PDF, XML oder HTML. Am Ende verfügen Sie über eine produktionsreife Lösung, die auf jedem Java‑Server läuft, ohne dass Microsoft Project installiert sein muss.

## Schnelle Antworten
- **Was macht Aspose.Tasks?** Es stellt eine reine Java‑API zum Lesen, Schreiben und Manipulieren von Microsoft Project‑Dateien und -Datenbanken bereit.  
- **Benötige ich Microsoft Project installiert?** Nein, Aspose.Tasks funktioniert unabhängig von Microsoft Project.  
- **Welcher Datenbanktyp wird unterstützt?** Microsoft SQL Server, das Backend von Project Server.  
- **Kann ich in andere Formate exportieren?** Ja – PDF, XML, HTML, CSV, PNG, JPEG und mehr.  
- **Was sind die wichtigsten Voraussetzungen?** JDK 8 oder neuer, Aspose.Tasks für Java‑Bibliothek, der SQL‑Server‑JDBC‑Treiber und gültige Project‑Server‑Anmeldeinformationen.

## Was bedeutet „Microsoft Project‑Datenbank lesen“?
Das Lesen einer Microsoft Project‑Datenbank bedeutet, eine Verbindung zum SQL‑Server‑Repository des Project Servers herzustellen, die gespeicherten Projektdaten zu extrahieren und in ein `Project`‑Objekt zu laden, das Aspose.Tasks manipulieren kann. Dieser Ansatz eignet sich ideal für automatisierte Berichte, Datenmigration oder benutzerdefinierte Analysen.

## Warum Aspose.Tasks für Java verwenden?
Aspose.Tasks für Java ermöglicht die Arbeit mit Microsoft Project‑Daten, ohne die Desktop‑Anwendung zu benötigen, und bietet eine reine Java‑Lösung, die auf jeder Plattform läuft. Es stellt ein umfassendes Objektmodell für Aufgaben, Ressourcen, Kalender und benutzerdefinierte Felder bereit und kann große Unternehmensprojekte effizient verarbeiten – ideal für automatisierte Berichte, Migration und Integrationsszenarien.

- **Keine Abhängigkeit von Microsoft Project** – läuft auf jedem Server oder CI‑Umgebung.  
- **Umfangreiches Objektmodell** – programmgesteuerter Zugriff auf Aufgaben, Ressourcen, Zuordnungen, Kalender und benutzerdefinierte Felder.  
- **Mehrere Exportoptionen** – Aspose.Tasks unterstützt den Export in **über 20 Dateiformate**, darunter PDF, XML, HTML, CSV, PNG und JPEG, mit einem einzigen API‑Aufruf.  
- **Hohe Leistung** – die Bibliothek kann Projekte mit **bis zu 10 000 Aufgaben** in weniger als einer Minute verarbeiten und streamt Daten, um das Laden der gesamten Datei in den Speicher zu vermeiden.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Eine funktionierende Java‑Entwicklungsumgebung (JDK 8 oder neuer).  
2. Die Aspose.Tasks‑Bibliothek für Java in Ihrem Klassenpfad.  
3. Anmeldeinformationen für die Project‑Server‑SQL‑Datenbank (Servername, Port, Datenbankname, Benutzername, Passwort), um eine Verbindung zum Project Server herzustellen.  
4. Der Microsoft JDBC‑Treiber für SQL Server (z. B. `sqljdbc4.jar`).  

## Pakete importieren
Importieren Sie zunächst die Klassen, die Sie benötigen. Die Liste enthält Kernklassen von Aspose.Tasks sowie Standard‑Java‑Utilities.

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

## So verbinden Sie sich mit Project Server
Der Aufbau einer zuverlässigen Verbindung ist die Grundlage für das Auslesen von Projektdaten. Stellen Sie sicher, dass die SQL‑Server‑Instanz von Ihrem Java‑Host aus erreichbar ist und dass das von Ihnen verwendete Login **SELECT**‑Rechte auf dem Project‑Server‑Schema besitzt. Prüfen Sie außerdem die Netzwerklatenz und konfigurieren Sie ggf. erforderliche SSL‑Einstellungen, um eine sichere Kommunikation zu gewährleisten.

## Schritt 1: Datenbankverbindung einrichten
Die Klasse `MspDbSettings` kapselt die JDBC‑Verbindungsdetails, die zum Zugriff auf eine Microsoft Project Server‑Datenbank erforderlich sind. Erzeugen Sie eine `MspDbSettings`‑Instanz, die den JDBC‑Verbindungsstring enthält. Ersetzen Sie die Platzhalterwerte durch Ihre tatsächlichen Serverdetails.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro‑Tipp:** Speichern Sie den Verbindungsstring in einer sicheren Konfigurationsdatei oder einer Umgebungsvariable, anstatt Anmeldeinformationen hart zu kodieren.

## Schritt 2: JDBC‑Treiber hinzufügen
Laden Sie den Microsoft SQL Server JDBC‑Treiber zur Laufzeit, damit die JVM mit der Datenbank kommunizieren kann.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warnung:** Stellen Sie sicher, dass die Treiberversion zu Ihrer SQL‑Server‑Version passt. Ein inkompatibler Treiber kann Verbindungsfehler verursachen.

## Schritt 3: Projektdaten auslesen
Die Klasse `Project` repräsentiert eine Microsoft Project‑Datei, die im Speicher geladen ist und Aufgaben, Ressourcen sowie Zuordnungen bereitstellt. Instanziieren Sie ein `Project`‑Objekt, indem Sie die `MspDbSettings` übergeben. Aspose.Tasks ruft die Projektdaten automatisch aus der Datenbank ab.

```java
Project project = new Project(settings);
```

An diesem Punkt können Sie das `project`‑Objekt erkunden – Aufgaben, Ressourcen auflisten oder Felder nach Bedarf ändern.

## Schritt 4: Projekt als PDF speichern
Die Aufzählung `SaveFileFormat` definiert das Ausgabeformat für die Methode `Project.save`, z. B. PDF, XML oder HTML. Exportieren Sie das geladene Projekt in das von Ihnen gewünschte Format. Das nachfolgende Beispiel speichert das Projekt als **PDF**, ideal für druckbare Berichte. Sie können das Projekt auch **nach XML exportieren** oder **nach HTML konvertieren**, indem Sie das `SaveFileFormat`‑Enum ändern.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Möchten Sie XML, ersetzen Sie einfach `SaveFileFormat.Pdf` durch `SaveFileFormat.Xml`. Für HTML‑Ausgabe verwenden Sie `SaveFileFormat.Html`.

## Häufige Probleme & Lösungen
| Problem | Typische Ursache | Lösung |
|-------|---------------|-----|
| **Verbindungs‑Timeout** | Falscher Server/Port oder Firewall blockiert | Serveradresse prüfen, Port 1433 öffnen und die Konnektivität mit einem einfachen JDBC‑Testprogramm überprüfen. |
| **Authentifizierungsfehler** | Ungültiger Benutzername/Passwort oder SQL Server nicht für SQL‑Authentifizierung konfiguriert | Gültigen SQL‑Login verwenden oder gemischten Modus auf dem Server aktivieren. |
| **Treiber nicht gefunden** | JDBC‑Jar nicht im Klassenpfad | Sicherstellen, dass `addJDBCDriver` auf die korrekte `.jar`‑Datei zeigt und der Pfad doppelte Backslashes (`\\`) verwendet. |
| **Leeres Projekt nach dem Laden** | Unzureichende Berechtigungen zum Lesen der Project‑Server‑Tabellen | Dem Login SELECT‑Rechte auf das Project‑Server‑Datenbankschema gewähren. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks verwendet werden, um Projektdaten aus anderen Datenbanken als Microsoft Project zu lesen?**  
A: Ja, Aspose.Tasks unterstützt das Lesen von Projektdaten aus XML‑Dateien, Primavera‑Datenbanken und anderen gängigen Projektformaten.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?**  
A: Ja, die Bibliothek funktioniert mit Microsoft Project 2007 bis zu den neuesten 2024‑Versionen und gewährleistet nahtlose Integration über alle Versionen hinweg.

**F: Kann ich die Projektdaten vor dem Speichern manipulieren?**  
A: Absolut, Sie können Aufgaben, Ressourcen und benutzerdefinierte Felder mithilfe der umfangreichen API hinzufügen, aktualisieren oder löschen, bevor Sie exportieren.

**F: Unterstützt Aspose.Tasks mehrere Ausgabeformate?**  
A: Ja, Sie können Projekte als PDF, XML, HTML, CSV, PNG, JPEG und mehr – über 20 Formate insgesamt – speichern.

**F: Wo finde ich weitere Unterstützung oder Hilfe zu Aspose.Tasks?**  
A: Für zusätzliche Hilfe besuchen Sie das Aspose.Tasks‑Forum oder die Dokumentation auf der Website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Fazit
Durch Befolgen dieser Schritt‑für‑Schritt‑Anleitung wissen Sie jetzt, wie Sie **Microsoft Project‑Datenbank lesen**, **das Projekt als PDF speichern** und in weitere Formate exportieren können – alles mit Aspose.Tasks für Java. Dieser Ansatz eliminiert die Abhängigkeit von Microsoft Project, vereinfacht automatisierte Berichte und eröffnet leistungsstarke, benutzerdefinierte Integrationsmöglichkeiten.

---

**Zuletzt aktualisiert:** 2026-10-31  
**Getestet mit:** Aspose.Tasks für Java 24.5 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Save Project as PDF with Aspose.Tasks – Export Guide](/tasks/java/project-file-operations/save-as-pdf/)
- [Save Project as PDF – Render Task Sheet with Aspose.Tasks for Java](/tasks/java/task-properties/render-task-sheet/)
- [Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}