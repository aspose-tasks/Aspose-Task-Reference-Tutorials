---
date: 2026-01-18
description: Leer hoe u het standaardtarief en andere resource‑eigenschappen in MS
  Project instelt met Aspose.Tasks voor Java, inclusief hoe u een resource aan MS
  Project toevoegt en resources efficiënt beheert.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe het standaardtarief voor resources in Aspose.Tasks instellen
url: /nl/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Standaardtarief instellen voor resources in Aspose.Tasks

## Introductie
Als je Java‑toepassingen bouwt die moeten communiceren met Microsoft Project‑bestanden, is **het instellen van het standaardtarief** voor een resource een van de meest voorkomende taken. In deze tutorial leer je hoe je **het standaardtarief** en andere resource‑eigenschappen kunt instellen met Aspose.Tasks voor Java. Aan het einde van de gids kun je een projectobject maken, een resource toevoegen aan een MS Project‑bestand en MS Project‑resources met vertrouwen beheren.

## Snelle antwoorden
- **Wat is de primaire klasse om met een Project‑bestand te werken?** `Project`
- **Welke methode voegt een nieuwe resource toe?** `project.getResources().add()`
- **Hoe stel je het standaardtarief in?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Heb ik een licentie nodig voor productie?** Ja, een geldige Aspose.Tasks‑licentie is vereist.
- **Welke Java‑versie wordt ondersteund?** Java 8+ (de nieuwste JDK wordt aanbevolen).

## Wat is “standaardtarief instellen”?
De *set standard rate*‑bewerking kent een standaard uurtarief toe aan een resource. Projectmanagers gebruiken deze waarde om arbeidskosten te berekenen, kostrapporten te genereren en budgetten te voorspellen.

## Waarom tarieven instellen met Aspose.Tasks?
- **Geen Microsoft Project‑installatie nodig** – bewerk bestanden rechtstreeks vanuit Java.
- **Volledige nauwkeurigheid** – alle resource‑velden, inclusief overuren en kostentarieven, blijven behouden.
- **Cross‑platform** – werkt op Windows, Linux en macOS.
- **Automatisering vriendelijk** – ideaal voor batchverwerking of integratie met CI‑pipelines.

## Voorvereisten
Zorg ervoor dat je het volgende hebt voordat je begint:

### Java Development Environment Setup
1. **Installeer JDK:** Zorg ervoor dat je Java Development Kit (JDK) op je systeem hebt geïnstalleerd. Je kunt het downloaden van de [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **IDE‑configuratie:** Kies een Integrated Development Environment (IDE) zoals IntelliJ IDEA, Eclipse of NetBeans en zorg dat deze op je machine is ingesteld.

### Aspose.Tasks for Java Installation
1. **Download Aspose.Tasks for Java:** Ga naar de [downloadpagina](https://releases.aspose.com/tasks/java/) en haal de nieuwste versie van Aspose.Tasks for Java.
2. **Integreren met project:** Voeg de Aspose.Tasks for Java‑bibliotheek toe aan je Java‑project door deze als afhankelijkheid toe te voegen.

## Pakketten importeren
Om te beginnen moet je de benodigde pakketten van Aspose.Tasks for Java in je project importeren. Deze stap zorgt ervoor dat je toegang hebt tot de vereiste functionaliteiten.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Stap 1: Maak een Project‑object
Het maken van een **project object** is de eerste stap bij elke MS Project‑bewerking. Het vertegenwoordigt het volledige projectbestand in het geheugen.

```java
Project project = new Project();
```

## Stap 2: Voeg een resource toe (add resource ms project)
Nu gaan we **resource MS Project** toevoegen met behulp van de Resources‑collectie. De resource‑naam kan alles zijn die logisch is voor je planning.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Stap 3: Stel resource‑eigenschappen in (how to set rates)
Hier stellen we **het standaardtarief** in en laten we ook zien hoe je een overurenttarief kunt instellen. Deze tarieven worden opgeslagen als `BigDecimal`‑waarden om precisie te behouden.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| `NullPointerException` bij het aanroepen van `set` | De resource is niet correct toegevoegd. | Zorg ervoor dat `project.getResources().add()` een niet‑null `Resource` retourneert. |
| Tarieven verschijnen als 0 in het opgeslagen bestand | Gebruik van `int` in plaats van `BigDecimal`. | Gebruik altijd `BigDecimal.valueOf()` voor monetaire waarden. |
| Licentie niet gevonden | Licentiebestand niet geladen vóór het aanmaken van `Project`. | Laad de licentie (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) aan het begin van je programma. |

## Conclusie
Door deze stappen te volgen heb je geleerd hoe je een **project object** maakt, een **resource MS Project** toevoegt en een **standaardtarief** instelt, samen met andere resource‑eigenschappen. Dit stelt je in staat om kostencalculaties te automatiseren, aangepaste rapporten te genereren en MS Project‑resources volledig te beheren vanuit Java.

## Veelgestelde vragen
### Kan Aspose.Tasks for Java complexe MS Project‑bestanden aan?
Ja, Aspose.Tasks for Java kan een breed scala aan MS Project‑bestandsformaten aan, inclusief complexe bestanden met uitgebreide taak‑hiërarchieën.

### Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?
Ja, je kunt een gratis proefversie van Aspose.Tasks for Java krijgen via [hier](https://releases.aspose.com/).

### Waar kan ik ondersteuning vinden voor Aspose.Tasks for Java?
Je kunt hulp zoeken en deelnemen aan discussies over Aspose.Tasks for Java op het [ondersteuningsforum](https://forum.aspose.com/c/tasks/15).

### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks for Java?
Je kunt een tijdelijke licentie verkrijgen via de [pagina voor tijdelijke licenties](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

### Waar kan ik een gelicentieerde versie van Aspose.Tasks for Java kopen?
Je kunt een gelicentieerde versie van Aspose.Tasks for Java kopen via de [aankooppagina](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-01-18  
**Getest met:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur:** Aspose