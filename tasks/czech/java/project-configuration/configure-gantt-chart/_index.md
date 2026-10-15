---
date: 2026-10-15
description: Naučte se, jak vytvořit activity, nastavit data directory, přizpůsobit
  pole tabulky a uložit projekt jako MPP pomocí Aspose.Tasks for Java. Praktický návod
  krok za krokem pro vývojáře Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Jak vytvořit activity a nastavit data directory pomocí Aspose.Tasks for
  Java
og_description: Jak vytvořit activity, přizpůsobit pole tabulky a uložit projekt jako
  MPP pomocí Aspose.Tasks for Java. Postupujte podle tohoto podrobného návodu pro
  rychlou implementaci.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Jak vytvořit activity a nastavit data directory v Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Jak vytvořit activity a nastavit data directory pomocí Aspose.Tasks for Java
url: /cs/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit aktivitu a nastavit adresář dat pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu objevíte **jak vytvořit aktivitu** programově, nakonfigurujete **adresář dat** a **uložíte projekt jako MPP**, přičemž také **přizpůsobíte pole tabulky** v zobrazení Ganttova diagramu. Aspose.Tasks pro Java je výkonné API, které podporuje více než 30 vstupních a výstupních formátů a dokáže zpracovat projekty až s 10 000 úkoly, aniž by načítalo celý soubor do paměti. Na konci průvodce budete schopni automatizovat tvorbu projektů, obohatit úkoly o vlastní atributy a vytvořit připravený k otevření soubor MPP pro Microsoft Project.

## Rychlé odpovědi
- **Jaký je první krok?** Nastavte cestu k adresáři dat, kde jsou uloženy soubory projektu.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (ke stažení na oficiální stránce).  
- **Mohu přidat vlastní atributy?** Ano – můžete definovat rozšířené atributy a zobrazit je v Ganttově diagramu.  
- **Potřebuji licenci pro testování?** Dočasná licence je k dispozici pro evaluační účely.  
- **Které IDE je nejlepší?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, NetBeans) bude fungovat.

## Co je „nastavení adresáře dat“ a proč je to důležité?
Nastavení adresáře dat říká Aspose.Tasks, kde má číst a zapisovat soubory projektu. Bez správné cesty API nemůže najít vaše soubory `.mpp`, což vede k chybám `FileNotFoundException`. Definování tohoto adresáře na začátku kódu činí workflow opakovatelným a odděluje problémy se souborovým systémem od obchodní logiky.

## Proč přizpůsobit pole tabulky v Ganttově diagramu?
Vlastní pole tabulky vám umožní zobrazit další informace – například vlastní atributy, data o zdrojích nebo projektově specifické poznámky – přímo v Ganttově zobrazení. To snižuje potřebu samostatných reportů a poskytuje stakeholderům jednotný, datově bohatý vizuál, který může zrychlit rozhodování až o 30 %.

## Jak vytvořit novou aktivitu?
Novou aktivitu (úkol) vytvoříte vytvořením instance objektu `Task` a přidáním do kolekce kořenových úkolů projektu. Tento přístup vám umožní automaticky generovat rozsáhlé harmonogramy, načítat data úkolů z externích systémů nebo provádět hromadné aktualizace bez ručního editování.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo novější.  
2. **Aspose.Tasks pro Java** – stáhněte jej ze **Aspose.Tasks Java release page**.  
3. **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli Java‑kompatibilní editor, který preferujete.  

## Import balíčků
Namespace `com.aspose.tasks` obsahuje všechny třídy, které budete potřebovat pro manipulaci s projektem. Importování vám poskytne přístup k `Project`, `Task`, `ExtendedAttributeDefinition` a dalším základním typům.

```java
import com.aspose.tasks.*;
```

## Maven závislost (volitelné)
Pokud spravujete svůj projekt pomocí Maven, přidejte závislost Aspose.Tasks do `pom.xml`. Tím zajistíte, že knihovna bude automaticky vyřešena během sestavení.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Průvodce krok za krokem

### Krok 1: nastavení adresáře dat
Definujte složku, která obsahuje vaše soubory projektu. Proměnná `dataDir` uchovává absolutní cestu a je používána po celou dobu tutoriálu.

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` úplnou cestou ke složce, kde se nachází `project.mpp`, například `C:/Projects/MyGantt`.

### Krok 2: načtení souboru projektu
`Project` je hlavní objekt Aspose.Tasks, který představuje jeden soubor Microsoft Project v paměti. Načtení existujícího souboru vám poskytne přístup k jeho úkolům, zdrojům a tabulkám.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Krok 3: přidání nové aktivity
`Task` představuje jednotlivou aktivitu v harmonogramu. Přidání úkolu do kolekce kořenových úkolů vloží jej na nejvyšší úroveň hierarchie projektu.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Krok 4: definice vlastního atributu
`ExtendedAttributeDefinition` vám umožní vytvořit znovupoužitelné vlastní pole, které lze přiřadit libovolnému úkolu, zdroji nebo přiřazení.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Krok 5: přidání vlastního atributu k úkolu
`ExtendedAttribute` je konkrétní instance vlastního atributu, kterou přiřadíte konkrétnímu úkolu.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Krok 6: přizpůsobení tabulky – přidání vlastního atributu jako sloupce
`TableField` popisuje sloupec v tabulce Ganttova diagramu. Přidáním `TableField`, který odkazuje na vlastní atribut, učiníte atribut viditelným v zobrazení diagramu.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Krok 7: uložení projektu
Volání `project.save` uloží všechny změny do nového souboru. Konstantu `SaveFileFormat.MPP` Aspose.Tasks říká, aby soubor zapsal v nativním binárním formátu Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Časté problémy a řešení
| Problém | Proč se vyskytuje | Řešení |
|-------|----------------|-----|
| **FileNotFoundException** při načítání projektu | Cesta **set data directory** je nesprávná nebo chybí koncová lomítka. | Ověřte, že `dataDir` ukazuje na přesnou složku a zahrňte správný oddělovač souborů (`/` nebo `\\`). |
| Vlastní atribut není viditelný v Ganttově zobrazení | Pole tabulky bylo přidáno na špatném indexu nebo je šířka sloupce příliš malá. | Ujistěte se, že `table.getTableFields().add(3, attrField);` používá platný index a podle potřeby upravte `setWidth`. |
| LicenseException při ukládání | Nebyla použita platná licence pro produkční použití. | Aplikujte dočasnou nebo trvalou licenci před voláním `project.save()`. |

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks je k dispozici pro .NET, Java a C++.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi ze **Aspose.Tasks free trial download page**.

**Q: Kde mohu najít podporu pro Aspose.Tasks?**  
A: Podporu a otázky najdete na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Jak si mohu zakoupit licenci pro Aspose.Tasks?**  
A: Licence je k zakoupení na **Aspose.Tasks purchase page**.

**Q: Potřebuji dočasnou licenci pro testovací účely?**  
A: Ano, můžete získat dočasnou licenci na **temporary license request page**.

## Závěr
Nyní víte **jak vytvořit aktivitu**, nastavit adresář dat, definovat a přiřadit vlastní atribut a **uložit projekt jako MPP** při **přizpůsobení polí tabulky** v Ganttově diagramu pomocí Aspose.Tasks pro Java. Tyto možnosti vám poskytují plnou programovou kontrolu nad daty projektu, umožňují automatizovanou generaci harmonogramu a bohatší vizuální reportování pro vaše stakeholdery.

---

**Poslední aktualizace:** 2026-10-15  
**Testováno s:** Aspose.Tasks Java 24.12 (latest)  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit prázdný soubor projektu v Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Jak vytvořit soubor MPP – Vytvořit a uložit prázdný projekt ve formátu MPP pomocí Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Jak vytvořit projekt aspose.tasks – Nastavit nové atributy úkolu](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}