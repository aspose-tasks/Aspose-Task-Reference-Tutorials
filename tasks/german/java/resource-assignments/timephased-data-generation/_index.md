---
date: 2026-01-10
description: Erfahren Sie, wie Sie die Kontur ändern und zeitbezogene Daten für Ressourcen‑Zuweisungen
  mit Aspose.Tasks für Java generieren, um die Effizienz im Projektmanagement zu verbessern.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man die Kontur in Aspose.Tasks für zeitbezogene Daten ändert
url: /de/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Kontur in Aspose.Tasks für zeitbezogene Daten ändert

## Einführung
In diesem Tutorial erfahren Sie **wie man die Kontur** für eine Ressourcen‑Zuweisung ändert und zeitbezogene Daten mit Aspose.Tasks für Java erzeugt. Zeitbezogene Daten zeigen die Verteilung der Arbeit über den Projektzeitplan hinweg und ermöglichen es Ihnen, Zeitpläne fein abzustimmen, Arbeitslasten auszugleichen und datenbasierte Entscheidungen zu treffen.

## Schnelle Antworten
- **Was ist eine Kontur?** Eine Arbeitskontur definiert, wie Aufwand über die Dauer einer Aufgabe verteilt wird (z. B. Flat, Turtle, Bell).  
- **Warum eine Kontur ändern?** Um realistische Arbeitsmuster wie Front‑Loading oder Back‑Loading des Aufwands abzubilden.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (jede aktuelle Version).  
- **Benötige ich eine Lizenz?** Ja, für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich die Ergebnisse in der Konsole sehen?** Das Beispiel gibt Startdaten und Werte für jedes zeitbezogene Segment aus.

## Was bedeutet „wie man die Kontur ändert“?
Das Ändern einer Kontur bedeutet, die Eigenschaft `WORK_CONTOUR` einer `ResourceAssignment` zu aktualisieren. Aspose.Tasks unterstützt mehrere vordefinierte Konturen (Flat, Turtle, Bell usw.), die beeinflussen, wie Arbeit über die Zeit verteilt wird.

## Warum Aspose.Tasks zur Erzeugung zeitbezogener Daten verwenden?
- **Genaues Reporting:** Präzise Arbeitsverteilung für Reporting‑Tools exportieren.  
- **Szenario‑Planung:** Verschiedene Konturen testen, ohne den ursprünglichen Zeitplan zu ändern.  
- **Automatisierung:** In CI‑Pipelines integrieren, um den Projektstatus automatisch zu validieren.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass das JDK auf Ihrem System installiert ist. Sie können das JDK von [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen und installieren.
2. Aspose.Tasks für Java‑Bibliothek: Sie benötigen die Aspose.Tasks für Java‑Bibliothek. Sie können sie von der [Website](https://releases.aspose.com/tasks/java/) herunterladen.

## Pakete importieren
Zuerst importieren wir die notwendigen Pakete, um mit Aspose.Tasks zu arbeiten:
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
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Schritt 2: Aufgabe und Ressourcen‑Zuweisung abrufen
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Wie man die Kontur ändert – Flat (Standard)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Wie man die Kontur ändert – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Häufige Probleme & Tipps
- **Kontur wird nicht aktualisiert?** Stellen Sie sicher, dass Sie `firstRA.set(Asn.WORK_CONTOUR, …)` *vor* dem Abrufen der zeitbezogenen Daten aufrufen.
- **Unerwartete Werte?** Überprüfen Sie, ob die Start‑ und Enddaten der Aufgabe in der Quell‑MPP korrekt gesetzt sind.
- **Performance‑Tipp:** Verwenden Sie dieselbe `Project`‑Instanz, wenn Sie durch mehrere Konturen iterieren, um unnötige Datei‑I/O zu vermeiden.

## FAQ

### Kann ich Aspose.Tasks mit anderen Java‑Bibliotheken verwenden?
Ja, Aspose.Tasks kann mit anderen Java‑Bibliotheken integriert werden, um die Projektmanagement‑Funktionen zu erweitern.

### Ist Aspose.Tasks für groß angelegte Unternehmensprojekte geeignet?
Absolut, Aspose.Tasks ist darauf ausgelegt, Projekte jeder Größe zu bewältigen, einschließlich groß angelegter Unternehmensinitiativen.

### Unterstützt Aspose.Tasks verschiedene Projektdateiformate?
Ja, Aspose.Tasks unterstützt eine Vielzahl von Formaten, wie MPP, XML und MPX.

### Kann ich Arbeitskonturen an meine Projektanforderungen anpassen?
Ja, Sie können benutzerdefinierte Arbeitskonturen definieren, um spezifische Planungsanforderungen zu erfüllen.

### Gibt es ein Community‑Forum, in dem ich Unterstützung für Aspose.Tasks erhalten kann?
Ja, Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung und Diskussionen besuchen.

---

**Zuletzt aktualisiert:** 2026-01-10  
**Getestet mit:** Aspose.Tasks für Java (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}