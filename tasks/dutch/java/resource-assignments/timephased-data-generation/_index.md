---
date: 2026-01-10
description: Leer hoe u de contour kunt wijzigen en tijdgebaseerde gegevens kunt genereren
  voor resource‑toewijzingen met Aspose.Tasks voor Java, waardoor de efficiëntie van
  projectbeheer wordt verbeterd.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe de contour wijzigen in Aspose.Tasks voor tijdgephaseerde gegevens
url: /nl/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe contour wijzigen in Aspose.Tasks voor tijdgephaseerde gegevens

## Introductie
In deze tutorial ontdek je **hoe je een contour wijzigt** voor een resource‑toewijzing en tijdgephaseerde gegevens genereert met Aspose.Tasks voor Java. Tijdgephaseerde gegevens tonen de verdeling van werk over de projecttijdlijn, waardoor je planningen kunt verfijnen, werklast kunt balanceren en datagedreven beslissingen kunt nemen.

## Snelle antwoorden
- **Wat is een contour?** Een werkcontour bepaalt hoe inspanning wordt verdeeld over de duur van een taak (bijv. Flat, Turtle, Bell).  
- **Waarom een contour wijzigen?** Om realistische werkpatronen weer te geven, zoals front‑loading of back‑loading van inspanning.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (elke recente versie).  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Kan ik de resultaten in de console zien?** Het voorbeeld print startdatums en waarden voor elk tijdgephaseerd segment.

## Wat betekent “hoe contour wijzigen”?
Een contour wijzigen betekent het bijwerken van de `WORK_CONTOUR`‑eigenschap van een `ResourceAssignment`. Aspose.Tasks ondersteunt verschillende vooraf gedefinieerde contouren (Flat, Turtle, Bell, enz.) die bepalen hoe werk over de tijd wordt toegewezen.

## Waarom Aspose.Tasks gebruiken om tijdgephaseerde gegevens te genereren?
- **Nauwkeurige rapportage:** Exporteer een precieze werkverdeling voor rapportagetools.  
- **Scenario‑planning:** Test verschillende contouren zonder het originele schema te wijzigen.  
- **Automatisering:** Integreer in CI‑pipelines om de projectgezondheid automatisch te valideren.

## Vereisten
Voordat we beginnen, zorg ervoor dat je de volgende vereisten hebt:
1. Java Development Kit (JDK): Zorg ervoor dat je JDK op je systeem hebt geïnstalleerd. Je kunt JDK downloaden en installeren via [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks voor Java‑bibliotheek: Je moet de Aspose.Tasks voor Java‑bibliotheek hebben. Je kunt deze downloaden van de [website](https://releases.aspose.com/tasks/java/).

## Importer pakketten
Laten we eerst de benodigde pakketten importeren om met Aspose.Tasks te werken:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Stap 1: Lees het bron‑MPP‑bestand
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Stap 2: Haal taak en resource‑toewijzing op
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Hoe contour wijzigen – Flat (Standaard)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe contour wijzigen – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Veelvoorkomende problemen & tips
- **Contour wordt niet bijgewerkt?** Zorg ervoor dat je `firstRA.set(Asn.WORK_CONTOUR, …)` *vóór* het ophalen van tijdgephaseerde gegevens aanroept.
- **Onverwachte waarden?** Controleer of de start‑ en einddatums van de taak correct zijn ingesteld in het bron‑MPP.
- **Prestatie‑tip:** Hergebruik dezelfde `Project`‑instantie bij het itereren door meerdere contouren om onnodige bestands‑I/O te vermijden.

## Veelgestelde vragen
### Kan ik Aspose.Tasks gebruiken met andere Java‑bibliotheken?
Ja, Aspose.Tasks kan worden geïntegreerd met andere Java‑bibliotheken om de mogelijkheden voor projectbeheer uit te breiden.

### Is Aspose.Tasks geschikt voor grootschalige enterprise‑projecten?
Absoluut, Aspose.Tasks is ontworpen om projecten van elke omvang te verwerken, inclusief grootschalige enterprise‑initiatieven.

### Biedt Aspose.Tasks ondersteuning voor verschillende projectbestandformaten?
Ja, Aspose.Tasks ondersteunt verschillende formaten, zoals MPP, XML en MPX.

### Kan ik werkcontouren aanpassen aan mijn projectvereisten?
Ja, je kunt aangepaste werkcontouren definiëren die passen bij specifieke planningsbehoeften.

### Is er een community‑forum waar ik hulp kan krijgen bij Aspose.Tasks?
Ja, je kunt het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken voor ondersteuning en discussies.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}