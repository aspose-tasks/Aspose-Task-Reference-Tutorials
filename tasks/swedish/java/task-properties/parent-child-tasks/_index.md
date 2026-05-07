---
date: 2026-02-23
description: Lär dig hur du ställer in projektets startdatum, anger uppgiftens varaktighet
  och sparar projektet som MPP med Aspose.Tasks för Java. Hantera föräldra‑ och underuppgifter
  effektivt.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ange projektets startdatum och hantera föräldra- och underuppgifter i Aspose.Tasks
url: /sv/java/task-properties/parent-child-tasks/
weight: 24
---

All good.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ange projektets startdatum och hantera föräldra‑ och underuppgifter i Aspose.Tasks

## Introduktion
Effektiv uppgiftsorganisation är ryggraden i framgångsrik projektledning, och **att ange projektets startdatum** korrekt är det första steget mot ett välstrukturerat schema. I den här handledningen kommer du att se hur du **anger projektets startdatum**, konfigurerar uppgiftens varaktighet och hanterar föräldra‑underordnade relationer med Aspose.Tasks för Java. När du är klar är du redo att **spara projekt som MPP**, uppdatera uppgiftens färdigstegprocent och anpassa uppgiftsegenskaper för att passa alla verkliga scenarier.

## Snabba svar
- **Hur anger jag projektets startdatum?** Använd `proj.set(Prj.START_DATE, startDate);` efter att ha initierat `Project`‑objektet.  
- **Kan jag lägga till underuppgifter under en föräldrauppgift?** Ja – anropa `parentTask.getChildren().add("Child Task")`.  
- **I vilket format sparar Aspose.Tasks filen?** Använd `SaveFileFormat.Mpp` för att **spara projekt som MPP**.  
- **Hur uppdaterar jag uppgiftens färdigsteg?** Sätt `Tsk.PERCENT_COMPLETE` på uppgiftsobjektet.  
- **Var kan jag få en tillfällig licens?** Besök sidan för tillfällig licens som länkas i FAQ‑avsnittet.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för Java‑programmering.  
- Aspose.Tasks för Java‑biblioteket installerat. Du kan ladda ner det [här](https://releases.aspose.com/tasks/java/).  
- En Java Integrated Development Environment (IDE) installerad på ditt system.

## Importera paket
För att börja, importera de nödvändiga paketen till ditt Java‑projekt. Dessa paket underlättar sömlös integration med Aspose.Tasks för Java‑funktionalitet.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Steg 1: Ange projektets startdatum
Börja med att ange projektets startdatum och andra relevanta parametrar.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Steg 2: Lägg till föräldrauppgift (Uppgift 1)
Skapa en föräldrauppgift med namnet "Task 1" och konfigurera dess egenskaper, inklusive **set task duration**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Steg 3: Lägg till föräldrauppgift (Uppgift 2) med underuppgifter
Lägg nu till en annan föräldrauppgift med namnet "Task 2" och inkludera underuppgifter (Task 3 och Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Steg 4: Konfigurera underuppgifter
Specificera startdatum, varaktigheter och begränsningar för Task 3 och Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Steg 5: Uppdatera uppgiftens färdigstegprocent
Justera färdigstegprocenten för Task 3 och Task 4 – så här **uppdaterar du uppgiftens färdigsteg**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Steg 6: Spara projektet
Slutligen **spara projekt som MPP** med de tillämpade ändringarna.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Denna steg‑för‑steg‑guide visar hur du effektivt hanterar föräldra‑ och underuppgifter med Aspose.Tasks för Java. Experimentera med olika konfigurationer för att passa ditt projekts krav.

## Varför anpassa uppgiftsegenskaper?
Att anpassa uppgiftsegenskaper såsom startdatum, varaktigheter, begränsningar och färdigstegprocent ger dig fin kontroll över schemats beteende. Oavsett om du behöver synkronisera uppgifter med resursens tillgänglighet eller verkställa affärsregler, låter Aspose.Tasks dig **anpassa uppgiftsegenskaper** programmässigt.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Start date not applied** | Ensure you call `proj.set(Prj.START_DATE, …)` **after** creating the `Project` object and before adding tasks. |
| **Child tasks inherit wrong constraints** | Set each child’s `ConstraintType` and `ConstraintDate` explicitly, as shown in Step 4. |
| **Saved file cannot be opened in MS Project** | Verify you are using the latest Aspose.Tasks version and save with `SaveFileFormat.Mpp`. |
| **Percentage not reflecting in UI** | After setting `Tsk.PERCENT_COMPLETE`, call `proj.calculateTaskSchedule()` if you need recalculated dates. |

## Vanliga frågor
### Är Aspose.Tasks för Java kompatibel med olika projektfilformat?
Ja, Aspose.Tasks för Java stöder olika projektfilformat, inklusive MPP och XML.

### Kan jag anpassa uppgiftsegenskaper utöver vad som täcks i den här handledningen?
Absolut! Aspose.Tasks för Java erbjuder omfattande anpassningsalternativ för uppgiftsegenskaper.

### Finns det ett community‑forum för Aspose.Tasks där jag kan få support?
Ja, du kan besöka [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för community‑support.

### Hur kan jag få en tillfällig licens för Aspose.Tasks för Java?
Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta omfattande dokumentation för Aspose.Tasks för Java?
Dokumentationen finns tillgänglig [här](https://reference.aspose.com/tasks/java/).

**Ytterligare Q&A**

**Q: How do I programmatically obtain a temporary license?**  
A: Load the temporary license file using `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Can I change the default task duration unit?**  
A: Yes – modify the `TimeUnitType` argument in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: What version of Aspose.Tasks is required to use `SaveFileFormat.Mpp`?**  
A: All recent versions (2022‑2026) support saving as MPP; check the release notes for any breaking changes.

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}