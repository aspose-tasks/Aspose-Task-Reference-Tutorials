---
date: 2025-12-13
description: Erfahren Sie, wie Sie die Microsoft Project‑Datenbank mit Aspose.Tasks
  für Java lesen. Schritt‑für‑Schritt‑Anleitung mit Codebeispielen und bewährten Methoden.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Microsoft Project‑Datenbank mit Aspose.Tasks für Java lesen
url: /de/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Microsoft Project‑Datenbank mit Aspose.Tasks für Java lesen

## Einleitung
In diesem Tutorial erfahren Sie, wie Sie **Microsoft Project‑Datenbank** direkt von einem Microsoft Project Server mithilfe der Aspose.Tasks Java‑API lesen können. Egal, ob Sie Berichte erstellen, Daten migrieren oder Projektinformationen in Ihre eigenen Anwendungen integrieren müssen – diese führt Sie Schritt für Schritt von der Einrichtung der Datenbankverbindung bis zum Export des Projekts nach XML. Am Ende verfügen Sie über eine solide, produktionsreife Lösung, die ohne Installation von Microsoft Project auf dem Host‑Computer funktioniert.

## Schnelle Antworten
- **Was macht Aspose.Tasks?** Es stellt eine reine Java‑API zum Lesen, Schreiben und Manipulieren von Microsoft Project‑Dateien und -Datenbanken bereit.  
- **Benötige ich Microsoft Project installiert?** Nein, Aspose.Tasks arbeitet unabhängig von Microsoft Project.  
- **Welcher Datenbanktyp wird unterstützt?** Microsoft SQL Server (das Backend von Project Server).  
- **Kann ich in andere Formate exportieren?** Ja, neben XML können Sie als PDF, HTML, CSV und mehr speichern.  
- **Was sind die wichtigsten Voraussetzungen?** JDK, Aspose.Tasks für Java Bibliothek und der SQL Server JDBC‑Treiber.

## Was bedeutet „Microsoft Project‑Datenbank lesen“?
Das Lesen einer Microsoft Project‑Datenbank bedeutet, eine Verbindung zum SQL‑Server‑Repository des Project Servers herzustellen, die gespeicherten Projektdaten zu extrahieren und in ein `Project`‑Objekt zu laden, das Aspose.Tasks manipulieren kann. Dieser Ansatz eignet sich ideal für automatisierte Berichte, Datenmigration oder benutzerdefinierte Analysen.

## Warum Aspose.Tasks für Java verwenden?
- **Keine Microsoft Project‑Abhängigkeit** – läuft auf jedem Server oder CI‑Umgebung.  
- **Umfangreiches Objektmodell** – Zugriff auf Aufgaben, Ressourcen, Zuordnungen, Kalender und benutzerdefinierte Felder programmgesteuert.  
- **Mehrere Exportoptionen** – XML, PDF, HTML, PNG usw., mit einem einzigen API‑Aufruf.  
- **Hohe Leistung** – optimiert für große Unternehmensprojekte.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Eine funktionierende Java‑Entwicklungsumgebung (JDK 8 oder neuer).  
2. Aspose.Tasks für Java Bibliothek zum Klassenpfad Ihres Projekts hinzugefügt.  
3. Zugangsdaten für die Project Server SQL‑Datenbank (Servername, Port, Datenbankname, Benutzername, Passwort).  
4. Der Microsoft JDBC‑Treiber für SQL Server (z. B. `sqljdbc4.jar`).  

## Pakete importieren
Zuerst importieren Sie die Klassen, die Sie benötigen. Die Liste enthält Aspose.Tasks‑Kernklassen und gängige Java‑Hilfsmittel.

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

## Schritt 1: Datenbankverbindung einrichten
Erstellen Sie eine `MspDbSettings`‑Instanz, die die JDBC‑Verbindungszeichenfolge enthält. Ersetzen Sie die Platzhalterwerte durch Ihre tatsächlichen Serverdetails.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro‑Tipp:** Speichern Sie die Verbindungszeichenfolge in einer sicheren Konfigurationsdatei oder Umgebungsvariable, anstatt Anmeldeinformationen hart zu codieren.

## Schritt 2: JDBC‑Treiber hinzufügen
Laden Sie den Microsoft SQL Server JDBC‑Treiber zur Laufzeit, damit die JVM mit der Datenbank kommunizieren kann.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warnung:** Stellen Sie sicher, dass die Treiberversion zu Ihrer SQL‑Server‑Version passt. Die Verwendung eines inkompatiblen Treibers kann Verbindungsfehler verursachen.

## Schritt 3: Projektdaten lesen
Instanziieren Sie ein `Project`‑Objekt, indem Sie die `MspDbSettings` übergeben. Aspose.Tasks ruft die Projektdaten automatisch aus der Datenbank ab.

```java
Project project = new Project(settings);
```

An diesem Punkt können Sie das `project`‑Objekt erkunden – Aufgaben, Ressourcen auflisten oder Felder nach Bedarf ändern.

## Schritt 4: Projektdaten speichern
Exportieren Sie das geladene Projekt in ein Dateiformat Ihrer Wahl. Das nachfolgende Beispiel speichert das Projekt als XML, das später in Microsoft Project importiert oder weiterverarbeitet werden kann.

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

Sie können `SaveFileFormat.Xml` durch `Pdf`, `Html`, `Csv` usw. ersetzen, je nach Ihren Berichtserfordernissen.

## Häufige Probleme & Lösungen
| Problem | Typische Ursache | Lösung |
|---------|------------------|--------|
| **Verbindungs‑Timeout** | Falscher Server/Port oder Firewall blockiert | Serveradresse prüfen, Port 1433 öffnen und die Konnektivität mit einem einfachen JDBC‑Testprogramm testen. |
| **Authentifizierungsfehler** | Ungültiger Benutzername/Passwort oder SQL Server nicht für SQL‑Authentifizierung konfiguriert | Verwenden Sie einen gültigen SQL‑Login oder aktivieren Sie die gemischte Authentifizierung auf dem Server. |
| **Treiber nicht gefunden** | JDBC‑Jar nicht im Klassenpfad | Stellen Sie sicher, dass `addJDBCDriver` auf die korrekte `.jar`‑Datei verweist und dass der Pfad doppelte Backslashes (`\\`) verwendet. |
| **Leeres Projekt nach dem Laden** | Unzureichende Berechtigungen zum Lesen der Project‑Server‑Tabellen | Gewähren Sie dem Login SELECT‑Rechte auf das Schema der Project‑Server‑Datenbank. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks verwendet werden, um Projektdaten aus anderen Datenbanken als Microsoft Project zu lesen?**  
A: Ja, Aspose.Tasks unterstützt das Lesen von Projektdaten aus verschiedenen Quellen, einschließlich XML‑Dateien, Primavera und Microsoft Project‑Datenbanken.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?**  
A: Ja, Aspose.Tasks ist so konzipiert, dass es mit mehreren Microsoft Project‑Versionen funktioniert und nahtlose Integration gewährleistet.

**F: Kann ich die Projektdaten vor dem Speichern manipulieren?**  
A: Absolut, Aspose.Tasks bietet eine umfangreiche API zum Hinzufügen von Aufgaben, Aktualisieren von Ressourcen und Festlegen von Projekteigenschaften vor dem Export.

**F: Unterstützt Aspose.Tasks mehrere Ausgabeformate?**  
A: Ja, Sie können Projekte als XML, PDF, HTML, CSV, PNG, JPEG und mehr speichern.

**F: Wo finde ich weitere Unterstützung oder Hilfe zu Aspose.Tasks?**  
A: Für zusätzliche Hilfe besuchen Sie das Aspose.Tasks‑Forum oder erkunden Sie die Dokumentation auf der Website [here](https://forum.aspose.com/c/tasks/15).

## Fazit
Durch Befolgen dieser Schritt‑für‑Schritt‑Anleitung wissen Sie jetzt, wie Sie **Microsoft Projectatenbank** mit Aspose.Tasks für Java lesen, die Daten programmgesteuert manipulieren und in das gewünschte Format exportieren können. Dieser Ansatz eliminiert die Abhängigkeit von Microsoft Project, vereinfacht automatisierte Berichte und eröffnet leistungsstarke, benutzerdefinierte Integrationsmöglichkeiten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-13  
**Getestet mit:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Autor:** Aspose