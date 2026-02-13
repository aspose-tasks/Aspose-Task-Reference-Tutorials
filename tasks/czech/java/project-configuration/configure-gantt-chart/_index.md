---
date: 2026-02-13
description: Naučte se, jak vytvořit novou aktivitu, nastavit adresář s daty a uložit
  projekt jako MPP v Aspose.Tasks Java. Tento průvodce krok za krokem také zahrnuje
  přizpůsobení polí tabulky.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak vytvořit novou aktivitu a nastavit datový adresář Aspose.Tasks
url: /cs/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit novou aktivitu a nastavit adresář dat Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **jak nastavit adresář dat**, jak **vytvořit novou aktivitu** a jak **uložit projekt jako MPP** při konfiguraci zobrazení Gantt MS Project Chart ve projektech Aspose.Tasks pomocí Javy. Aspose.Tasks je robustní Java API, které vám umožní programově manipulovat se soubory Microsoft Project. Na konci tohoto průvodce budete schopni **přizpůsobit pole tabulky**, upravit adresář dat a vizualizovat svůj projekt přesně tak, jak potřebujete.

## Rychlé odpovědi
- **Jaký je první krok?** Nastavte cestu k adresáři dat, kde jsou uloženy soubory projektu.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (ke stažení z oficiálního webu).  
- **Mohu přidat vlastní atributy?** Ano – můžete definovat rozšířené atributy a zobrazit je v Ganttově diagramu.  
- **Potřebuji licenci pro testování?** Dočasná licence je k dispozici pro evaluační účely.  
- **Které IDE je nejlepší?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, NetBeans) bude fungovat.

## Co je „nastavení adresáře dat“ a proč je to důležité?
Nastavení adresáře dat říká Aspose.Tasks, kde má číst a zapisovat soubory projektu. Bez správné cesty API nemůže najít vaše soubory `.mpp`, což vede k chybám FileNotFound. Definování tohoto adresáře na začátku kódu činí zbytek pracovního postupu čistým a opakovatelným.

## Proč přizpůsobit pole tabulky v Ganttově diagramu?
Vlastní pole tabulky vám umožní zobrazit další informace – například vlastní atributy, data o zdrojích nebo projektově specifické poznámky – přímo v Ganttově pohledu. To činí diagram informativnějším pro zainteresované strany a snižuje potřebu přepínat mezi několika zprávami.

## Jak vytvořit novou aktivitu?
Vytvoření nové aktivity (úkolu) je jednou ze základních operací při budování nebo aktualizaci harmonogramu projektu. Přidáním úkolů programově můžete automatizovat generování složitých projektových plánů, integrovat data z jiných systémů nebo provádět hromadné změny bez ručního editování.

## Požadavky
1. **Java Development Kit (JDK)** – jakákoli aktuální verze (8+).  
2. **Aspose.Tasks Library** – stáhněte ji z [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli Java‑kompatibilní editor, který preferujete.

## Import balíčků
Nejprve importujte jmenný prostor Aspose.Tasks, abyste mohli pracovat s jeho třídami:

```java
import com.aspose.tasks.*;
```

## Postupný návod

### Krok 1: Nastavení adresáře dat
Definujte složku, která obsahuje vaše soubory projektu. Toto je krok **nastavení adresáře dat**, na který se tutoriál zaměřuje.

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní cestou ke složce, kde je uložen `project.mpp`.

### Krok 2: Načtení souboru projektu
Vytvořte instanci `Project` načtením existujícího souboru Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Krok 3: Přidání nové aktivity
Vložte nový úkol (aktivitu) do kořene projektu. Toto demonstruje **jak vytvořit novou aktivitu** programově.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Krok 4: Definování vlastního atributu
Vytvořte definici vlastního atributu, kterou můžete později přiřadit k úkolům.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Krok 5: Přidání vlastního atributu k úkolu
Přiřaďte nově definovaný atribut k úkolu, který jste vytvořili.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Krok 6: Přizpůsobení tabulky – **customize table fields**
Přidejte vlastní atribut jako sloupec do tabulky Ganttova diagramu, specifikujte šířku, název a zarovnání.

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

### Krok 7: Uložení projektu
Uložte změny do nového souboru, který lze otevřít v Microsoft Project. Tento krok **uloží projekt jako MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Časté problémy a řešení
| Problém | Proč se vyskytuje | Řešení |
|-------|----------------|-----|
| **FileNotFoundException** při načítání projektu | Cesta **nastavení adresáře dat** je nesprávná nebo chybí koncová lomítko. | Ověřte, že `dataDir` ukazuje na přesnou složku a zahrnuje správný oddělovač souborů (`/` nebo `\\`). |
| Vlastní atribut není viditelný v Ganttově zobrazení | Pole tabulky bylo přidáno na špatném indexu nebo je šířka sloupce příliš malá. | Ujistěte se, že `table.getTableFields().add(3, attrField);` používá platný index a upravte `setWidth` podle potřeby. |
| LicenseException při uložení | Nebyla použita platná licence pro produkční použití. | Použijte dočasnou nebo trvalou licenci před voláním `project.save()`. |

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks je k dispozici pro více programovacích jazyků včetně .NET, Java a C++.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [here](https://releases.aspose.com/).

**Q: Kde mohu najít podporu pro Aspose.Tasks?**  
A: Podporu a otázky můžete najít na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Jak mohu zakoupit licenci pro Aspose.Tasks?**  
A: Licenci můžete zakoupit [here](https://purchase.aspose.com/buy).

**Q: Potřebuji dočasnou licenci pro testovací účely?**  
A: Ano, dočasnou licenci můžete získat [here](https://purchase.aspose.com/temporary-license/).

## Závěr
Nyní jste se naučili **nastavit adresář dat**, **vytvořit novou aktivitu**, definovat a přiřadit vlastní atribut a **uložit projekt jako MPP** při **přizpůsobování polí tabulky** v zobrazení Ganttova diagramu pomocí Aspose.Tasks pro Java. Tyto kroky vám poskytují plnou kontrolu nad tím, jak jsou projektová data zobrazena, což činí vaše Ganttovy diagramy informativnějšími a přizpůsobenými potřebám vašich stakeholderů.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}