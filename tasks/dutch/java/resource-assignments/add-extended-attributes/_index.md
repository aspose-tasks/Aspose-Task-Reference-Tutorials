---
date: 2026-01-05
description: Leer hoe u de startdatum van een project instelt en MS Project‑XML opslaat
  met Aspose.Tasks voor Java. Stapsgewijze gids voor Java‑ontwikkelaars.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Stel de projectstartdatum in met Aspose.Tasks voor Java
url: /nl/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel project startdatum in met Aspose.Tasks voor Java

## Introductie
In deze tutorial leer je **hoe je de project startdatum instelt** in een Microsoft Project‑bestand en vervolgens **MS Project XML opslaat** met de Aspose.Tasks‑bibliotheek voor Java. Of je nu een rapportage‑pipeline automatiseert of een aangepast project‑managementtool bouwt, het beheersen van deze taak bespaart je tijd en elimineert handmatige fouten.

## Snelle antwoorden
- **Wat is de primaire methode om een startdatum in te stellen?** Gebruik `project.set(Prj.START_DATE, …)`.
- **Welk formaat moet ik gebruiken om het bestand te exporteren?** Sla het op als XML met `SaveFileFormat.Xml`.
- **Heb ik een licentie nodig voor deze bewerking?** Een proefversie werkt, maar een volledige licentie verwijdert watermerken.
- **Kan ik de startdatum wijzigen nadat taken zijn aangemaakt?** Ja, werk de project‑eigenschap bij voordat je taken toevoegt.
- **Is dit compatibel met alle MS Project‑versies?** Aspose.Tasks ondersteunt XML, MPP en meer.

## Wat is “Project startdatum instellen”?
Het instellen van de project startdatum definieert de basisagenda waaruit alle taak‑planning berekeningen beginnen. Het is de eerste stap in het programmatisch opbouwen van een betrouwbaar projectschema.

## Waarom Aspose.Tasks voor Java gebruiken?
Aspose.Tasks biedt een pure‑Java API die op elk platform werkt zonder dat Microsoft Project geïnstalleerd hoeft te zijn. Het stelt je in staat om projectgegevens snel te maken, te wijzigen en te exporteren, waardoor het ideaal is voor server‑side automatisering.

## Prerequisites
1. **Java Development Kit (JDK)** – elke recente JDK‑versie.
2. **Aspose.Tasks for Java** – download van [here](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse, of je favoriete Java‑IDE.

## Pakketten importeren
First, import the necessary classes:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Stap 1: Data‑directory instellen
Definieer waar de gegenereerde bestanden worden opgeslagen.

```java
String dataDir = "Your Data Directory";
```

### Stap 2: Een project‑instantie maken
Instantieer een nieuw, leeg project.

```java
Project project = new Project();
```

### Stap 3: Project‑informatie‑eigenschappen instellen
Hier **stellen we de project startdatum in** en gerelateerde plannings‑eigenschappen.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Stap 4: MS Project XML opslaan
Exporteer het geconfigureerde project naar een XML‑bestand.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen en oplossingen
- **Onjuist datumformaat:** Zorg ervoor dat je `java.util.Calendar` gebruikt en `getTime()` aanroept voordat je toewijst.
- **Bestand niet opgeslagen:** Controleer of `dataDir` naar een bestaande, schrijfbare map wijst.
- **Licentie‑waarschuwingen:** Een proefversie voegt watermerken toe; pas een geldige licentie toe om ze te verwijderen.

## Frequently Asked Questions

### Q: Kan ik Aspose.Tasks voor Java gebruiken om MS Project‑bestanden te lezen?  
**A:** Ja, Aspose.Tasks voor Java biedt robuuste functionaliteiten voor zowel het lezen als schrijven van MS Project‑bestanden.

### Q: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?  
**A:** Absoluut, Aspose.Tasks voor Java ondersteunt diverse MS Project‑formaten, wat brede compatibiliteit garandeert.

### Q: Zijn er beperkingen aan de proefversie van Aspose.Tasks voor Java?  
**A:** De proefversie laat je de bibliotheek verkennen, maar voegt watermerken toe aan uitvoerbestanden.

### Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?  
**A:** Je kunt hulp zoeken op het Aspose.Tasks community‑forum [hier](https://forum.aspose.com/c/tasks/15).

### Q: Kan ik een tijdelijke licentie voor Aspose.Tasks voor Java aanschaffen?  
**A:** Ja, tijdelijke licenties zijn beschikbaar voor kortetermijngebruik. Verkrijg er een via [hier](https://purchase.aspose.com/temporary-license/).

### Q: Behoudt opslaan als XML aangepaste velden?  
**A:** Ja, wanneer je opslaat met `SaveFileFormat.Xml`, blijven alle aangepaste attributen en uitgebreide velden behouden.

### Q: Kan ik de startdatum wijzigen nadat taken zijn toegevoegd?  
**A:** Je kunt de startdatum op elk moment vóór het opslaan bijwerken; roep gewoon opnieuw `project.set(Prj.START_DATE, …)` aan.

---

**Laatst bijgewerkt:** 2026-01-05  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}