---
date: 2025-12-23
description: Lär dig hur du använder Aspose Tasks Java för att uppdatera projektschemat,
  ställa in veckans startdag, ändra dagar per månad och anpassa projektkalendern effektivt.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Hantera veckodagsegenskaper
url: /sv/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Hantera veckodagsegenskaper

## Introduktion
Aspose.Tasks for Java (aspose tasks java) är ett robust API som låter Java‑utvecklare arbeta med Microsoft Project‑filer utan att behöva ha Microsoft Project installerat. I den här handledningen kommer du att lära dig hur du **laddar en MPP‑fil**, **sätter veckans startdag**, **ändrar dagar per månad** och på annat sätt **anpassar projektkalendern** – alla viktiga steg för att uppdatera ett projektschema. I slutet kommer du att kunna justera veckodagsegenskaper programatiskt och spara ändringarna i det format du behöver.

## Snabba svar
- **Vad är den primära klassen för att hantera projekt?** `Project` från Aspose.Tasks‑biblioteket.  
- **Hur ändrar jag veckans startdag?** Använd `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Kan jag ladda en befintlig .mpp‑fil?** Ja—instansiera `Project` med filsökvägen.  
- **Vilken metod sparar projektet som XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.

## Förutsättningar
Innan du börjar, se till att du har följande:

- **Java Development Kit (JDK)** – senaste versionen installerad.  
- **Aspose.Tasks for Java‑biblioteket** – ladda ner det [här](https://releases.aspose.com/tasks/java/).  
- **En IDE** såsom IntelliJ IDEA, Eclipse eller NetBeans.  

## Importera paket
För att börja, importera de nödvändiga Aspose.Tasks‑klasserna:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Låt oss nu gå igenom varje steg för att hantera veckodagsegenskaper.

## Steg 1: Ladda en MPP‑fil
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Här **laddar vi en befintlig .mpp‑fil** (`load mpp file`) så att vi kan inspektera och ändra dess kalendersinställningar.*

## Steg 2: Visa aktuella veckodagsegenskaper
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Denna kod skriver ut den aktuella **veckans startdag**, **dagar per månad**, **minuter per dag** och **minuter per vecka** — de grundläggande elementen du ofta behöver för att **anpassa projektkalendern**.

## Steg 3: Ställ in nya veckodagsegenskaper
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
I detta steg **sätter vi veckans startdag** till måndag, **ändrar dagar per månad** till 24 och justerar dagliga och veckovisa minutantal. Dessa inställningar är vanliga när du behöver **uppdatera projektschemat** för att matcha en icke‑standard arbetskalender.

## Steg 4: Spara det uppdaterade projektet
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Det modifierade projektet sparas som en XML‑fil, vilket gör det enkelt att dela eller importera till andra verktyg.

## Steg 5: Bekräfta operationen
```java
System.out.println("Process completed Successfully");
```
Ett enkelt konsolmeddelande låter dig veta att arbetsflödet avslutades utan fel.

## Vanliga problem & tips
- **Felaktig filsökväg** – Verifiera att `dataDir` slutar med ett snedstreck eller använd `Paths.get(...)` för plattformsoberoende sökvägar.  
- **Licens inte angiven** – I en produktionsmiljö, anropa `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` innan du skapar `Project`.  
- **Oväntad veckostartdag** – Se till att du använder rätt `DayType`‑enumvärde (t.ex. `DayType.Sunday`).  

## Vanliga frågor

**Q: Kan Aspose.Tasks for Java hantera komplexa projektstrukturer?**  
A: Ja, Aspose.Tasks for Java erbjuder omfattande stöd för att hantera komplexa projektstrukturer med lätthet.

**Q: Är Aspose.Tasks for Java kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Absolut, Aspose.Tasks for Java stöder olika versioner av Microsoft Project‑filer, vilket säkerställer kompatibilitet över plattformar.

**Q: Kan jag integrera Aspose.Tasks for Java i mina befintliga Java‑applikationer?**  
A: Ja, Aspose.Tasks for Java erbjuder sömlösa integrationsmöjligheter, så att du kan förbättra dina Java‑applikationer med kraftfulla projektstyrningsfunktioner.

**Q: Tillhandahåller Aspose.Tasks for Java dokumentation och support?**  
A: Ja, du kan få tillgång till omfattande dokumentation och community‑support för Aspose.Tasks for Java på deras [website](https://releases.aspose.com/).

**Q: Finns det en gratis provversion av Aspose.Tasks for Java?**  
A: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks for Java från deras [website](https://reference.aspose.com/tasks/java/) för att utforska funktionerna innan du köper.

---

**Senast uppdaterad:** 2025-12-23  
**Testad med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}