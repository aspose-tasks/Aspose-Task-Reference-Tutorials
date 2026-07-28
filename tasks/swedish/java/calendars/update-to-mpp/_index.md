---
date: 2026-02-05
description: Lär dig hur du lägger till helgdagar i en kalender, tilldelar kalendern
  till ett projekt och sparar MS Project-filen som MPP med Aspose.Tasks för Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lägg till helgdagar i kalendern och spara som MPP med Aspose.Tasks
url: /sv/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till helgdagar i kalender och spara som MPP med Aspose.Tasks

## Introduktion

I modern projektledning behöver du ofta **lägga till helgdagar i kalender**‑filer, skapa en **MS Project‑kalender** och sedan dela schemat i det inhemska MPP‑formatet. Oavsett om du konsoliderar tidslinjer från flera källor eller migrerar legacy‑data, eliminerar ett programatiskt genererat kalenderfel manuella misstag och påskyndar leveransen. Denna handledning guidar dig genom hela processen att skapa en kalender i MS Project, anpassa den med helgdagar, **tilldela kalender till projekt** och slutligen **konvertera projekt till MPP** med Aspose.Tasks Java‑API.

## Snabba svar
- **Vad täcker den här handledningen?** Att lägga till helgdagar i en kalender, tilldela den till ett projekt och spara resultatet som en MPP‑fil med Aspose.Tasks för Java.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version krävs?** Java 8 eller högre (JDK 8+).  
- **Kan jag anpassa kalendern?** Ja – du kan lägga till arbetstider, undantag och helgdagar.  
- **Hur lång tid tar implementeringen?** Cirka 10‑15 minuter för en grundläggande kalender.  

## Vad betyder “create calendar MS Project”?

Att skapa en calendar MS Project innebär att programatiskt definiera arbetsdagar, timmar och undantag som styr uppgiftsschemaläggning i en Microsoft Project‑fil. Genom att använda Aspose.Tasks kan du **java create project calendar**, modifiera den och spara ändringarna utan att någonsin öppna Microsoft Project‑gränssnittet.

## Varför använda Aspose.Tasks för denna uppgift?

- **Full .NET/Java‑kompatibilitet** – fungerar på alla plattformar som stödjer Java.  
- **Ingen COM‑ eller Office‑installation behövs** – idealiskt för server‑sidig automatisering och **automate schedule generation**.  
- **Rik API** – stödjer varje kalender‑egenskap, inklusive anpassade arbetsveckor och helgdagar.  
- **Direkt MPP‑utdata** – du kan **save project as MPP** utan mellankonverteringar.

## Förutsättningar

1. **Java Development Kit (JDK) 8+** – säkerställ att `java -version` rapporterar 1.8 eller nyare.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse eller någon annan editor du föredrar.  
4. **Grundläggande Java‑kunskaper** – bekantskap med klasser, metoder och fil‑I/O.

## Hur man lägger till helgdagar i kalendern

Nedan går vi igenom varje steg, från att sätta upp miljön till att spara den slutliga MPP‑filen. Kodblocken är oförändrade från den ursprungliga handledningen; de omgivande förklaringarna har utökats för tydlighet.

### Steg 1: Importera nödvändiga paket

Först importerar du Aspose.Tasks‑klasserna och Java‑verktygen till ditt projekt.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Steg 2: Ställ in datakatalogen

Definiera var dina inmatningsmallar och utdatafiler ska ligga. Ersätt platshållaren med den faktiska sökvägen på din maskin.

```java
String dataDir = "Your Data Directory";
```

### Steg 3: Definiera in- och utdatafilnamn

Vi laddar en befintlig MPP‑fil (eller ett tomt projekt) och skriver resultatet till en ny fil.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Steg 4: Ladda projektet och lägg till en ny kalender

Skapa en `Project`‑instans från källfilen och lägg till en kalender med namnet **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Steg 5: Anpassa kalendern (valfritt)

Om du behöver specifika arbetstider, helgdagar eller undantag, anropa din egen hjälpfunktion. Exemplet använder `GetTestCalendar` som en platshållare.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Proffstips:** Du kan direkt manipulera `cal1.getWeekDays()` för att sätta arbetstimmar för varje veckodag, eller använda `cal1.getExceptions()` för att **add holidays to calendar**.

### Steg 6: Tilldela kalendern till projektet

Berätta för projektet att använda den nyss skapade kalendern för alla sina schemaläggningsberäkningar.

```java
project.set(Prj.CALENDAR, cal1);
```

### Steg 7: Spara projektet som MPP

Nu **convert project to MPP** genom att spara det med alternativet `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Steg 8: Bekräfta lyckad slutförande

Ett enkelt konsolmeddelande visar att processen avslutades utan fel.

```java
System.out.println("Process completed Successfully");
```

## Vanliga användningsområden

- **Automatiserad schemagenerering** för återkommande projekt (t.ex. veckovisa sprintar).  
- **Migrering av legacy‑CSV‑ eller Excel‑kalendrar** till en fullt utrustad MS Project‑fil.  
- **Server‑sidig rapportering** där en webbtjänst returnerar en MPP‑fil på begäran.  

## Felsökning & vanliga fallgropar

| Problem | Orsak | Lösning |
|---------|------|---------|
| `NullPointerException` på `project.save` | `dataDir` pekar på en icke‑existerande mapp | Säkerställ att katalogen finns eller skapa den programatiskt. |
| Kalendern tillämpas inte på uppgifter | Uppgifter refererar fortfarande standardkalendern | Efter att ha satt `Prj.CALENDAR`, uppdatera även varje uppgifts `Task.CALENDAR` om de tidigare har överskrivits. |
| Utdatafilen är 0 KB | Saknade skrivbehörigheter | Kör JVM med lämpliga filsystemsrättigheter eller välj en skrivbar sökväg. |

## Vanliga frågor

**Q: Är Aspose.Tasks for Java kompatibel med olika versioner av MS Project?**  
A: Ja, Aspose.Tasks for Java stödjer ett brett spektrum av MS Project‑versioner, från Project 2007 upp till den senaste releasen, vilket säkerställer sömlös kompatibilitet.

**Q: Kan jag anpassa kalendrar enligt specifika projektkrav?**  
A: Absolut. Du kan definiera arbetsdagar, ställa in anpassade arbetsveckor, lägga till helgdagar och till och med skapa flera kalendrar inom en och samma projektfil.

**Q: Erbjuder Aspose.Tasks for Java support för felsökning och hjälp?**  
A: Ja, du kan få hjälp via Aspose.Tasks‑community‑forum [här](https://forum.aspose.com/c/tasks/15).

**Q: Finns det en gratis provversion av Aspose.Tasks for Java?**  
A: Ja, en fullt funktionell gratis provversion finns tillgänglig [här](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Tasks for Java?**  
A: Tillfälliga licenser kan begäras via Aspose‑webbplatsen [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-02-05  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}