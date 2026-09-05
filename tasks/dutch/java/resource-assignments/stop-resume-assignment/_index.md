---
date: 2026-07-14
description: Leer hoe u resource‑toewijzing in Java kunt stoppen, resource‑toewijzingen
  kunt beheren en voorbeelden kunt bekijken met Aspose.Tasks voor Java in deze stapsgewijze
  gids.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Stop en hervat resource‑toewijzingen in Aspose.Tasks
og_description: Stop resource‑toewijzing in Java met Aspose.Tasks. Deze tutorial laat
  zien hoe u toewijzingen kunt pauzeren en hervatten, datums kunt verwerken en de
  API kunt integreren zonder Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Stop resource‑toewijzing in Java – Aspose.Tasks-gids
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Hoe resource‑toewijzing in Java te stoppen – Hervatten met Aspose.Tasks
url: /nl/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe resource‑toewijzing in Java te stoppen – Hervatten met Aspose.Tasks

## Introductie
In deze tutorial leer je **how to stop resource assignment java** en later hervatten met Aspose.Tasks voor Java. Aspose.Tasks is een robuuste Java‑API die je in staat stelt Microsoft Project‑bestanden te lezen en te schrijven, schema's te manipuleren en resource‑toewijzingen te beheren — allemaal zonder dat Microsoft Project geïnstalleerd hoeft te zijn. We lopen elke stap door, leggen uit waarom elke regel belangrijk is, en delen praktische tips die je kunt toepassen op echte projectplannen.

## Snelle antwoorden
- **Wat betekent “stop assignment”?** Het markeert een resource‑toewijzing als tijdelijk inactief vanaf een specifieke stopdatum.  
- **Kan ik dezelfde toewijzing later hervatten?** Ja, door een hervattingsdatum in te stellen op dezelfde toewijzing.  
- **Heb ik Microsoft Project nodig om deze API te gebruiken?** Nee, Aspose.Tasks werkt onafhankelijk van Microsoft Project.  
- **Welke Java‑versie is vereist?** Java 8 of hoger wordt aanbevolen.  
- **Waar kan ik de bibliotheek downloaden?** Van de officiële Aspose.Tasks Java‑downloadpagina.

## Hoe resource‑toewijzing in Java te stoppen?
Laad je project, zoek de doel‑`ResourceAssignment`, stel de `STOP`‑datum in, stel eventueel een `RESUME`‑datum in, en sla vervolgens het bestand op. Deze reeks pauzeert het werk voor de opgegeven periode en activeert het automatisch opnieuw na de hervattingsdatum, waardoor je nauwkeurige controle krijgt over resource‑kalenders zonder handmatige bestandsbewerkingen.

## Wat betekent “how to stop assignment” in de context van Aspose.Tasks?
Het stoppen van een toewijzing vertelt de planner om het werk dat aan een resource is toegewezen na de **stop date** te negeren tot de **resume date** (indien aanwezig). Dit is nuttig voor het afhandelen van vakanties, uitval van apparatuur, of elke periode waarin een resource niet als actief moet worden beschouwd.

## Waarom Aspose.Tasks gebruiken om resource‑toewijzingen te beheren?
Aspose.Tasks stelt je in staat om programmatiche toewijzingsdatums te beheren, waardoor handmatige bewerkingen worden geëlimineerd en het risico op fouten wordt verminderd. Het ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan projecten verwerken met **tot 10.000 taken** terwijl het geheugenverbruik onder 200 MB blijft, omdat het gegevens streamt in plaats van het hele bestand in het geheugen te laden. De API draait op elk besturingssysteem dat Java ondersteunt, waardoor je cross‑platform flexibiliteit krijgt.

## Vereisten
- Java Development Kit (JDK) 8 of nieuwer geïnstalleerd.  
- Aspose.Tasks voor Java‑bibliotheek gedownload. Je kunt deze downloaden van [hier](https://releases.aspose.com/tasks/java/).  
- Basiskennis van Java‑programmeren.  

## Pakketten importeren
De `Project`, `ResourceAssignment` en `Asn` klassen bevinden zich in de `com.aspose.tasks` namespace. Importeer ze bovenaan je bronbestand:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Stap 1: Laad het projectbestand
De `Project`‑klasse is het top‑level object van Aspose.Tasks dat een enkel Microsoft Project‑bestand in het geheugen vertegenwoordigt. Het maken van een instantie laadt het bestand en geeft je toegang tot taken, resources en toewijzingen.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Stap 2: Doorloop resource‑toewijzingen
`ResourceAssignment`‑objecten geven alle toewijzingsgerelateerde velden weer. We stellen een **minimum datum** in om placeholder‑datums te filteren en vervolgens doorlopen we elke toewijzing. Dit patroon is het standaard *resource‑toewijzingsvoorbeeld* voor inspectie of wijziging.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Stap 3: Controleer stop‑ en hervattingsdatums
In dit blok onderzoeken we de `STOP`‑ en `RESUME`‑velden voor elke toewijzing. Als een datum vóór onze `minDate` ligt, behandelen we deze als niet ingesteld (`"NA"`); anders printen we de werkelijke datum. Deze logica is essentieel om **resource‑toewijzingen** correct te beheren.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Veelvoorkomende problemen en oplossingen
- **Null‑datums** – `ra.get(Asn.STOP)` kan `null` retourneren. Bescherm hiertegen door een null‑check toe te voegen voordat je `.before(minDate)` aanroept.  
- **Onjuist bestandspad** – Zorg ervoor dat `dataDir` eindigt met een pad‑scheidingsteken (`/` of `\\`) dat geschikt is voor jouw OS.  
- **Versiemismatch** – Gebruik de nieuwste versie van Aspose.Tasks voor Java om ontbrekende enum‑waarden te voorkomen.  

## Veelgestelde vragen

**Q: Hoe kan ik programmatically een stopdatum voor een toewijzing instellen?**  
A: Gebruik `ra.set(Asn.STOP, yourDateObject);` waarbij `yourDateObject` een `java.util.Date` is.

**Q: Wat gebeurt er als de hervattingsdatum eerder is dan de stopdatum?**  
A: De API handhaaft geen chronologische volgorde; echter zal de planner de toewijzing alleen als actief beschouwen na de latere van de twee datums, dus moet je de datums zelf valideren.

**Q: Kan ik toewijzingen filteren tot alleen diegene met een ingestelde stopdatum?**  
A: Ja, door door `prj.getResourceAssignments()` te itereren en te controleren of `ra.get(Asn.STOP) != null`.

**Q: Is het mogelijk om een stopdatum te verwijderen zodra deze is ingesteld?**  
A: Stel de stopdatum in op `null` met `ra.set(Asn.STOP, null);` en sla vervolgens het project op.

**Q: Ondersteunt Aspose.Tasks andere datumgerelateerde velden zoals start, finish of actual start?**  
A: Absoluut. De `Asn`‑enum biedt constanten voor alle toewijzingsvelden, zoals `Asn.START`, `Asn.FINISH`, enz.

## Conclusie
Door deze stappen te volgen weet je nu **how to stop resource assignment java**, kun je de stop‑/hervattingsdatums inspecteren en de toewijzing hervatten wanneer nodig. Deze mogelijkheid stelt je in staat **resource‑toewijzingen** nauwkeuriger te beheren, vooral in scenario's zoals vakanties van resources of uitval van apparatuur. Voel je vrij om het voorbeeld uit te breiden om datums bij te werken, rapporten te genereren, of te integreren met je eigen planningslogica.

---

**Last Updated:** 2026-07-14  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Gerelateerde tutorials

- [Resource‑toewijzingen maken in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Hoe kostenvariatie te berekenen en toewijzingskosten te beheren met Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Hoe notities toe te voegen aan resource‑toewijzingen in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}