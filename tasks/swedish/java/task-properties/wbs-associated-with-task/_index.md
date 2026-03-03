---
date: 2026-03-03
description: Lär dig hur du omnumrerar WBS i Aspose.Tasks för Java, hanterar arbetsnedbrytning
  och anpassar WBS‑koder effektivt med steg‑för‑steg‑exempel.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man omnumrerar WBS i Aspose.Tasks för Java
url: /sv/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här numrerar du om WBS i Aspose.Tasks för Java

## Introduktion
Om du behöver **hur man numrerar om WBS** i en Microsoft Project‑fil med Aspose.Tasks för Java, är du på rätt plats. Den här handledningen guidar dig genom att läsa befintliga WBS‑koder, anpassa dem och sedan omnumrera hierarkin så att ditt projekt förblir organiserat. Oavsett om du rensar upp ett äldre schema eller bygger ett nytt från grunden, kommer behärskning av dessa steg hjälpa dig att **hantera work breakdown**‑strukturer med självförtroende.

## Snabba svar
- **Vad gör en omnumering av WBS?** Det beräknar om den hierarkiska numreringen av uppgifter för att återspegla eventuella strukturella förändringar.  
- **Vilken klass utför omnumreringen?** `Project.renumberWBSCode`.  
- **Behöver jag en licens för att köra koden?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning.  
- **Kan jag anpassa WBS‑formatet?** Ja—använd `Task.set(Tsk.WBS, "...")` för att tilldela vilken sträng du vill.  
- **Vad är de viktigaste förutsättningarna?** Java JDK, Aspose.Tasks för Java‑biblioteket och en giltig projektfil (.mpp).

## Vad är en Work Breakdown Structure (WBS)?
En Work Breakdown Structure (WBS) är en hierarkisk representation av ett projekts leveranser och uppgifter. Varje uppgift får en kod (t.ex. 1.2.3) som speglar dess position i hierarkin. Omnumering blir nödvändig när uppgifter läggs till, tas bort eller omordnas, så att koderna förblir logiska och lätta att läsa.

## Varför hantera work breakdown och anpassa WBS‑koder?
- **Klarhet:** Klara WBS‑koder gör det enkelt för intressenter att hitta uppgifter.  
- **Rapportering:** Många rapportverktyg förlitar sig på konsekvent numrering.  
- **Flexibilitet:** Anpassade koder låter dig anpassa projektstrukturen efter interna standarder.  

## Förutsättningar
Innan vi dyker ner i koden, bekräfta att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.Tasks för Java‑biblioteket tillagt i ditt projekt. Du kan hämta det [här](https://releases.aspose.com/tasks/java/).  

## Importera paket
Se till att importera de nödvändiga paketen för att starta ditt projekt:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Läs WBS‑koder
Först läser vi de befintliga WBS‑koderna så att du kan se vad du arbetar med.

### Steg 1: Ladda projektet
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Steg 2: Samla uppgifter
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Steg 3: Analysera och anpassa
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Kodsnutten ovan skriver ut varje uppgifts nuvarande WBS och nivå, och demonstrerar sedan **anpassa wbs‑koder** genom att tilldela en ny sträng.

## Omnumrera uppgifts‑WBS‑koder
Nu ska vi faktiskt omnumrera WBS‑hierarkin.

### Steg 1: Ladda projektet (exempel på omnumrering)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Steg 2: Välj alla uppgifter
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Steg 3: Skriv ut initiala WBS‑koder
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Steg 4: Omnumrera WBS‑koder
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Steg 5: Skriv ut uppdaterade WBS‑koder
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Genom att följa dessa steg kommer du effektivt att **hur man numrerar om wbs** för vilken uppsättning uppgifter som helst i din projektfil.

## Vanliga problem och lösningar
- **WBS ändras inte efter `set`‑anrop:** Se till att du arbetar med rätt uppgiftsinstans och att projektet sparas efter ändringar.  
- **`renumberWBSCode` kastar ett undantag:** Verifiera att listan med ID:n matchar antalet toppnivåuppgifter; annars kan metoden inte mappa nya nummer korrekt.  
- **Saknade WBS‑värden:** Vissa uppgifter kan ha ett `null` WBS om de importerades från en fil som inte definierade någon. Använd ett reservvärde innan du skriver ut.  

## Vanliga frågor

**Q: Var kan jag hitta dokumentationen för Aspose.Tasks för Java?**  
A: Dokumentationen finns tillgänglig [här](https://reference.aspose.com/tasks/java/).

**Q: Hur kan jag ladda ner Aspose.Tasks för Java?**  
A: Du kan ladda ner det [här](https://releases.aspose.com/tasks/java/).

**Q: Finns det en gratis provversion av Aspose.Tasks för Java?**  
A: Ja, du kan få en gratis provversion [här](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks för Java?**  
A: Besök [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för support.

**Q: Kan jag få en tillfällig licens för Aspose.Tasks för Java?**  
A: Ja, skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Kan jag byta namn på WBS‑formatet efter omnumrering?**  
A: Absolut. Efter att du har anropat `renumberWBSCode` kan du iterera över uppgifterna och tillämpa `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` för att passa dina namngivningskonventioner.

**Q: Påverkar omnumrering uppgiftsberoenden?**  
A: Nej. Metoden uppdaterar bara WBS‑strängen; länkar och begränsningar för uppgifter förblir oförändrade.

**Senast uppdaterad:** 2026-03-03  
**Testad med:** Aspose.Tasks för Java 24.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}