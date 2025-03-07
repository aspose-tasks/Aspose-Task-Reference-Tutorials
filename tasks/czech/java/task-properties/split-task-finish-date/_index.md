---
title: Rozdělit datum dokončení úkolu v Aspose.Tasks
linktitle: Rozdělit datum dokončení úkolu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak snadno rozdělit data dokončení úkolů pomocí Aspose.Tasks for Java. Vylepšete řízení projektů s přesnými časovými osami.
weight: 28
url: /cs/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozdělit datum dokončení úkolu v Aspose.Tasks

## Úvod
projektovém řízení je pro úspěšné dokončení projektu klíčové pochopení harmonogramu úkolů. Aspose.Tasks for Java poskytuje výkonné funkce pro efektivní manipulaci s projektovými úkoly. V tomto tutoriálu se ponoříme do rozdělení dat dokončení úkolů pomocí Aspose.Tasks, což vám pomůže efektivně řídit časové osy projektů.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Tasks pro Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/java/).
- Vytvořeno vývojové prostředí Java.
## Importujte balíčky
Začněte tím, že do svého projektu Java zahrnete potřebné balíčky:
```java
import com.aspose.tasks.*;
```
## Krok 1: Najděte rozdělený úkol
Najděte úkol, který chcete v projektu rozdělit:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Přečtěte si projekt
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Krok 2: Najděte kalendář projektu
Načtěte kalendář projektu pro přesné výpočty data:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Krok 3: Vypočítejte datum dokončení úkolu s různým trváním
Nyní vypočítejte datum dokončení úkolu pro různé doby trvání:
## Krok 3.1: Doba trvání 8 hodin
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Opakujte výše uvedený kód pro různé doby trvání a podle toho upravte hodiny.
## Závěr
Zvládnutí umění manipulace s termíny dokončení úkolů je klíčové pro efektivní řízení projektu. Aspose.Tasks for Java tento proces zjednodušuje a umožňuje vám bez námahy zefektivnit časové osy vašeho projektu.
## Nejčastější dotazy
### Q1: Jak si mohu stáhnout Aspose.Tasks for Java?
 A1: Můžete si to stáhnout[tady](https://releases.aspose.com/tasks/java/).
### Q2: Kde najdu dokumentaci pro Aspose.Tasks?
 A2: Viz dokumentace[tady](https://reference.aspose.com/tasks/java/).
### Q3: Jak získám dočasnou licenci pro Aspose.Tasks?
 A3: Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Q4: Kde mohu hledat podporu pro Aspose.Tasks?
 A4: Navštivte fórum podpory[tady](https://forum.aspose.com/c/tasks/15).
### Q5: Mohu si zakoupit Aspose.Tasks?
 A5: Ano, můžete si to koupit[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
