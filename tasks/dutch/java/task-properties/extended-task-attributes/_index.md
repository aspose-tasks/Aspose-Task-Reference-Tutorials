---
date: 2026-01-28
description: Leer hoe u uitgebreide taak‑attributen kunt lezen met Aspose.Tasks voor
  Java en efficiënt het type van aangepaste velden kunt wijzigen.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Uitgebreide taakattributen lezen met Aspose.Tasks voor Java
url: /nl/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees uitgebreide taak‑attributen met Aspose.Tasks voor Java

## Inleiding
In deze uitgebreide tutorial ontdek je hoe je **uitgebreide taak‑attributen** kunt lezen uit Microsoft Project‑bestanden met behulp van de Aspose.Tasks‑bibliotheek voor Java. Of je nu een rapportagetool bouwt, gegevens synchroniseert, of gewoon dieper inzicht nodig hebt in aangepaste velden, het beheersen van deze functie stelt je in staat om elk stukje informatie dat in een project is opgeslagen te extraheren. We lopen de benodigde setup door, laten zien hoe je het type van een aangepast veld kunt wisselen bij het verwerken van attributen, en geven praktische tips om veelvoorkomende valkuilen te vermijden.

## Snelle Antwoorden
- **Wat betekent “read extended task attributes”?** Het verwijst naar het extraheren van waarden van aangepaste velden die verder gaan dan de standaard taak‑eigenschappen in een Project‑bestand.  
- **Welke klasse biedt toegang tot deze attributen?** De `ExtendedAttribute`‑klasse in Aspose.Tasks.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik het attribuuttype tijdens runtime wijzigen?** Ja – gebruik de `switch`‑statement om **het type van een aangepast veld te wisselen** op basis van `CustomFieldType`.  
- **Is dit compatibel met Java 8 en later?** Absoluut, de API ondersteunt JDK 8+.

## Wat zijn uitgebreide taak‑attributen?
Uitgebreide taak‑attributen zijn door de gebruiker gedefinieerde velden (tekst, datum, getal, vlag, enz.) die de standaard taak‑eigenschappen in Microsoft Project aanvullen. Aspose.Tasks maakt ze beschikbaar via de `ExtendedAttribute`‑collectie die aan elk `Task`‑object is gekoppeld, zodat je hun waarden programmatisch kunt lezen of wijzigen.

## Waarom uitgebreide taak‑attributen lezen?
- **Volledig inzicht:** Krijg inzicht in aangepaste gegevens die belanghebbenden aan de planning hebben toegevoegd.  
- **Automatisering:** Vul dashboards, genereer aangepaste rapporten, of migreer gegevens naar andere systemen zonder handmatige export.  
- **Flexibiliteit:** Werk met elk type aangepast veld—tekst, datum, duur, kosten, vlag—door elk geval op de juiste manier af te handelen.

## Voorwaarden
Voordat we beginnen, zorg ervoor dat je het volgende hebt:
- Basiskennis van Java‑programmeren.  
- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Een IDE zoals IntelliJ IDEA of Eclipse.  

## Pakketten importeren
Begin met het importeren van de benodigde klassen voor het Aspose.Tasks‑project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Stap 1: Toegang tot taak‑ en uitgebreide attributen
Laad een Project‑bestand en doorloop elke taak om bij de uitgebreide attributen te komen:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Stap 2: Het ophalen van veld‑ID en waarde‑GUID
Print de interne identifiers die je helpen te begrijpen met welk aangepast veld je te maken hebt:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Stap 3: Hoe het type van een aangepast veld te wisselen bij het lezen van uitgebreide taak‑attributen
Gebruik een `switch`‑statement op `CustomFieldType` om elk mogelijk gegevenstype correct af te handelen:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Herhaal deze stappen voor elke taak in je project om elk uitgebreid taak‑attribuut te verkennen en te manipuleren.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Null‑waarden geretourneerd** | Controleer of het aangepaste veld daadwerkelijk is ingevuld in het bron‑.mpp‑bestand. |
| **Onjuist type weergegeven** | Zorg ervoor dat je de juiste `CustomFieldType` gebruikt in de `switch`‑statement; niet‑overeenkomende types veroorzaken standaardwaarden. |
| **Prestatie‑vertraging bij grote projecten** | Verwerk taken in batches of filter alleen de taken die je nodig hebt door `project.getRootTask().getChildren().stream()` te gebruiken met geschikte predicaten. |

## Veelgestelde vragen
### Kan ik uitgebreide taak‑attributen programmatisch wijzigen?
Ja, je kunt uitgebreide taak‑attributen wijzigen met Aspose.Tasks voor Java. Raadpleeg de documentatie voor gedetailleerde instructies.

### Is er een proefversie beschikbaar?
Ja, je kunt de gratis proefversie [hier](https://releases.aspose.com/) benaderen.

### Waar kan ik ondersteuning vinden voor Aspose.Tasks voor Java?
Voor ondersteuning kun je het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken.

### Hoe kan ik een tijdelijke licentie verkrijgen?
Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen.

### Waar kan ik de volledige versie van Aspose.Tasks voor Java kopen?
Je kunt de volledige versie [hier](https://purchase.aspose.com/buy) kopen.

---

**Laatst bijgewerkt:** 2026-01-28  
**Getest met:** Aspose.Tasks Java API (latest stable release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}