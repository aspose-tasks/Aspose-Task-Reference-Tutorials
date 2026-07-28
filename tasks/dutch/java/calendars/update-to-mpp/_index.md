---
date: 2026-02-05
description: Leer hoe u feestdagen aan een kalender toevoegt, de kalender aan een
  project toewijst en het MS Project‑bestand opslaat als MPP met Aspose.Tasks voor
  Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Feestdagen toevoegen aan de agenda en opslaan als MPP met Aspose.Tasks
url: /nl/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg vakantiedagen toe aan de agenda en sla op als MPP met Aspose.Tasks

## Introductie

In modern projectmanagement moet u vaak **vakantiedagen toevoegen aan agenda**‑bestanden, een **MS Project‑agenda** maken, en vervolgens het schema delen in het native MPP‑formaat. Of u nu tijdlijnen van meerdere bronnen consolideert of legacy‑gegevens migreert, het programmatisch genereren van een agenda elimineert handmatige fouten en versnelt de levering. Deze tutorial leidt u door het volledige proces van het creëren van een agenda in MS Project, het aanpassen met vakantiedagen, **agenda toewijzen aan project**, en uiteindelijk **project converteren naar MPP** met de Aspose.Tasks Java‑API.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Het toevoegen van vakantiedagen aan een agenda, deze toewijzen aan een project en het opslaan van het resultaat als een MPP‑bestand met Aspose.Tasks voor Java.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of hoger (JDK 8+).  
- **Kan ik de agenda aanpassen?** Ja – u kunt werktijden, uitzonderingen en vakantiedagen toevoegen.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basisagenda.  

## Wat is “create calendar MS Project”?

Een **create calendar MS Project** betekent dat u programmatisch de werkdagen, uren en uitzonderingen definieert die de taakplanning binnen een Microsoft Project‑bestand aansturen. Met Aspose.Tasks kunt u **java create project calendar**, deze wijzigen en de wijzigingen opslaan zonder ooit de Microsoft Project‑UI te openen.

## Waarom Aspose.Tasks gebruiken voor deze taak?

- **Volledige .NET/Java‑compatibiliteit** – werkt op elk platform dat Java ondersteunt.  
- **Geen COM‑ of Office‑installatie nodig** – ideaal voor server‑side automatisering en **automatiseren van schema‑generatie**.  
- **Rijke API** – ondersteunt elke agenda‑eigenschap, inclusief aangepaste werkweken en vakantiedagen.  
- **Directe MPP‑output** – u kunt **project opslaan als MPP** zonder tussenconversies.

## Voorvereisten

1. **Java Development Kit (JDK) 8+** – zorg ervoor dat `java -version` 1.8 of nieuwer rapporteert.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, of een andere editor naar keuze.  
4. **Basiskennis van Java** – vertrouwdheid met klassen, methoden en bestands‑I/O.

## Hoe vakantiedagen toevoegen aan de agenda

Hieronder lopen we elke stap door, van het opzetten van de omgeving tot het opslaan van het uiteindelijke MPP‑bestand. De codeblokken blijven ongewijzigd; de omliggende uitleg is uitgebreid voor duidelijkheid.

### Stap 1: Vereiste pakketten importeren

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Stap 2: De gegevensdirectory instellen

```java
String dataDir = "Your Data Directory";
```

### Stap 3: Invoer‑ en uitvoerbestandsnamen definiëren

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Stap 4: Het project laden en een nieuwe agenda toevoegen

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Stap 5: De agenda aanpassen (optioneel)

Als u specifieke werktijden, vakantiedagen of uitzonderingen nodig heeft, roept u uw eigen hulpmethode aan. Het voorbeeld gebruikt `GetTestCalendar` als placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** U kunt direct `cal1.getWeekDays()` manipuleren om de werktijden voor elke dag van de week in te stellen, of `cal1.getExceptions()` gebruiken om **vakantiedagen aan de agenda toe te voegen**.

### Stap 6: De agenda aan het project toewijzen

```java
project.set(Prj.CALENDAR, cal1);
```

### Stap 7: Het project opslaan als MPP

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Stap 8: Bevestig succesvolle voltooiing

```java
System.out.println("Process completed Successfully");
```

## Veelvoorkomende gebruikssituaties

- **Geautomatiseerde schema‑generatie** voor terugkerende projecten (bijv. wekelijkse sprints).  
- **Migreren van legacy CSV‑ of Excel‑agenda's** naar een volledig uitgeruste MS Project‑file.  
- **Server‑side rapportage** waarbij een webservice op aanvraag een MPP‑bestand retourneert.  

## Problemen oplossen & veelvoorkomende valkuilen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| `NullPointerException` bij `project.save` | `dataDir` wijst naar een niet‑bestaande map | Zorg ervoor dat de map bestaat of maak deze programmatically aan. |
| Agenda niet toegepast op taken | Taken verwijzen nog steeds naar de standaardagenda | Na het instellen van `Prj.CALENDAR`, werk ook elke taak’s `Task.CALENDAR` bij indien deze eerder overschreven was. |
| Uitvoerbestand is 0 KB | Ontbrekende schrijfrechten | Voer de JVM uit met de juiste bestandsysteemrechten of kies een schrijfbare pad. |

## Veelgestelde vragen

**Q: Is Aspose.Tasks for Java compatibel met verschillende versies van MS Project?**  
A: Ja, Aspose.Tasks for Java ondersteunt een breed scala aan MS Project‑versies, van Project 2007 tot de nieuwste release, waardoor naadloze compatibiliteit wordt gegarandeerd.

**Q: Kan ik agenda's aanpassen volgens specifieke projectvereisten?**  
A: Absoluut. U kunt werkdagen definiëren, aangepaste werkweken instellen, vakantiedagen toevoegen en zelfs meerdere agenda's binnen één projectbestand creëren.

**Q: Biedt Aspose.Tasks for Java ondersteuning voor probleemoplossing en assistentie?**  
A: Ja, u kunt hulp krijgen via het Aspose.Tasks‑communityforum [hier](https://forum.aspose.com/c/tasks/15).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, een volledig functionele gratis proefversie is beschikbaar [hier](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks for Java?**  
A: Tijdelijke licenties kunnen worden aangevraagd via de Aspose‑website [hier](https://purchase.aspose.com/temporary-license/).

**Laatst bijgewerkt:** 2026-02-05  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}