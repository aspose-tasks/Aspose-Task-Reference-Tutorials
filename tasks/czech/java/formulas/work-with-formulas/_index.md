---
date: 2026-10-05
description: Naučte se, jak vytvořit testovací projekt a vypočítat dny mezi daty pomocí
  Aspose.Tasks pro Java, přidat vlastní pole a efektivně manipulovat se soubory MPP.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Práce s vzorci v Aspose.Tasks
og_description: Vytvořte testovací projekt a vypočítejte dny mezi daty pomocí Aspose.Tasks
  pro Java. Tento návod ukazuje, jak přidat vlastní pole, nastavit termíny úkolů a
  uložit projekt jako soubor MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Vytvořit testovací projekt a vypočítat dny mezi daty
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Vytvořit testovací projekt a vypočítat dny mezi daty
url: /cs/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte testovací projekt a vypočítejte dny mezi daty

V tomto tutoriálu **vytvoříte testovací projekt** a **vypočítáte dny mezi daty** přidáním vlastního pole, definováním rozšířeného atributu a použitím vzorce Microsoft Project prostřednictvím knihovny Aspose.Tasks pro Javu. Ať už potřebujete generovat harmonogramy, vypočítat termíny nebo automatizovat reportování, Aspose.Tasks vám umožňuje programově manipulovat s daty Projectu bez instalace desktopové aplikace, podporuje více než 50 vstupních a výstupních formátů a zpracovává soubory o stovkách stránek v paměťově úsporném režimu.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Ukazuje, jak vytvořit testovací projekt, definovat rozšířený atribut, nastavit termín úkolu a použít vzorec k výpočtu dnů mezi daty.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Javu (nejnovější verze).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkční použití je vyžadována komerční licence.  
- **Jaké IDE mohu použít?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, VS Code), které podporuje JDK 8+.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut na zkopírování kódu a jeho spuštění.

## Co je „vypočítat dny mezi daty“ v Aspose.Tasks?
V Aspose.Tasks je vzorec řetězec, který může odkazovat na pole úkolu a provádět výpočty. `[Deadline] - [Finish]` je syntaxe vzorce, kterou Aspose.Tasks používá k vrácení číselného rozdílu ve dnech mezi dvěma datovými poli. Výsledek je uložen jako číselná hodnota představující celé dny, kterou můžete zobrazit ve vlastním poli nebo použít v dalších výpočtech.

## Proč použít Aspose.Tasks k výpočtu dnů mezi daty?
Aspose.Tasks poskytuje **úplné pokrytí API** pro každou vlastnost Projectu, úkolu a zdroje, běží na Windows, Linuxu a macOS a **nevyžaduje instalaci Microsoft Project ani Office**. Engine dokáže zpracovat projekty s **více než 500 úkoly** za méně než sekundu na typickém serverovém hardware, což ho činí ideálním pro CI pipeline, Docker kontejnery a zpracování velkých dávkových úloh.

## Jak nastavit termín úkolu
`java.util.Calendar` je třída v Javě, která představuje konkrétní okamžik v čase. Termín nastavíte přiřazením hodnoty `java.util.Calendar` do pole `Tsk.DEADLINE` úkolu. Po vytvoření instance Calendar nastavte rok, měsíc a den na požadovaný termín a poté zavolejte `task.set(Tsk.DEADLINE, calendar);`. Termín je uložen v souboru projektu a může být použit ve vzorcích jako `[Deadline] - [Finish]`.

## Jak definovat rozšířený atribut
Rozšířený atribut je vlastní pole, které ukládá výsledek vašeho vzorce. Vytvoříte jej jednou, přiřadíte mu přátelský alias a připojíte výraz `[Deadline] - [Finish]`, aby každý úkol mohl automaticky vypočítat interval. Vytvoříte jej vytvořením instance `ExtendedAttribute`, nastavením jeho Alias, přiřazením vzorce a přidáním do kolekce projektu.

## Předpoklady
- **Java Development Kit (JDK) 8+** – stáhněte z webu Oracle nebo použijte OpenJDK.  
- **Aspose.Tasks pro Java** – získáte nejnovější JAR ze [stránky ke stažení Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/) a přidáte jej do classpath vašeho projektu nebo do závislostí Maven/Gradle.

## Import balíčků
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Průvodce krok za krokem

### Krok 1: Vytvořte testovací projekt s vlastním polem
Začínáme **vytvořením testovacího projektu** a přidáním vlastního pole, které později bude obsahovat výsledek našeho vzorce.

```java
Project project = CreateTestProjectWithCustomField();
```

*Tip:* `CreateTestProjectWithCustomField()` je pomocná metoda, která vytvoří minimální harmonogram a zaregistruje rozšířený atribut připravený pro přiřazení vzorce.

### Krok 2: Definujte rozšířený atribut (přidejte vlastní pole)
Dále **definujeme rozšířený atribut** – v podstatě vlastní pole – a přiřadíme mu přátelský alias. Zde přidáváme logiku **přidání vlastního pole**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** dělá pole čitelným v Projectu.  
- **Formula** vypočítává počet dnů mezi datem *Finish* úkolu a jeho *Deadline* – jádro *vypočítat dny mezi daty*.

### Krok 3: Nastavte termín úkolu (přidejte úkol s termínem a nastavte termín úkolu)
Nyní **přidáváme data úkolu s termínem** nastavením vlastnosti *Deadline* u konkrétního úkolu.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instance `Calendar` určuje přesný okamžik termínu.  
- `set(Tsk.DEADLINE, …)` **nastavuje termín úkolu** pro vybraný úkol.

### Krok 4: Uložte projekt (manipulujte souborem Microsoft Project)
Nakonec **manipulujeme Microsoft Project** uložením změn do souboru MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Můžete otevřít `SaveFile.mpp` v Microsoft Project a zobrazit vlastní pole, výsledek vzorce a termín zobrazený v harmonogramu.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Vzorec se nevyhodnocuje** | Ujistěte se, že řetězec `Formula` atributu používá správná názvy polí (např. `[Deadline]`, `[Finish]`). |
| **Úkol nenalezen** | Ověřte, že ID úkolu (`1` v příkladu) existuje; použijte `project.getRootTask().getChildren().size()` pro ladění. |
| **Výjimka licence** | Aplikujte platnou licenci Aspose.Tasks před voláním jakýchkoli metod API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks poskytuje API pro .NET, Javu a další platformy, což vám umožní manipulovat se soubory Microsoft Project v jazyce dle vašeho výběru.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Ano. Stáhněte plně funkční zkušební verzi ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci k Aspose.Tasks?**  
A: Oficiální dokumentace je k dispozici na [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Jak mohu získat podporu pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a sdílet zkušenosti s komunitou.

**Q: Potřebuji dočasnou licenci pro hodnocení?**  
A: Dočasná licence je k dispozici pro krátkodobé testování; můžete ji požádat na [stránce pro žádost o dočasnou licenci](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-10-05  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit soubor MPP – Vytvořit a uložit prázdný projekt ve formátu MPP pomocí Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Nastavit datum zahájení projektu v MS Project pomocí Aspose.Tasks pro Java](/tasks/java/project-properties/write-project-info/)
- [Jak vytvořit rozšířený atribut v Javě s Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}