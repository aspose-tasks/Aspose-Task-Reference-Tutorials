---
date: 2025-12-07
description: Leer hoe je **een testproject maakt** en **een aangepast veld toevoegt**
  terwijl je Microsoft Project‑bestanden manipuleert met Aspose.Tasks voor Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Maak testproject en gebruik formules met Aspose.Tasks voor Java
url: /nl/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak testproject en gebruik formules met Aspose.Tasks voor Java

## Introductie
In deze tutorial **maak je testproject**-bestanden, voeg je een aangepast veld toe, en werk je met MS Project-formules met behulp van de Aspose.Tasks-bibliotheek voor Java. Aspose.Tasks maakt het eenvoudig om **Microsoft Project**-gegevens programmatisch te **manipuleren**—of je nu schema's moet genereren, data moet berekenen of rapportage moet automatiseren. Aan het einde van de gids heb je een uitvoerbaar voorbeeld dat een uitgebreid attribuut definieert, een deadline voor een taak instelt en het project opslaat als een MPP-bestand.

## Snelle antwoorden
- **Waar gaat de tutorial over?** Een testproject maken, een aangepast veld toevoegen, een uitgebreid attribuut definiëren en een taakdeadline instellen met een formule.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (nieuwste versie).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Welke IDE kan ik gebruiken?** Elke Java-IDE (IntelliJ IDEA, Eclipse, VS Code) die JDK 8+ ondersteunt.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten om de code te kopiëren en uit te voeren.

## Wat is een “Testproject” in Aspose.Tasks?
Een **testproject** is een lichtgewicht Microsoft Project‑bestand dat programmatisch wordt aangemaakt om functionaliteit te demonstreren of te valideren. Het bevat een minimale set taken, resources en aangepaste velden die je kunt manipuleren zonder echte projectgegevens te beïnvloeden.

## Waarom Aspose.Tasks gebruiken om Microsoft Project te manipuleren?
- **Volledige API-dekking** – toegang tot elke Project-, Task- en Resource‑eigenschap.  
- **Geen Office‑installatie vereist** – werkt op servers, CI‑pipelines en Docker‑containers.  
- **Cross‑platform** – draait op Windows, Linux en macOS met dezelfde Java‑code.  
- **Robuuste formule‑engine** – bereken datums, duur en aangepaste velden direct in het projectbestand.

## Voorwaarden
Zorg ervoor dat je het volgende hebt voordat je begint:

- **Java Development Kit (JDK) 8+** – download van de Oracle‑website of adopteer OpenJDK.  
- **Aspose.Tasks for Java** – verkrijg de nieuwste JAR van de [Aspose.Tasks for Java downloadpagina](https://releases.aspose.com/tasks/java/) en voeg deze toe aan de classpath van je project of de Maven/Gradle‑afhankelijkheden.

## Import pakketten
Importeer eerst de klassen die we nodig hebben:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Stapsgewijze handleiding

### Stap 1: Maak een testproject met een aangepast veld
We beginnen met **het maken van een testproject** en het toevoegen van een aangepast veld dat later ons formule‑resultaat zal bevatten.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` is een hulpfunctie die een minimaal schema bouwt en een uitgebreid attribuut registreert dat klaar is voor toewijzing van een formule.

### Stap 2: Definieer een uitgebreid attribuut (voeg aangepast veld toe)
Vervolgens **definiëren we een uitgebreid attribuut** – in feite het aangepaste veld – en geven we het een vriendelijke alias. Hier voegen we de **logica voor aangepast veld** toe.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** maakt het veld leesbaar in Project.  
- **Formule** berekent het aantal dagen tussen de *Finish*-datum van een taak en de *Deadline*.

### Stap 3: Stel deadline in voor een taak (voeg deadline‑taak toe & stel taakdeadline in)
Nu **voegen we deadline‑taak**-gegevens toe door de *Deadline*-eigenschap op een specifieke taak in te stellen.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- De `Calendar`‑instantie definieert het exacte deadline‑moment.  
- `set(Tsk.DEADLINE, …)` **stelt de taakdeadline** in voor de gekozen taak.

### Stap 4: Sla het project op (manipuleer Microsoft Project‑bestand)
Tot slot **manipuleren we Microsoft Project** door de wijzigingen op te slaan in een MPP‑bestand.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Je kunt `SaveFile.mpp` openen in Microsoft Project om het aangepaste veld, het formule‑resultaat en de deadline in het schema te zien.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Formule wordt niet geëvalueerd** | Zorg ervoor dat de `Formula`‑string van het attribuut de juiste veldnamen gebruikt (bijv. `[Deadline]`, `[Finish]`). |
| **Taak niet gevonden** | Controleer of de taak‑ID (`1` in het voorbeeld) bestaat; gebruik `project.getRootTask().getChildren().size()` om te debuggen. |
| **Licentie‑exceptie** | Pas een geldige Aspose.Tasks‑licentie toe voordat je API‑methoden aanroept (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks biedt API's voor .NET, Java en andere platforms, waardoor je **Microsoft Project**‑bestanden kunt manipuleren in de taal van jouw keuze.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Zeker. Download een volledig functionele proefversie van de [Aspose.Tasks downloadpagina](https://releases.aspose.com/).

**Q: Waar kan ik gedetailleerde documentatie voor Aspose.Tasks vinden?**  
A: De officiële documentatie staat op [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?**  
A: Bezoek het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) om vragen te stellen en ervaringen te delen met de community.

**Q: Heb ik een tijdelijke licentie nodig voor evaluatie?**  
A: Een tijdelijke licentie is beschikbaar voor kortetermijntesten; je kunt er een aanvragen [hier](https://purchase.aspose.com/temporary-license/).

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}