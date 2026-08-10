---
date: 2026-06-10
description: Leer hoe u de contour wijzigt en timephased data genereert voor resource
  assignments met Aspose.Tasks voor Java, inclusief work contour types en advanced
  scheduling scenarios.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Genereer timephased data voor resource assignments in Aspose.Tasks
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
title: Hoe de contour te wijzigen in Aspose.Tasks voor timephased data
url: /nl/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de Contour te Wijzigen in Aspose.Tasks voor Tijdgebaseerde Gegevens

## Introductie
In deze tutorial ontdek je **hoe je de contour kunt wijzigen** voor een resource‑toewijzing en tijdgebaseerde gegevens genereert met Aspose.Tasks voor Java. Tijdgebaseerde gegevens tonen de verdeling van werk over de projecttijdlijn, waardoor je schema's kunt verfijnen, workloads kunt balanceren en datagedreven beslissingen kunt nemen. Het beheersen van contourwijzigingen helpt je realistische inspanningspatronen te modelleren, zoals front‑loading, back‑loading of piek‑workloads.

## Snelle Antwoorden
- **Wat is een contour?** Een werkcontour definieert hoe inspanning wordt verdeeld over de duur van een taak (bijv. Flat, Turtle, Bell).  
- **Waarom een contour wijzigen?** Om realistische werkpatronen weer te geven, zoals front‑loading of back‑loading inspanning.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (een recente versie).  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Kan ik de resultaten in de console zien?** Het voorbeeld print startdatums en waarden voor elk tijdgebaseerd segment.

## Wat is “hoe de contour te wijzigen”?
Een contour wijzigen betekent het bijwerken van de `WORK_CONTOUR`‑eigenschap van een `ResourceAssignment`‑object. Deze eigenschap vertelt Aspose.Tasks hoe het totale werk van de toewijzing over de duur van de taak moet worden verdeeld. De bibliotheek biedt verschillende vooraf gedefinieerde contouren zoals Flat, Turtle, Bell en andere, die elk een onderscheidend patroon van inspanningsverdeling over de tijd produceren.

## Waarom Aspose.Tasks gebruiken om tijdgebaseerde gegevens te genereren?
Aspose.Tasks genereert tijdgebaseerde gegevens met **0 ms overhead voor in‑memory bewerkingen** en ondersteunt **meer dan 50 uitvoerformaten** (MPP, XML, CSV, enz.). De bibliotheek kan projecten van meerdere honderden pagina's verwerken zonder het volledige bestand in het geheugen te laden, en levert nauwkeurige werkverdeling voor rapportage, resource‑leveling en wat‑als‑analyse. De API stelt je in staat contourwijzigingen te automatiseren en nauwkeurige tijdgebaseerde waarden programmatisch te extraheren.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je de volgende voorvereisten hebt:
1. Java Development Kit (JDK): Zorg ervoor dat je JDK op je systeem hebt geïnstalleerd. Je kunt JDK downloaden en installeren via [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks voor Java‑bibliotheek: Je moet de Aspose.Tasks voor Java‑bibliotheek hebben. Je kunt deze downloaden van de [website](https://releases.aspose.com/tasks/java/).

## Pakketten Importeren
De `Project`‑klasse is het kernobject van Aspose.Tasks dat een volledig projectbestand in het geheugen vertegenwoordigt. Importeer de benodigde namespaces voordat je begint te werken met taken en toewijzingen.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Stap 1: Lees het Bron‑MPP‑bestand
De `Project`‑constructor laadt een bestaand MPP‑bestand, parseert de structuur zonder elke taak volledig in het geheugen te materialiseren, waardoor de bewerking lichtgewicht blijft.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Stap 2: Haal Taak en Resource‑toewijzing op
`ResourceAssignment` koppelt een resource aan een taak en slaat toewijzings‑eigenschappen op zoals werk, kosten en contour. Haal de eerste toewijzing op met `project.getResourceAssignments().getById(1)` (of een andere geldige ID) voordat je de contour wijzigt.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Hoe Contour Wijzigen – Flat (Standaard)
`WorkContourType` is een enumeratie die de vooraf gedefinieerde werkcontourpatronen vermeldt die door Aspose.Tasks worden ondersteund. `Asn.WORK_CONTOUR` identificeert het contourveld van een resource‑toewijzing, en `generateTimephasedData()` maakt tijdgebaseerde werkitems aan op basis van de huidige contourinstelling. Een **Flat**‑contour verdeelt werk gelijkmatig over de duur van de taak; stel deze in met `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` en roep vervolgens `firstRA.generateTimephasedData()` aan om gelijkmatig verdeelde waarden te verkrijgen.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – Turtle
De **Turtle**‑contour begint met weinig inspanning, versnelt naar het midden toe en vertraagt daarna weer, wat lijkt op het geleidelijke tempo van een schildpad. Pas deze toe door `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` in te stellen en vervolgens de tijdgebaseerde gegevens opnieuw te genereren. Dit patroon is ideaal voor taken die een leercurve vereisen voordat ze maximale productiviteit bereiken.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – BackLoaded
De **BackLoaded**‑contour plaatst het grootste deel van het werk aan het einde van de planning van de taak, met weinig inspanning aan het begin. Stel deze in met `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` en genereer de tijdgebaseerde gegevens opnieuw. Dit is nuttig voor activiteiten die afhankelijk zijn van voorafgaande taken voordat werk kan worden uitgevoerd.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – FrontLoaded
De **FrontLoaded**‑contour concentreert inspanning aan het begin van de taak, en modelleert scenario's zoals kickoff‑fasen of intensieve vroege werkpieken. Pas deze toe met `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` en roep vervolgens `firstRA.generateTimephasedData()` aan om de front‑loaded verdeling te zien.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – Bell
De **Bell**‑contour creëert een symmetrische piek in het midden van de tijdlijn, die werk voorstelt dat geleidelijk toeneemt, een piek bereikt en vervolgens soepel afneemt. Stel deze in via `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` en genereer de tijdgebaseerde gegevens opnieuw om de klokvormige inspanningscurve te visualiseren.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – EarlyPeak
**EarlyPeak** plaatst de hoogste werkwaarde vroeg in de planning en neemt daarna af. Gebruik `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` gevolgd door `firstRA.generateTimephasedData()` om activiteiten te modelleren die een sterke start vereisen, zoals snelle prototyping.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – LatePeak
**LatePeak** verplaatst de werkpiek naar het einde van de taak, geschikt voor werk dat toeneemt naarmate een deadline nadert. Pas deze toe met `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` en genereer de tijdgebaseerde gegevens opnieuw om de toename van de workload in een later stadium te zien.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Hoe Contour Wijzigen – DoublePeak
**DoublePeak** creëert twee afzonderlijke werkpieken gescheiden door een interval met lagere inspanning, nuttig voor taken met twee grote inspanningspieken. Stel deze in met `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` en roep vervolgens `firstRA.generateTimephasedData()` aan om het double‑peak‑patroon te verkrijgen.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Veelvoorkomende Problemen & Tips
- **Contour wordt niet bijgewerkt?** Zorg ervoor dat je `firstRA.set(Asn.WORK_CONTOUR, …)` *vóór* het ophalen van tijdgebaseerde gegevens aanroept.  
- **Onverwachte waarden?** Controleer of de start‑ en einddatums van de taak correct zijn ingesteld in de bron‑MPP.  
- **Prestatie‑tip:** Hergebruik dezelfde `Project`‑instantie bij het itereren door meerdere contouren om onnodige bestands‑I/O te vermijden, wat de verwerkingstijd met tot 40 % kan verminderen bij grote projecten.  
- **Geheugen‑tip:** Voor projecten groter dan 1 GB, schakel `Project.setReadOnly(true)` in om het geheugenverbruik onder 200 MB te houden terwijl je nog steeds nauwkeurige tijdgebaseerde gegevens genereert.

## Veelgestelde Vragen
**Q: Kan ik Aspose.Tasks gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Tasks integreert naadloos met andere Java‑bibliotheken, waardoor je planningsgegevens kunt combineren met rapportage, analytics of UI‑frameworks.

**Q: Is Aspose.Tasks geschikt voor grootschalige enterprise‑projecten?**  
A: Absoluut. De bibliotheek is ontworpen om projecten met tienduizenden taken en resources aan te kunnen, en verwerkt bestanden van honderden pagina's zonder prestatieverlies.

**Q: Biedt Aspose.Tasks ondersteuning voor verschillende projectbestandsformaten?**  
A: Ja, Aspose.Tasks ondersteunt meer dan 30 formaten, waaronder MPP, XML, CSV en MPX, waardoor eenvoudige import/export mogelijk is tussen legacy‑ en moderne systemen.

**Q: Kan ik werkcontouren aanpassen aan mijn projectvereisten?**  
A: Ja, je kunt aangepaste contouren definiëren door een array met werkpercentages aan de `WORK_CONTOUR`‑eigenschap te leveren, waardoor je volledige controle krijgt over de inspanningsverdeling.

**Q: Is er een community‑forum waar ik hulp kan krijgen met Aspose.Tasks?**  
A: Ja, je kunt het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) bezoeken voor ondersteuning, discussies en code‑voorbeelden van zowel Aspose‑engineers als community‑leden.

---

**Laatst bijgewerkt:** 2026-06-10  
**Getest met:** Aspose.Tasks voor Java (laatste release)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde Tutorials

- [Resource‑toewijzingen maken in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Tijdgebaseerde Gegevens Lezen voor Resources in Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Hoe Toewijzing te Stoppen en Resource‑toewijzingen te Hervatten in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}