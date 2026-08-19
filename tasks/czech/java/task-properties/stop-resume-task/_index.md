---
date: 2026-02-26
description: Naučte se, jak obnovit úkol a zastavit úkol v Aspose.Tasks pro Javu,
  včetně filtrování úkolů podle data pro přesné řízení projektu.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak obnovit úkol a zastavit úkol v Aspose.Tasks
url: /cs/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak obnovit úkol a zastavit úkol v Aspose.Tasks

## Úvod
Pokud vytváříte řešení pro řízení projektů založené na Javě, často budete potřebovat **pozastavit** úkol dočasně a později jej **pokračovat**. Aspose.Tasks pro Javu to usnadňuje pomocí vestavěných vlastností pro zastavení a obnovení úkolů. V tomto tutoriálu se dozvíte, jak **obnovit úkol** a **zastavit úkol** programově a také jak **filtrovat úkoly podle data**, abyste pracovali jen s relevantními položkami ve svém plánu.

## Rychlé odpovědi
- **Co znamená „stop“ (zastavení) pro úkol?** Nastaví datum zastavení, čímž se práce po tomto bodě pozastaví.  
- **Jak mohu obnovit zastavený úkol?** Přiřazením data obnovení, které je pozdější než datum zastavení.  
- **Mohu omezit operaci na časové období?** Ano – použijte minimální datum pro filtrování úkolů.  
- **Jaká verze knihovny je vyžadována?** Jakákoli aktuální verze Aspose.Tasks pro Javu (API zůstává stabilní).  
- **Potřebuji licenci pro vývoj?** Pro testování stačí bezplatná zkušební verze; pro produkci je licence vyžadována.

## Co znamená „jak obnovit úkol“ v Aspose.Tasks?
Obnovení úkolu jednoduše znamená nastavení data **RESUME** na objektu `Task`. Když projektový engine zpracuje plán, práce bude pokračovat od tohoto data dál. To je zvláště užitečné při řešení přerušení, jako je nedostupnost zdrojů nebo externí závislosti.

## Proč používat funkci zastavení/obnovení?
- **Kontrola nad časovými osami:** Pozastavte práci, aniž byste úkol smazali.  
- **Přesné reportování:** Zobrazte realistické datum zahájení/ukončení v Ganttových diagramech.  
- **Jednoduchá automatizace:** Kombinujte s filtry podle data pro hromadnou aktualizaci úkolů.

## Předpoklady
- Solidní znalost základů Javy.  
- Nainstalovaný JDK na vašem počítači.  
- Knihovna Aspose.Tasks pro Javu přidaná do vašeho projektu (stáhněte ji [zde](https://releases.aspose.com/tasks/java/)).

## Import balíčků
Nejprve načtěte požadované třídy, aby byly k dispozici pro práci s projekty a úkoly.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Krok 1: Inicializace projektu a sběrače
Vytvořte instanci `Project`, která ukazuje na váš soubor MPP, a nastavte `ChildTasksCollector` pro shromáždění všech úkolů v hierarchii.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Krok 2: Definování minimálního data pro filtrování
Pokud chcete pracovat jen s úkoly, které mají smysluplná data zastavení nebo obnovení, definujte **minimální datum**. To je jádro techniky *filtrování úkolů podle data*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Krok 3: Procházení, kontrola a zobrazení hodnot zastavení/obnovení
Nyní projděte shromážděné úkoly, aplikujte logiku **jak zastavit úkol**, a vytiskněte data. Kód také ukazuje **jak obnovit úkol** čtením vlastnosti `RESUME`.

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

> **Pro tip:** Nahraďte volání `System.out.println` vlastní logikou (např. aktualizací dat, logováním do souboru nebo úpravou objektů úkolů), abyste skutečně *zastavili* nebo *obnovili* úkoly podle potřeby.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| `NullPointerException` při `tsk.get(Tsk.STOP)` | Úkol nemá nastavené datum zastavení. | Zkontrolujte `null` před voláním `.before(minDate)`. |
| Data se zobrazují jako `NA` i po nastavení | Minimální datum je příliš nedávné. | Použijte dřívější `minDate` nebo filtr odeberte. |
| Změny se neprojevily v uloženém MPP | Projekt nebyl po úpravách uložen. | Po aktualizaci úkolů zavolejte `project.save("output.mpp");`. |

## Často kladené otázky

### Je Aspose.Tasks pro Javu vhodný pro rozsáhlé projekty?
Rozhodně! Aspose.Tasks pro Javu je navržen tak, aby zvládl projekty různých velikostí, a zajišťuje efektivitu i spolehlivost.

### Mohu přizpůsobit datum pro zastavení a obnovení úkolů?
Ano, uvedený příklad umožňuje flexibilně nastavit minimální datum podle požadavků vašeho projektu.

### Kde najdu další podporu pro Aspose.Tasks pro Javu?
Navštivte [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) pro komunitní podporu a diskuse.

### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Javu?
Ano, můžete získat [bezplatnou zkušební verzi](https://releases.aspose.com/) a vyzkoušet funkce před zakoupením.

### Jak získat dočasnou licenci pro Aspose.Tasks pro Javu?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/) pro testovací účely.

**Additional Q&A**

**Q: Jak skutečně nastavit nové datum zastavení pro úkol?**  
A: Použijte `tsk.set(Tsk.STOP, new Date(...));` a poté projekt uložte.

**Q: Mohu filtrovat úkoly podle konkrétního rozsahu místo jen minimálního data?**  
A: Ano – porovnejte jak `before`, tak `after` s vašimi počátečními a koncovými daty.

**Q: Přepočítá API automaticky plán po změně dat zastavení/obnovení?**  
A: Po úpravě dat zavolejte `project.calculateCriticalPath();`, aby se plán obnovil.

## Závěr
V tomto průvodci jsme pokryli **jak obnovit úkol** a **jak zastavit úkol** pomocí Aspose.Tasks pro Javu, spolu s praktickou metodou **filtrování úkolů podle data**. Integrací těchto úryvků do vaší aplikace získáte detailní kontrolu nad časovými osami projektu a můžete s jistotou automatizovat úpravy plánu.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}