---
date: 2026-01-10
description: Leer hoe u toewijzingen stopt, resource‑toewijzingen beheert en een voorbeeld
  van een resource‑toewijzing bekijkt in Aspose.Tasks voor Java met deze stapsgewijze
  tutorial.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een toewijzing te stoppen en resource‑toewijzingen te hervatten in Aspose.Tasks
url: /nl/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Toewijzing te Stoppen en Resource‑toewijzingen te Hervatten in Aspose.Tasks

## Inleiding
In deze tutorial **ontdek je hoe je een toewijzing kunt stoppen** en later kunt hervatten met Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java‑API waarmee je projectbestanden in Java‑formaten kunt lezen, Microsoft Project‑gegevens kunt manipuleren en resource‑toewijzingen kunt beheren zonder dat Microsoft Project geïnstalleerd hoeft te zijn. We lopen elke stap door, leggen uit waarom elke regel belangrijk is, en geven praktische tips die je kunt toepassen op projecten uit de praktijk.

## Snelle Antwoorden
- **Wat betekent “stop assignment”?** Het markeert een resource‑toewijzing als tijdelijk inactief vanaf een specifieke stopdatum.  
- **Kan ik dezelfde toewijzing later hervatten?** Ja, door een hervatdatum in te stellen op dezelfde toewijzing.  
- **Heb ik Microsoft Project nodig om deze API te gebruiken?** Nee, Aspose.Tasks werkt onafhankelijk van Microsoft Project.  
- **Welke versie van Java is vereist?** Java 8 of hoger wordt aanbevolen.  
- **Waar kan ik de bibliotheek downloaden?** Van de officiële Aspose.Tasks Java‑downloadpagina.

## Wat betekent “how to stop assignment” in de context van Aspose.Tasks?
Een toewijzing stoppen vertelt de planner om het werk dat aan een resource is toegewezen na de **stopdatum** te negeren tot de **hervatdatum** (indien aanwezig). Dit is nuttig voor vakanties, uitval van apparatuur, of elke periode waarin een resource niet als actief moet worden beschouwd.

## Waarom Aspose.Tasks gebruiken voor het beheren van resource‑toewijzingen?
- **Geen Microsoft Project nodig** – werk direct met .mpp‑bestanden.  
- **Volledige controle over datums** – je kunt programmatic stop‑ en hervatdatums controleren en aanpassen.  
- **Cross‑platform** – draait op elk OS dat Java ondersteunt.  
- **Rijke API** – biedt een *resource assignment example* dat je kunt uitbreiden voor aangepaste rapportage.

## Vereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je systeem.  
- Aspose.Tasks voor Java‑bibliotheek gedownload. Je kunt deze downloaden van [hier](https://releases.aspose.com/tasks/java/).  
- Basiskennis van Java‑programmeren.  

## Pakketten Importeren
Laten we eerst de benodigde pakketten in ons Java‑project importeren:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Stap 1: Het Projectbestand Laden
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Hier **lezen we een projectbestand in Java‑formaat** (`.mpp`) en maken we een `Project`‑object aan dat ons toegang geeft tot alle projectgegevens, inclusief resource‑toewijzingen.

## Stap 2: Door Resource‑toewijzingen Itereren
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

We stellen een **minimumdatum** in om placeholder‑datums te filteren en lopen vervolgens elke toewijzing af. Dit is het typische *resource assignment example*‑patroon dat wordt gebruikt wanneer je toewijzingen moet inspecteren of wijzigen.

## Stap 3: Stop‑ en Hervatdatums Controleren
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

In dit blok **controleren we de stopdatum** en **de hervatdatum** voor elke toewijzing. Als de datum vóór onze `minDate` ligt, behandelen we deze als niet ingesteld (`"NA"`); anders printen we de werkelijke datum. Deze logica is essentieel om **resource‑toewijzingen correct te beheren**.

## Veelvoorkomende Problemen en Oplossingen
- **Null‑datums** – `ra.get(Asn.STOP)` kan `null` retourneren. Voeg een null‑check toe voordat je `.before(minDate)` aanroept.  
- **Onjuiste bestands‑pad** – Zorg ervoor dat `dataDir` eindigt op een pad‑separator (`/` of `\\`) die geschikt is voor jouw OS.  
- **Versiemis‑match** – Gebruik de nieuwste Aspose.Tasks voor Java‑versie om ontbrekende enum‑waarden te vermijden.

## FAQ's
### Kan ik Aspose.Tasks gebruiken zonder Microsoft Project geïnstalleerd?
Ja, Aspose.Tasks stelt je in staat om met Microsoft Project‑bestanden te werken zonder dat Microsoft Project op je systeem geïnstalleerd hoeft te zijn.

### Waar vind ik meer documentatie?
Gedetailleerde documentatie vind je [hier](https://reference.aspose.com/tasks/java/).

### Is er een gratis proefversie beschikbaar?
Ja, je kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning als ik problemen tegenkom?
Je kunt ondersteuning krijgen van de community [hier](https://forum.aspose.com/c/tasks/15).

### Kan ik een tijdelijke licentie aanschaffen?
Ja, een tijdelijke licentie kun je aanschaffen [hier](https://purchase.aspose.com/temporary-license/).

## Veelgestelde Vragen

**Q: Hoe stel ik programmatic een stopdatum in voor een toewijzing?**  
A: Gebruik `ra.set(Asn.STOP, yourDateObject);` waarbij `yourDateObject` een `java.util.Date` is.

**Q: Wat gebeurt er als de hervatdatum eerder is dan de stopdatum?**  
A: De API handhaaft geen chronologische volgorde; de planner zal de toewijzing echter alleen als actief beschouwen na de latere van de twee datums, dus je moet de datums zelf valideren.

**Q: Kan ik toewijzingen filteren zodat alleen die met een ingestelde stopdatum worden getoond?**  
A: Ja, iterateer door `prj.getResourceAssignments()` en controleer `ra.get(Asn.STOP) != null`.

**Q: Is het mogelijk om een stopdatum te verwijderen nadat deze is ingesteld?**  
A: Stel de stopdatum in op `null` met `ra.set(Asn.STOP, null);` en sla vervolgens het project op.

**Q: Ondersteunt Aspose.Tasks andere datumgerelateerde velden zoals start, finish of actual start?**  
A: Absoluut. De `Asn`‑enum biedt constanten voor alle toewijzingsvelden, zoals `Asn.START`, `Asn.FINISH`, enzovoort.

## Conclusie
Door deze stappen te volgen weet je nu **hoe je een toewijzing kunt stoppen**, de stop‑/hervatdatums kunt inspecteren, en de toewijzing kunt hervatten wanneer dat nodig is. Deze mogelijkheid stelt je in staat **resource‑toewijzingen nauwkeuriger te beheren**, bijvoorbeeld bij vakanties of uitval van apparatuur. Voel je vrij om het voorbeeld uit te breiden om datums bij te werken, rapporten te genereren, of te integreren met je eigen planningslogica.

---

**Laatst bijgewerkt:** 2026-01-10  
**Getest met:** Aspose.Tasks voor Java 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}