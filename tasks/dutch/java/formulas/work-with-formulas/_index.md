---
date: 2026-02-13
description: Leer hoe u het aantal dagen tussen datums berekent, een testproject maakt
  en een aangepast veld toevoegt terwijl u Microsoft Project‑bestanden bewerkt met
  Aspose.Tasks voor Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Bereken dagen tussen datums met Aspose.Tasks voor Java
url: /nl/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bereken dagen tussen datums met Aspose.Tasks voor Java

## Inleiding
In deze tutorial **bereken je dagen tussen datums** door een testproject te maken, een aangepast veld toe te voegen en Microsoft Project‑formules te gebruiken via de Aspose.Tasks‑bibliotheek voor Java. Of je nu planningen moet genereren, deadlines moet berekenen of rapportage moet automatiseren, Aspose.Tasks stelt je in staat Project‑gegevens programmatisch te manipuleren zonder een desktop‑installatie. Aan het einde van de gids heb je een uitvoerbaar voorbeeld dat een uitgebreid attribuut definieert, een deadline voor een taak instelt en het project opslaat als een MPP‑bestand.

## Snelle antwoorden
- **Waar gaat de tutorial over?** Een testproject maken, een aangepast veld toevoegen, een uitgebreid attribuut definiëren en een taak‑deadline instellen met een formule om dagen tussen datums te berekenen.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (nieuwste versie).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Welke IDE kan ik gebruiken?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, VS Code) die JDK 8+ ondersteunt.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten om de code te kopiëren en uit te voeren.

## Wat is “dagen tussen datums berekenen” in Aspose.Tasks?
Dagen tussen datums berekenen betekent een Project‑formule gebruiken die één datumveld (bijv. **Finish**) van een ander datumveld (bijv. **Deadline**) aftrekt en het numerieke verschil in dagen retourneert. Dit is handig voor het bijhouden van planning‑verschuivingen, het meten van speling of het genereren van aangepaste rapporten.

## Waarom Aspose.Tasks gebruiken om dagen tussen datums te berekenen?
- **Volledige API‑dekking** – toegang tot elk Project‑, Taak‑ en Resource‑eigenschap.  
- **Geen Office‑installatie vereist** – werkt op servers, CI‑pipelines en Docker‑containers.  
- **Cross‑platform** – draait op Windows, Linux en macOS met dezelfde Java‑code.  
- **Robuuste formule‑engine** – laat je berekeningen zoals `[Deadline] - [Finish]` direct in het projectbestand definiëren.

## Hoe een deadline voor een taak instellen
Het instellen van een deadline is de eerste stap voordat je het interval kunt berekenen. De deadline wordt opgeslagen in het `Tsk.DEADLINE`‑veld van een taak en kan worden toegewezen met een `java.util.Calendar`‑instantie.

## Hoe een uitgebreid attribuut definiëren
Een uitgebreid attribuut is het aangepaste veld dat het resultaat van je formule zal bevatten. Je definieert het één keer, geeft het een alias voor leesbaarheid, en koppelt vervolgens een formule die de datum‑aftrekking uitvoert.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

- **Java Development Kit (JDK) 8+** – download van de Oracle‑website of adopteer OpenJDK.  
- **Aspose.Tasks voor Java** – verkrijg de nieuwste JAR van de [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) en voeg deze toe aan de classpath van je project of aan Maven/Gradle‑afhankelijkheden.

## Importeer pakketten
Eerst importeren we de klassen die we nodig hebben:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Stapsgewijze handleiding

### Stap 1: Maak een testproject met een aangepast veld
We beginnen met **het maken van een testproject** en voegen een aangepast veld toe dat later het resultaat van onze formule zal bevatten.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` is een hulpfunctie die een minimale planning bouwt en een uitgebreid attribuut registreert dat klaar is voor formule‑toewijzing.

### Stap 2: Definieer een uitgebreid attribuut (Voeg aangepast veld toe)
Vervolgens **definiëren we een uitgebreid attribuut** – in feite het aangepaste veld – en geven we het een vriendelijke alias. Hier **voegen we het aangepaste veld** toe.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** maakt het veld leesbaar in Project.  
- **Formula** berekent het aantal dagen tussen de *Finish*‑datum van een taak en de *Deadline* – de kern van *dagen tussen datums berekenen*.

### Stap 3: Stel deadline voor een taak in (Voeg deadline‑taak toe & stel taakdeadline in)
Nu **voegen we deadline‑taak**‑gegevens toe door de *Deadline*‑eigenschap op een specifieke taak in te stellen.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- De `Calendar`‑instantie definieert het exacte deadline‑moment.  
- `set(Tsk.DEADLINE, …)` **stelt de taak‑deadline** in voor de gekozen taak.

### Stap 4: Sla het project op (Manipuleer Microsoft Project‑bestand)
Tot slot **manipuleren we Microsoft Project** door de wijzigingen op te slaan in een MPP‑bestand.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Je kunt `SaveFile.mpp` openen in Microsoft Project om het aangepaste veld, het formule‑resultaat en de deadline in de planning terug te zien.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Formule wordt niet geëvalueerd** | Zorg ervoor dat de `Formula`‑string van het attribuut de juiste veldnamen gebruikt (bijv. `[Deadline]`, `[Finish]`). |
| **Taak niet gevonden** | Controleer of de taak‑ID (`1` in het voorbeeld) bestaat; gebruik `project.getRootTask().getChildren().size()` om te debuggen. |
| **Licentie‑exception** | Pas een geldige Aspose.Tasks‑licentie toe voordat je API‑methoden aanroept (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks biedt API’s voor .NET, Java en andere platforms, zodat je **Microsoft Project**‑bestanden kunt manipuleren in de taal van jouw keuze.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Absoluut. Download een volledig functionele proefversie vanaf de [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Waar vind ik gedetailleerde documentatie voor Aspose.Tasks?**  
A: De officiële documentatie staat op [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?**  
A: Bezoek het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) om vragen te stellen en ervaringen te delen met de community.

**Q: Heb ik een tijdelijke licentie nodig voor evaluatie?**  
A: Een tijdelijke licentie is beschikbaar voor kortetermijntesten; je kunt er een aanvragen [hier](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.Tasks voor Java 24.12 (nieuwste op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}