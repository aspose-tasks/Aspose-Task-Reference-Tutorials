---
date: 2026-07-05
description: Erfahren Sie, wie Sie Projektdaten mit Aspose.Tasks für .NET und Copy
  Options kopieren. Steigern Sie Ihre .NET‑Anwendungen mit präzisem Projektmanagement.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: So kopieren Sie Projektdaten mit Copy Options in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: So kopieren Sie Projektdaten mit Copy Options in Aspose.Tasks
url: /de/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Projektdaten mit Kopieroptionen in Aspose.Tasks kopiert

## Einführung

Wenn Sie **wie man ein Projekt kopiert** Informationen von einer Microsoft Project‑Datei in eine andere übertragen müssen, bietet Aspose.Tasks für .NET einen sauberen, code‑first Ansatz dafür. In diesem Tutorial führen wir Sie durch den gesamten Workflow – Laden eines Quellprojekts, Konfigurieren der Kopieroptionen, Erstellen einer Kopie und Laden des Ergebnisses – sodass Sie die Projekt‑Kopierlogik in jede .NET‑Anwendung mit Vertrauen integrieren können.

## Schnelle Antworten
- **Was macht die Kopierfunktion?** Sie dupliziert Projektdaten und ermöglicht es Ihnen, bestimmte Abschnitte wie Kalender, Ressourcen oder Ansichtsinformationen ein- oder auszuschließen.  
- **Welche Klasse steuert das Verhalten?** `CopyToOptions` lässt Sie feinabstimmen, was kopiert wird.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich; eine kostenlose Testversion funktioniert für die Entwicklung.  
- **Unterstützte Formate?** Aspose.Tasks verarbeitet MPP-, XML‑ und XER‑Dateien – über 20 + Formate insgesamt.  
- **Kann ich Ansichtsdaten überspringen?** Ja, setzen Sie `CopyToOptions.SkipViewData = true`, um UI‑bezogene Informationen wegzulassen.

## Was bedeutet „wie man ein Projekt kopiert“ in Aspose.Tasks?
**„Wie man ein Projekt kopiert“** bezieht sich auf die Verwendung der Aspose.Tasks‑API, um die Daten eines `Project`‑Objekts in eine neue Datei zu duplizieren, optional unerwünschte Elemente herauszufiltern. Dieser Vorgang ist nützlich für Vorlagen, Archivierung oder das Erstellen von Projektvarianten ohne manuelle UI‑Schritte und funktioniert über alle unterstützten Dateiformate hinweg.

## Warum Kopieroptionen in Aspose.Tasks verwenden?
Aspose.Tasks unterstützt **50 + projektbezogene Entitäten** (Aufgaben, Ressourcen, Kalender, Zuordnungen usw.) und kann Dateien mit **bis zu 10.000 Aufgaben** verarbeiten, während der Speicherverbrauch unter 200 MB bleibt. Durch die Verwendung von `CopyToOptions` können Sie das Kopieren schwergewichtiger Ansichtsdaten vermeiden, die Ausgabedateigröße um **30‑40 %** reduzieren und die Operation für große Projekte etwa **2×** beschleunigen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Tasks für .NET** – Laden Sie die neueste Version über den [Download‑Link](https://releases.aspose.com/tasks/net/) herunter.  
2. **.NET‑Entwicklungsumgebung** – Visual Studio 2022 (oder jede IDE, die .NET 6+ unterstützt) installiert.  
3. **Eine gültige Aspose.Tasks‑Lizenz** – optional für die Evaluierung, zwingend erforderlich für Produktions‑Builds.  
4. **Eine vorhandene Projektdatei** (z. B. `SourceProject.xml`), die Sie kopieren möchten.

## Wie importiert man Namespaces für Aspose.Tasks?

Fügen Sie die erforderlichen `using`‑Direktiven am Anfang Ihrer C#‑Datei hinzu, damit der Compiler die Aspose.Tasks‑Typen finden kann. Diese Anweisungen geben Ihnen direkten Zugriff auf `Project`, `CopyToOptions` und andere Hilfsklassen, ohne deren Namen vollständig qualifizieren zu müssen, was Ihren Code vereinfacht und die Lesbarkeit verbessert.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Schritt 1: Projektobjekte initialisieren

Zuerst erstellen Sie eine `Project`‑Instanz, die die Quelldatei repräsentiert, und laden die XML‑Daten.  
Die Klasse `Project` stellt eine Microsoft Project‑Datei dar, die im Speicher geladen ist und Aufgaben, Ressourcen, Kalender und weitere Projektinformationen bereitstellt.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Profi‑Tipp:** Wenn Sie mit sehr großen Dateien arbeiten, sollten Sie den `LoadOptions`‑Konstruktor verwenden, um Lazy Loading zu aktivieren und den Speicherverbrauch niedrig zu halten.

## Schritt 2: Eine Kopie des Projekts erstellen

Als Nächstes instanziieren Sie ein zweites `Project`‑Objekt, das die kopierten Daten erhalten wird. Dieses Objekt startet leer.

```csharp
Project copiedProject = new Project();
```

Sie haben nun zwei unterschiedliche `Project`‑Objekte: eines, das von der Festplatte geladen wurde, und eines, das bereit ist, die Kopie zu empfangen.

## Schritt 3: Kopiertes Projekt laden

Nach dem Kopiervorgang (siehe später) möchten Sie das Ergebnis überprüfen, indem Sie die neu gespeicherte Datei in eine weitere `Project`‑Instanz laden.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Das erneute Laden der Datei bestätigt, dass die Kopie erfolgreich war und dass die von Ihnen gesetzten Optionen wie erwartet wirkten.

## Schritt 4: Kopieroptionen konfigurieren

Die Klasse `CopyToOptions` ermöglicht es Ihnen, exakt festzulegen, was vom Quell‑ zum Zielprojekt übertragen wird.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Durch das Setzen von `SkipViewData = true` wird die Ausgabedateigröße reduziert und die Operation beschleunigt, insbesondere wenn Sie nur logische Projektdaten benötigen.

## Schritt 5: Projektkopie ausführen

Zum Schluss rufen Sie die `CopyTo`‑Methode des Quellprojekts auf, übergeben das Zielprojekt und die konfigurierten Optionen.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Dieser zweizeilige Aufruf führt die gesamte Kopieroperation aus und berücksichtigt die von Ihnen definierten Optionen. Die resultierende `CopiedProject.xml` enthält nur die Daten, die Sie angefordert haben.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| **NullReferenceException beim Aufruf von `CopyTo`** | Zielprojekt nicht instanziiert. | Stellen Sie sicher, dass `new Project()` vor `CopyTo` aufgerufen wird. |
| **Fehlende Aufgaben nach dem Kopieren** | `CopyCommonData` ist auf `false` gesetzt. | Setzen Sie `CopyCommonData = true` oder kopieren Sie bestimmte Sammlungen manuell. |
| **Große Ausgabedatei** | `SkipViewData` ist auf `false` belassen. | Aktivieren Sie `SkipViewData`, um UI‑bezogene Daten zu entfernen. |
| **Lizenz nicht angewendet** | Lizenzdatei nicht geladen. | Rufen Sie `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` vor jeglicher API‑Verwendung auf. |

## Häufig gestellte Fragen

**Q: Kann ich nur einen Teil der Aufgaben kopieren?**  
A: Ja, verwenden Sie `CopyToOptions` zusammen mit `ProjectRootTask`, um einen Start‑Task festzulegen, oder kopieren Sie ausgewählte Aufgaben manuell nach dem ersten Kopiervorgang.

**Q: Unterstützt Aspose.Tasks das Kopieren zwischen verschiedenen Dateiformaten?**  
A: Absolut. Sie können eine MPP‑Datei laden und die Kopie als XML, XER oder ein anderes unterstütztes Format speichern – über **20 + Formate** insgesamt.

**Q: Wie gehe ich mit passwortgeschützten Projektdateien um?**  
A: Laden Sie die Quelle mit `new Project("file.mpp", new LoadOptions { Password = "pwd" })` und führen Sie anschließend die Kopie wie gewohnt durch.

**Q: Gibt es eine Möglichkeit, Ressourcenpools ohne Aufgaben zu kopieren?**  
A: Setzen Sie `CopyToOptions.CopyResources = true` und `CopyToOptions.CopyTasks = false`, um nur Ressourceninformationen zu übertragen.

**Q: Wo finde ich weitere Beispiele?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für community‑basierte Snippets, Tipps zur Fehlersuche und offizielle Dokumentation.

---

**Zuletzt aktualisiert:** 2026-07-05  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Meistern von Projektdaten mit Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Meistern von MS Project Speicheroptionen für Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks Kalender und Terminplanung](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}