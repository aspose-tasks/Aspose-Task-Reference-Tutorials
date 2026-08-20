---
date: 2026-03-14
description: Erfahren Sie, wie Sie das Datenbankschema für eine Microsoft Project‑Datenbank
  mit Aspose.Tasks festlegen und wie Sie Projektdaten in .NET‑Anwendungen importieren.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Datenbankschema für Projekt‑DB mit Aspose.Tasks festlegen
url: /de/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Einstellungen für Microsoft Project-Datenbank in Aspose.Tasks

## Einführung

Wenn Sie in Ihren .NET‑Anwendungen mit Microsoft Project‑Datenbanken unter Verwendung von Aspose.Tasks arbeiten, müssen Sie **das Datenbankschema angeben** und die erforderlichen Einstellungen konfigurieren, um **Projekt‑Daten** nahtlos zu **importieren**. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess und zeigt Ihnen, **wie Sie Verbindungsdetails konfigurieren**, **eine .NET‑Verbindungszeichenfolge erstellen** und schließlich **ein Projekt als MPP speichern**.

## Schnellantworten
- **Was ist das Hauptziel?** Das Datenbankschema angeben und eine Project‑Datenbank in eine .NET‑App importieren.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für .NET.  
- **Wie stelle ich eine Verbindung zu Project Server her?** Durch Erstellen einer korrekten SQL‑Verbindungszeichenfolge und Verwendung von `MspDbSettings`.  
- **Welches Dateiformat wird erzeugt?** Eine MPP‑Datei, gespeichert mit `SaveFileFormat.Mpp`.  
- **Kann ich den Schemanamen ändern?** Ja, setzen Sie die Eigenschaft `Schema` von `MspDbSettings`.

## Wie man das Datenbankschema für Project‑DB angibt

Zu verstehen, warum Sie **das Datenbankschema angeben** müssen, ist entscheidend. In vielen Unternehmensumgebungen befindet sich die Project‑Server‑Datenbank unter einem benutzerdefinierten Schema (z. B. `dbo`, `psdata`). Durch das explizite Festlegen des Schemas stellen Sie sicher, dass Aspose.Tasks die richtigen Tabellen abfragt, wodurch Laufzeitfehler vermieden und ein genauer Datenimport gewährleistet wird.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks‑Bibliothek von [hier](https://releases.aspose.com/tasks/net/) herunter und installieren Sie sie.  
2. Zugriff auf eine Microsoft Project‑Datenbank: Sie benötigen Zugriff auf eine Microsoft Project‑Datenbank, aus der Sie Daten importieren können.  

## Namespaces importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Schritt 1: Verbindungszeichenfolge erstellen

Erstellen Sie die Verbindungszeichenfolge zu Ihrer Microsoft Project‑Datenbank. Hierbei **erstellen Sie die .NET‑Verbindungszeichenfolge** und definieren, wie Sie **eine Verbindung zu Project Server** herstellen.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Pro Tipp:** Überprüfen Sie die Werte für `DataSource` und `InitialCatalog` sorgfältig; sie müssen mit der Adresse Ihres Servers und dem veröffentlichten Datenbanknamen übereinstimmen.

## Schritt 2: MspDbSettings konfigurieren

Erzeugen Sie eine Instanz von `MspDbSettings`, übergeben Sie die Verbindungszeichenfolge und **geben Sie das Datenbankschema an**, indem Sie die Eigenschaft `Schema` setzen. Damit teilt Sie Aspose.Tasks mit, welches Schema abgefragt werden soll.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Hier geben wir außerdem die Projekt‑GUID an, die das spezifische Projekt identifiziert, das Sie laden möchten.

## Schritt 3: Projektdaten laden

Instanziieren Sie ein `Project`‑Objekt mit den konfigurierten Einstellungen. Dieser Schritt demonstriert **wie Projekt‑Daten** aus der Datenbank in ein .NET‑Objekt importiert werden.

```csharp
var project = new Project(settings);
```

## Schritt 4: Projektdaten speichern

Zum Schluss speichern Sie das geladene Projekt als MPP‑Datei auf dem Datenträger. Dies zeigt, **wie man ein Projekt als MPP speichert** mithilfe der Aspose.Tasks‑API.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Nach dem Ausführen des Codes finden Sie die Datei `ImportProjectDataFromDatabase_out.mpp` im Ausgabeverzeichnis, bereit zum Öffnen in Microsoft Project.

## Fazit

In diesem Tutorial haben Sie gelernt, **das Datenbankschema** für eine Microsoft Project‑Datenbank anzugeben, **die Verbindung zu konfigurieren**, **Projekt‑Daten** zu importieren und **das Projekt als MPP** mit Aspose.Tasks für .NET zu speichern. Diese Schritte ermöglichen eine nahtlose Integration von Project‑Server‑Daten in Ihre eigenen Anwendungen und unterstützen Sie beim Aufbau robuster Projektmanagement‑Lösungen.

## Häufig gestellte Fragen

### Q1: Kann ich Aspose.Tasks mit verschiedenen Versionen von Microsoft Project‑Datenbanken verwenden?
A1: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project‑Datenbanken und bietet damit Flexibilität bei der Integration.

### Q2: Wie kann ich Verbindungsprobleme mit der Datenbank beheben?
A2: Stellen Sie sicher, dass Ihre Verbindungszeichenfolge korrekt konfiguriert ist und die richtigen Anmeldeinformationen sowie Datenbankdetails enthält. Weitere Informationen finden Sie in der Dokumentation oder im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

### Q3: Gibt es eine Testversion von Aspose.Tasks?
A3: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) erhalten.

### Q4: Kann ich das Schema für die Datenbankinteraktion anpassen?
A4: Ja, Sie können das Schema für das `MspDbSettings`‑Objekt gemäß Ihrer Datenbankstruktur festlegen.

### Q5: Wo finde ich ausführlichere Dokumentation zur Verwendung von Aspose.Tasks?
A5: Die umfassende Dokumentation finden Sie [hier](https://reference.aspose.com/tasks/net/) für detaillierte Einblicke in die Funktionen von Aspose.Tasks.

**F: Funktioniert dieser Ansatz mit Azure‑SQL‑Datenbanken?**  
A: Absolut. Passen Sie einfach den `DataSource` an den Namen Ihres Azure‑Servers an und stellen Sie sicher, dass TLS/SSL‑Einstellungen aktiviert sind.

**F: Wie gehe ich mit großen Project‑Datenbanken um, ohne dass ein Timeout auftritt?**  
A: Erhöhen Sie den Wert `ConnectTimeout` in der Verbindungszeichenfolge und erwägen Sie, Projekte bei Bedarf in Batches zu laden.

---

**Zuletzt aktualisiert:** 2026-03-14  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}