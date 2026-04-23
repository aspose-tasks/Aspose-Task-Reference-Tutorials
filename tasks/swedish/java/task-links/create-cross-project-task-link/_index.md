---
date: 2026-01-20
description: Lär dig hur du länkar projekt och länkar uppgifter mellan projekt med
  Aspose.Tasks för Java. Följ en steg‑för‑steg‑guide för att skapa kors‑projektuppgiftslänkar.
linktitle: Create Cross-Project Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Hur man länkar projekt: Skapa en korsprojekt‑uppgiftslänk i Aspose.Tasks'
url: /sv/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

 korsprojekt är det avgörande att veta **hur man länkar projekt** för att hålla flera planer synkroniserade. Aspose.Tasks for Java ger dig ett kraftfullt API för att skapa korsprojekt‑uppgiftslänkar, vilket gör att du kan **länka uppgifter över projekt** med bara några rader kod. I den här handledningen bibliotek kräsenastevändning.  
- **Hur många minuter tar det att implementera?** Ungefär 10–15 minuter för en grundläggande länk.  
- **Kan jag länka uppgifter över olika filformat?** Ja – API:et stöder MPP, XML och andra format.

## Förutsättningar
Innan vi dyker ner, se till att du har följande redo:

- En fungerande kunskap i Java‑programmering.  
- Aspose.Tasks for Java installerat. Du kan ladda ner det från [Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/).  
- Grundläggande förståelse för projektledningskoncept som uppgiftsberoenden och samlingsuppgifter.

## Importera paket
Först, importera de klasser du behöver. Detta ger dig åtkomst till den grundläggande Aspose.Tasks‑funktionaliteten:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

## Steg 1: Ställ in din miljö
Se till att Java är installerat på din maskin och att Aspose.Tasks‑JAR‑filen har lagts till i ditt projekts classpath. Detta steg är avgörande för att koden ska kunna kompileras utan fel.

## Steg 2: Skapa ett projekt‑instans
Skapa ett nytt `Project`‑objekt som kommer att innehålla uppgifterna och länkarna:

```java
Project project = new Project();
```

## Steg 3: Lägg till en samlingsuppgift
En samlingsuppgift fungerar som en behållare för de uppgifter du ska länka. Den gör strukturen tydligare när du senare visar projektet:

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

## Steg 4: Lägg till en extern uppgift
Lägg nu till en extern uppgift som pekar på en uppgift i en annan projektfil. Detta är “käll”-sidan av korsprojekt‑länken:

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

## Steg 5: Lägg till en lokal uppgift
Skapa den lokala uppgiften som ska länkas till den externa. Detta är “mål”-sidan av relationen:

```java
Task t = summary.getChildren().add("Task");
```

## Steg 6: Skapa uppgiftslänk
Skapa länken mellan den externa uppgiften och den lokala uppgiften. Genom att sätta `CrossProject` till `true` talar du om för Aspose.Tasks att länken sträcker sig över två olika projektfiler:

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

## Steg 7: Visa resultat
Till sist, skriv ut en enkel bekräftelse så att du vet att processen slutfördes utan undantag:

```java
System.out.println("Process completed Successfully");
```

## Varför länka uppgifter över projekt?
Att länka uppgifter över projekt låter dig:

- Hålla beroende arbetsuppgifter synkroniserade utan manuella uppdateringar.  
- Minska dubbelarbete när samma uppgift förekommer i flera planer.  
- Tillhandahålla en enda sanningskälla för milstolpsspårning över team.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| Extern uppgift hittades inte | Verifiera att sökvägen `EXTERNAL_TASK_PROJECT` och `EXTERNAL_ID` är korrekta. |
| Länktype matchar inte | Säkerställ att `TaskLinkType` matchar önskad beroende (t.ex. Finish‑to‑Start). |
| Licensundantag | Installera en giltig Aspose.Tasks‑licens innan du skapar projektinstansen. |

## Vanliga frågor

**Q: Kan jag länka uppgifter från flera externa projekt i samma samlingsuppgift?**  
A: Ja, du kan länka uppgifter från olika externa projekt inom samma samlingsuppgift, genom en liknande process.

**Q: Vad händer om den externa uppgiften i det länkade projektet ändras?**  
A: Alla ändringar i den externa uppgiften kommer att återspeglas i den länkade uppgiften i ditt nuvarande projekt.

**Q: Är det möjligt att skapa länkar mellan uppgifter i olika filformat?**  
A: Ja, Aspose.Tasks for Java stöder att länka uppgifter mellan projekt i olika filformat.

**Q: Kan jag ta bort länken mellan uppgifter när de är länkade över projekt?**  
A: Ja, du kan ta bort länken genom att ta bort uppgiftslänken med lämpliga Aspose.Tasks‑metoder.

**Q: Finns det några begränsningar för hur många uppgifter som kan länkas över projekt?**  
A: Antalet uppgifter som kan länkas är beroiseringsje. Känn dig fri att experimentera med olika länktyper och utforska ytterligare Aspose.Tasks‑funktioner för att ytterligare förbättra ditt projektledningsflöde.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}