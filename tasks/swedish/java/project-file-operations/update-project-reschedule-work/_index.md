---
date: 2025-12-23
description: Lär dig hur du uppdaterar MS Project‑filer och omplanerar ofullbordat
  arbete med Aspose.Tasks för Java. Se också hur du sparar MS Project‑XML.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Uppdatera MS Project och schemalägg om arbete med Aspose.Tasks
url: /sv/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uppdatera MS Project och omplanera arbete med Aspose.Tasks

## Introduktion
Microsoft Project är ett allmänt använt projekt‑hanteringsverktyg som hjälper team att planera, följa upp och leverera arbete i tid. När scheman förändras behöver du ofta **uppdatera MS Project**‑filer programatiskt – markera arbete som slutfört, flytta återstående uppgifter och hålla projektbaslinjen korrekt. Aspose.Tasks för Java ger dig ett rent, typ‑säkert API för att göra exakt detta utan att öppna GUI‑gränssnittet. I den här handledningen ser du hur du uppdaterar ett projekt, markerar arbete som färdigt fram till ett specifikt datum och sedan **hur du omplanerar MS Project**‑arbete som fortfarande är kvar.

## Snabba svar
- **Vad betyder “update MS Project”?** Det markerar uppgifter som slutförda fram till ett givet datum och skriver tillbaka ändringarna till filen.  
- **Kan jag omplanera återstående arbete automatiskt?** Ja – använd `rescheduleUncompletedWorkToStartAfter` för att skjuta ofullständiga uppgifter framåt.  
- **Vilket filformat sparas?** Exemplen sparar projektet som XML (`SaveFileFormat.Xml`).  
- **Behöver jag en licens för att köra koden?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version krävs?** JDK 8 eller högre.

## Vad är “update MS Project” i kod?
Att uppdatera ett projekt betyder att programatiskt ändra uppgiftsdatum, varaktigheter eller färdigstadsprocent och spara dessa ändringar. Aspose.Tasks exponerar metoder som `updateProjectWorkAsComplete` som tillämpar förändringarna baserat på ett referens‑`Date` du anger.

## Varför använda Aspose.Tasks för Java för att uppdatera MS Project?
- **Ingen UI‑beroende** – automatisera massändringar i många filer.  
- **Hög noggrannhet** – biblioteket bevarar all inbyggd Project‑data (resurser, kalendrar, anpassade fält).  
- **Plattformsoberoende** – kör samma kod på Windows, Linux eller macOS.  
- **Spara MS Project XML** – du kan exportera det uppdaterade projektet till det allmänt stödda XML‑formatet för efterföljande verktyg.

## Förutsättningar
1. Java Development Kit (JDK) installerat.  
2. Aspose.Tasks för Java‑biblioteket – ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. Grundläggande kunskap om Java‑syntax och objekt‑orienterade koncept.

## Importera paket
Först importerar du de nödvändiga Aspose.Tasks‑klasserna och Java‑verktygen:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Steg 1: Skapa projektet
Skapa en ny `Project`‑instans, definiera några exempeluppgifter, sätt deras varaktigheter och etablera beroenden. Spara sedan det initiala tillståndet så att du kan se före‑och‑efter‑effekten.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Steg 2: Uppdatera projektarbete
Markera arbete som slutfört fram till ett specifikt avstängningsdatum. Detta är kärnan i **update MS Project** – API‑et justerar automatiskt uppgiftens framsteg och datum.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Steg 3: Omplanera ofullständigt arbete
Efter att ha markerat slutfört arbete behöver du ofta skjuta de återstående uppgifterna framåt. Följande anrop flyttar allt ofullständigt arbete så att det startar efter samma avstängningsdatum, vilket i praktiken är **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| Uppgifter visar inte uppdaterade datum | Projektet sparades i ett annat format (t.ex. `.mpp`) | Använd `SaveFileFormat.Xml` för att behålla XML‑strukturen intakt. |
| `updateProjectWorkAsComplete` verkar göra ingenting | Referensdatumet är tidigare än projektets start | Säkerställ att `Calendar`‑datumet ligger inom projektets tidslinje. |
| Omplanerade uppgifter överlappar | Ingen kalender eller resursutjämning tillämpad | Applicera en `Project`‑kalender eller använd `Task.setStart` manuellt efter omplanering. |

## Vanliga frågor (utökad)

**Q: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?**  
A: Ja, Aspose.Tasks för Java tillhandahåller robusta API:er för att hantera uppgifter, beroenden, resurser och andra projektdelar effektivt.

**Q: Finns en provversion av Aspose.Tasks för Java?**  
A: Ja, du kan få en gratis provversion från [here](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Tasks för Java?**  
A: Du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för hjälp eller frågor.

**Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?**  
A: Ja, tillfälliga licenser finns att köpa [here](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks för Java?**  
A: Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/tasks/java/) för omfattande guider och API‑referenser.

## Slutsats
I den här handledningen gick vi igenom hela processen för att **uppdatera MS Project**‑filer, markera arbete som slutfört och sedan **hur du omplanerar MS Project**‑uppgifter som fortfarande är ofullständiga. Genom att spara projektet som XML behåller du kompatibilitet med andra verktyg och har en tydlig revisionsspårning av förändringarna. Använd dessa mönster för att automatisera schemajusteringar i stora portföljer, integrera med CI‑pipelines eller bygga anpassade rapporteringsdashboards.

---

**Senast uppdaterad:** 2025-12-23  
**Testat med:** Aspose.Tasks för Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}