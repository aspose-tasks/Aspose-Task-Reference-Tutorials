---
date: 2025-12-20
description: Lär dig hur du använder Aspose.Tasks för att extrahera projektkalenderdetaljer
  från Microsoft Project‑filer med Java. Steg‑för‑steg‑guide med kodexempel.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Så här använder du Aspose.Tasks för att hämta kalenderinformation från MS Project
url: /sv/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så använder du Aspose.Tasks för att hämta kalenderinformation från MS Project

## Introduktion
I den här handledningen **kommer du att upptäcka hur du använder Aspose.Tasks** för att programatiskt hämta kalenderinformation från Microsoft Project‑filer. Att komma åt kalenderdata såsom arbetsdagar, timmar och undantag är viktigt när du behöver **extrahera projektkalender**‑detaljer för rapportering, integration eller anpassad schemaläggningslogik. Låt oss gå igenom processen steg för steg.

## Snabba svar
- **Vilket bibliotek använder den här handledningen?** Aspose.Tasks för Java.  
- **Vilket primärt nyckelord behandlas?** *how to use aspose.tasks*.  
- **Vad kan du extrahera?** Projektkalendrar, inklusive arbetsdagar och timmar.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Vilken Java‑version stöds?** Java 8 eller högre.

## Varför extrahera projektkalenderinformation?
Projektkalendrar styr uppgiftsdatum, resursallokeringar och övergripande tidslinjebereäkningar. Genom att extrahera dessa data kan du:
- Skapa anpassade rapporter som återspeglar faktiska arbetsscheman.  
- Synkronisera Microsoft Project‑tidslinjer med externa system (ERP, BI osv.).  
- Utföra “what‑if”-analyser genom att programatiskt ändra kalenderinställningar.

## Förutsättningar
Innan vi börjar, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Java Development Kit (JDK) installerat på ditt system.  
- Aspose.Tasks för Java‑biblioteket. Du kan ladda ner det [här](https://releases.aspose.com/tasks/java/).

## Importera paket
Importera först de nödvändiga Aspose.Tasks‑klasserna till ditt Java‑projekt.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Steg 1: Ange datakatalog
Definiera mappen som innehåller din *.mpp*-fil.

```java
String dataDir = "Your Data Directory";
```

Byt ut `"Your Data Directory"` mot den absoluta sökvägen till den mapp där **project.mpp** ligger.

## Steg 2: Definiera tidsenheter
Skapa konstanter som hjälper till att konvertera den interna tidsrepresentationen till mänskligt läsbara timmar.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Dessa värden uttrycks i mikrosekunder, vilket är hur Aspose.Tasks lagrar tid internt.

## Steg 3: Skapa projektinstans
Läs in Microsoft Project‑filen i ett `Project`‑objekt.

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project`‑konstruktorn parsar *.mpp*-filen och gör all projektdata, inklusive kalendrar, tillgänglig via API‑t.

## Steg 4: Hämta kalenderinformation
Hämta samlingen av kalendrar som definierats i projektet.

```java
CalendarCollection alCals = project.getCalendars();
```

Ett projekt kan innehålla flera kalendrar (standard, resurs och anpassade kalendrar). Denna samling ger dig åtkomst till var och en.

## Steg 5: Iterera genom kalendrar
Loopa igenom varje kalender, visa dess UID, namn och arbetsdagarna med motsvarande timmar.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Den inre loopen kontrollerar varje `WeekDay`‑objekt. Om dagen är markerad som arbetsdag skrivs dagtypen (Monday, Tuesday, …) ut tillsammans med de beräknade arbetstimmarna.

## Steg 6: Visa avslutningsmeddelande
Signalera att extraktionsprocessen är klar.

```java
System.out.println("Process completed Successfully");
```

## Slutsats
Genom att följa dessa steg **vet du nu hur du använder Aspose.Tasks för att extrahera projektkalender**‑information från en MS Project‑fil med Java. Du kan integrera denna logik i större applikationer, automatisera rapportering eller synkronisera scheman med andra företagsystem.

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks stöder flera plattformar och programmeringsspråk, inklusive .NET, C++, Python och Java.

**Q: Finns det en gratis provversion av Aspose.Tasks?**  
A: Ja, du kan ladda ner en gratis provversion [här](https://releases.aspose.com/).

**Q: Hur kan jag få support för Aspose.Tasks?**  
A: Du kan få support via Aspose.Tasks‑communityforum [här](https://forum.aspose.com/c/tasks/15).

**Q: Kan jag köpa en tillfällig licens för Aspose.Tasks?**  
A: Ja, tillfälliga licenser finns att köpa [här](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?**  
A: Du kan hänvisa till dokumentationen [här](https://reference.aspose.com/tasks/java/).

---

**Senast uppdaterad:** 2025-12-20  
**Testat med:** Aspose.Tasks för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}