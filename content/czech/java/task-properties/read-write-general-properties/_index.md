---
title: Mastering Task Properties v Aspose.Tasks
linktitle: Číst a zapisovat obecné vlastnosti úloh v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte sílu Aspose.Tasks pro Java při správě vlastností úloh bez námahy. Čtěte a pište snadno pomocí našeho podrobného průvodce.
type: docs
weight: 26
url: /cs/java/task-properties/read-write-general-properties/
---
## Úvod
Odemkněte plný potenciál správy úloh v Javě pomocí Aspose.Tasks. V této komplexní příručce se ponoříme do čtení a psaní obecných vlastností úloh pomocí Aspose.Tasks for Java. Ať už jste zkušený vývojář nebo začátečník, tento tutoriál vás vybaví dovednostmi, jak bez námahy manipulovat s vlastnostmi úkolu.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Tasks pro knihovnu Java staženy a nastaveny. Odkaz ke stažení najdete[tady](https://releases.aspose.com/tasks/java/).
- Editor kódu, jako je IntelliJ IDEA nebo Eclipse.
## Importujte balíčky
Chcete-li věci začít, importujte potřebné balíčky do svého projektu Java. Tento krok zajistí, že budete mít přístup k funkcím Aspose.Tasks. Zde je úryvek, který vás provede:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Čtení obecných vlastností úloh
## Krok 1: Vytvořte úkol
Začněte vytvořením úkolu ve svém projektu. To zahrnuje nastavení názvu úlohy, data zahájení a dalších relevantních podrobností. Zde je příklad:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## Krok 2: Přečtěte si vlastnosti úlohy
Nyní, když jste vytvořili úlohu, pojďme načíst a zobrazit její obecné vlastnosti. Toho dosáhne následující fragment kódu:
```java
// Čtení obecných vlastností úloh
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## Psaní obecných vlastností úkolů
## Krok 3: Načtěte projekt a vytvořte kolektor
 Chcete-li napsat obecné vlastnosti, načtěte existující projekt a nastavte a`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## Krok 4: Vlastnosti analýzy a zobrazení
Nakonec analyzujte shromážděné úkoly a zobrazte jejich vlastnosti:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Gratulujeme! Úspěšně jste si přečetli a napsali obecné vlastnosti úloh pomocí Aspose.Tasks for Java.
## Závěr
V tomto tutoriálu jsme prozkoumali základní kroky k bezproblémové manipulaci s vlastnostmi úloh pomocí Aspose.Tasks for Java. Zvládnutím těchto technik můžete pozvednout své vývojové dovednosti v Javě a zefektivnit správu úloh ve svých projektech.
## Nejčastější dotazy
### Je Aspose.Tasks kompatibilní s Java 11?
Ano, Aspose.Tasks je kompatibilní s Java 11 a novějšími verzemi.
### Mohu použít Aspose.Tasks pro komerční projekty?
 Absolutně! Aspose.Tasks je výkonný nástroj pro osobní i komerční projekty. Návštěva[tady](https://purchase.aspose.com/buy) prozkoumat možnosti licencování.
### Jak mohu získat dočasnou licenci pro testovací účely?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro testování a hodnocení.
### Kde najdu podporu komunity pro Aspose.Tasks?
 Zapojte se do komunitní diskuse na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za pomoc a spolupráci.
### Jsou k dispozici nějaké vzorové projekty pro referenci?
 Prozkoumejte sekci s příklady dokumentace[tady](https://reference.aspose.com/tasks/java/) pro vzorové projekty a úryvky kódu.