---
date: 2025-12-25
description: Verken deze Aspose Tasks Java‑tutorial om te leren hoe u de projectversie
  van MS Project‑bestanden kunt bepalen. Stapsgewijze handleiding met codevoorbeelden.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose Tasks Java Tutorial: Bepaal MS Project‑versie'
url: /nl/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java Tutorial: Bepaal MS Project‑versie

## Introductie
In deze **aspose tasks java tutorial** ontdek je hoe je programmatisch de versie van een Microsoft Project‑bestand kunt vinden met behulp van de Aspose.Tasks‑bibliotheek voor Java. Het kennen van de bestandsversie helpt je compatibiliteitsproblemen te behandelen, migratiebeleid af te dwingen, of eenvoudigweg te loggen welke Project‑release een bestand heeft gemaakt. We lopen elke stap door—van het opzetten van de omgeving tot het afdrukken van de versie en de datum van laatste opslaan—zodat je deze controle kunt integreren in elke Java‑applicatie met vertrouwen.

## Snelle antwoorden
- **Waar gaat deze tutorial over?** Het bepalen van de MS Project‑bestandversie met Aspose.Tasks voor Java.  
- **Moet ik Microsoft Project geïnstalleerd hebben?** Nee, Aspose.Tasks werkt onafhankelijk.  
- **Welke bestandsformaten worden ondersteund?** XML‑gebaseerde Project‑bestanden (MPP, XML, enz.).  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een eenvoudige controle.  
- **Is een licentie vereist?** Een gratis proefversie werkt voor evaluatie; een licentie is nodig voor productie.

## Wat is Aspose Tasks Java Tutorial?
Een **aspose tasks java tutorial** biedt praktische begeleiding voor het gebruik van de Aspose.Tasks‑API in Java‑projecten. Het laat zien hoe je Microsoft Project‑gegevens kunt lezen, wijzigen en analyseren zonder dat Microsoft Project zelf nodig is.

## Waarom Aspose.Tasks gebruiken om de projectversie te bepalen?
- **Geen afhankelijkheid van Microsoft Project** – perfect voor server‑side automatisering.  
- **Nauwkeurige versie‑metadata** – haal de exacte SAVE_VERSION‑ en LAST_SAVED‑velden op.  
- **Cross‑platform** – werkt op elk OS dat Java ondersteunt.  
- **Hoge prestaties** – lichtgewicht parsing geschikt voor batchverwerking.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – elke recente JDK (8 of hoger).  
2. **Aspose.Tasks for Java JAR** – download deze van de [website](https://releases.aspose.com/tasks/java/) en voeg toe aan de classpath van je project.  
3. **MS Project‑bestand** – een XML‑gebaseerd Project‑bestand (bijv. `input.xml`) dat je wilt inspecteren.  

> **Pro tip:** Bewaar het Project‑bestand in een speciale `data`‑map om padbeheer te vereenvoudigen.

## Pakketten importeren
Eerst importeer je de essentiële Aspose.Tasks‑klassen:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Stap 1: Stel de projectdirectory in
Definieer de map die je Project‑bestand bevat.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute of relatieve pad waar `input.xml` zich bevindt.

## Stap 2: Laad het project
Maak een `Project`‑instantie aan door het XML‑bestand te laden.

```java
Project project = new Project(dataDir + "input.xml");
```

Als je bestand een andere naam heeft, pas dan `"input.xml"` dienovereenkomstig aan.

## Stap 3: Hoe de projectversie te bepalen
Haal de versie‑informatie en de tijdstempel van de laatste opslaan op.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

De eigenschap `Prj.SAVE_VERSION` geeft de Microsoft Project‑versie aan die werd gebruikt om het bestand op te slaan (bijv. 12 voor Project 2010). `Prj.LAST_SAVED` geeft de datum/tijd van de meest recente opslaan‑bewerking terug.

## Stap 4: Resultaat weergeven
Geef een succesvolle voltooiing van de versiecontrole aan.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| `NullPointerException` op `project.get(...)` | Bestand niet gevonden of pad onjuist | Controleer `dataDir` en bestandsnaam; gebruik een absoluut pad voor testen. |
| Onverwacht versienummer (bijv. 0) | Een niet‑Project XML‑bestand laden | Zorg ervoor dat het bestand een geldig Microsoft Project‑bestand is (MPP/XML). |
| Licentie‑exception | De proefversie gebruiken zonder een geldige licentie in productie | Pas je Aspose.Tasks‑licentie toe (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Veelgestelde vragen

### V: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?
A: Ja, Aspose.Tasks ondersteunt meerdere talen, waaronder .NET, Java en C++.

### V: Is Aspose.Tasks geschikt voor grootschalige projecten?
A: Absoluut, Aspose.Tasks is ontworpen om projecten van elke omvang moeiteloos te verwerken.

### V: Kan ik projectgegevens aanpassen met Aspose.Tasks?
A: Ja, je kunt projectgegevens manipuleren, taken, resources en veel meer aanpassen met Aspose.Tasks.

### V: Vereist Aspose.Tasks een Microsoft Project‑installatie?
A: Nee, Aspose.Tasks werkt onafhankelijk en vereist geen installatie van Microsoft Project.

### V: Is technische ondersteuning beschikbaar voor Aspose.Tasks?
A: Ja, je kunt technische ondersteuning krijgen via het Aspose.Tasks‑forum op [hier](https://forum.aspose.com/c/tasks/15).

**V: Hoe haal ik andere projecteigenschappen op (bijv. auteur, bedrijf)?**  
A: Gebruik `project.get(Prj.AUTHOR)` of `project.get(Prj.COMPANY)` op dezelfde manier als het versie‑voorbeeld.

**V: Kan ik de versie van een MPP‑bestand (binair formaat) controleren?**  
A: Ja, Aspose.Tasks kan `.mpp`‑bestanden direct laden; dezelfde `Prj.SAVE_VERSION`‑eigenschap werkt.

**V: Is er een manier om een ouder projectbestand programmatisch te upgraden naar een nieuwere versie?**  
A: Laad het oudere bestand en sla het vervolgens op met `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks schrijft standaard in het nieuwste formaat.

## Conclusie
Je hebt nu een beknopte **aspose tasks java tutorial** voltooid die **laat zien hoe je de projectversie** van MS Project‑bestanden kunt bepalen met Aspose.Tasks voor Java. Integreer dit fragment in grotere automatiseringsworkflows, rapportagetools of migratie‑hulpmiddelen om er zeker van te zijn dat je altijd de exacte Project‑versie kent waarmee je werkt.

---

**Laatst bijgewerkt:** 2025-12-25  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}