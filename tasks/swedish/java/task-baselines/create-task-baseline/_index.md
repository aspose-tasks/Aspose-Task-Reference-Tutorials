---
date: 2026-08-29
description: Lär dig hur du lägger till en uppgift i ett projekt i Java, skapar en
  uppgiftslista och sätter en baslinje utan Microsoft Project med hjälp av Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Skapa en uppgiftsbaslinje i Aspose.Tasks
og_description: Lär dig hur du lägger till en uppgift i ett projekt i Java och sätter
  en baslinje med Aspose.Tasks. Denna guide visar steg‑för‑steg‑kod utan att behöva
  Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Hur man lägger till en uppgift i ett projekt i Java och sätter en baslinje
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Hur man lägger till en uppgift i ett projekt i Java och sätter en baslinje
url: /sv/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till en uppgift i projekt i Java och sätter en baslinje

## Introduktion
I den här handledningen kommer du att **lägga till en uppgift i projektet** programatiskt, generera en Microsoft Project‑uppgiftsbaslinje och spara filen — allt utan att någonsin öppna Microsoft Project. Aspose.Tasks for Java ger dig ett rent Java‑API som fungerar på alla plattformar, vilket gör det perfekt för automatiserade byggpipelines, rapporteringstjänster eller någon server‑sid lösning som behöver manipulera .mpp‑filer.

## Snabba svar
- **Vad gör Aspose.Tasks?** Den tillhandahåller ett Java‑API för att skapa, läsa och redigera Microsoft Project‑filer utan att kräva Microsoft Project.  
- **Behöver jag ha Microsoft Project installerat?** Nej, biblioteket fungerar helt oberoende.  
- **Vilken Java‑version krävs?** JDK 8 eller högre.  
- **Kan jag sätta en baslinje för en enskild uppgift?** Ja – anropa `setBaseline` på en lista som bara innehåller de uppgifter du vill.  
- **Behövs en licens för produktion?** Ja, en kommersiell licens tar bort utvärderingsgränser och låser upp alla funktioner.

## Vad är en uppgiftsbaslinje?
En uppgiftsbaslinje fångar det ursprungligt planerade startdatumet, slutdatumet och arbetsinsatsen för en uppgift vid den tidpunkt då schemat först sparas. Denna ögonblicksbild fungerar som en referenspunkt, vilket gör det möjligt för projektledare att jämföra faktisk framdrift och kostnader mot den ursprungliga planen, samt att beräkna avvikelser för prestationsanalys.

## Varför använda Aspose.Tasks för att lägga till en uppgift i projekt i Java?
Du kan skapa, modifiera och sätta baslinjer för uppgifter utan någon skrivbordsinstallation, vilket möjliggör helt automatiserade arbetsflöden. Aspose.Tasks stöder **50+ in‑ och utdataformat** och kan hantera projekt med **hundratals uppgifter** medan minnesanvändningen hålls under 200 MB, vilket gör det idealiskt för molntjänster och CI/CD‑pipelines.

## Förutsättningar
1. **Java Development Kit (JDK)** – installera JDK 8 eller nyare.  
2. **Aspose.Tasks for Java** – ladda ner biblioteket från [download link](https://releases.aspose.com/tasks/java/).  

## Importera paket
För att börja arbeta med Aspose.Tasks i ditt Java‑projekt, importera de nödvändiga paketen:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Steg 1: skapa ett projektobjekt
`Project`‑klassen är Aspose.Tasks övergripande objekt som representerar en Microsoft Project‑fil i minnet. Att instansiera den ger dig ett tomt projekt som du kan fylla med uppgifter, resurser och kalendrar.

```java
Project project = new Project();
```
Här instansierar vi ett nytt `Project`‑objekt – detta representerar MS Project‑filen som kommer att innehålla vår uppgiftslista.

## Steg 2: lägg till en uppgift i projektet
`Task`‑klassen representerar ett enskilt arbetsobjekt i ett projektschema. Varje `Task` kan ha sin egen varaktighet, startdatum och resursallokeringar.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Genom att använda `getRootTask()` får vi åtkomst till rotpunkten i projektets hierarki och **lägger till en uppgift i Microsoft Project**. Strängen `"Task"` är uppgiftsnamnet; du kan ersätta den med vilken beskrivning du behöver.

## Steg 3: sätt baslinje för angivna uppgifter
`BaselineType` är en uppräkning som definierar vilken baslinjeslot (Baseline, Baseline1 … Baseline10) du vill skriva till. Genom att skicka en lista med uppgifter kan du sätta baslinje endast för de objekt du väljer.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
För att **sätta en baslinje utan MS Project**, skapa en lista med de uppgifter du vill sätta baslinje för (här `myList`) och skicka den till `setBaseline`. Fyll `myList` med de uppgifter du lagt till om du bara behöver en selektiv baslinje.

## Steg 4: sätt baslinje för hela projektet
`setBaseline` skriver de valda baslinjevärdena till varje uppgift i projektet.  
Om du föredrar att sätta baslinje för hela projektet i ett enda anrop, anropa helt enkelt `setBaseline` med önskad `BaselineType`.

```java
project.setBaseline(BaselineType.Baseline);
```
Detta anrop skriver de valda baslinjevärdena för **varje uppgift** i projektet, vilket säkerställer en komplett ögonblicksbild av det ursprungliga schemat.

## Hur man lägger till en uppgift i Microsoft Project med Aspose.Tasks
`add()` skapar en ny underuppgift under den angivna föräldrauppgiften och returnerar det nyss skapade `Task`‑objektet.  
Du lägger till en uppgift genom att anropa `add()` på ett föräldra‑`Task`‑objekt (vanligtvis rotuppgiften). Metoden returnerar en ny `Task`‑instans som du kan vidare konfigurera — varaktighet, startdatum, resurser eller anpassade fält — innan du sparar projektfilen.

## Hur man sätter en baslinje utan MS Project
Aspose.Tasks möjliggör skapande av baslinjer helt via kod. Välj en `BaselineType` (t.ex. `BaselineType.Baseline`) och anropa `setBaseline`. Du kan upprepa detta med `Baseline1`‑`Baseline10` för att behålla flera revisionsbaslinjer, allt utan att öppna Microsoft Project.

## Vanliga problem och lösningar
- **Baslinjen visas inte:** Se till att du anropar `project.save("output.mpp")` efter att ha satt baslinjen (sparsteg utelämnat här för korthet).  
- **Uppgiftslistan visas tom:** Verifiera att du lägger till uppgifter till rätt förälder (`getRootTask()` eller en underuppgift).  
- **Version mismatch‑fel:** Använd den senaste Aspose.Tasks‑JAR‑filen för att garantera kompatibilitet med nyare .mpp‑format.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java utan att Microsoft Project är installerat?**  
A: Ja, Aspose.Tasks fungerar oberoende och kräver inte Microsoft Project på värddatorn.

**Q: Är Aspose.Tasks för Java kompatibel med olika versioner av Microsoft Project?**  
A: Absolut. Biblioteket stöder projektfiler från 2007 till de senaste 2024‑utgåvorna.

**Q: Kan jag manipulera projektresurser med Aspose.Tasks för Java?**  
A: Ja, du kan lägga till, uppdatera och ta bort resurser programatiskt, precis som uppgifter.

**Q: Stöder Aspose.Tasks för Java att sätta uppgiftsberoenden?**  
A: Ja, du kan definiera föregångare‑efterföljare‑relationer med hjälp av `TaskLink`‑klassen.

**Q: Finns teknisk support för Aspose.Tasks för Java?**  
A: Ja, du kan få hjälp via [supportforumet](https://forum.aspose.com/c/tasks/15), där Aspose‑personal och communityn svarar på frågor.

## Slutsats
Genom att följa dessa steg har du lärt dig hur man **lägger till en uppgift i projektet** i Java, skapar en uppgiftslista och **sätter en baslinje utan MS Project** med Aspose.Tasks. Detta tillvägagångssätt effektiviserar projektautomation, tar bort behovet av skrivbordsinstallationer av Project och ger dig full programmatisk kontroll över varje aspekt av ditt schema.

---

**Senast uppdaterad:** 2026-08-29  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar ett projekt med Aspose.Tasks – Ange nya uppgiftsegenskaper](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Hur man anger baslinjeduration i Aspose.Tasks för Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Skapa uppgifter Aspose Java – Uppgiftsegenskaper](/tasks/java/task-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}