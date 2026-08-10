---
date: 2026-05-15
description: Lär dig hur du ställer in projektets startdatum, skriver projektinformation
  och sparar projektet som XML med Aspose.Tasks för Java.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: Skriv projektinformation i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java
url: /sv/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ange projektets startdatum i MS Project med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att upptäcka hur du **anger projektets startdatum** och skriver ytterligare MS Project‑information med Aspose.Tasks för Java. Oavsett om du automatiserar projektscheman, genererar rapporter eller integrerar projektdata i ett större system, ger programmatisk kontroll av startdatumet dig exakt styrning över dina tidslinjer. Vi går igenom varje steg—från att konfigurera miljön till att spara det uppdaterade projektet som en XML‑fil—så att du kan börja använda dessa tekniker omedelbart.

## Snabba svar
- **Vad är den primära klassen för att manipulera ett projekt?** `Project` från Aspose.Tasks‑biblioteket.  
  `Project`‑klassen representerar en MS Project‑fil i minnet.  
- **Hur anger jag projektets startdatum?** Använd `project.set(Prj.START_DATE, <date>)`.  
  `Prj.START_DATE` är nyckeln för egenskapen som används för att ange projektets startdatum.  
- **Kan jag också ange statusdatum?** Ja, med `project.set(Prj.STATUS_DATE, <date>)`.  
  `Prj.STATUS_DATE` specificerar datumet som speglar projektets aktuella status.  
- **Vilket format ska jag använda för att exportera projektet?** Spara som XML med `SaveFileFormat.Xml`.  
  `SaveFileFormat.Xml` indikerar att projektet kommer att sparas i XML‑format.  
- **Behöver jag en licens för produktionsanvändning?** En giltig Aspose.Tasks‑licens krävs för full funktionalitet.  
- **Vilka miljöer stöder Aspose.Tasks?** Windows, Linux och macOS med Java 8+.

## Vad är att ange projektets startdatum?
Att ange projektets startdatum bestämmer kalenderdagen då schemat börjar, vilket etablerar en grundlinje för alla uppgiftsberäkningar, beroenden och kritisk‑vägs‑analys. Genom att definiera detta datum programmässigt garanterar du att varje genererad projektfil startar från samma punkt, eliminerar manuella inmatningsfel och säkerställer repeterbara resultat över byggprocesser.

## Varför använda Aspose.Tasks för Java för att skriva projektinformation?
Aspose.Tasks för Java erbjuder **över 150 konfigurerbara projektegenskaper** och stödjer **30+ filformat**, vilket gör att du kan läsa, modifiera och skriva MS Project‑data utan att ha Microsoft Project installerat. Biblioteket körs på Windows, Linux och macOS, bearbetar filer med flera hundra sidor i ett minnes‑effektivt läge, och kan integreras i CI/CD‑pipelines, batch‑processingtjänster eller molnbaserade back‑ends. Dessa kvantifierade möjligheter gör det till det mest pålitliga valet för automatisering i företags‑skala.

## Förutsättningar
1. **Java Development Kit (JDK)** – någon nyare version (8+ rekommenderas).  
2. **Aspose.Tasks for Java‑biblioteket** – ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. **En IDE** – IntelliJ IDEA, Eclipse eller din favoriteditor för Java.  

## Importera paket
Först, importera de nödvändiga paketen i ditt Java‑projekt:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Steg 1: Ställ in datakatalog
Definiera katalogen där dina projektdata ska lagras.
```java
String dataDir = "Your Data Directory";
```

## Steg 2: Skapa projektinstans
`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild MS Project‑fil i minnet. Att initiera den skapar ett tomt schema som du omedelbart kan börja fylla.
```java
Project project = new Project();
```

## Steg 3: Ange projektinformationsegenskaper
Här anger vi **projektets startdatum**, flaggan för schema‑från‑start och statusdatum—som täcker de primära och sekundära nyckelorden *write project information* och *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Steg 4: Spara projekt som XML
Slutligen, spara den uppdaterade projektfilen. Att spara som XML säkerställer maximal kompatibilitet med efterföljande verktyg och håller filstorleken liten.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Fel startdatum** | Kalendermånaden är nollbaserad i Java. | Använd `Calendar.JULY` (eller lägg till 1 till månadsindex) som visas. |
| **Filen sparas inte** | `dataDir` finns inte eller saknar skrivbehörighet. | Skapa katalogen i förväg eller välj en skrivbar sökväg. |
| **Licensvarning** | Körning utan licens lägger till ett vattenmärke. | Applicera en giltig Aspose.Tasks‑licens innan du skapar `Project`‑objektet. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java för att läsa MS Project‑filer?**  
A: Ja, Aspose.Tasks för Java erbjuder robusta funktioner för både läsning och skrivning av MS Project‑filer.

**Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?**  
A: Absolut, Aspose.Tasks för Java stöder olika MS Project‑versioner, vilket säkerställer sömlös hantering av MPP-, XML- och Primavera‑format.

**Q: Finns det några begränsningar i provversionen av Aspose.Tasks för Java?**  
A: Provversionen tillåter full utforskning av funktioner men lägger till ett vattenmärke på genererade filer och begränsar antalet projekt‑entiteter du kan skapa.

**Q: Hur kan jag få support för Aspose.Tasks för Java?**  
A: Du kan söka hjälp i Aspose.Tasks‑community‑forumet [here](https://forum.aspose.com/c/tasks/15).

**Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?**  
A: Ja, tillfälliga licenser finns tillgängliga för korttidsanvändning. Du kan skaffa en från [here](https://purchase.aspose.com/temporary-license/).

## Slutsats
Du har nu lärt dig hur du **anger projektets startdatum**, skriver viktig projektinformation och **sparar projektet som XML** med Aspose.Tasks för Java. Dessa byggstenar ger dig möjlighet att automatisera projekt‑hanteringsarbetsflöden, generera konsekventa scheman och integrera MS Project‑data i dina Java‑applikationer. Nästa steg är att utforska hur du lägger till uppgifter, resurser och anpassade fält för att ytterligare berika dina automatiserade scheman.

---

**Last Updated:** 2026-05-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Relaterade handledningar

- [Hur man ställer in projektkalender med Aspose.Tasks för Java](/tasks/java/calendars/properties/)
- [Hur man läser projektinformation från Microsoft Project med Aspose.Tasks för Java](/tasks/java/project-properties/read-project-info/)
- [Ladda MPP‑fil Java – hantera projektegenskaper med Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}