---
date: 2026-09-09
description: Lär dig hur du identifierar cross project tasks med Aspose.Tasks för
  Java. Utforska sömlös integration, effektiv hantering och verkliga exempel.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identifiera cross project tasks i Aspose.Tasks
og_description: Identifiera cross project tasks i Aspose.Tasks för Java. Lär dig hur
  du ställer in document directory, hämtar task IDs och hanterar linked projects effektivt.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identifiera cross project tasks i Aspose.Tasks – Java guide
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identifiera cross project tasks i Aspose.Tasks
url: /sv/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identifiera projektöverskridande uppgifter i Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **hur man identifierar projektöverskridande uppgifter** med Aspose.Tasks för Java. Oavsett om du underhåller en portfölj av inter‑beroende scheman eller behöver granska externa beroenden, visar stegen nedan hur du hittar uppgifter som refererar till andra projektfiler, hämtar deras identifierare och arbetar med dem programmässigt.

## Snabba svar
- **Vad betyder “identifiera projektöverskridande uppgifter”?** Det betyder att lokalisera uppgifter som refererar till eller är beroende av uppgifter i en annan projektfil.  
- **Vilken metod skriver ut uppgiftens ID?** Använd `externalTask.get(Tsk.ID)` för att skriva ut uppgiftens ID.  
- **Hur sätter jag dokumentkatalogen?** Tilldela mappens sökväg till en `String`-variabel (t.ex. `dataDir`).  
- **Vilken egenskap hämtar en uppgift via UID?** Anropa `getChildren().getByUid(yourUid)`.  
- **Behöver jag en licens för produktionsanvändning?** Ja, en giltig Aspose.Tasks-licens krävs för kommersiella distributioner.

## Vad är “identifiera projektöverskridande uppgifter”?
Att identifiera projektöverskridande uppgifter låter dig spåra relationer mellan uppgifter som är spridda över flera Microsoft Project-filer. Genom att lokalisera uppgifter som refererar till eller är beroende av externa scheman kan du förstå hur arbetsobjekt interagerar över projektgränser, förhindra dubbelt arbete och upprätthålla korrekta tidslinjer. Denna funktion är avgörande för storskaliga portföljer där uppgifter delas eller är beroende av externa scheman.

## Varför använda Aspose.Tasks för Java?
Aspose.Tasks för Java stöder **över 50 in- och utdataformat** (inklusive MPP, MPX, XML och CSV) och kan bearbeta projekt med **upp till 10 000 uppgifter** utan att ladda hela filen i minnet. Biblioteket fungerar på alla JVM‑kompatibla plattformar, kräver ingen Microsoft Project‑installation och erbjuder full API‑åtkomst till ID:n, UID:n, externa ID:n och länkningsmetadata.

## Förutsättningar
- En fungerande Java‑utvecklingsmiljö (JDK 8 eller högre).  
- Aspose.Tasks för Java installerat. Du kan ladda ner det **[here](https://releases.aspose.com/tasks/java/)**.  
- En giltig Aspose.Tasks‑licensfil om du planerar att köra koden i produktion.

## Importera paket
`Project`‑klassen representerar en Microsoft Project‑fil, `Task` representerar en enskild uppgift, och `Tsk` tillhandahåller konstanter för uppgiftsfält.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Steg 1: ange dokumentkatalog
`dataDir`‑strängen innehåller sökvägen till mappen som innehåller dina `.mpp`‑filer.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Steg 2: ladda externt projekt
`Project externalProject` laddar den angivna externa projektfilen för inspektion.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Steg 3: hämta extern uppgift via uid
`externalProject.getChildren().getByUid(uid)` hämtar en uppgift från det externa projektets uppgiftskollektion med hjälp av dess unika identifierare.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Steg 4: skriv ut uppgiftens ID (primärt användningsfall)
`externalTask.get(Tsk.ID)` returnerar det interna ID som tilldelats av Aspose.Tasks för den angivna uppgiften.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Steg 5: skriv ut original (extern) uppgifts‑ID
`externalTask.get(Tsk.ExternalID)` hämtar det ursprungliga ID:t för uppgiften som definierats i källprojektfilen.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Upprepa ovanstående steg för alla ytterligare uppgifter du behöver spåra över projekt.

## Vanliga problem & tips
- **Sökvägsfel** – Se till att `dataDir` slutar med rätt filsökare (`/` eller `\\`).  
- **UID ej funnen** – Verifiera att UID finns i det externa projektet; använd `externalProject.getRootTask().getChildren().size()` för att lista tillgängliga UID:n.  
- **Licensundantag** – En saknad eller ogiltig licens kommer att kasta ett licensundantag vid körning.  
- **Stora projekt** – För projekt med mer än 5 000 uppgifter, överväg att använda `ProjectReader` med `LoadOptions`‑flaggan för att strömma data och minska minnesförbrukningen.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks stöder flera språk, inklusive Java, .NET och fler.

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks för Java?**  
A: Se dokumentationen **[here](https://reference.aspose.com/tasks/java/)**.

**Q: Finns det en gratis provperiod för Aspose.Tasks för Java?**  
A: Ja, du kan få en gratis provperiod **[here](https://releases.aspose.com/)**.

**Q: Hur kan jag få tillfällig licens för Aspose.Tasks?**  
A: Skaffa en tillfällig licens **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Behöver du hjälp eller har du specifika frågor?**  
A: Besök Aspose.Tasks supportforum **[here](https://forum.aspose.com/c/tasks/15)**.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Relaterade handledningar

- [Skapa projektledningsuppgiftsberoenden i Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Ställ in projektets startdatum och hantera föräldra- och barnuppgifter i Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Skapa MPP-projekt Java – Ändra uppgiftens framsteg med Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}