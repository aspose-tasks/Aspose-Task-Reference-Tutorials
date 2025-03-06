---
title: Zastavit a obnovit úlohu v Aspose.Tasks
linktitle: Zastavit a obnovit úlohu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte sílu Aspose.Tasks pro Java pomocí našeho podrobného průvodce zastavením a obnovením úloh. Vylepšete bezproblémové řízení projektů!
type: docs
weight: 30
url: /cs/java/task-properties/stop-resume-task/
---
## Úvod
V oblasti vývoje Java je efektivní řízení úloh klíčovým aspektem realizace projektu. Aspose.Tasks for Java poskytuje robustní řešení pro zpracování úkolů s jeho výkonnými funkcemi. V tomto tutoriálu se ponoříme do jedné konkrétní funkce – zastavení a obnovení úloh. Podle tohoto podrobného průvodce budete moci tuto funkci bez problémů integrovat do svých projektů Java.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
- Nainstalovaný Java Development Kit (JDK) ve vašem systému.
- Knihovna Aspose.Tasks pro Java byla stažena a přidána do vašeho projektu. Můžete jej získat z[tady](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Chcete-li proces zahájit, nezapomeňte importovat potřebné balíčky do svého projektu Java:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## Krok 1: Inicializace
 Začněte inicializací projektu a vytvořením a`ChildTasksCollector` instance pro shromažďování všech úkolů.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Krok 2: Nastavte minimální datum
Definujte minimální datum pro filtrování úkolů, které je třeba zastavit nebo obnovit.
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## Krok 3: Zastavte a obnovte úkoly
Procházejte úkoly, kontrolujte a tiskněte data ukončení a obnovení.
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
Opakujte tyto kroky ve svém projektu Java, abyste hladce integrovali funkci zastavení a obnovení pomocí Aspose.Tasks for Java.
## Závěr
V tomto tutoriálu jsme prozkoumali proces zastavení a obnovení úloh pomocí Aspose.Tasks for Java. Dodržením výše uvedených kroků můžete vylepšit své schopnosti projektového řízení a zefektivnit provádění úkolů.
## Často kladené otázky
### Je Aspose.Tasks for Java vhodný pro rozsáhlé projekty?
Absolutně! Aspose.Tasks for Java je navržena tak, aby zvládala projekty různých velikostí a zajistila efektivitu a spolehlivost.
### Mohu upravit datum pro zastavení a obnovení úkolů?
Ano, uvedený příklad umožňuje flexibilitu v nastavení minimálního data podle požadavků vašeho projektu.
### Kde najdu další podporu pro Aspose.Tasks for Java?
 Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a diskuze.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks for Java?
 Ano, máte přístup k[zkušební verze zdarma](https://releases.aspose.com/) k prozkoumání funkcí před nákupem.
### Jak mohu získat dočasnou licenci pro Aspose.Tasks for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro testovací účely.