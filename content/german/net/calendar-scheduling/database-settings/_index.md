---
title: Datenbankeinstellungen in Aspose.Tasks
linktitle: Datenbankeinstellungen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Projekte aus einer Primavera-Datenbank importieren. Erhalten Sie eine Schritt-für-Schritt-Anleitung in diesem umfassenden Tutorial.
type: docs
weight: 29
url: /de/net/calendar-scheduling/database-settings/
---
## Einführung

Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, in ihren .NET-Anwendungen mit Microsoft Project-Dateien zu arbeiten. In diesem Tutorial konzentrieren wir uns auf den Import von Projekten aus einer Primavera-Datenbank mithilfe von Aspose.Tasks.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Visual Studio ist auf Ihrem System installiert.
-  Aspose.Tasks für .NET-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
- Zugriff auf eine Primavera-Datenbank, zusammen mit den erforderlichen Berechtigungen.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die für die Arbeit mit Aspose.Tasks für .NET erforderlich sind.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Lassen Sie uns nun den bereitgestellten Beispielcode in mehrere Schritte aufteilen:

## Schritt 1: Verbindungszeichenfolge definieren

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 In diesem Schritt definieren wir die Verbindungszeichenfolge für die Verbindung zur Primavera-Datenbank. Stellen Sie sicher, dass Sie ersetzen`DataDir` mit dem Verzeichnis, in dem sich Ihre Datenbankdatei befindet.

## Schritt 2: Datenbankeinstellungen erstellen

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Hier erstellen wir eine Instanz von`PrimaveraDbSettings` Klasse, wobei die Verbindungszeichenfolge und die Projekt-ID als Parameter übergeben werden. Passen Sie die Projekt-ID entsprechend Ihren Anforderungen an.

## Schritt 3: Legen Sie den invarianten Namen des Anbieters fest

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Geben Sie den invarianten Namen des Anbieters an. In diesem Beispiel verwenden wir SQLite, Sie können es jedoch je nach Datenbankanbieter ändern.

## Schritt 4: Projekt laden

```csharp
var project = new Project(settings);
```

 Erstelle eine neue`Project` Objekt und übergibt die Datenbankeinstellungen als Parameter.

## Schritt 5: Projekt speichern

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Speichern Sie abschließend das Projekt im angegebenen Dateiformat am gewünschten Ort.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für .NET Projekte aus einer Primavera-Datenbank importiert. Wenn Sie die bereitgestellten Schritte befolgen, können Sie die Projektimportfunktionalität nahtlos in Ihre .NET-Anwendungen integrieren.

## FAQs

### F1: Kann ich mit Aspose.Tasks für .NET Projekte von verschiedenen Datenbankanbietern importieren?

A1: Ja, Sie können Projekte von verschiedenen Datenbankanbietern importieren, indem Sie die Verbindungszeichenfolge und den invarianten Namen des Anbieters entsprechend anpassen.

### F2: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?

 A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET bei erhalten[Hier](https://releases.aspose.com/).

### F3: Wo finde ich Dokumentation für Aspose.Tasks für .NET?

 A3: Sie finden die Dokumentation[Hier](https://reference.aspose.com/tasks/net/).

### F4: Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?

 A4: Sie können Unterstützung vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).

### F5: Benötige ich eine temporäre Lizenz, um Aspose.Tasks für .NET zu verwenden?

 A5: Wenn Sie den vollen Funktionsumfang der Bibliothek testen möchten, können Sie bei uns eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).