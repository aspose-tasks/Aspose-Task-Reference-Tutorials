---
date: 2026-01-28
description: Leer hoe u een projectkalender maakt met Aspose, weekdagen definieert
  voor kalenderexcepties en een niet‑werkdagenrooster beheert met Aspose.Tasks voor
  Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Maak projectkalender Aspose – Definieer weekdagen voor kalenderexcepties
url: /nl/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projectkalender maken met Aspose – Werkdagen definiëren voor kalenderuitzonderingen

### Inleiding
Wanneer u **create project calendar aspose** moet maken, moet u in staat zijn om niet‑standaard werkdagen te modelleren, zoals feestdagen, speciale diensten of tijdelijke sluitingen. Aspose.Tasks for Java geeft u volledige controle over kalenderdefinities, zodat u uitzonderingen kunt toevoegen die real‑world schema's weerspiegelen. In deze tutorial lopen we de exacte stappen door om werkdagen voor kalenderuitzonderingen te definiëren, zodat uw projecttijdlijnen nauwkeurig en betrouwbaar blijven. Aan het einde ziet u ook hoe dit past in een bredere **non‑working days schedule** strategie voor elk bedrijfsproject.

## Snelle antwoorden
- **What does “create project calendar aspose” mean?**  
  Het verwijst naar het gebruik van Aspose.Tasks om een aangepast kalenderobject te bouwen dat de taakplanning aanstuurt.
- **Do I need a license to run the sample?**  
  Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.
- **Which IDEs are supported?**  
  IntelliJ IDEA, Eclipse, NetBeans, of elke IDE die Java 8+ ondersteunt.
- **Can I add multiple exceptions to the same calendar?**  
  Ja – u kunt zoveel `CalendarException`-objecten toevoegen als nodig.
- **What file formats can I save the project to?**  
  XML, MPP en verschillende andere formaten die door Aspose.Tasks worden ondersteund.

## Wat is een projectkalender in Aspose.Tasks?
Een **projectkalender** definieert de werkdagen en -uren voor een project. Het beïnvloedt de start/einddatums van taken, de toewijzing van resources en de algemene planningsberekeningen. Door een kalender aan te passen, zorgt u ervoor dat het schema rekening houdt met real‑world beperkingen zoals bedrijfsfeestdagen of weekendwerkbeleid.

## Waarom werkdagen definiëren voor kalenderuitzonderingen?
- **Accurate timelines:** Taken worden niet gepland op dagen die als niet‑werkend zijn gemarkeerd.  
- **Resource planning:** Resources worden alleen toegewezen op geldige werkdagen.  
- **Compliance:** Zorgt ervoor dat projectschema's overeenkomen met organisatorisch beleid of wettelijke feestdagen.

## Non‑working Days Schedule met kalenderuitzonderingen
Wanneer u een **non‑working days schedule** bijhoudt, heeft u doorgaans een masterlijst van feestdagen, onderhoudsvensters of andere blackout‑periodes. Het toevoegen van die data als `CalendarException`-objecten garandeert dat elke berekening—of het nu kritieke pad‑analyse of resource‑leveling is—automatisch rekening houdt met die beperkingen. Deze aanpak elimineert handmatige datumaanpassingen en vermindert het risico op schema‑afwijkingen.

## Voorvereisten
Zorg ervoor dat u het volgende heeft voordat u begint:

1. **Java Development Kit (JDK)** – versie 8 of later.  
2. **Aspose.Tasks for Java** – download van de officiële [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, of elke Java‑compatibele editor.  

## Hoe projectkalender maken met Aspose – Werkdagen definiëren voor kalenderuitzonderingen

### Stapsgewijze handleiding

### Stap 1: Vereiste pakketten importeren
We hebben de kernklassen van Aspose.Tasks en Java’s `GregorianCalendar` nodig voor datumafhandeling.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Stap 2: Definieer de gegevensdirectory
Geef op waar het gegenereerde projectbestand wordt opgeslagen.

```java
String dataDir = "Your Data Directory";
```

### Stap 3: Maak een Project‑instantie
Instantieer een nieuw `Project`‑object – dit is de container voor alle projectgegevens, inclusief kalenders.

```java
Project project = new Project();
```

### Stap 4: Definieer een kalender
Voeg een aangepaste kalender toe aan het project. Deze kalender zal onze uitzonderingen bevatten.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Stap 5: Definieer werkdagen‑uitzondering
Maak een `CalendarException` die een reeks dagen (bijv. de laatste week van december) markeert als niet‑werkend.  
Het voorbeeld stelt de uitzondering in van **24 Dec 2009** tot **31 Dec 2009**, schakelt werk voor die dagen uit, en behandelt de uitzondering als een dagelijks type.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Stap 6: Sla het project op
Sla het project op, inclusief de aangepaste kalender en de uitzondering, in een XML‑bestand.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Uitzonderingsdatums niet toegepast** | Zorg ervoor dat `setEnteredByOccurrences(false)` en de juiste `FromDate/ToDate`-waarden zijn ingesteld. |
| **Opgeslagen bestand is leeg** | Controleer of `dataDir` naar een schrijfbare map wijst en de bestandsnaam eindigt op `.xml`. |
| **Kalender niet weerspiegeld in taakplanning** | Wijs de kalender toe aan taken of resources met `task.setCalendar(cal)` of `resource.setCalendar(cal)`. |

## Veelgestelde vragen

**Q: Kan ik meerdere uitzonderingen definiëren voor verschillende werkdagen binnen dezelfde kalender?**  
A: Ja. Voeg extra `CalendarException`-objecten toe aan `cal.getExceptions()` voor elke afzonderlijke periode of regel.

**Q: Is Aspose.Tasks for Java compatibel met verschillende Java‑IDE's?**  
A: Absoluut. De bibliotheek werkt met IntelliJ IDEA, Eclipse, NetBeans en elke IDE die standaard Java‑projecten ondersteunt.

**Q: Kan ik uitzonderingstypen aanpassen anders dan dagelijkse uitzonderingen?**  
A: Ja. Gebruik `CalendarExceptionType.Weekly`, `Monthly` of `Yearly` om aan uw planningsbehoeften te voldoen.

**Q: Hoe kan ik uitzonderingen dynamisch afhandelen op basis van projectvereisten?**  
A: Bouw de uitzonderingobjecten programmatisch—bijv. lees feestdagdatums uit een database of configuratiebestand en maak `CalendarException`-instanties aan in een lus.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, u kunt een gratis proefversie downloaden van de [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusie
Door deze stappen te volgen weet u nu hoe u **create project calendar aspose** kunt maken en werkdagen‑uitzonderingen kunt definiëren die nauwkeurig feestdagen of speciale niet‑werkperiodes weerspiegelen. Een juiste kalenderconfiguratie is essentieel voor realistische schema's, resource‑toewijzing en het algehele projectsucces. Verken verder door de aangepaste kalender aan taken of resources te koppelen en te experimenteren met andere uitzonderingstypen om een uitgebreide **non‑working days schedule** voor elk project op te bouwen.

---

**Laatst bijgewerkt:** 2026-01-28  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}