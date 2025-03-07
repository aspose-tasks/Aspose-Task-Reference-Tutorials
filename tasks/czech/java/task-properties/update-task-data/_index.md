---
title: Aktualizujte data úkolu na formát MPP v Aspose.Tasks
linktitle: Aktualizujte data úkolu na formát MPP v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se aktualizovat data úlohy do formátu MPP pomocí Aspose.Tasks for Java. Postupujte podle našeho podrobného průvodce pro efektivní řízení projektů.
weight: 35
url: /cs/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aktualizujte data úkolu na formát MPP v Aspose.Tasks

## Úvod
Vítejte v našem podrobném průvodci aktualizací dat úlohy do formátu MPP pomocí Aspose.Tasks for Java. V tomto tutoriálu vás provedeme celým procesem a zajistíme, že každý krok pochopíte srozumitelně. Aspose.Tasks for Java poskytuje robustní řešení pro práci se soubory Microsoft Project a na konci této příručky budete schopni efektivně aktualizovat data úlohy ve formátu MPP.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Tasks for Java: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Tasks. Můžete si jej stáhnout z[stránka vydání](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu.
- Integrované vývojové prostředí (IDE): Použijte IDE dle svého výběru pro vývoj v Javě.
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java. Následující úryvek ukazuje, jak importovat balíčky:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Vytvořte a nakonfigurujte počáteční úlohu
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Pokračujte zbytkem kódu)
```
## 2. Nastavte datum zahájení a trvání
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Pokračujte zbytkem kódu)
```
## 3. Vytvořte souhrnnou úlohu
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Pokračujte zbytkem kódu)
```
## 4. Nastavte termín a poznámky k úkolu
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Pokračujte zbytkem kódu)
```
## 5. Nakonfigurujte omezení úloh
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Pokračujte zbytkem kódu)
```
## 6. Vytvořte další úkoly
```java
//Vytvořte 10 nových úkolů
for (int i = 0; i < 10; i++) {
    //... (Pokračujte zbytkem kódu)
}
//... (Pokračujte zbytkem kódu)
```
## 7. Uložte projekt
```java
// Uložte projekt
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Pomocí těchto kroků jste úspěšně aktualizovali data úlohy na formát MPP pomocí Aspose.Tasks for Java.
## Závěr
Gratulujeme! Dokončili jste komplexního průvodce aktualizací dat úlohy ve formátu MPP pomocí Aspose.Tasks for Java. Tato výkonná knihovna zjednodušuje úkoly projektového managementu, což z ní činí cenný nástroj pro vývojáře v Javě.
## Nejčastější dotazy
### Otázka: Kde najdu dokumentaci Aspose.Tasks for Java?
 Odpověď: Dokumentace je k dispozici[tady](https://reference.aspose.com/tasks/java/).
### Otázka: Jak si mohu stáhnout Aspose.Tasks for Java?
 A: Můžete si jej stáhnout z[stránka vydání](https://releases.aspose.com/tasks/java/).
### Otázka: Je k dispozici bezplatná zkušební verze?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Kde mohu získat podporu pro Aspose.Tasks for Java?
 Odpověď: Navštivte fórum podpory[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Nabízíte dočasné licence pro testovací účely?
 Odpověď: Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
