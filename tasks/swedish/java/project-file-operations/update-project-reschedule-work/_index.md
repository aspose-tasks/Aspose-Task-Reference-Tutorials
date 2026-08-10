---
date: 2026-03-29
description: Lär dig hur du omplanerar ofullständigt arbete, uppdaterar projektarbetet
  och sparar MS Project-filer som XML med Aspose.Tasks för Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Omplanera ej slutfört arbete och uppdatera MS Project-filer med Aspose.Tasks
url: /sv/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Omplanera ofullständigt arbete och uppdatera MS Project-filer med Aspose.Tasks

## Introduktion
Microsoft Project är ett allmänt använt projektledningsverktyg som hjälper team att planera uppgifter, tilldela resurser och följa tidslinjer. Aspose.Tasks för Java ger utvecklare ett kraftfullt API för att programatiskt manipulera Microsoft Project-filer. I den här handledningen kommer du att lära dig hur du **uppdaterar projektarbete**, **omplanerar ofullständigt arbete** och **sparar MS Project-filen** i XML-format med Aspose.Tasks för Java.

## Snabba svar
- **Vad betyder “reschedule uncompleted work”?** Den flyttar allt återstående uppgiftsarbete så att det startar efter ett valt datum, medan slutförda delar förblir orörda.  
- **Vilken metod markerar arbete som slutfört?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Hur sparar jag ändringarna?** Använd `project.save(<path>, SaveFileFormat.Xml)`.  
- **Behöver jag en licens för produktion?** Ja, en giltig Aspose.Tasks-licens krävs för kommersiell användning.  
- **Vilken Java-version stöds?** Java 8 och senare stöds fullt ut.

## Vad är “reschedule uncompleted work”?
Omplanering av ofullständigt arbete justerar startdatumen för alla uppgifter som ännu inte är slutförda, så att de börjar efter ett angivet avstängningsdatum. Detta är användbart när en projektplan förändras på grund av förseningar eller förändringar i omfattning.

## Varför använda Aspose.Tasks för att uppdatera projektarbete och omplanera uppgifter?
- **Finjusterad kontroll:** Ställ in arbetsprocent och datum direkt.  
- **Ingen UI krävs:** Automatisera massuppdateringar i många projektfiler.  
- **Plattformsoberoende:** Fungerar på alla system som kör Java.  
- **Bevarar dataintegritet:** Alla beroenden, begränsningar och resurser förblir konsekventa.

## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.  
2. Aspose.Tasks för Java-biblioteket. Du kan ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. Grundläggande förståelse för Java-programmeringsspråket.

## Importera paket
Först, importera de nödvändiga paketen i din Java-kod:
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
Initiera ett nytt `Project`-objekt, definiera uppgifter, ange varaktigheter och etablera beroenden. Detta skapar baslinjeprojektet som vi senare kommer att uppdatera och omplanera.
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
Markera arbete som slutfört fram till ett specifikt datum. Detta steg demonstrerar **update project work**-operationen, som ofta är den första åtgärden före omplanering.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Steg 3: Omplanera ofullständigt arbete
Nu flyttar vi eventuellt återstående (ofullständigt) arbete så att det startar efter samma avstängningsdatum. Detta är den centrala **reschedule uncompleted work**-funktionen.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Slutsats
I den här handledningen gick vi igenom hur man **uppdaterar projektarbete**, **omplanerar ofullständigt arbete** och **sparar MS Project-filen** som XML med Aspose.Tasks för Java. Dessa funktioner är avgörande när projektplaner måste justeras baserat på faktiskt framsteg eller förändrade affärsprioriteringar.

## Vanliga frågor
### Q: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?
A: Ja, Aspose.Tasks för Java erbjuder robusta API:er för att effektivt hantera uppgifter, beroenden, resurser och andra projekteelement.

### Q: Finns en provversion tillgänglig för Aspose.Tasks för Java?
A: Ja, du kan få en gratis provversion från [here](https://releases.aspose.com/).

### Q: Hur kan jag få support för Aspose.Tasks för Java?
A: Du kan besöka [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för hjälp eller frågor.

### Q: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
A: Ja, tillfälliga licenser kan köpas [here](https://purchase.aspose.com/temporary-license/).

### Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks för Java?
A: Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/tasks/java/) för omfattande guider och API-referenser.

## Ytterligare vanliga frågor

**Q: Hur säkerställer jag att den sparade filen är kompatibel med äldre versioner av Microsoft Project?**  
A: Spara projektet med `SaveFileFormat.Xml`; XML stöds brett över Project-versioner.

**Q: Kan jag omplanera endast en delmängd av uppgifter istället för hela projektet?**  
A: Ja, du kan iterera över specifika uppgifter och anropa `task.setStart(date)` efter att ha beräknat det nya startdatumet.

**Q: Vad händer med resursallokeringar när jag omplanerar ofullständigt arbete?**  
A: Resursallokeringar flyttas automatiskt för att matcha de nya uppgiftens startdatum, vilket bevarar allokeringslogiken.

**Q: Är det möjligt att ångra en omplaneringsåtgärd programatiskt?**  
A: Du kan ladda om den ursprungliga projektfilen (eller en säkerhetskopia) för att återställa ändringar.

**Q: Stöder Aspose.Tasks att spara till andra format som .mpp?**  
A: Absolut. Använd `SaveFileFormat.MPP` för att spara i det inhemska Microsoft Project-formatet.

---

**Senast uppdaterad:** 2026-03-29  
**Testad med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}