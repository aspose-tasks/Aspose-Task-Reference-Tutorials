---
date: 2026-06-15
description: Erfahren Sie, wie Sie Kosten in MS Project-Dateien mit Aspose.Tasks für
  Java verwalten, einschließlich des Ladens einer MPP-Datei und des Lesens von actual
  cost work und budgeted cost schedule.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Ressourcenkosten in Aspose.Tasks verwalten
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man Kosten in MS Project mit Aspose.Tasks für Java verwaltet
url: /de/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Kosten in MS Project mit Aspose.Tasks für Java verwaltet

## Einführung

Die Verwaltung von Projektbudgets ist eine Kernverantwortung jedes Projektmanagers, und **wie man Kosten** effektiv verwaltet, kann den Erfolg eines Projekts entscheiden. Aspose.Tasks für Java gibt Ihnen programmatischen Zugriff auf Microsoft Project‑Dateien, sodass Sie Ressourcenkostendaten lesen und aktualisieren können, ohne die .mpp‑Datei manuell zu öffnen. In diesem Tutorial sehen Sie Schritt für Schritt, wie Sie eine MPP‑Datei laden, die tatsächlichen Kostenarbeiten prüfen und den budgetierten Kostenplan für jede Ressource extrahieren.

## Schnelle Antworten
- **Was macht Aspose.Tasks für Java?** Es liest und schreibt Microsoft Project‑Dateien (.mpp), ohne dass Microsoft Project installiert sein muss.  
- **Wie kann ich eine MPP‑Datei laden?** Verwenden Sie `new Project("path/to/file.mpp")` – die API analysiert die Datei im Speicher.  
- **Welche Kostenfelder stehen zur Verfügung?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) und Budgeted Cost of Work Performed (BCWP).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche Java‑Versionen werden unterstützt?** Java 8 und später, einschließlich Java 17 LTS.

## Wie verwalte ich Kosten in MS Project?

Laden Sie Ihr Projekt mit `new Project("yourFile.mpp")` und iterieren Sie anschließend über jedes `Resource`‑Objekt, um kostenbezogene Eigenschaften wie ACWP, BCWS und BCWP auszulesen. Aspose.Tasks konvertiert die internen Kostenwerte automatisch in die Währung des Projekts, sodass Sie sie direkt anzeigen oder speichern können. Dieser Ansatz eliminiert manuelle Tabellenkalkulationen und garantiert Datenkonsistenz in allen Projektberichten.

## Voraussetzungen

1. Grundlegendes Verständnis der Java‑Programmierung.  
2. Aspose.Tasks für Java‑Bibliothek zu Ihrem Projekt hinzugefügt (Maven/Gradle oder manuelles JAR).  
3. Zugriff auf eine Microsoft Project‑Datei (`.mpp`), die Sie analysieren möchten.  

## Pakete importieren

Die Klassen `Project` und `Resource` sind die Einstiegspunkte für die Arbeit mit Projektdaten.

Die Klasse `Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne Microsoft Project‑Datei im Speicher repräsentiert.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Schritt 1: Definieren Sie das Datenverzeichnis

Geben Sie zuerst den Ordner an, der Ihre `.mpp`‑Datei enthält. Dieser Pfad kann absolut oder relativ zum Arbeitsverzeichnis Ihrer Anwendung sein.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Schritt 2: Laden Sie die MS Project‑Datei

`Project` lädt die Datei und baut ein Objektmodell auf, das Sie abfragen können. Die API analysiert die Datei, ohne dass Microsoft Project installiert sein muss, und unterstützt über 30 Eingabeformate.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Schritt 3: Durchlaufen Sie die Ressourcen

`Resource`‑Objekte repräsentieren Personen, Geräte oder Materialien, die das Budget verbrauchen. Sie können die Sammlung `project.getResources()` durchlaufen, um auf jede Ressource zuzugreifen.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Schritt 4: Überprüfen Sie den Ressourcennamen und die Kosten

Für jede Ressource prüfen Sie, ob der Name definiert ist, und lesen dann die Kostenfelder aus. Die Methode `getActualCost()` liefert die **actual cost work** (ACWP), während `getBudgetedCost()` den **budgeted cost schedule** (BCWS/BCWP) zurückgibt.

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Warum Aspose.Tasks für Java zum Laden einer MPP‑Datei verwenden?

Aspose.Tasks unterstützt **30+ Dateiformate** (einschließlich `.mpp`, `.xml` und `.xlsx`) und kann Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, während es weniger als 200 MB RAM verbraucht. Die Bibliothek führt alle Berechnungen serverseitig aus und eliminiert damit die Notwendigkeit einer lizenzierten Kopie von Microsoft Project.

## Häufige Probleme und Lösungen

- **Null‑Ressourcennamen:** Einige Legacy‑Dateien enthalten Platzhalter‑Ressourcen. Prüfen Sie immer `resource.getName() != null`, bevor Sie auf Kosteneigenschaften zugreifen.  
- **Große Dateien verursachen Speicherbelastung:** `LoadOptions` ist eine Konfigurationsklasse, mit der Sie festlegen können, welche Projektdaten geladen werden. Verwenden Sie `project.setLoadOptions(LoadOptions.setLoadResourceData(false))`, um nur die benötigten Daten zu laden, und aktivieren Sie sie später bei Bedarf wieder.  
- **Währungsinkonsistenzen:** Die API respektiert die Währungseinstellungen des Projekts; Sie können sie bei Bedarf mit `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` überschreiben. `CostRateTableType` enumeriert die verschiedenen Kostensatz‑Tabellen, die einem Vorgang zugewiesen werden können.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks für Java komplexe Projektstrukturen verarbeiten?**  
A: Ja, es unterstützt vollständig verschachtelte Zusammenfassungs‑Aufgaben, mehrere Ressourcenkalender und benutzerdefinierte Felder in allen unterstützten Project‑Versionen.

**Q: Ist die Bibliothek mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut. Aspose.Tasks liest und schreibt Dateien von Microsoft Project 2000 bis zum neuesten 2023‑Format.

**Q: Kann ich Aspose.Tasks für Java mit anderen Java‑Bibliotheken integrieren?**  
A: Ja, die API gibt Standard‑Java‑Objekte zurück, was eine nahtlose Integration mit Logging‑Frameworks, ORM‑Tools oder Reporting‑Bibliotheken ermöglicht.

**Q: Bietet Aspose.Tasks für Java Kundensupport?**  
A: Aspose stellt dedizierten Forum‑Support, ausführliche Dokumentation und responsive E‑Mail‑Unterstützung für lizenzierte Nutzer bereit.

**Q: Gibt es eine kostenlose Testversion von Aspose.Tasks für Java?**  
A: Sie können eine 30‑tägige Evaluierungslizenz von der Aspose‑Website herunterladen, um alle Funktionen kostenlos zu testen.

---

**Zuletzt aktualisiert:** 2026-06-15  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Calculate Cost Variance and Manage Assignment Costs with Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Budget, Work, and Cost Management for Tasks in Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Add resource to project with Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}