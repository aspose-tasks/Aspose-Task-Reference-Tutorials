---
date: 2025-12-03
description: Lär dig hur du skapar kalender i MS Project, konverterar projekt till
  MPP och sparar projekt‑MPP utan ansträngning med Aspose.Tasks för Java.
language: sv
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Skapa kalender i MS Project och spara som MPP med Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa kalender i MS Project och spara som MPP med Aspose.Tasks

## Introduktion

I modern projektledning behöver du ofta **skapa kalender‑MS‑Project**‑filer och sedan dela dem i det inhemska MPP‑formatet. Oavsett om du konsoliderar scheman från flera källor eller migrerar legacy‑data, sparar det tid att programatiskt generera en kalender och eliminerar manuella fel. Denna handledning guidar dig genom hela processen att skapa en kalender i MS Project, anpassa den och slutligen **konvertera projektet till MPP** med Aspose.Tasks Java‑API.

## Snabba svar
- **Vad täcker den här handledningen?** Att skapa en kalender i MS Project och spara den som en MPP‑fil med Aspose.Tasks för Java.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version krävs?** Java 8 eller högre (JDK 8+).  
- **Kan jag anpassa kalendern?** Ja – du kan lägga till arbetstider, undantag och helgdagar.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande kalender.

## Vad betyder “create calendar MS Project”?

Att skapa en kalender‑MS‑Project innebär att programatiskt definiera arbetsdagar, timmar och undantag som styr uppgiftsschemaläggning i en Microsoft Project‑fil. Med Aspose.Tasks kan du bygga, modifiera och spara dessa kalendrar utan att någonsin öppna Microsoft Project‑gränssnittet.

## Varför använda Aspose.Tasks för denna uppgift?

- **Full .NET/Java‑kompatibilitet** – fungerar på alla plattformar som stödjer Java.  
- **Ingen COM‑ eller Office‑installation behövs** – idealiskt för server‑sidig automatisering.  
- **Rik API** – stödjer varje kalender‑egenskap, inklusive anpassade arbetsveckor och helgdagar.  
- **Direkt MPP‑utmatning** – du kan **spara projekt MPP** utan mellankonverteringar.

## Förutsättningar

1. **Java Development Kit (JDK) 8+** – säkerställ att `java -version` visar 1.8 eller senare.  
2. **Aspose.Tasks för Java** – ladda ner den senaste JAR‑filen från [Aspose webbplats](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse eller någon annan editor du föredrar.  
4. **Grundläggande Java‑kunskaper** – bekantskap med klasser, metoder och fil‑I/O.

## Steg‑för‑steg‑guide

### Steg 1: Importera nödvändiga paket

Först importerar du Aspose.Tasks‑klasserna och Java‑verktygen.

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

### Steg 3: Definiera in‑ och utfilnamn

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

> **Proffstips:** Du kan direkt manipulera `cal1.getWeekDays()` för att sätta arbetstimmar för varje veckodag.

### Steg 6: Tilldela kalendern till projektet

Berätta för projektet att använda den nyss skapade kalendern för alla sina schemaläggningsberäkningar.

```java
project.set(Prj.CALENDAR, cal1);
```

### Steg 7: Spara projektet som MPP

Nu **konverterar du projektet till MPP** genom att spara det med alternativet `SaveFileFormat.Mpp`.

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

| Problem | Orsak | Åtgärd |
|---------|-------|--------|
| `NullPointerException` på `project.save` | `dataDir` pekar på en icke‑existerande mapp | Säkerställ att katalogen finns eller skapa den programatiskt. |
| Kalendern tillämpas inte på uppgifter | Uppgifter refererar fortfarande standardkalendern | Efter att ha satt `Prj.CALENDAR`, uppdatera även varje uppgifts `Task.CALENDAR` om de tidigare har överskrivits. |
| Utdatafilen är 0 KB | Saknade skrivbehörigheter | Kör JVM med lämpliga filsystemsrättigheter eller välj en skrivbar sökväg. |

## Vanliga frågor

**Q: Är Aspose.Tasks för Java kompatibelt med olika versioner av MS Project?**  
A: Ja, Aspose.Tasks för Java stödjer ett brett spektrum av MS Project‑versioner, från Project 2007 upp till den senaste releasen, vilket säkerställer sömlös kompatibilitet.

**Q: Kan jag anpassa kalendrar efter specifika projektkrav?**  
A: Absolut. Du kan definiera arbetsdagar, skapa anpassade arbetsveckor, lägga till helgdagar och till och med skapa flera kalendrar i en och samma projektfil.

**Q: Erbjuder Aspose.Tasks för Java support för felsökning och hjälp?**  
A: Ja, du kan få hjälp via Aspose.Tasks‑community‑forum [här](https://forum.aspose.com/c/tasks/15).

**Q: Finns det en gratis provversion av Aspose.Tasks för Java?**  
A: Ja, en fullt funktionell gratis provversion finns tillgänglig [här](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Tasks för Java?**  
A: Tillfälliga licenser kan begäras via Aspose‑webbplatsen [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2025-12-03  
**Testad med:** Aspose.Tasks för Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}