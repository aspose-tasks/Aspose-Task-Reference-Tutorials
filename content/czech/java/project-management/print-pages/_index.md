---
title: Tisk stránek k oddělení obrázku v Aspose.Tasks
linktitle: Tisk stránek k oddělení obrázku v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se tisknout stránky k oddělení obrázků v Aspose.Tasks for Java. Vylepšete vizualizaci projektu pomocí tohoto podrobného průvodce.
type: docs
weight: 22
url: /cs/java/project-management/print-pages/
---
## Úvod
V tomto tutoriálu vás provedeme procesem tisku stránek na samostatné obrázky pomocí Aspose.Tasks for Java. Tato funkce může být zvláště užitečná, když potřebujete samostatně vizualizovat rozvržení projektu nebo kritické úkoly.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[tady](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Knihovna Aspose.Tasks for Java: Stáhněte si a zahrňte knihovnu Aspose.Tasks for Java do svého projektu. Můžete to získat od[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Ujistěte se, že jste na začátku svého souboru Java importovali potřebné balíčky:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Krok 1: Načtěte data projektu
Nejprve načtěte data projektu ze souboru MPP:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Krok 2: Nastavte možnosti uložení obrázku
Definujte možnosti pro uložení obrázku, včetně data zahájení, data ukončení, kritických úkolů, legendy a mřížky:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Krok 3: Přizpůsobte mřížku
Přizpůsobte mřížku obrázku, určete typ, barvu a vzor:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Krok 4: Uložte obrázky
Uložte rozvržení projektu jako obrázky, a to jako jeden soubor i samostatné soubory:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Závěr
V tomto tutoriálu jsme si ukázali, jak tisknout stránky na samostatné obrázky pomocí Aspose.Tasks for Java. Podle výše uvedených kroků můžete efektivně vizualizovat rozvržení projektu a kritické úkoly podle vašich požadavků.
## FAQ
### Otázka: Mohu přizpůsobit formát obrázku při ukládání rozvržení projektu?
 Odpověď: Ano, Aspose.Tasks for Java podporuje různé formáty obrázků, jako je PNG, JPEG, BMP atd. Požadovaný formát můžete zadat v`ImageSaveOptions` třída.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými vývojovými prostředími Java?
Odpověď: Ano, Aspose.Tasks for Java je kompatibilní s většinou vývojových prostředí Java, včetně Eclipse, IntelliJ IDEA a NetBeans.
### Otázka: Mohu integrovat Aspose.Tasks pro Javu do svého projektu Maven nebo Gradle?
Odpověď: Ano, Aspose.Tasks for Java můžete snadno integrovat do svého projektu Maven nebo Gradle přidáním příslušné závislosti do vašeho`pom.xml` nebo`build.gradle` soubor.
### Otázka: Podporuje Aspose.Tasks for Java export dat projektu do jiných formátů kromě obrázků?
Odpověď: Ano, Aspose.Tasks for Java podporuje export projektových dat do různých formátů, jako je PDF, HTML, XLSX atd., což poskytuje flexibilitu při vizualizaci dat a vytváření sestav.
### Otázka: Je pro Aspose.Tasks pro Java k dispozici nějaká podpora komunity?
 Odpověď: Ano, na webu můžete najít podporu komunity, klást otázky a komunikovat s ostatními uživateli[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).