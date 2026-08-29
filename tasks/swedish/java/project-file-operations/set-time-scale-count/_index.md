---
date: 2026-03-29
description: Lär dig hur du skapar projekt‑PDF‑filer samtidigt som du anpassar Gantt‑diagrammets
  tidslinjeantal med Aspose.Tasks för Java. Den här guiden visar dig steg för steg
  hur du exporterar Gantt till PDF med full kontroll.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Skapa projekt‑PDF – Anpassa Gantt‑diagrammets tidsskala
url: /sv/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa projekt-PDF – Anpassa Gantt-diagrammets tidslinjeskala

## Introduktion
Om du behöver **skapa projekt-PDF**-filer som återspeglar ett perfekt justerat Gantt-diagram är kontroll av tidslinjeskalan nyckeln. Med Aspose.Tasks for Java kan du programatiskt ställa in de nedre och mellersta tidslinjeskikt‑nivåerna, dölja tick‑markeringar och sedan **spara projekt som PDF** för enkel distribution. I den här handledningen går vi igenom allt du behöver – från att sätta upp utvecklingsmiljön till att generera en polerad PDF som visar ditt anpassade Gantt‑vy.

## Snabba svar
- **Vad betyder “anpassa Gantt-diagram”?** Justering av tidslinjeskikt‑nivåer, färger och layout för att matcha dina rapporteringsbehov.  
- **Vilken API‑metod sätter antalet för det nedre skiktet?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Kan jag generera en PDF direkt från projektet?** Ja—använd `project.save(..., SaveFileFormat.Pdf)`.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs; en gratis provversion finns tillgänglig.  
- **Vilken Java‑version stöds?** Java 8 eller högre fungerar med det senaste Aspose.Tasks‑biblioteket.

## Vad betyder “anpassa Gantt-diagram” i Aspose.Tasks?
Att anpassa ett Gantt-diagram innebär att programatiskt ändra dess visuella komponenter—såsom tidslinjeintervall, tick‑markeringar och uppgiftsstaplar—så att diagrammet stämmer överens med hur du vill **hantera projektvisualisering**. Genom att ändra tidslinjeskalan styr du hur många dagar, veckor eller månader varje segment representerar, vilket gör diagrammet tydligare för olika målgrupper.

## Varför skapa projekt-PDF med ett anpassat Gantt-diagram?
- **Stakeholder‑ready output:** PDF är universellt visbart, vilket säkerställer att alla ser samma schemaläggningslayout.  
- **Print‑friendly:** Precisa kontroller över tidslinjeskikt‑nivåerna förhindrar trånga eller tvetydiga utskrifter.  
- **Automation:** Integrera PDF-generering i CI‑pipelines eller rapporteringstjänster för noll‑manuell insats.

## Förutsättningar
1. **Java Development Environment** – JDK 8 eller nyare installerat.  
2. **Aspose.Tasks for Java Library** – Ladda ner den från [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – Bekantskap med Java‑syntax och objekt‑orienterade koncept.

## Importera paket
Importera de nödvändiga klasserna i ditt Java‑projekt:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Steg‑för‑steg guide

### Steg 1: Ange datakatalog
Definiera var dina projektfiler ska läsas från och skrivas till:

```java
String dataDir = "Your Data Directory";
```

Ersätt `"Your Data Directory"` med den absoluta sökvägen på din maskin.

### Steg 2: Skapa en ny projektinstans
Instansiera ett nytt `Project`‑objekt som kommer att innehålla alla uppgifter och vyinställningar:

```java
Project project = new Project();
```

### Steg 3: Konfigurera Gantt-diagramvyn
Skapa ett `GanttChartView`‑objekt—detta är där du kommer att **generera Gantt view Java**-kod för att kontrollera diagrammets utseende:

```java
GanttChartView view = new GanttChartView();
```

### Steg 4: Ställ in tidslinjeskala‑antal för det nedre skiktet
Justera det nedre skiktet för att visa två intervaller och dölja tick‑markeringarna:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Steg 5: Ställ in tidslinjeskala‑antal för det mellersta skiktet
Tillämpa samma konfiguration på det mellersta skiktet:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Steg 6: Lägg till den anpassade vyn i projektet
Koppla vyn du just konfigurerat till `Project`‑instansen:

```java
project.getViews().add(view);
```

### Steg 7: Lägg till exempeluppgifter (testdata)
Skapa ett par uppgifter med specifika varaktigheter för att illustrera det anpassade Gantt‑diagrammet:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Steg 8: Spara projektet som PDF
Slutligen, exportera projektet—inklusive ditt **anpassade Gantt-diagram**—till en PDF‑fil:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Den resulterande PDF‑filen visar hur de nedre och mellersta tidslinjeskikt‑nivåerna har **anpassats**, vilket ger intressenter en tydlig, utskrivbar vy av schemat.

## Vanliga problem & felsökning
- **PDF is blank** – Se till att `dataDir`‑sökvägen slutar med en filseparator (`/` eller `\`) och att katalogen finns.  
- **Ticks still appear** – Verifiera att `setShowTicks(false)` anropas på båda skikten.  
- **Duration not applied** – Bekräfta att du använder `TimeUnitType.Hour` (eller lämplig enhet) när du skapar varaktigheter.

## Vanliga frågor

**Q: Kan Aspose.Tasks for Java hantera stora projektfiler?**  
A: Ja, biblioteket är optimerat för högpresterande bearbetning av omfattande projektdata.

**Q: Är Aspose.Tasks for Java kompatibel med olika Java‑IDE:n?**  
A: Absolut – den fungerar sömlöst med Eclipse, IntelliJ IDEA, NetBeans och andra populära IDE:n.

**Q: Kan jag anpassa utseendet på Gantt-diagram utöver tidslinjeinställningarna?**  
A: Ja, Aspose.Tasks erbjuder omfattande stilalternativ såsom stapelfärger, typsnitt och rutnätslinjer.

**Q: Finns en provversion av Aspose.Tasks for Java?**  
A: Ja, du kan få en gratis provversion från [here](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks for Java?**  
A: Du kan hitta support och hjälp på Aspose.Tasks‑forumet [here](https://forum.aspose.com/c/tasks/15).

**Q: Hur ändrar jag programatiskt Gantt-diagrammets bakgrundsfärg?**  
A: Använd metoden `view.getGanttChartProperties().setBackgroundColor(Color)` efter att ha importerat `java.awt.Color`.

## Slutsats
Genom att följa dessa steg har du lärt dig hur du **skapar projekt-PDF**-filer med en fullt anpassad Gantt-diagramtidslinje, förbättrar **projektvisualisering** och **sparar projekt som PDF** med Aspose.Tasks for Java. Detta tillvägagångssätt ger dig full kontroll över den visuella utdata, vilket gör det enklare att dela tydliga, professionella scheman med ditt team eller dina kunder.

---

**Senast uppdaterad:** 2026-03-29  
**Testad med:** Aspose.Tasks for Java (latest)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}