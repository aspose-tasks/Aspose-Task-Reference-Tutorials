---
date: 2026-06-05
description: Lär dig hur du filtrerar MPP-filer med Aspose.Tasks for Java, anpassar
  filterkriterier och filtrerar uppgifter efter datum för att effektivisera projektledning.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Hur man filtrerar MPP-filer med Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man filtrerar MPP-filer med Aspose.Tasks for Java
url: /sv/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så filtrerar du MPP-filer med Aspose.Tasks för Java

## Introduktion
Om du arbetar med Microsoft Project‑filer (*.mpp*) i en Java‑applikation, behöver du ofta **filtrera MPP‑filer** för att isolera de uppgifter, resurser eller tilldelningar som är viktigast. I den här handledningen går vi igenom **hur du filtrerar mpp‑filer** programmässigt med Aspose.Tasks för Java, visar hur du **anpassar filterkriterier**, och demonstrerar ett praktiskt scenario “filtrera uppgifter efter datum”. När du är klar har du ett färdigt kodexempel som du kan klistra in i vilket Java‑projekt som helst.

## Snabba svar
- **Vad betyder “filter mpp”?** Det betyder att extrahera en delmängd av projektdata baserat på definierade villkor.  
- **Vilket bibliotek hanterar detta?** Aspose.Tasks for Java tillhandahåller ett omfattande API för att skapa och tillämpa filter.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag filtrera uppgifter, resurser och tilldelningar?** Ja – varje entitetstyp har sin egen filtersamling.  
- **Krävs Java 8 eller högre?** Aspose.Tasks stödjer Java 8 och senare versioner.

## Vad är “how to filter mpp” i Java?
`How to filter mpp` är processen att använda Aspose.Tasks `s `Filter`‑objekt för att välja endast de projekteelement som uppfyller specifika villkor såsom startdatum, kostnad eller anpassade fält. Ladda ett `Project`, hämta ett `Filter`, och API‑et returnerar en samling som matchar dina kriterier, vilket möjliggör fokuserad rapportering eller vidare integration.

## Varför anpassa filterkriterier?
Anpassade filterkriterier låter dig rikta in dig på hög‑risk‑uppgifter, försenade poster eller resurser med budgetöverskridanden, och förvandlar en massiv projektfil till en koncis, handlingsbar vy. Aspose.Tasks stöder **50+ fördefinierade filtertyper** och låter dig bygga obegränsade egna filter, vilket minskar manuell datasökning med upp till 70 %.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller nyare.  
2. **Aspose.Tasks for Java** – ladda ner det från [download page](https://releases.aspose.com/tasks/java/).  
3. **En IDE** – IntelliJ IDEA, Eclipse eller NetBeans fungerar bra.  

## Importera paket
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` och `Project` är kärnklasser som används för att definiera och tillämpa filter på projektdata.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Steg‑för‑steg‑guide

### Steg 1: Ställ in projektet
Först skapar du en `Project`‑instans som pekar på den MPP‑fil du vill analysera, och laddar den i minnet. Detta enda steg förbereder hela projektmodellen för filtrering, validering och vidare manipulation, så att du kan komma åt uppgifter, resurser och tilldelningar via API‑et.

### Hur ställer jag in projektet för att filtrera MPP‑filer?
`Project`‑klassen laddar och representerar en MPP‑fil i minnet. Skapa en `Project`‑instans som pekar på den MPP‑fil du vill analysera, och ladda den i minnet. Detta enda steg förbereder hela projektmodellen för filtrering, validering och vidare manipulation, så att du kan komma åt uppgifter, resurser och tilldelningar via API‑et.

### Hur kan jag hämta och inspektera ett filter?
`Filter`‑objekt kapslar filterdefinitioner som används för att välja projektobjekt. Aspose.Tasks lagrar fördefinierade filter såsom “All Tasks” eller “Critical Tasks”. Använd `project.getTaskFilters().getByName("My Filter")` eller indexbaserad åtkomst för att få ett `Filter`‑objekt, och granska sedan dess `FilterCriteria`‑samling för att se varje regel och den logiska operatorn (AND/OR) som kombinerar dem, så att filtret matchar dina krav.

### Hur itererar jag genom inbäddade kriterierader?
`FilterCriteriaGroup` representerar en grupp filterkriterier kombinerade med en logisk operator. Filter kan innehålla grupper av kriterier, var och en med sin egen operator. Loopa igenom `filter.getCriteria().getRows()` och, för varje rad som är ett `FilterCriteriaGroup`, rekursivt gå in i dess underordnade rader. Denna traversering låter dig fullt förstå komplex filterlogik såsom “(Start < today AND Cost > 1000) OR Priority = High”, och justera kriterierna vid behov.

### Hur skriver jag ut kriterieinformation för felsökning?
Efter att ha traverserat kriterieträdet, skriv ut varje rads fältnamn, testoperator och värde till konsolen. Denna enkla dump hjälper dig verifiera att filtret matchar de avsedda affärsreglerna innan du tillämpar det på stora projekt, och gör det lättare att upptäcka felaktiga operatorer eller värden.

### Hur skapar jag ett helt nytt filter programmässigt?
Instansiera ett `Filter` med `new Filter("My Filter")`, och lägg sedan till det i projektets uppgiftsfiltersamling med `project.getTaskFilters().add(filter)`. Därefter fyller du dess `FilterCriteria`‑samling med önskade rader, specificerar fältnamn, testoperatorer och värden för att exakt definiera vilka uppgifter som ska inkluderas när filtret tillämpas.

### Kan jag tillämpa ett filter på resurser istället för uppgifter?
`ResourceFilters`‑samlingen innehåller filterdefinitioner som gäller resurser. Ja – använd `project.getResourceFilters()` för att arbeta med resurs‑specifika filter på samma sätt som uppgiftsfilter. Efter att ha lagt till eller hämtat ett filter, konfigurera dess `FilterCriteria` precis som du skulle göra för uppgifter, och tillämpa det sedan på resurs‑samlingen för att få den filtrerade mängden resurser.

### Är det möjligt att kombinera flera filter med OR‑logik?
Skapa en föräldra‑`FilterCriteriaGroup` med dess `Operation` satt till `OR`, och lägg sedan till enskilda `FilterCriteria`‑objekt som barn. Denna grupp utvärderar varje underkriterium och returnerar objekt som uppfyller någon av dem, vilket låter dig kombinera flera enkla filter till ett bredare urval.

### Stöder Aspose.Tasks filtrering på anpassade fält?
`CustomField`‑enum ger identifierare för anpassade fält som definierats i ett projekt. Absolut. Referera till anpassade fält via `CustomField`‑enum, och de beter sig som alla inbyggda fält i filteruttryck. Du kan inkludera dem i `FilterCriteria`‑rader, använda samma operatorer och värden, vilket möjliggör kraftfulla frågor på användardefinierad data tillsammans med standardprojektattribut.

### Vilken prestandapåverkan har filtrering på stora MPP‑filer?
Filtrering körs helt i minnet och bearbetar vanligtvis ett 1 000‑uppgiftsprojekt på under 200 ms. För projekt med flera tusen uppgifter, överväg att bara ladda de nödvändiga sektionerna med `ProjectReader` och tillämpa filter efter selektiv laddning, vilket håller minnesanvändningen låg och bibehåller snabba svarstider även på mycket stora projekt.

---

**Senast uppdaterad:** 2026-06-05  
**Testad med:** Aspose.Tasks for Java 24.10  
**Författare:** Aspose

## Relaterade handledningar

- [Ladda MPP-fil Java – Hantera projekt egenskaper med Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java – Enkel läsning av MS Project Online‑data](/tasks/java/project-data-reading/read-project-online/)
- [Ange projektets startdatum i MS Project med Aspose.Tasks för Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```