---
date: 2025-12-09
description: Naučte se, jak vytvořit objekt projektu v Javě a podporovat evaluační
  funkce ve vzorcích Aspose.Tasks pomocí Javy. Objevte, jak vytvořit rozšířený atribut
  pro úkoly.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Vytvořit objekt projektu v Javě – Podpora evaluačních funkcí v Aspose.Tasks
url: /cs/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Podpora evaluačních funkcí v Aspose.Tasks formulích

## Úvod
Aspose.Tasks pro Java vám umožňuje **create project object java** instance a vyhodnocovat funkce Microsoft Project přímo ve vašem Java kódu. Vložením těchto formulí můžete provádět složité výpočty, generovat vlastní zprávy a automatizovat analýzu projektů, aniž byste opustili vývojové prostředí. Tento tutoriál vás provede celým procesem – od nastavení objektu projektu až po přidání rozšířeného atributu, který může obsahovat vlastní data.

## Rychlé odpovědi
- **Co znamená “create project object java”?** Vytváří v‑paměti `Project` instanci, kterou můžete programově manipulovat.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (stáhněte z oficiálního webu).  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence; je k dispozici bezplatná zkušební verze.  
- **Mohu použít vlastní pole?** Ano – můžete definovat a přiřadit rozšířené atributy k úkolům.  
- **Je to kompatibilní se všemi formáty souborů Project?** Aspose.Tasks podporuje formáty MPP, MPT a XML.

## Požadavky
1. **Java vývojové prostředí** – JDK 8+ a IDE jako IntelliJ IDEA nebo Eclipse.  
2. **Aspose.Tasks pro Java knihovna** – Stáhněte a zahrňte knihovnu ze [stránky ke stažení Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/).

## Import balíčků
Přidejte namespace Aspose.Tasks do vaší Java třídy, abyste mohli pracovat s projekty, úkoly a rozšířenými atributy:

```java
import com.aspose.tasks.*;
```

## Krok 1: Vytvořit projektový objekt Java
Instancujte nový objekt `Project`. Ten bude sloužit jako kontejner pro všechny úkoly, zdroje a vlastní data, které definujete.

```java
Project project = new Project();
```

Řádek výše **creates project object java** který začíná prázdný a je připravený k přizpůsobení.

## Krok 2: Jak vytvořit rozšířený atribut
Definujte rozšířený atribut, který bude pro každý úkol ukládat vlastní číselná data (např. hodnotu sinus).

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Zde **create extended attribute** typu `Number` pojmenovaný „Sine“ a přiřazujeme jej úkolům.

## Krok 3: Přidat rozšířený atribut do projektu
Zaregistrujte definici atributu v projektu, aby na něj mohl odkazovat každý úkol.

```java
project.getExtendedAttributes().add(attr);
```

## Krok 4: Vytvořit nový úkol
Přidejte jednoduchý úkol pojmenovaný „Task“ pod kořenový úkol projektu.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Krok 5: Připojit rozšířený atribut k úkolu
Propojte dříve definovaný rozšířený atribut s nově vytvořeným úkolem.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nyní úkol obsahuje vlastní pole „Sine“, které můžete použít ve formulích nebo výpočtech.

## Proč používat evaluační funkce?
- Provádět výpočty za běhu (např. `Sin([Start])`) bez externích nástrojů.  
- Udržet veškerou logiku projektu v jedné, snadno udržovatelné kódové základně.  
- Generovat dynamické zprávy, které odrážejí změny dat v reálném čase.

## Časté problémy a řešení
| Problém | Řešení |
|---------|--------|
| **Formula vrací `NaN`** | Ověřte, že typ vlastního pole odpovídá očekávanému číselnému typu. |
| **Rozšířený atribut není viditelný** | Ujistěte se, že definice atributu je přidána do projektu **před** vytvořením úkolů. |
| **Licence výjimka** | Nainstalujte dočasnou nebo plnou licenci; režim zkušební verze může omezovat některé funkce. |

## Často kladené otázky

**Q: Může Aspose.Tasks pro Java zpracovat složité MS Project formule?**  
A: Ano, Aspose.Tasks pro Java podporuje vyhodnocování široké škály funkcí MS Project, což umožňuje složité výpočty v Java aplikacích.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Ano, Aspose.Tasks pro Java podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.

**Q: Mohu vyzkoušet Aspose.Tasks pro Java před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro Java z webu [zde](https://purchase.aspose.com/buy).

**Q: Jak mohu získat podporu pro Aspose.Tasks pro Java?**  
A: Podporu můžete získat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Je k dispozici dočasná licence pro Aspose.Tasks pro Java?**  
A: Ano, dočasnou licenci pro testovací účely můžete získat na webu Aspose [zde](https://purchase.aspose.com/temporary-license/).

**Poslední aktualizace:** 2025-12-09  
**Testováno s:** Aspose.Tasks pro Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}