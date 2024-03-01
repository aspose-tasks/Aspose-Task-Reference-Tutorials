---
title: Aktualizujte a přeplánujte MS Project v Aspose.Tasks
linktitle: Aktualizujte projekt a přeplánujte nedokončenou práci v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak aktualizovat a přeplánovat soubory MS Project programově pomocí Aspose.Tasks for Java.
type: docs
weight: 23
url: /cs/java/project-file-operations/update-project-reschedule-work/
---
## Úvod
Microsoft Project je široce používaný software pro správu projektů, který uživatelům umožňuje efektivně spravovat úkoly, zdroje a časové osy. Aspose.Tasks for Java poskytuje výkonnou sadu rozhraní API pro programovou manipulaci se soubory aplikace Microsoft Project. V tomto tutoriálu se naučíme, jak aktualizovat soubory MS Project a přeplánovat nedokončenou práci pomocí Aspose.Tasks for Java.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Aspose.Tasks pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
3. Základní znalost programovacího jazyka Java.

## Importujte balíčky
Nejprve importujte potřebné balíčky do kódu Java:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Krok 1: Nastavte projekt
Inicializujte nový objekt projektu a definujte v něm úkoly spolu s jejich trváním a závislostmi.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Definujte úkoly a jejich trvání
// ...
// Definujte závislosti úkolů
// ...
// Uložte počáteční stav projektu
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Krok 2: Aktualizujte práci na projektu
Aktualizujte práci na projektu a označte ji jako dokončenou k určitému datu.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Uložte aktualizovaný projekt
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Krok 3: Přeplánujte nedokončenou práci
Přeplánujte jakoukoli nedokončenou práci tak, aby začala po zadaném datu.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Uložte přeplánovaný projekt
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak aktualizovat soubory MS Project a přeplánovat nedokončenou práci pomocí Aspose.Tasks for Java. To může být užitečné zejména ve scénářích, kdy je třeba upravit harmonogramy projektů na základě pokroku nebo měnících se priorit.

## FAQ
### Otázka: Dokáže Aspose.Tasks for Java zvládnout složité projektové struktury?
Odpověď: Ano, Aspose.Tasks for Java poskytuje robustní rozhraní API pro efektivní správu úloh, závislostí, zdrojů a dalších prvků projektu.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks pro Java?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks for Java?
 Odpověď: Ano, dočasné licence je možné zakoupit[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde najdu podrobnou dokumentaci k Aspose.Tasks for Java?
 Odpověď: Můžete se podívat do dokumentace[tady](https://reference.aspose.com/tasks/java/) pro komplexní průvodce a reference API.