---
date: 2026-02-13
description: Naučte se, jak generovat projektovou zprávu vytvořením objektu projektu
  v Javě, přidáním rozšířených atributů a použitím evaluačních funkcí s Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Generovat projektovou zprávu – Vytvořit objekt projektu v Javě
url: /cs/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Podpora evaluačních funkcí v Aspose.Tasks formulích

## Úvod
Aspose.Tasks pro Java vám umožňuje **generovat projektové zprávy** vytvořením **projektového objektu** v Javě a vyhodnocováním funkcí Microsoft Project přímo ve vašem kódu. Vložením těchto formulí můžete provádět složité výpočty, generovat vlastní zprávy a automatizovat analýzu projektů, aniž byste opustili vývojové prostředí. V tomto tutoriálu si projdeme vytvoření projektového objektu, přidání rozšířeného atributu a použití evaluačních funkcí k **přidání dat úkolu do vlastního pole**.

## Rychlé odpovědi
- **Co znamená „create project object java“?** Vytvoří se instance `Project` v paměti, kterou můžete programově manipulovat.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (stáhněte z oficiálního webu).  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence Aspose.Tasks; k dispozici je bezplatná zkušební verze.  
- **Mohu použít vlastní pole?** Ano – můžete **přidat rozšířený atribut** k úkolům a používat jej jako vlastní pole.  
- **Je to kompatibilní se všemi formáty souborů Project?** Aspose.Tasks podporuje formáty MPP, MPT i XML.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. **Vývojové prostředí Java** – JDK 8+ a IDE jako IntelliJ IDEA nebo Eclipse.  
2. **Aspose.Tasks pro Java knihovna** – Stáhněte a zahrňte knihovnu ze [stránky ke stažení Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/).

## Import balíčků
Přidejte jmenný prostor Aspose.Tasks do své Java třídy, abyste mohli pracovat s projekty, úkoly a rozšířenými atributy:

```java
import com.aspose.tasks.*;
```

## Generování projektové zprávy – Vytvoření projektového objektu Java
Instancujte nový objekt `Project`. Ten bude sloužit jako kontejner pro všechny úkoly, zdroje a vlastní data, která definujete.

```java
Project project = new Project();
```

Řádek výše **vytváří projektový objekt java**, který je zpočátku prázdný a připravený k úpravám.

## Jak přidat rozšířený atribut
Definujte rozšířený atribut, který bude pro každý úkol uchovávat vlastní číselná data (např. hodnotu sinu).

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Zde **přidáváme rozšířený atribut** typu `Number` s názvem „Sine“ a spojujeme jej s úkoly.

## Přidání rozšířeného atributu do projektu
Zaregistrujte definici atributu v projektu, aby na něj mohl odkazovat každý úkol.

```java
project.getExtendedAttributes().add(attr);
```

## Vytvoření nového úkolu
Přidejte jednoduchý úkol s názvem „Task“ pod kořenový úkol projektu.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Propojení rozšířeného atributu s úkolem
Propojte dříve definovaný rozšířený atribut s nově vytvořeným úkolem.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nyní úkol obsahuje vlastní pole „Sine“, které můžete použít ve formulích nebo výpočtech. Takto také **přidáváte data úkolu do vlastního pole** programově.

## Proč používat evaluační funkce?
Vkládání funkcí MS Project do Aspose.Tasks formulí vám umožní:

- Provádět výpočty za běhu (např. `Sin([Start])`) bez externích nástrojů.  
- Udržet veškerou logiku projektu v jednom udržovatelném kódu.  
- Generovat dynamické zprávy, které odrážejí změny dat v reálném čase, a tím **automaticky generovat projektové zprávy**.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Formula returns `NaN`** | Ověřte, že typ vlastního pole odpovídá očekávanému číselnému typu. |
| **Extended attribute not visible** | Ujistěte se, že definice atributu je přidána do projektu **před** vytvořením úkolů. |
| **License exception** | Nainstalujte dočasnou nebo plnou **licenci Aspose.Tasks**; režim zkušební verze může omezovat některé funkce. |
| **Missing temporary license** | Získejte **dočasnou licenci Aspose** na webu Aspose. |

## Často kladené otázky

**Q: Dokáže Aspose.Tasks pro Java zpracovat složité MS Project formule?**  
A: Ano, Aspose.Tasks pro Java podporuje vyhodnocování široké škály funkcí MS Project, což umožňuje provádět komplexní výpočty v Java aplikacích.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Ano, Aspose.Tasks pro Java podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.

**Q: Můžu si Aspose.Tasks pro Java vyzkoušet před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro Java z webu [zde](https://purchase.aspose.com/buy).

**Q: Jak získám podporu pro Aspose.Tasks pro Java?**  
A: Podporu můžete získat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Existuje dočasná licence pro Aspose.Tasks pro Java?**  
A: Ano, dočasnou licenci pro testovací účely můžete získat na webu Aspose [zde](https://purchase.aspose.com/temporary-license/).

## Závěr
Postupným sledováním těchto kroků jste se naučili, jak **vytvořit projektový objekt**, **přidat rozšířený atribut** a využít evaluační funkce k **automatickému generování projektových zpráv**. Nyní můžete tuto základnu rozšířit o pokročilejší projektovou analytiku, vlastní dashboardy nebo automatizované nástroje plánování – vše poháněné Aspose.Tasks pro Java.

---

**Poslední aktualizace:** 2026-02-13  
**Testováno s:** Aspose.Tasks pro Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}