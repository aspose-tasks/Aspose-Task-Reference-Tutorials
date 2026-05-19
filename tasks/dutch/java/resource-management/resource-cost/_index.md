---
date: 2026-01-15
description: Leer hoe u kunt werken met begroot kostwerk dat gepland is in Microsoft
  Project‑bestanden met behulp van Aspose.Tasks voor Java. Volg onze stapsgewijze
  handleiding.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Begroot kostenwerk gepland met Aspose.Tasks voor Java
url: /nl/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Begroot kosten werk gepland met Aspose.Tasks for Java

## Inleiding

Het beheren van **budgeted cost work scheduled** (BCWS) is essentieel om een project op koers te houden en ervoor te zorgen dat de financiële prognose overeenkomt met het geplande werk. In Microsoft Project vertegenwoordigt BCWS het bedrag dat tot een bepaalde datum aan het geplande werk had moeten worden uitgegeven. Aspose.Tasks for Java geeft u volledige programmatische controle over deze waarden, waardoor u resourcekosten kunt lezen, wijzigen en rapporteren zonder handmatig het .mpp‑bestand te openen. In deze tutorial lopen we een volledig voorbeeld door dat laat zien hoe een project te laden, door de resources te itereren en de budgeted cost work scheduled weer te geven naast andere belangrijke kostmetrische.

## Snelle antwoorden
- **Wat betekent BCWS?** Budgeted Cost Work Scheduled – de geplande kosten voor werk dat tot nu toe is gepland.  
- **Welke API‑eigenschap haalt BCWS op?** `Rsc.BCWS` op een `Resource`‑object.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis evaluatielicentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Kan ik BCWS‑waarden wijzigen?** Ja, u kunt `Rsc.BCWS` instellen net als elk ander numeriek veld.  
- **Ondersteunde Project‑versies?** Alle Microsoft Project‑versies van 2000 tot het nieuwste .mpp‑formaat.

## Wat is budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** is een prestatiemeting die de kosten weergeeft die tot een bepaald moment voor het geplande werk hadden moeten worden gemaakt. Het is een hoeksteen van Earned Value Management (EVM) en helpt projectmanagers de geplande uitgaven te vergelijken met de werkelijke uitgaven.

## Voorvereisten

Voordat u in de code duikt, zorg ervoor dat u het volgende heeft:

1. Een stevige basis in Java‑fundamentals.  
2. Aspose.Tasks for Java toegevoegd aan uw project (Maven/Gradle of JAR).  
3. Een Microsoft Project‑bestand (`.mpp`) dat resources met kostengegevens bevat (bijv. *ResourceCosts.mpp*).

## Importeer pakketten

Eerst importeert u de Aspose.Tasks‑klassen die nodig zijn voor het verwerken van projecten en resources:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Stap 1: Definieer de gegevensdirectory

Vervang `"Your Data Directory"` door het absolute of relatieve pad waar *ResourceCosts.mpp* zich bevindt.

```java
String dataDir = "Your Data Directory";
```

## Stap 2: Laad het MS Project‑bestand

De `Project`‑constructor leest het .mpp‑bestand en bouwt een in‑memory‑representatie die u kunt opvragen.

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

## Stap 3: Itereer door resources

Deze lus doorloopt elke resource die in het project is gedefinieerd, waardoor u toegang krijgt tot de kostvelden.

```java
for (Resource res : prj.getResources()) {
```

## Stap 4: Controleer resource‑naam en kosten

In de `if`‑block doen we:

* Print de **total cost** (`Rsc.COST`).  
* Print de **actual cost of work performed** (`Rsc.ACWP`).  
* Print de **budgeted cost work scheduled** (`Rsc.BCWS`) – de primaire metriek waarop we ons richten.  
* Print de **budgeted cost work performed** (`Rsc.BCWP`).

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Deze vier waarden geven u een snel overzicht van de financiële status van het project.

## Waarom het monitoren van budgeted cost work scheduled belangrijk is

* **Vroegtijdige waarschuwing:** Als BCWS aanzienlijk hoger is dan de werkelijke kosten, kunt u resources over‑toewijzen.  
* **Earned Value‑analyse:** BCWS is een belangrijke invoer voor het berekenen van Cost Variance (CV) en Schedule Variance (SV).  
* **Forecasting:** Nauwkeurige BCWS‑gegevens helpen bij het voorspellen van toekomstige cash‑flowbehoeften en informeren de rapportage aan stakeholders.

## Veelvoorkomende problemen & probleemoplossing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| `null` afgedrukt voor BCWS | Resource heeft geen kosttarieftabel gedefinieerd | Definieer een kosttarieftabel voor de resource in Microsoft Project of stel deze programmatisch in via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` bij itereren van resources | Projectbestand beschadigd of bevat lege resource‑items | Valideer het .mpp‑bestand in Microsoft Project en verwijder lege resources |
| Onverwachte waarden (bijv. negatieve BCWS) | Aangepaste velden die standaard kostvelden overschrijven | Zorg ervoor dat u de standaard `Rsc.BCWS` benadert en niet een aangepast veld met dezelfde naam |

## Veelgestelde vragen

**Q: Kan ik de BCWS‑waarde programmatisch bijwerken?**  
A: Ja. Gebruik `res.set(Rsc.BCWS, newValue)` en sla vervolgens het project op met `prj.save("Updated.mpp")`.

**Q: Ondersteunt Aspose.Tasks projecten met meerdere valuta?**  
A: Absoluut. Kostvelden respecteren de valutainstellingen die in het Project‑bestand zijn gedefinieerd.

**Q: Is er een manier om deze kostmetrische naar CSV te exporteren?**  
A: U kunt over de resources itereren en de waarden naar een `StringBuilder` schrijven of een CSV‑bibliotheek gebruiken om het bestand te genereren.

**Q: Hoe verschilt BCWS van BCWP?**  
A: BCWS is de geplande kost voor gepland werk, terwijl BCWP (Budgeted Cost Work Performed) de geplande kost weergeeft voor werk dat daadwerkelijk is voltooid.

**Q: Heb ik een speciale licentie nodig om kostgegevens te lezen?**  
A: De evaluatielicentie biedt volledige lees‑/schrijftoegang; een commerciële licentie is vereist voor productie‑implementaties.

## Conclusie

Door gebruik te maken van Aspose.Tasks for Java krijgt u nauwkeurige, programmatische toegang tot **budgeted cost work scheduled** en andere essentiële kostmetrische. Dit stelt u in staat om aangepaste dashboards te bouwen, Earned Value‑rapporten te automatiseren en uw projecten financieel op koers te houden — allemaal zonder handmatige interactie met Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose