---
date: 2025-12-20
description: Leer hoe u Aspose.Tasks kunt gebruiken om projectkalenderdetails uit
  Microsoft Project‑bestanden te extraheren met Java. Stapsgewijze gids met codevoorbeelden.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe Aspose.Tasks te gebruiken om MS Project‑kalenderinformatie op te halen
url: /nl/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Aspose.Tasks te gebruiken om MS Project kalenderinformatie op te halen

## Introductie
In deze tutorial ontdek je **hoe je Aspose.Tasks** kunt gebruiken om programmatisch kalenderinformatie op te halen uit Microsoft Project‑bestanden. Toegang tot kalendergegevens zoals werkdagen, uren en uitzonderingen is essentieel wanneer je **projectkalender**‑details moet extraheren voor rapportage, integratie of aangepaste planningslogica. Laten we stap voor stap door het proces gaan.

## Snelle antwoorden
- **Welke bibliotheek wordt in deze tutorial gebruikt?** Aspose.Tasks for Java.  
- **Welk primair trefwoord wordt behandeld?** *how to use aspose.tasks*.  
- **Wat kun je extraheren?** Projectkalenders, inclusief werkdagen en uren.  
- **Heb ik een licentie nodig?** Een gratis proefversie is beschikbaar; een licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.

## Waarom projectkalenderinformatie extraheren?
Projectkalenders bepalen taakdata, resource‑toewijzingen en algemene tijdlijnberekeningen. Door deze gegevens te extraheren kun je:
- Aangepaste rapporten genereren die de werkelijke werkschema's weergeven.  
- Microsoft Project‑tijdlijnen synchroniseren met externe systemen (ERP, BI, enz.).  
- What‑if‑analyses uitvoeren door kalenderinstellingen programmatisch aan te passen.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Java Development Kit (JDK) geïnstalleerd op je systeem.  
- Aspose.Tasks for Java‑bibliotheek. Je kunt deze downloaden van [here](https://releases.aspose.com/tasks/java/).

## Importeer pakketten
Importeer eerst de benodigde Aspose.Tasks‑klassen in je Java‑project.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Stap 1: Stel gegevensdirectory in
Definieer de map die je *.mpp*-bestand bevat.

```java
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute pad naar de map waar **project.mpp** zich bevindt.

## Stap 2: Definieer tijdseenheden
Maak constanten die helpen de interne tijdrepresentatie om te zetten naar menselijk leesbare uren.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Deze waarden worden uitgedrukt in microseconden, wat de manier is waarop Aspose.Tasks tijd intern opslaat.

## Stap 3: Maak projectinstantie
Laad het Microsoft Project‑bestand in een `Project`‑object.

```java
Project project = new Project(dataDir + "project.mpp");
```

De `Project`‑constructor parseert het *.mpp*-bestand en maakt alle projectgegevens, inclusief kalenders, toegankelijk via de API.

## Stap 4: Haal kalenderinformatie op
Verkrijg de collectie kalenders die in het project zijn gedefinieerd.

```java
CalendarCollection alCals = project.getCalendars();
```

Een project kan meerdere kalenders bevatten (standaard, resource‑ en aangepaste kalenders). Deze collectie geeft je toegang tot elke kalender.

## Stap 5: Doorloop kalenders
Loop door elke kalender, toon de UID, naam en de werkdagen met bijbehorende uren.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

De binnenste lus controleert elk `WeekDay`‑object. Als de dag als werkdag is gemarkeerd, wordt het dagtype (Monday, Tuesday, …) samen met de berekende werkuren afgedrukt.

## Stap 6: Toon voltooiingsbericht
Geef een signaal dat het extractieproces is voltooid.

```java
System.out.println("Process completed Successfully");
```

## Conclusie
Door deze stappen te volgen, **weet je nu hoe je Aspose.Tasks kunt gebruiken om projectkalender**‑informatie uit een MS Project‑bestand te extraheren met Java. Je kunt deze logica integreren in grotere applicaties, rapportage automatiseren of schema's synchroniseren met andere enterprise‑systemen.

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks ondersteunt meerdere platforms en programmeertalen, waaronder .NET, C++, Python en Java.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, je kunt een gratis proefversie downloaden van [here](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?**  
A: Je kunt ondersteuning krijgen via het Aspose.Tasks community‑forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Kan ik een tijdelijke licentie voor Aspose.Tasks aanschaffen?**  
A: Ja, tijdelijke licenties zijn verkrijgbaar voor aankoop [here](https://purchase.aspose.com/temporary-license/).

**Q: Waar kan ik gedetailleerde documentatie voor Aspose.Tasks vinden?**  
A: Je kunt de documentatie raadplegen [here](https://reference.aspose.com/tasks/java/).

---

**Laatst bijgewerkt:** 2025-12-20  
**Getest met:** Aspose.Tasks for Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}