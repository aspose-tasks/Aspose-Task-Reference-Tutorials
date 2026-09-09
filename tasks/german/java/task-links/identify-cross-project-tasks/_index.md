---
date: 2026-09-09
description: Erfahren Sie, wie Sie Cross‑Projekt‑Aufgaben mit Aspose.Tasks für Java
  identifizieren. Entdecken Sie nahtlose Integration, effizientes Management und Praxisbeispiele.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Cross‑Projekt‑Aufgaben in Aspose.Tasks identifizieren
og_description: Cross‑Projekt‑Aufgaben in Aspose.Tasks für Java identifizieren. Erfahren
  Sie, wie Sie das Dokumentverzeichnis festlegen, Aufgaben‑IDs abrufen und verknüpfte
  Projekte effizient verwalten.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Cross‑Projekt‑Aufgaben in Aspose.Tasks – Java‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Cross‑Projekt‑Aufgaben in Aspose.Tasks identifizieren
url: /de/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identifizieren von projektübergreifenden Aufgaben in Aspose.Tasks

## Einführung
In diesem Tutorial lernen Sie **wie man projektübergreifende Aufgaben** mit Aspose.Tasks für Java identifiziert. Egal, ob Sie ein Portfolio interdependenter Zeitpläne verwalten oder externe Abhängigkeiten prüfen müssen, die nachfolgenden Schritte zeigen Ihnen, wie Sie Aufgaben finden, die auf andere Projektdateien verweisen, deren Kennungen abrufen und programmgesteuert damit arbeiten.

## Schnelle Antworten
- **Was bedeutet „identify cross project tasks“?** Es bedeutet, Aufgaben zu finden, die auf Aufgaben in einer anderen Projektdatei verweisen oder von ihnen abhängen.  
- **Welche Methode gibt die Task-ID aus?** Verwenden Sie `externalTask.get(Tsk.ID)`, um die Task-ID auszugeben.  
- **Wie lege ich das Dokumentverzeichnis fest?** Weisen Sie den Ordnerpfad einer `String`‑Variablen zu (z. B. `dataDir`).  
- **Welche Eigenschaft ruft eine Aufgabe nach UID ab?** Rufen Sie `getChildren().getByUid(yourUid)` auf.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Ja, eine gültige Aspose.Tasks‑Lizenz ist für kommerzielle Bereitstellungen erforderlich.

## Was bedeutet „identify cross project tasks“?
Das Identifizieren projektübergreifender Aufgaben ermöglicht es Ihnen, Beziehungen zwischen Aufgaben, die über mehrere Microsoft‑Project‑Dateien verteilt sind, nachzuvollziehen. Indem Sie Aufgaben finden, die auf externe Zeitpläne verweisen oder von ihnen abhängen, können Sie verstehen, wie Arbeitspakete über Projektgrenzen hinweg interagieren, Doppelarbeit vermeiden und genaue Zeitpläne beibehalten. Diese Fähigkeit ist für groß angelegte Portfolios unverzichtbar, in denen Aufgaben geteilt werden oder von externen Zeitplänen abhängen.

## Warum Aspose.Tasks für Java verwenden?
Aspose.Tasks für Java unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** (einschließlich MPP, MPX, XML und CSV) und kann Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Die Bibliothek funktioniert auf jeder JVM‑kompatiblen Plattform, erfordert keine Installation von Microsoft Project und bietet vollständigen API‑Zugriff auf IDs, UIDs, externe IDs und Verknüpfungs‑Metadaten.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie:

- Eine funktionierende Java‑Entwicklungsumgebung (JDK 8 oder höher).  
- Aspose.Tasks für Java installiert. Sie können es **[hier](https://releases.aspose.com/tasks/java/)** herunterladen.  
- Eine gültige Aspose.Tasks‑Lizenzdatei, falls Sie den Code in der Produktion ausführen möchten.

## Pakete importieren
Die Klasse `Project` repräsentiert eine Microsoft‑Project‑Datei, `Task` steht für eine einzelne Aufgabe und `Tsk` liefert Konstanten für Aufgabenfelder.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Schritt 1: Dokumentverzeichnis festlegen
Der String `dataDir` enthält den Pfad zu dem Ordner, der Ihre `.mpp`‑Dateien enthält.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Schritt 2: externes Projekt laden
`Project externalProject` lädt die angegebene externe Projektdatei zur Inspektion.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Schritt 3: externen Task nach UID abrufen
`externalProject.getChildren().getByUid(uid)` ruft eine Aufgabe aus der Aufgaben‑Collection des externen Projekts anhand ihrer eindeutigen Kennung ab.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Schritt 4: Task-ID ausgeben (primärer Anwendungsfall)
`externalTask.get(Tsk.ID)` gibt die von Aspose.Tasks für die jeweilige Aufgabe zugewiesene interne ID zurück.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Schritt 5: ursprüngliche (externe) Task-ID ausgeben
`externalTask.get(Tsk.ExternalID)` holt die ursprüngliche ID der Aufgabe, wie sie in der Quell‑Projektdatei definiert ist.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Wiederholen Sie die obigen Schritte für alle weiteren Aufgaben, die Sie projektübergreifend verfolgen möchten.

## Häufige Probleme & Tipps
- **Pfadfehler** – Stellen Sie sicher, dass `dataDir` mit dem passenden Dateiseparator (`/` oder `\\`) endet.  
- **UID nicht gefunden** – Prüfen Sie, ob die UID im externen Projekt existiert; verwenden Sie `externalProject.getRootTask().getChildren().size()`, um verfügbare UIDs aufzulisten.  
- **Lizenzausnahmen** – Eine fehlende oder ungültige Lizenz löst zur Laufzeit eine Lizenz‑Ausnahme aus.  
- **Große Projekte** – Bei Projekten mit mehr als 5.000 Aufgaben sollten Sie `ProjectReader` mit dem `LoadOptions`‑Flag verwenden, um Daten zu streamen und den Speicherverbrauch zu reduzieren.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
A: Ja, Aspose.Tasks unterstützt mehrere Sprachen, darunter Java, .NET und weitere.

**F: Wo finde ich die ausführliche Dokumentation für Aspose.Tasks für Java?**  
A: Siehe die Dokumentation **[hier](https://reference.aspose.com/tasks/java/)**.

**F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion **[hier](https://releases.aspose.com/)** erhalten.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?**  
A: Eine temporäre Lizenz erhalten Sie **[hier](https://purchase.aspose.com/temporary-license/)**.

**F: Benötigen Sie Hilfe oder haben Sie spezifische Fragen?**  
A: Besuchen Sie das Aspose.Tasks‑Support‑Forum **[hier](https://forum.aspose.com/c/tasks/15)**.

**Zuletzt aktualisiert:** 2026-09-09  
**Getestet mit:** Aspose.Tasks für Java 24.11 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Erstellen von Aufgabenabhängigkeiten im Projektmanagement in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Projektstartdatum festlegen und Eltern‑ und Kindaufgaben in Aspose.Tasks verwalten](/tasks/java/task-properties/parent-child-tasks/)
- [MPP-Projekt in Java erstellen – Aufgabenfortschritt mit Aspose.Tasks ändern](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}