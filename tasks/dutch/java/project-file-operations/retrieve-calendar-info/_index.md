---
date: 2026-03-27
description: Leer hoe je Aspose en Aspose.Tasks kunt gebruiken om projectkalenderdetails
  uit Microsoft Project‑bestanden te extraheren met Java. Stapsgewijze handleiding
  met codevoorbeelden.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe Aspose.Tasks te gebruiken om MS Project‑kalenderinformatie op te halen
url: /nl/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe gebruik je Aspose.Tasks om MS Project‑kalenderinformatie op te halen

## Introductie
In deze tutorial **ontdek je hoe je Aspose.Tasks** kunt gebruiken om programmatisch kalenderinformatie uit Microsoft Project‑bestanden op te halen. Toegang tot kalendergegevens zoals werkdagen, uren en uitzonderingen is essentieel wanneer je **projectkalender**‑details moet **extraheren** voor rapportage, integratie of aangepaste planningslogica. Laten we stap voor stap door het proces lopen, en je zult precies zien **hoe je Aspose** kunt gebruiken om deze gegevens uit een *.mpp*-bestand te halen.

## Snelle antwoorden
- **Welke bibliotheek wordt in deze tutorial gebruikt?** Aspose.Tasks voor Java.  
- **Welk primair trefwoord wordt behandeld?** *how to use aspose*.  
- **Wat kun je extraheren?** Projectkalenders, inclusief werkdagen en uren.  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar; een licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.

## Wat is Aspose.Tasks en waarom gebruiken?
Aspose.Tasks is een krachtige Java‑API waarmee ontwikkelaars Microsoft Project‑bestanden kunnen lezen, schrijven en manipuleren zonder Microsoft Project zelf te hoeven hebben. Door Aspose.Tasks te gebruiken kun je **how to extract calendar**‑informatie verkrijgen, planningsberekeningen automatiseren en projectgegevens integreren met andere enterprise‑systemen — allemaal vanuit pure Java‑code.

## Waarom projectkalenderinformatie extraheren?
Projectkalenders bepalen taakdatums, resource‑toewijzingen en algemene tijdlijnberekeningen. Door deze gegevens te extraheren kun je:
- Aangepaste rapporten genereren die de werkelijke werkschema’s weergeven.  
- Microsoft Project‑tijdlijnen synchroniseren met externe systemen (ERP, BI, enz.).  
- What‑if‑analyses uitvoeren door kalenderinstellingen programmatisch aan te passen.  
- **MS Project‑kalender**‑gegevens extraheren voor migratie naar andere planningshulpmiddelen.

## Voorvereisten
Voordat we beginnen, zorg dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Java Development Kit (JDK) geïnstalleerd op je systeem.  
- Aspose.Tasks voor Java‑bibliotheek. Je kunt deze downloaden van [hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Importeer eerst de benodigde Aspose.Tasks‑klassen in je Java‑project.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Stap 1: Gegevensmap instellen
Definieer de map die je *.mpp*-bestand bevat.

```java
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute pad naar de map waar **project.mpp** zich bevindt.

## Stap 2: Tijdseenheden definiëren
Maak constanten die helpen de interne tijdrepresentatie om te zetten naar menselijk leesbare uren.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Deze waarden worden uitgedrukt in microseconden, wat de manier is waarop Aspose.Tasks tijd intern opslaat.

## Stap 3: Project‑instantie maken
Laad het Microsoft Project‑bestand in een `Project`‑object.

```java
Project project = new Project(dataDir + "project.mpp");
```

De `Project`‑constructor parseert het *.mpp*-bestand en maakt alle projectgegevens, inclusief kalenders, toegankelijk via de API.

## Stap 4: Kalenderinformatie ophalen
Verkrijg de collectie kalenders die in het project zijn gedefinieerd.

```java
CalendarCollection alCals = project.getCalendars();
```

Een project kan meerdere kalenders bevatten (standaard, resource en aangepaste kalenders). Deze collectie geeft je toegang tot elk van hen.

## Stap 5: Door kalenders itereren
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

## Stap 6: Voltooiingsbericht weergeven
Geef aan dat het extractie‑proces is voltooid.

```java
System.out.println("Process completed Successfully");
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Geen kalenders geretourneerd** | Het projectbestand bevat mogelijk geen aangepaste kalenders. | Controleer of het *.mpp* daadwerkelijk kalenders definieert of open het in Microsoft Project om dit te bevestigen. |
| **Onjuiste werkuren** | Tijdconversie‑constanten zijn onjuist voor een andere Project‑versie. | Pas `OneSec`, `OneMin`, `OneHour` aan als je met een nieuwere Aspose.Tasks‑versie werkt die de interne tijdseenheid wijzigt. |
| **`NullPointerException` op `cal.getName()`** | Sommige kalenderobjecten kunnen null zijn. | Voeg een null‑check toe vóór het benaderen van eigenschappen (reeds gedemonstreerd). |

## Veelgestelde vragen

**V: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks ondersteunt meerdere platforms en programmeertalen, waaronder .NET, C++, Python en Java.

**V: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, je kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

**V: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?**  
A: Je kunt ondersteuning krijgen via het Aspose.Tasks‑communityforum [hier](https://forum.aspose.com/c/tasks/15).

**V: Kan ik een tijdelijke licentie voor Aspose.Tasks aanschaffen?**  
A: Ja, tijdelijke licenties zijn verkrijgbaar via [hier](https://purchase.aspose.com/temporary-license/).

**V: Waar vind ik gedetailleerde documentatie voor Aspose.Tasks?**  
A: Je kunt de documentatie raadplegen [hier](https://reference.aspose.com/tasks/java/).

## Conclusie
Door deze stappen te volgen, **weet je nu hoe je Aspose.Tasks kunt gebruiken om projectkalender**‑informatie uit een MS Project‑bestand te extraheren met Java. Je kunt deze logica integreren in grotere applicaties, rapportage automatiseren of schema’s synchroniseren met andere enterprise‑systemen. Onthoud dat het beheersen van **how to use aspose** de deur opent naar vele geavanceerde project‑management‑automatiseringsscenario’s.

---

**Laatst bijgewerkt:** 2026-03-27  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}