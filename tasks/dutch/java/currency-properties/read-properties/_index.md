---
date: 2026-02-07
description: Leer hoe je valutaproperties in Java kunt lezen en het valutasymbool
  in Java kunt extraheren uit MS Project‑bestanden met Aspose.Tasks voor Java. Volg
  deze stapsgewijze handleiding om de valutacode, het symbool, het aantal decimalen
  en de positie programmatic​h te extraheren.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Lees Valuta-eigenschappen Java met Aspose.Tasks-projecten
url: /nl/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees valuta‑eigenschappen Java met Aspose.Tasks‑projecten

## Inleiding
In deze tutorial zult u **read currency properties java** lezen uit Microsoft Project‑bestanden met behulp van de Aspose.Tasks for Java API. Aspose.Tasks stelt u in staat om met .mpp‑bestanden te werken zonder dat Microsoft Project geïnstalleerd is, waardoor het ideaal is voor geautomatiseerde rapportage, datamigratie of integratie in Java‑gebaseerde enterprise‑applicaties. Aan het einde van deze gids kunt u de valutacode, het symbool, het aantal decimale cijfers en de positie van het symbool direct uit een projectbestand extraheren.

## Snelle antwoorden
- **What does “read currency properties java” mean?** Het verwijst naar het ophalen van valuta‑gerelateerde metadata (code, symbool, cijfers, positie) uit een MS Project‑bestand met Java‑code.  
- **Do I need a license to try this?** Een gratis proefversie van Aspose.Tasks is beschikbaar; een commerciële licentie is vereist voor productiegebruik.  
- **Which JDK version is required?** Java 8 of hoger.  
- **Can I modify the currency settings after reading them?** Ja, Aspose.Tasks staat zowel lees‑ als schrijf‑operaties op valutaparameters toe.  
- **Is this compatible with all .mpp versions?** De API ondersteunt bestanden die zijn gemaakt met Microsoft Project 2003‑2021.

## Wat is read currency properties java?
Het lezen van valutaparameters in Java betekent dat u de project‑niveau instellingen benadert die bepalen hoe monetaire waarden worden weergegeven in een Microsoft Project‑bestand. Deze instellingen omvatten de ISO‑valutacode (bijv. **USD**), het symbool (**$**), het aantal decimale cijfers en of het symbool vóór of na het bedrag verschijnt.

## Waarom read currency properties java met Aspose.Tasks?
- **No Microsoft Project installation needed** – de API werkt op elk platform dat Java ondersteunt.  
- **Fast, in‑process extraction** – ideaal voor batchverwerking van grote aantallen projectbestanden.  
- **Full control** – u kunt de opgehaalde waarden combineren met aangepaste rapportage of integreren in ERP‑systemen.  
- **Cross‑version support** – werkt met .mpp‑bestanden van Project 2003 tot en met de nieuwste 2021‑release.

## Vereisten
Zorg ervoor dat u het volgende heeft voordat u begint:

1. **Java Development Kit (JDK)** – Java 8 of nieuwer geïnstalleerd en geconfigureerd in uw `PATH`.  
2. **Aspose.Tasks for Java JAR** – download de nieuwste bibliotheek van [here](https://releases.aspose.com/tasks/java/) en voeg deze toe aan de classpath van uw project.  

## Importeer pakketten
Begin met het importeren van de Aspose.Tasks‑namespace die nodig is voor projectmanipulatie:

```java
import com.aspose.tasks.*;
```

## Stap 1: Stel uw projectmap in
Definieer de map die het `.mpp`‑bestand bevat dat u wilt analyseren. Het pad in een variabele bewaren maakt de code herbruikbaar:

```java
String dataDir = "Your Data Directory";
```

*Vervang `"Your Data Directory"` door het absolute of relatieve pad naar de map waar `project.mpp` zich bevindt.*

## Stap 2: Maak een Project Reader‑instantie
Laad het Microsoft Project‑bestand in een `Project`‑object. Dit object geeft u toegang tot alle projecteigenschappen, inclusief valutainstellingen:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Als uw bestand een andere naam heeft, wijzig dan `"project.mpp"` dienovereenkomstig.*

## Stap 3: Toon valutaparameters
Haal nu elk valutatribuut op met behulp van de `Prj`‑enumeratie en print de resultaten naar de console. De API retourneert objecten die u naar strings kunt converteren voor weergave:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Wat u zult zien:**  
- **Currency Code** – ISO‑4217‑code zoals `USD`, `EUR`, `JPY`.  
- **Currency Digits** – meestal `2` voor de meeste valuta’s, `0` voor de Japanse Yen.  
- **Currency Symbol** – het teken dat in rapporten wordt getoond (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` voor **before** het bedrag, `1` voor **after**.

## Hoe currency symbol java extraheren?
Als u alleen geïnteresseerd bent in het symbool zelf, kunt u zich richten op de `Prj.CURRENCY_SYMBOL`‑eigenschap. Dezelfde `project.get(...)`‑aanroep retourneert het symbool, dat u kunt opslaan, loggen of doorgeven aan een andere service voor verdere verwerking. Dit is vooral nuttig wanneer u **extract currency symbol java** nodig heeft voor financiële dashboards of gelokaliseerde UI‑componenten.

## Stap 4: Proces voltooid
Geef een signaal dat de extractie succesvol is afgerond. Dit eenvoudige bericht is handig wanneer de code wordt uitgevoerd als onderdeel van een grotere batchtaak:

```java
System.out.println("Process completed Successfully");
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **FileNotFoundException** | `dataDir`‑pad is onjuist of de bestandsnaam is verkeerd gespeld. | Controleer de map‑string en zorg ervoor dat het `.mpp`‑bestand bestaat op de opgegeven locatie. |
| **NullPointerException on `project.get(...)`** | Het projectbestand bevat geen valutainformatie (onwaarschijnlijk) of de eigenschaps‑sleutel is fout. | Gebruik `project.contains(Prj.CURRENCY_CODE)` om het bestaan te controleren vóór het lezen. |
| **LicenseException** | Uitvoeren zonder een geldige Aspose.Tasks‑licentie in een productieomgeving. | Pas een licentiebestand toe met `License license = new License(); license.setLicense("Aspose.Tasks.lic");` vóór het maken van het `Project`‑object. |

## Veelgestelde vragen

**Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?**  
A: Aspose.Tasks ondersteunt .mpp‑bestanden die zijn gegenereerd door Microsoft Project 2003‑2021, zowel oudere als de nieuwste formaten.

**Q: Can I modify currency properties using Aspose.Tasks?**  
A: Ja, u kunt zowel lezen als schrijven van valutainstellingen. Gebruik `project.set(Prj.CURRENCY_CODE, "EUR");` en sla vervolgens het project op.

**Q: Is Aspose.Tasks suitable for commercial use?**  
A: Absoluut. Het is een commerciële bibliotheek; u kunt een licentie aanschaffen [here](https://purchase.aspose.com/buy).

**Q: Does Aspose.Tasks offer a free trial?**  
A: Ja, een volledig functionele proefversie is beschikbaar via [here](https://releases.aspose.com/).

**Q: Where can I seek help or support for Aspose.Tasks?**  
A: Het officiële Aspose.Tasks‑forum is de beste plek voor ondersteuning – bezoek het [here](https://forum.aspose.com/c/tasks/15).

## Aanvullende FAQ (AI‑geoptimaliseerd)

**Q: How do I programmatically extract only the currency symbol in Java?**  
A: Roep `project.get(Prj.CURRENCY_SYMBOL)` aan en cast het resultaat naar een `String`. Dit retourneert het exacte symbool dat in het projectbestand wordt gebruikt.

**Q: Can I read currency properties from a password‑protected .mpp file?**  
A: Ja. Laad het bestand met de juiste overload van de `Project`‑constructor die een wachtwoord accepteert, en lees vervolgens de eigenschappen zoals getoond.

**Q: What performance can I expect when processing many project files?**  
A: Aspose.Tasks werkt in‑process en leest een standaard .mpp‑bestand doorgaans in enkele milliseconden. Voor bulkbewerkingen kunt u overwegen dezelfde `Project`‑instantie waar mogelijk te hergebruiken.

## Conclusie
U heeft nu geleerd hoe u **read currency properties java** en **extract currency symbol java** kunt gebruiken vanuit een MS Project‑bestand met Aspose.Tasks for Java. Deze mogelijkheid stelt u in staat om valutametadata op te nemen in aangepaste rapporten, financiële analyses of integratie‑pijplijnen zonder afhankelijk te zijn van Microsoft Project zelf. Voel u vrij om te experimenteren met het wijzigen van de eigenschappen of het combineren van deze gegevens met andere projectattributen om rijkere oplossingen te bouwen.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}