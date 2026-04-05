---
date: 2026-02-26
description: Lär dig hur du återupptar en uppgift och stoppar en uppgift i Aspose.Tasks
  för Java, inklusive filtrering av uppgifter efter datum för exakt projektkontroll.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man återupptar en uppgift och stoppar en uppgift i Aspose.Tasks
url: /sv/java/task-properties/stop-resume-task/
weight: 30
---

.

"## Import Packages" paragraph.

All good.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man återupptar en uppgift och stoppar en uppgift i Aspose.Tasks

## Introduktion
Om du bygger en Java‑baserad projektledningslösning kommer du ofta behöva **pausa** en uppgift tillfälligt och sedan **fortsätta** den senare. Aspose.Tasks for Java gör detta enkelt med inbyggda egenskaper för att stoppa och återuppta uppgifter. I den här handledningen kommer du att upptäcka **how to resume task** och **how to stop task** programmässigt, och du kommer också att se hur du **filter tasks by date** så att du bara arbetar med de relevanta objekten i ditt schema.

## Snabba svar
- **Vad betyder “stop” för en uppgift?** Det sätter ett stoppdatum, vilket pausar arbetet efter den tidpunkten.  
- **Hur kan jag återuppta en stoppad uppgift?** Genom att tilldela ett återupptagningsdatum som är senare än stoppdatumet.  
- **Kan jag begränsa operationen till ett datumintervall?** Ja – använd ett minimidatum för att filtrera uppgifter.  
- **Vilken biblioteksversion krävs?** Vilken som helst nyare Aspose.Tasks for Java‑utgåva (API:et förblir stabilt).  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.

## Vad är “how to resume task” i Aspose.Tasks?
Att återuppta en uppgift innebär helt enkelt att ange ett **RESUME**‑datum på ett `Task`‑objekt. När projektmotorn bearbetar schemat kommer arbetet att fortsätta från det datumet och framåt. Detta är särskilt användbart för att hantera avbrott såsom resursbrist eller externa beroenden.

## Varför använda stoppa/återuppta‑funktionen?
- **Kontroll över tidslinjer:** Pausa arbete utan att radera uppgiften.  
- **Noggrann rapportering:** Visa realistiska start-/slutdatum i Gantt‑diagram.  
- **Enkel automatisering:** Kombinera med datumfilter för att uppdatera många uppgifter på en gång.

## Förutsättningar
Innan du börjar, se till att du har:

- En god förståelse för Java‑grunderna.  
- JDK installerat på din maskin.  
- Aspose.Tasks for Java‑biblioteket tillagt i ditt projekt (ladda ner det från [here](https://releases.aspose.com/tasks/java/)).  

## Importera paket
Först, importera de nödvändiga klasserna så att du kan arbeta med projekt och uppgifter.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Steg 1: Initiera projektet och samlaren
Skapa en `Project`‑instans som pekar på din MPP‑fil och konfigurera en `ChildTasksCollector` för att samla alla uppgifter i hierarkin.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Steg 2: Definiera ett minimidatum för filtrering
Om du bara vill arbeta med uppgifter som har meningsfulla stopp‑ eller återupptagningsdatum, definiera ett **minimidatum**. Detta är kärnan i *filter tasks by date*-tekniken.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Steg 3: Iterera, kontrollera och visa stopp-/återupptagningsvärden
Loopa nu igenom de insamlade uppgifterna, tillämpa logiken för **how to stop task**, och skriv ut datumen. Koden demonstrerar också **how to resume task** genom att läsa `RESUME`‑egenskapen.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Proffstips:** Ersätt `System.out.println`‑anropen med din egen logik (t.ex. uppdatera datumen, logga till en fil, eller modifiera uppgiftsobjekten) för att faktiskt *stoppa* eller *återuppta* uppgifter vid behov.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | Uppgiften har inget stoppdatum satt. | Kontrollera `null` innan du anropar `.before(minDate)`. |
| Dates appear as `NA` even after setting | Minimidatumet är för nyligt. | Använd ett tidigare `minDate` eller ta bort filtret. |
| Changes not reflected in the saved MPP | Projektet sparas inte efter ändringar. | Anropa `project.save("output.mpp");` efter att ha uppdaterat uppgifter. |

## Vanliga frågor

### Är Aspose.Tasks for Java lämplig för storskaliga projekt?
Absolut! Aspose.Tasks for Java är designat för att hantera projekt av olika storlekar, vilket säkerställer effektivitet och pålitlighet.

### Kan jag anpassa datumet för att stoppa och återuppta uppgifter?
Ja, det medföljande exemplet ger flexibilitet att sätta minimidatumet enligt dina projektkrav.

### Var kan jag hitta ytterligare support för Aspose.Tasks for Java?
Besök [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) för community‑support och diskussioner.

### Finns det en gratis provversion av Aspose.Tasks for Java?
Ja, du kan komma åt [free trial](https://releases.aspose.com/) för att utforska funktionerna innan du gör ett köp.

### Hur kan jag skaffa en tillfällig licens för Aspose.Tasks for Java?
Du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/) för teständamål.

**Ytterligare Q&A**

**Q: Hur sätter jag faktiskt ett nytt stoppdatum för en uppgift?**  
A: Använd `tsk.set(Tsk.STOP, new Date(...));` och spara sedan projektet.

**Q: Kan jag filtrera uppgifter efter ett specifikt intervall istället för bara ett minimidatum?**  
A: Ja—jämför både `before` och `after` mot dina start- och slutdatum.

**Q: Uppdaterar API:t automatiskt schemat efter att stopp-/återupptagningsdatum har ändrats?**  
A: Efter att ha ändrat datum, anropa `project.calculateCriticalPath();` för att uppdatera schemat.

## Slutsats
I den här guiden gick vi igenom **how to resume task** och **how to stop task** med Aspose.Tasks for Java, samt en praktisk metod för att **filter tasks by date**. Genom att integrera dessa kodsnuttar i din applikation får du finjusterad kontroll över projektets tidslinjer och kan automatisera schemajusteringar med förtroende.

---

**Senast uppdaterad:** 2026-02-26  
**Testad med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}