---
date: 2026-02-13
description: Naučte se, jak vypočítat počet dnů mezi daty, vytvořit testovací projekt
  a přidat vlastní pole při manipulaci se soubory Microsoft Project pomocí Aspose.Tasks
  pro Javu.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Vypočítejte dny mezi daty pomocí Aspose.Tasks pro Javu
url: /cs/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vypočítejte dny mezi daty pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu **vypočítáte dny mezi daty** vytvořením testovacího projektu, přidáním vlastního pole a použitím vzorců Microsoft Project prostřednictvím knihovny Aspose.Tasks pro Java. Ať už potřebujete generovat harmonogramy, počítat termíny nebo automatizovat reportování, Aspose.Tasks vám umožní programově manipulovat s daty Projectu bez nutnosti instalace desktopové aplikace. Na konci průvodce budete mít spustitelný příklad, který definuje rozšířený atribut, nastaví termín úkolu a uloží projekt jako soubor MPP.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Vytvoření testovacího projektu, přidání vlastního pole, definování rozšířeného atributu a nastavení termínu úkolu pomocí vzorce pro výpočet dnů mezi daty.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (nejnovější verze).  
- **Potřebuji licenci?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je licence povinná.  
- **Jaké IDE mohu použít?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, VS Code), které podporuje JDK 8+.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut na zkopírování kódu a jeho spuštění.

## Co znamená „vypočítat dny mezi daty“ v Aspose.Tasks?
Výpočet dnů mezi daty znamená použití vzorce v Projectu, který odečte jedno datumové pole (např. **Finish**) od druhého (např. **Deadline**) a vrátí číselný rozdíl ve dnech. To je užitečné pro sledování skluzu harmonogramu, měření rezervního času nebo tvorbu vlastních reportů.

## Proč použít Aspose.Tasks k výpočtu dnů mezi daty?
- **Kompletní pokrytí API** – přístup ke všem vlastnostem Projectu, úkolů i zdrojů.  
- **Bez nutnosti instalace Office** – funguje na serverech, v CI pipelinech i v Docker kontejnerech.  
- **Cross‑platform** – běží na Windows, Linuxu i macOS se stejným Java kódem.  
- **Robustní engine vzorců** – umožňuje definovat výpočty jako `[Deadline] - [Finish]` přímo v souboru projektu.

## Jak nastavit termín (deadline) pro úkol
Nastavení termínu je první krok, než budete moci vypočítat interval. Termín je uložen v poli `Tsk.DEADLINE` úkolu a lze jej přiřadit pomocí instance `java.util.Calendar`.

## Jak definovat rozšířený atribut
Rozšířený atribut je vlastní pole, které bude obsahovat výsledek vašeho vzorce. Definujete jej jednou, přiřadíte mu alias pro čitelnost a pak připojíte vzorec, který provádí odečtení dat.

## Požadavky
Před zahájením se ujistěte, že máte následující:

- **Java Development Kit (JDK) 8+** – stáhněte z webu Oracle nebo použijte OpenJDK.  
- **Aspose.Tasks pro Java** – získejte nejnovější JAR ze [stránky ke stažení Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/) a přidejte jej do classpath vašeho projektu nebo do Maven/Gradle závislostí.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Postupný návod

### Krok 1: Vytvořte testovací projekt s vlastním polem
Začínáme **vytvořením testovacího projektu** a přidáním vlastního pole, které později bude obsahovat výsledek našeho vzorce.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` je pomocná metoda, která vytvoří minimální harmonogram a zaregistruje rozšířený atribut připravený pro přiřazení vzorce.

### Krok 2: Definujte rozšířený atribut (přidejte vlastní pole)
Dále **definujeme rozšířený atribut** – v podstatě vlastní pole – a přiřadíme mu přátelský alias. Zde **přidáváme logiku vlastního pole**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** dělá pole čitelným v Project.  
- **Formula** vypočítává počet dnů mezi datem *Finish* úkolu a jeho *Deadline* – jádro funkce *vypočítat dny mezi daty*.

### Krok 3: Nastavte termín pro úkol (přidejte úkol s termínem a nastavte termín úkolu)
Nyní **přidáme data termínu** nastavením vlastnosti *Deadline* u konkrétního úkolu.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instance `Calendar` určuje přesný okamžik termínu.  
- `set(Tsk.DEADLINE, …)` **nastavuje termín úkolu** pro vybraný úkol.

### Krok 4: Uložte projekt (pracujte s souborem Microsoft Project)
Nakonec **pracujeme s Microsoft Project** tím, že změny uložíme do souboru MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Soubor `SaveFile.mpp` můžete otevřít v Microsoft Project a uvidíte vlastní pole, výsledek vzorce i nastavený termín v harmonogramu.

## Časté problémy a řešení
| Problém | Řešení |
|---------|--------|
| **Formula not evaluating** | Ujistěte se, že řetězec `Formula` atributu používá správná jména polí (např. `[Deadline]`, `[Finish]`). |
| **Task not found** | Ověřte, že ID úkolu (`1` v příkladu) existuje; pro ladění můžete použít `project.getRootTask().getChildren().size()`. |
| **License exception** | Aplikujte platnou licenci Aspose.Tasks před voláním jakýchkoli metod API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks poskytuje API pro .NET, Java a další platformy, což vám umožní **manipulovat soubory Microsoft Project** v jazyce dle vašeho výběru.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Rozhodně. Stáhněte si plně funkční zkušební verzi ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci k Aspose.Tasks?**  
A: Oficiální dokumentace je k dispozici na [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Jak získám podporu pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a sdílet zkušenosti s komunitou.

**Q: Potřebuji dočasnou licenci pro hodnocení?**  
A: Dočasná licence je k dispozici pro krátkodobé testování; můžete ji požádat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-02-13  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}