---
title: Einstellungen für die Microsoft Project-Datenbank in Aspose.Tasks
linktitle: Einstellungen für die Microsoft Project-Datenbank in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Datenbankeinstellungen mit Aspose.Tasks für eine nahtlose Integration in .NET-Anwendungen konfigurieren.
weight: 19
url: /de/net/advanced-concepts/msp-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Einstellungen für die Microsoft Project-Datenbank in Aspose.Tasks

## Einführung

Wenn Sie mit Aspose.Tasks in Ihren .NET-Anwendungen mit Microsoft Project-Datenbanken arbeiten, müssen Sie die erforderlichen Einstellungen konfigurieren, um Projektdaten nahtlos zu importieren. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie[Hier](https://releases.aspose.com/tasks/net/).
2. Zugriff auf eine Microsoft Project-Datenbank: Sie sollten Zugriff auf eine Microsoft Project-Datenbank haben, aus der Sie Daten importieren können.

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

Erstellen Sie die Verbindungszeichenfolge zu Ihrer Microsoft Project-Datenbank. Hier ist ein Beispiel:

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

Stellen Sie sicher, dass Sie die Platzhalterwerte durch Ihre tatsächlichen Datenbankanmeldeinformationen ersetzen.

## Schritt 2: Konfigurieren Sie MspDbSettings

 Erstellen Sie eine Instanz von`MspDbSettings` und geben Sie die Verbindungszeichenfolge zusammen mit der Projekt-GUID an:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Schritt 3: Projektdaten laden

 Instanziieren Sie a`Project` Objekt mit den konfigurierten Einstellungen:

```csharp
var project = new Project(settings);
```

## Schritt 4: Projektdaten speichern

Speichern Sie die geladenen Projektdaten in einer Datei:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie Einstellungen für den Zugriff auf Microsoft Project-Datenbanken mithilfe von Aspose.Tasks für .NET konfigurieren. Wenn Sie diese Schritte befolgen, können Sie Projektdaten nahtlos in Ihre Anwendungen importieren und so ein effizientes Projektmanagement ermöglichen.

## FAQs

### F1: Kann ich Aspose.Tasks mit verschiedenen Versionen von Microsoft Project-Datenbanken verwenden?

A1: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project-Datenbanken und ermöglicht so Flexibilität bei der Integration.

### F2: Wie kann ich Verbindungsprobleme mit der Datenbank beheben?

 A2: Stellen Sie sicher, dass Ihre Verbindungszeichenfolge korrekt mit den entsprechenden Anmeldeinformationen und Datenbankdetails konfiguriert ist. Sie können auch in der Dokumentation nachschlagen oder Unterstützung von der erhalten[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).

### F3: Gibt es eine Testversion für Aspose.Tasks?

 A3: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).

### F4: Kann ich das Schema für die Datenbankinteraktion anpassen?

 A4: Ja, Sie können das Schema dafür angeben`MspDbSettings` Objekt entsprechend Ihrer Datenbankstruktur.

### F5: Wo finde ich eine ausführlichere Dokumentation zur Verwendung von Aspose.Tasks?

 A5: Sie können die umfassende Dokumentation erkunden[Hier](https://reference.aspose.com/tasks/net/) für detaillierte Einblicke in die Funktionalitäten von Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
