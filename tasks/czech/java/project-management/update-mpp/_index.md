---
date: 2026-06-25
description: Naučte se, jak přidat task a aktualizovat soubory MPP pomocí Aspose.Tasks
  pro Java, knihovny pro správu projektů v jazyce Java, která vám umožní vytvářet
  soubory Microsoft Project a ukládat projekt jako MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Jak přidat task a aktualizovat soubor MPP v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak přidat task a aktualizovat soubor MPP v Aspose.Tasks
url: /cs/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat úkol a aktualizovat soubor MPP v Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **jak přidat úkol** do existujícího souboru Microsoft Project (MPP) a poté uložit aktualizovaný plán pomocí Aspose.Tasks pro Java, přední **java knihovny pro řízení projektů**. Ať už vytváříte vlastní plánovač, automatizujete hromadné aktualizace nebo integrujete projektová data do většího systému, níže uvedený krok‑za‑krokem průvodce přesně ukazuje, jak načíst projekt, vložit nový úkol, nastavit jeho data a uložit výsledek jako nový MPP dokument.

## Rychlé odpovědi
- **Co znamená “how to add task” v tomto kontextu?** To znamená programově vytvořit novou pracovní položku uvnitř existujícího souboru MPP.  
- **Která knihovna provádí operaci?** Aspose.Tasks pro Java, robustní java knihovna pro řízení projektů.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu výsledek uložit jako MPP?** Ano—použijte `project.save(..., SaveFileFormat.Mpp)` k **uložení projektu jako mpp**.  
- **Jaká verze Javy je požadována?** Java 8 nebo novější.

## Co je “how to add task” v souboru MPP?
Přidání úkolu znamená vložení nové pracovní položky do hierarchie projektu, definování jeho počátečních a koncových dat a uložení změny zpět do souboru MPP. Aspose.Tasks abstrahuje podrobnosti nízkoúrovňového formátu souboru, což vám umožňuje soustředit se na obchodní logiku, zatímco automaticky zpracovává přiřazení zdrojů, kalendáře a výpočty závislostí. Také aktualizuje všechna související přiřazení a přepočítá plán projektu, aby zachoval konzistenci mezi závislými úkoly.

## Proč používat Aspose.Tasks pro Java?
- **Plná kompatibilita**: Podporuje 100 % funkcí napříč Microsoft Project 2007‑2021 (více než 150 typů úkolů a 200 polí zdrojů).  
- **Bez závislostí**: Nepotřebuje COM, Office ani nativní knihovny—čisté Java API běží kdekoliv, kde je JRE.  
- **Bohatá sada funkcí**: Obsahuje propojení úkolů, přidělování zdrojů, vlastní pole a vestavěné reportování.  
- **Vysoký výkon**: Zpracovává projekty až s 10 000 úkoly s využitím méně než 200 MB RAM, což je ideální pro automatizaci na serveru.

## Předpoklady
1. **Java vývojové prostředí** – nainstalovaný a nakonfigurovaný JDK 8+.  
2. **Aspose.Tasks pro Java** – Stáhněte z [download page](https://releases.aspose.com/tasks/java/).  
3. **Základní znalost Javy** – Znalost tříd, objektů a práce s daty.  

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. To vám poskytne přístup k manipulaci s projektem, vlastnostmi úkolů a práci s daty.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` představuje soubor Microsoft Project načtený v paměti. `SaveFileFormat` vyjmenovává formáty, do kterých můžete ukládat, jako MPP nebo PDF. `Task` modeluje jednotlivou pracovní položku v hierarchii projektu. `Tsk` poskytuje konstanty pro pole úkolu používané při nastavení nebo získávání hodnot. `Calendar` nabízí nástroje pro datum‑čas pro definování plánů.

## Krok 1: Definovat adresář dat
```java
String dataDir = "Your Data Directory";
```  
Nahraďte `"Your Data Directory"` absolutní cestou, kde se nachází váš zdrojový soubor MPP.

## Krok 2: Načíst existující projekt
Třída `Project` je jádrový objekt Aspose.Tasks, který představuje soubor Microsoft Project v paměti.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Konstruktor načte **SampleMSP2010.mpp**, čímž získáte plně manipulovatelný objektový model.

## Krok 3: Vytvořit nový úkol (jak přidat úkol)
Třída `Task` představuje jednotlivou pracovní položku v hierarchii projektu.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Tento řádek **vytváří úkol v mpp** přidáním podřízeného s názvem *Task1* k hlavnímu úkolu.

## Krok 4: Nastavit počáteční a koncová data
Třída `Calendar` poskytuje nástroje pro datum‑čas; měsíce jsou číslovány od nuly (např. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Zde definujeme plán pro nově přidaný úkol. Přizpůsobte data tak, aby odpovídala časové ose vašeho projektu.

## Krok 5: Uložit projekt (uložit projekt jako mpp)
`SaveFileFormat.Mpp` říká Aspose.Tasks, aby zapsal soubor zpět v nativním formátu Microsoft Project.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Aktualizovaný projekt, nyní obsahující nový úkol, je uložen jako **AfterLinking.mpp**.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Soubor nenalezen** | Ověřte, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) a že název souboru je správný. |
| **Nesprávná data** | Pamatujte, že měsíce v `Calendar` jsou číslovány od nuly; `Calendar.JULY` je správný pro červenec. |
| **Výjimka licence** | Nainstalujte platnou licenci Aspose.Tasks před voláním jakéhokoli API, aby se předešlo vodoznakům z evaluační verze. |

## Často kladené otázky
**Q: Jak přidám více úkolů najednou?**  
A: Projděte kolekci názvů úkolů a opakujte blok „create task“ uvnitř smyčky.

**Q: Mohu nastavit vlastní pole pro nový úkol?**  
A: Ano—použijte `task.set(Tsk.CUSTOM_FIELD_x, value)`, kde *x* je index pole.

**Q: Je možné zkopírovat existující úkol jako šablonu?**  
A: Klonujte zdrojový úkol (`Task cloned = sourceTask.clone();`) a poté jej přidejte k požadovanému nadřazenému úkolu.

**Q: Co když potřebuji aktualizovat existující úkol místo přidání nového?**  
A: Získejte úkol podle ID (`Task existing = project.getRootTask().getChildren().getById(id);`) a upravte jeho vlastnosti.

**Q: Podporuje Aspose.Tasks ukládání do jiných formátů, jako PDF nebo PNG?**  
A: Ano—použijte `project.save("output.pdf", SaveFileFormat.Pdf);` nebo `SaveFileFormat.Png` pro vizuální reprezentace.

---

**Poslední aktualizace:** 2026-06-25  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit soubor MPP – Vytvořit a uložit prázdný projekt ve formátu MPP s Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Jak vytvořit projekt – Nastavit atributy nových úkolů s Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Vytvořit seznam úkolů Java – Základní linie MS Project pomocí Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}