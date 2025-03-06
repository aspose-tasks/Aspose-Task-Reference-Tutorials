---
title: Správa trvání úkolů v Aspose.Tasks
linktitle: Správa trvání úkolů v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte Aspose.Tasks pro Javu a naučte se spravovat dobu trvání úkolů bez námahy. Postupujte podle našeho podrobného průvodce pro efektivní plánování a realizaci projektu.
type: docs
weight: 20
url: /cs/java/task-properties/manage-durations/
---
## Úvod
Aspose.Tasks for Java poskytuje robustní řešení pro efektivní správu projektových úkolů a trvání. V tomto tutoriálu prozkoumáme, jak spravovat trvání úkolů pomocí Aspose.Tasks a provedeme vás každým krokem. Ať už jste zkušený vývojář nebo začátečník, tato příručka vám pomůže pochopit základy práce s trváním úkolů ve vašich projektech.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovanou Java. Můžete si jej stáhnout[tady](https://www.oracle.com/java/technologies/javase-downloads.html).
- Knihovna Aspose.Tasks: Stáhněte si a zahrňte knihovnu Aspose.Tasks do svého projektu. Knihovnu najdete[tady](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Ve svém projektu Java importujte potřebné balíčky pro práci s Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Krok 1: Nastavte svůj projekt
```java
// Vytvořte nový projekt
Project project = new Project();
```
## Krok 2: Přidejte nový úkol
```java
// Přidejte do projektu nový úkol
Task task = project.getRootTask().getChildren().add("Task");
```
## Krok 3: Získejte a převeďte dobu trvání úkolu
```java
// Získat trvání úkolu ve dnech (výchozí časová jednotka)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Převeďte dobu trvání na hodiny času
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Krok 4: Aktualizujte trvání úkolu na 1 týden
```java
// Prodlužte trvání úkolu na 1 týden
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Krok 5: Snižte dobu trvání úkolu
```java
// Zkraťte dobu trvání úkolu
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Pomocí těchto kroků jste úspěšně spravovali dobu trvání úkolů v projektu Aspose.Tasks for Java.
## Závěr
V tomto tutoriálu jsme probrali základy správy trvání úkolů pomocí Aspose.Tasks for Java. Nyní můžete tyto techniky s jistotou začlenit do svých projektů pro efektivní řízení doby trvání úkolů.
## Nejčastější dotazy
### Je Aspose.Tasks kompatibilní se všemi verzemi Java?
Aspose.Tasks je kompatibilní s Java 6 a novějšími verzemi.
### Mohu použít Aspose.Tasks pro komerční projekty?
 Ano, Aspose.Tasks můžete použít pro osobní i komerční projekty. Návštěva[tady](https://purchase.aspose.com/buy) pro podrobnosti o licencích.
### Kde najdu další podporu a zdroje?
 Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a diskuze.
### Jak mohu získat dočasnou licenci pro testovací účely?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro testování a hodnocení.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/) před nákupem prozkoumat Aspose.Tasks.