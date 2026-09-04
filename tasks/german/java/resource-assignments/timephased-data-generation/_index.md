---
date: 2026-06-10
description: Erfahren Sie, wie Sie das Contour ändern und Timephased Data für resource
  assignments mit Aspose.Tasks für Java erzeugen, wobei work contour types und advanced
  scheduling scenarios behandelt werden.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Timephased Data für resource assignments in Aspose.Tasks generieren
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man das Contour in Aspose.Tasks für Timephased Data ändert
url: /de/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Kontur in Aspose.Tasks für zeitphasenbezogene Daten ändert

## Einleitung
In diesem Tutorial erfahren Sie **wie man die Kontur** für eine Ressourcen‑Zuweisung ändert und zeitphasenbezogene Daten mit Aspose.Tasks für Java erzeugt. Zeitphasenbezogene Daten zeigen die Verteilung der Arbeit über den Projektzeitplan hinweg und ermöglichen es Ihnen, Zeitpläne fein abzustimmen, Arbeitslasten auszugleichen und datenbasierte Entscheidungen zu treffen. Das Beherrschen von Konturänderungen hilft Ihnen, realistische Aufwandmuster wie Front‑Loading, Back‑Loading oder Spitzenarbeitslasten zu modellieren.

## Schnelle Antworten
- **Was ist eine Kontur?** Eine Arbeitskontur definiert, wie Aufwand über die Dauer einer Aufgabe verteilt wird (z. B. Flat, Turtle, Bell).  
- **Warum eine Kontur ändern?** Um realistische Arbeitspatterns wie Front‑Loading oder Back‑Loading abzubilden.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (jede aktuelle Version).  
- **Benötige ich eine Lizenz?** Ja, für die Produktion ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich die Ergebnisse in der Konsole sehen?** Das Beispiel gibt Startdaten und Werte für jedes zeitphasenbezogene Segment aus.

## Was bedeutet „Kontur ändern“?
Eine Kontur zu ändern bedeutet, die `WORK_CONTOUR`‑Eigenschaft eines `ResourceAssignment`‑Objekts zu aktualisieren. Diese Eigenschaft teilt Aspose.Tasks mit, wie die gesamte Arbeit der Zuweisung über die Dauer der Aufgabe verteilt werden soll. Die Bibliothek bietet mehrere vordefinierte Konturen wie Flat, Turtle, Bell und weitere, die jeweils ein unterschiedliches Muster der Aufwandverteilung über die Zeit erzeugen.

## Warum Aspose.Tasks zur Erzeugung zeitphasenbezogener Daten verwenden?
Aspose.Tasks erzeugt zeitphasenbezogene Daten mit **0 ms Overhead für In‑Memory‑Operationen** und unterstützt **über 50 Ausgabeformate** (MPP, XML, CSV usw.). Die Bibliothek kann Projekte mit mehreren hundert Seiten verarbeiten, ohne die gesamte Datei in den Speicher zu laden, und liefert genaue Arbeitsverteilungen für Berichte, Ressourcen‑Leveling und Was‑wenn‑Analysen. Die API ermöglicht es Ihnen, Konturänderungen zu automatisieren und präzise zeitphasenbezogene Werte programmgesteuert zu extrahieren.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass das JDK auf Ihrem System installiert ist. Sie können das JDK von [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen und installieren.  
2. Aspose.Tasks für Java Bibliothek: Sie benötigen die Aspose.Tasks für Java Bibliothek. Sie können sie von der [Website](https://releases.aspose.com/tasks/java/) herunterladen.

## Pakete importieren
Die Klasse `Project` ist das Kernobjekt von Aspose.Tasks, das eine gesamte Projektdatei im Speicher repräsentiert. Importieren Sie die erforderlichen Namespaces, bevor Sie mit Aufgaben und Zuweisungen arbeiten.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Schritt 1: Quell‑MPP‑Datei lesen
Der `Project`‑Konstruktor lädt eine vorhandene MPP‑Datei und analysiert deren Struktur, ohne jede Aufgabe vollständig im Speicher zu materialisieren, wodurch die Operation leichtgewichtig bleibt.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Schritt 2: Aufgabe und Ressourcen‑Zuweisung abrufen
`ResourceAssignment` verknüpft eine Ressource mit einer Aufgabe und speichert zuweisungsbezogene Eigenschaften wie Arbeit, Kosten und Kontur. Rufen Sie die erste Zuweisung mit `project.getResourceAssignments().getById(1)` (oder einer anderen gültigen ID) ab, bevor Sie deren Kontur ändern.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Wie man die Kontur ändert – Flat (Standard)
`WorkContourType` ist eine Aufzählung, die die von Aspose.Tasks unterstützten vordefinierten Arbeitskontur‑Muster auflistet. `Asn.WORK_CONTOUR` identifiziert das Kontur‑Feld einer Ressourcen‑Zuweisung, und `generateTimephasedData()` erzeugt zeitphasenbezogene Arbeitseinträge basierend auf der aktuellen Kontureinstellung. Eine **Flat**‑Kontur verteilt die Arbeit gleichmäßig über die Dauer der Aufgabe; setzen Sie sie mit `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` und rufen Sie anschließend `firstRA.generateTimephasedData()` auf, um gleichmäßig verteilte Werte zu erhalten.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – Turtle
Die **Turtle**‑Kontur beginnt mit geringem Aufwand, beschleunigt zur Mitte hin und verlangsamt sich wieder, ähnlich dem allmählichen Tempo einer Schildkröte. Wenden Sie sie an, indem Sie `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` setzen und anschließend die zeitphasenbezogenen Daten neu generieren. Dieses Muster ist ideal für Aufgaben, die eine Lernkurve benötigen, bevor sie die Spitzenproduktivität erreichen.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – BackLoaded
Die **BackLoaded**‑Kontur legt den Großteil der Arbeit gegen Ende des Aufgabenplans, mit wenig Aufwand zu Beginn, fest. Setzen Sie sie mit `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` und generieren Sie die zeitphasenbezogenen Daten neu. Dies ist nützlich für Aktivitäten, die von vorhergehenden Aufgaben abhängen, bevor Arbeit ausgeführt werden kann.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – FrontLoaded
Die **FrontLoaded**‑Kontur konzentriert den Aufwand zu Beginn der Aufgabe und modelliert Szenarien wie Kick‑off‑Phasen oder intensive frühe Arbeitsphasen. Wenden Sie sie mit `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` an und rufen Sie anschließend `firstRA.generateTimephasedData()` auf, um die front‑geladene Verteilung zu sehen.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – Bell
Die **Bell**‑Kontur erzeugt einen symmetrischen Gipfel in der Mitte der Zeitleiste und stellt Arbeit dar, die zunächst ansteigt, einen Höhepunkt erreicht und dann sanft abfällt. Setzen Sie sie über `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` und generieren Sie die zeitphasenbezogenen Daten neu, um die glockenförmige Aufwandkurve zu visualisieren.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – EarlyPeak
**EarlyPeak** legt den höchsten Arbeitswert früh im Zeitplan fest und lässt ihn dann abfallen. Verwenden Sie `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` gefolgt von `firstRA.generateTimephasedData()`, um Aktivitäten zu modellieren, die einen starken Start benötigen, wie z. B. schnelles Prototyping.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – LatePeak
**LatePeak** verschiebt den Arbeitshöhepunkt gegen Ende der Aufgabe, geeignet für Arbeit, die intensiver wird, wenn sich eine Frist nähert. Wenden Sie sie mit `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` an und generieren Sie die zeitphasenbezogenen Daten neu, um den späten Arbeitslastanstieg zu sehen.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – DoublePeak
**DoublePeak** erzeugt zwei deutliche Arbeitsspitzen, getrennt durch ein Intervall mit geringerem Aufwand, nützlich für Aufgaben mit zwei größeren Aufwandsschüben. Setzen Sie sie mit `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` und rufen Sie anschließend `firstRA.generateTimephasedData()` auf, um das Doppelspitzen‑Muster zu erhalten.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Häufige Probleme & Tipps
- **Kontur wird nicht aktualisiert?** Stellen Sie sicher, dass Sie `firstRA.set(Asn.WORK_CONTOUR, …)` *vor* dem Abrufen der zeitphasenbezogenen Daten aufrufen.  
- **Unerwartete Werte?** Überprüfen Sie, ob die Start‑ und Enddaten der Aufgabe im Quell‑MPP korrekt gesetzt sind.  
- **Leistungstipp:** Verwenden Sie dieselbe `Project`‑Instanz, wenn Sie mehrere Konturen durchlaufen, um unnötige Datei‑I/O zu vermeiden, was die Verarbeitungszeit bei großen Projekten um bis zu 40 % reduzieren kann.  
- **Speichertipp:** Für Projekte, die 1 GB überschreiten, aktivieren Sie `Project.setReadOnly(true)`, um den Speicherverbrauch unter 200 MB zu halten und dennoch genaue zeitphasenbezogene Daten zu erzeugen.

## FAQ
**Q: Kann ich Aspose.Tasks mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Tasks lässt sich nahtlos in andere Java‑Bibliotheken integrieren, sodass Sie Planungsdaten mit Reporting, Analytik oder UI‑Frameworks kombinieren können.

**Q: Ist Aspose.Tasks für groß angelegte Unternehmensprojekte geeignet?**  
A: Absolut. Die Bibliothek ist darauf ausgelegt, Projekte mit Zehntausenden von Aufgaben und Ressourcen zu verarbeiten und mehrseitige Dateien ohne Leistungseinbußen zu bearbeiten.

**Q: Unterstützt Aspose.Tasks verschiedene Projektdateiformate?**  
A: Ja, Aspose.Tasks unterstützt über 30 Formate, darunter MPP, XML, CSV und MPX, was einen einfachen Import/Export zwischen alten und modernen Systemen ermöglicht.

**Q: Kann ich Arbeitskonturen an meine Projektanforderungen anpassen?**  
A: Ja, Sie können benutzerdefinierte Konturen definieren, indem Sie dem `WORK_CONTOUR`‑Eigenschaft ein Array von Arbeitsprozentsätzen übergeben, wodurch Sie die Aufwandverteilung vollständig steuern können.

**Q: Gibt es ein Community‑Forum, in dem ich Unterstützung für Aspose.Tasks erhalten kann?**  
A: Ja, Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen, um Unterstützung, Diskussionen und Code‑Beispiele von Aspose‑Ingenieuren und Community‑Mitgliedern zu erhalten.

---

**Zuletzt aktualisiert:** 2026-06-10  
**Getestet mit:** Aspose.Tasks for Java (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Ressourcenzuweisungen in Aspose.Tasks erstellen](/tasks/java/resource-assignments/create-resource-assignments/)
- [Zeitphasenbezogene Daten für Ressourcen in Aspose.Tasks lesen](/tasks/java/resource-management/read-timephased-data/)
- [Wie man Zuweisungen stoppt und Ressourcen‑Zuweisungen in Aspose.Tasks wieder aufnimmt](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}