---
date: 2025-12-21
description: Lär dig hur du anpassar Gantt-diagramvyer, hanterar projektvisualisering
  och sparar projektet som PDF med Aspose.Tasks för Java. Justera tidslinjens skala
  enkelt.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Anpassa Gantt-diagram – Behärska räknaren för tidslinjeskalan i MS Project
  i Aspose.Tasks
url: /sv/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Anpassa Gantt-diagram – Mästra tidslinjeskalan i MS Project med Aspose.Tasks

## Introduktion
Om du behöver **anpassa Gantt-diagram**‑visualiseringar i Microsoft Project är kontroll av tidslinjeskalan en viktig teknik. Med Aspose.Tasks för Java kan du programatiskt ange de nedre och mellersta tidslinjestegen, finjustera synligheten för tick‑markeringar och sedan **spara projektet som PDF** för att dela med intressenter. Denna handledning guidar dig genom hela processen – från att konfigurera miljön till att generera en polerad PDF som speglar din anpassade Gantt‑vy.

## Snabba svar
- **Vad betyder “anpassa Gantt-diagram”?** Att justera tidslinjesteg, färger och layout för att matcha dina rapporteringsbehov.  
- **Vilken API‑metod sätter antalet för den nedre stegen?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Kan jag generera en PDF direkt från projektet?** Ja – använd `project.save(..., SaveFileFormat.Pdf)`.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs; en gratis provversion finns tillgänglig.  
- **Vilken Java‑version stöds?** Java 8 eller högre fungerar med det senaste Aspose.Tasks‑biblioteket.

## Vad betyder “anpassa Gantt-diagram” i Aspose.Tasks?
Att anpassa ett Gantt-diagram innebär att programatiskt förändra dess visuella komponenter – såsom tidslinjeintervall, tick‑markeringar och aktivitetsstaplar – så att diagrammet stämmer överens med hur du vill **hantera projektvisualisering**. Genom att ändra tidslinjeskalan styr du hur många dagar, veckor eller månader varje segment representerar, vilket gör diagrammet tydligare för olika målgrupper.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java‑utvecklingsmiljö** – JDK 8 eller nyare installerad.  
2. **Aspose.Tasks för Java‑bibliotek** – Ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. **Grundläggande Java‑kunskaper** – Bekantskap med Java‑syntax och objekt‑orienterade koncept.

## Importera paket
Importera de nödvändiga klasserna till ditt Java‑projekt:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Steg‑för‑steg‑guide

### Steg 1: Ange datakatalog
Definiera var dina projektfiler ska läsas från och skrivas till:

```java
String dataDir = "Your Data Directory";
```

Byt ut `"Your Data Directory"` mot den absoluta sökvägen på din maskin.

### Steg 2: Skapa en ny projektinstans
Instansiera ett nytt `Project`‑objekt som kommer att innehålla alla aktiviteter och vyinställningar:

```java
Project project = new Project();
```

### Steg 3: Konfigurera Gantt‑diagramvyn
Skapa ett `GanttChartView`‑objekt – här kommer du att **generera Gantt‑vy Java**‑kod för att styra diagrammets utseende:

```java
GanttChartView view = new GanttChartView();
```

### Steg 4: Sätt tidslinjeskalan för den nedre stegen
Justera den nedre stegen så att den visar två intervall och döljer tick‑markeringarna:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Steg 5: Sätt tidslinjeskalan för den mellersta stegen
Applicera samma konfiguration på den mellersta stegen:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Steg 6: Lägg till den anpassade vyn i projektet
Fäst den vy du just konfigurerat på `Project`‑instansen:

```java
project.getViews().add(view);
```

### Steg 7: Lägg till exempeluppgifter (testdata)
Skapa ett par aktiviteter med specifika varaktigheter för att illustrera det anpassade Gantt‑diagrammet:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Steg 8: Spara projektet som PDF
Exportera slutligen projektet – inklusive ditt **anpassade Gantt-diagram** – till en PDF‑fil:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Den resulterande PDF‑filen visar hur de nedre och mellersta tidslinjestegen har **anpassats**, vilket ger intressenter en klar, utskrivbar vy av schemat.

## Vanliga problem & felsökning
- **PDF är tom** – Säkerställ att `dataDir`‑sökvägen slutar med en filseparator (`/` eller `\`) och att katalogen finns.  
- **Tick‑markeringar visas fortfarande** – Verifiera att `setShowTicks(false)` anropas på båda stegen.  
- **Varaktighet har inte tillämpats** – Bekräfta att du använder `TimeUnitType.Hour` (eller rätt enhet) när du skapar varaktigheter.

## Vanliga frågor

**Q: Kan Aspose.Tasks för Java hantera stora projektfiler?**  
A: Ja, biblioteket är optimerat för högpresterande bearbetning av omfattande projektdata.

**Q: Är Aspose.Tasks för Java kompatibelt med olika Java‑IDE:n?**  
A: Absolut – det fungerar sömlöst med Eclipse, IntelliJ IDEA, NetBeans och andra populära IDE:n.

**Q: Kan jag anpassa Gantt‑diagrammets utseende utöver tidslinjeinställningarna?**  
A: Ja, Aspose.Tasks erbjuder omfattande stilalternativ såsom stapelfärger, typsnitt och rutnätslinjer.

**Q: Finns det en provversion av Aspose.Tasks för Java?**  
A: Ja, du kan få en gratis provversion från [here](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks för Java?**  
A: Support och hjälp finns på Aspose.Tasks‑forumet [here](https://forum.aspose.com/c/tasks/15).

**Q: Hur ändrar jag programatiskt Gantt‑diagrammets bakgrundsfärg?**  
A: Använd `view.getGanttChartProperties().setBackgroundColor(Color)`‑metoden efter att ha importerat `java.awt.Color`.

## Slutsats
Genom att följa dessa steg har du lärt dig hur du **anpassar Gantt-diagram**‑tidslinjesteg, förbättrar **projektvisualisering** och **sparar projektet som PDF** med Aspose.Tasks för Java. Detta tillvägagångssätt ger dig full kontroll över det visuella resultatet, vilket gör det enklare att dela tydliga, professionella scheman med ditt team eller dina kunder.

---

**Senast uppdaterad:** 2025-12-21  
**Testat med:** Aspose.Tasks för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}