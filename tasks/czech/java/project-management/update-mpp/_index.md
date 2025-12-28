---
date: 2025-12-28
description: Naučte se, jak přidávat úkoly a aktualizovat soubory MPP pomocí Aspose.Tasks
  pro Javu, knihovny pro řízení projektů v Javě. Postupujte podle našeho krok‑za‑krokem
  průvodce, jak vytvořit úkol v MPP a uložit projekt jako MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak přidat úkol a aktualizovat soubor MPP v Aspose.Tasks
url: /cs/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat úkol a aktualizovat soubor MPP v Aspose.Tasks

## Úvod
V tomto tutoriálu vám ukážeme **jak přidat úkol** a aktualizovat soubor MPP pomocí Aspose.Tasks pro Java, přední **java knihovny pro řízení projektů**. Ať už vytváříte vlastní plánovač nebo potřebujete programově upravit existující projektové plány, tento průvodce vás provede každým krokem – od načtení souboru až po uložení změn jako nový dokument MPP.

## Rychlé odpovědi
- **Co znamená “how to add task” v tomto kontextu?** Odkazuje na programové vytvoření nového úkolu v existujícím souboru Microsoft Project (MPP).  
- **Která knihovna provádí operaci?** Aspose.Tasks pro Java, robustní java knihovna pro řízení projektů.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu výsledek uložit jako MPP?** Ano – použijte `project.save(..., SaveFileFormat.Mpp)` k **uložení projektu jako mpp**.  
- **Jaká verze Javy je požadována?** Java 8 nebo novější.

## Co je “how to add task” v souboru MPP?
Přidání úkolu znamená vložení nového pracovního položky do hierarchie projektu, definování jeho počátečních a koncových dat a uložení změny zpět do souboru MPP. Aspose.Tasks abstrahuje nízkoúrovňové detaily formátu souboru, což vám umožňuje soustředit se na obchodní logiku.

## Proč používat Aspose.Tasks pro Java?
- **Plná kompatibilita** se soubory Microsoft Project 2007‑2021.  
- **Není vyžadována instalace COM ani Office** – čisté Java API.  
- **Bohatá sada funkcí**: propojení úkolů, přidělování zdrojů, vlastní pole a další.  
- **Vysoký výkon** pro velké projektové soubory, což jej činí ideálním pro server‑side automatizaci.

## Předpoklady
1. **Java vývojové prostředí** – nainstalovaný a nakonfigurovaný JDK 8+.  
2. **Aspose.Tasks pro Java** – Stáhněte z [stránky ke stažení](https://releases.aspose.com/tasks/java/).  
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

## Krok 1: Definovat adresář dat
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní cestou, kde se nachází váš zdrojový soubor MPP.

## Krok 2: Načíst existující projekt
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
Konstruktor `Project` načte **SampleMSP2010.mpp**, čímž vám poskytne manipulovatelný objektový model.

## Krok 3: Vytvořit nový úkol (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Tento řádek **vytvoří úkol v mpp** přidáním podřízeného úkolu pojmenovaného *Task1* k hlavnímu úkolu.

## Krok 4: Nastavit počáteční a koncová data
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Zde definujeme plán pro nově přidaný úkol. Přizpůsobte data tak, aby odpovídala časové ose vašeho projektu.

## Krok 5: Uložit projekt (uložit projekt jako mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Aktualizovaný projekt, nyní obsahující nový úkol, je uložen jako **AfterLinking.mpp**.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Soubor nenalezen** | Ověřte, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) a že název souboru je správný. |
| **Nesprávná data** | Pamatujte, že měsíce v `Calendar` jsou číslovány od nuly; `Calendar.JULY` je správný pro červenec. |
| **Výjimka licence** | Nainstalujte platnou licenci Aspose.Tasks před voláním jakéhokoli API, aby se zabránilo vodoznakům z hodnocení. |

## Často kladené otázky
### Q: Dokáže Aspose.Tasks pro Java zvládat složité struktury projektů?
A: Ano, Aspose.Tasks pro Java poskytuje robustní funkce pro efektivní práci se složitými strukturami projektů.  
### Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [webu](https://releases.aspose.com/).  
### Q: Podporuje Aspose.Tasks pro Java různé verze souborů Microsoft Project?
A: Ano, Aspose.Tasks pro Java podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.  
### Q: Mohu získat dočasné licence pro Aspose.Tasks pro Java?
A: Ano, dočasné licence jsou k dispozici pro testovací účely. Můžete je získat na [stránce dočasných licencí](https://purchase.aspose.com/temporary-license/).  
### Q: Kde mohu získat pomoc nebo podporu ohledně Aspose.Tasks pro Java?
A: Můžete navštívit [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy.

## Často kladené otázky
**Q: Jak mohu přidat více úkolů najednou?**  
A: Projděte kolekci názvů úkolů a opakujte blok “create task” uvnitř smyčky.

**Q: Mohu nastavit vlastní pole pro nový úkol?**  
A: Ano – použijte `task.set(Tsk.CUSTOM_FIELD_x, value)`, kde *x* je index pole.

**Q: Je možné zkopírovat existující úkol jako šablonu?**  
A: Klonujte zdrojový úkol (`Task cloned = sourceTask.clone();`) a poté jej přidejte k požadovanému nadřazenému úkolu.

**Q: Co když potřebuji aktualizovat existující úkol místo přidání nového?**  
A: Získejte úkol podle ID (`Task existing = project.getRootTask().getChildren().getById(id);`) a upravte jeho vlastnosti.

**Q: Podporuje Aspose.Tasks ukládání do jiných formátů, jako PDF nebo PNG?**  
A: Ano – použijte `project.save("output.pdf", SaveFileFormat.Pdf);` nebo `SaveFileFormat.Png` pro vizuální reprezentace.

---

**Poslední aktualizace:** 2025-12-28  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}