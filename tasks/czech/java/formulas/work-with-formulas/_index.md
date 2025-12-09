---
date: 2025-12-07
description: Naučte se, jak **vytvořit testovací projekt** a **přidat vlastní pole**
  při manipulaci se soubory Microsoft Project pomocí Aspose.Tasks pro Javu.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Vytvořte testovací projekt a použijte vzorce s Aspose.Tasks pro Javu
url: /cs/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření testovacího projektu a použití vzorců s Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu **vytvoříte testovací projekt** soubory, přidáte vlastní pole a budete pracovat s MS Project vzorci pomocí knihovny Aspose.Tasks pro Java. Aspose.Tasks usnadňuje **manipulaci s Microsoft Project** daty programově – ať už potřebujete generovat harmonogramy, počítat data nebo automatizovat reportování. Na konci průvodce budete mít spustitelný příklad, který definuje rozšířený atribut, nastaví termín úkolu a uloží projekt jako MPP soubor.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Vytvoření testovacího projektu, přidání vlastního pole, definování rozšířeného atributu a nastavení termínu úkolu pomocí vzorce.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro Java (nejnovější verze).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; licence je vyžadována pro produkci.  
- **Jaké IDE mohu použít?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, VS Code), které podporuje JDK 8+.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut na zkopírování kódu a jeho spuštění.

## Co je „testovací projekt“ v Aspose.Tasks?
**Testovací projekt** je lehký soubor Microsoft Project vytvořený programově za účelem demonstrace nebo ověření funkčnosti. Obsahuje minimální sadu úkolů, zdrojů a vlastních polí, které můžete manipulovat, aniž byste ovlivnili reálná projektová data.

## Proč použít Aspose.Tasks k manipulaci s Microsoft Project?
- **Úplné pokrytí API** – přístup ke každé vlastnosti Project, Task a Resource.  
- **Bez nutnosti instalace Office** – funguje na serverech, v CI pipelinech i v Docker kontejnerech.  
- **Cross‑platform** – běží na Windows, Linuxu i macOS se stejným Java kódem.  
- **Robustní engine vzorců** – vypočítává data, trvání a vlastní pole přímo v souboru projektu.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- **Java Development Kit (JDK) 8+** – stáhněte z webu Oracle nebo použijte OpenJDK.  
- **Aspose.Tasks pro Java** – získejte nejnovější JAR ze [stránky ke stažení Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/) a přidejte jej do classpath vašeho projektu nebo do Maven/Gradle závislostí.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Postupný průvodce

### Krok 1: Vytvořte testovací projekt s vlastním polem
Začneme **vytvořením testovacího projektu** a přidáním vlastního pole, které později bude obsahovat výsledek našeho vzorce.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` je pomocná metoda, která vytvoří minimální harmonogram a zaregistruje rozšířený atribut připravený pro přiřazení vzorce.

### Krok 2: Definujte rozšířený atribut (přidejte vlastní pole)
Dále **definujeme rozšířený atribut** – v podstatě vlastní pole – a přiřadíme mu přátelský alias. Zde se provádí logika **přidání vlastního pole**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** dělá pole čitelným v Projectu.  
- **Formula** vypočítává počet dní mezi datem *Finish* úkolu a jeho *Deadline*.

### Krok 3: Nastavte termín úkolu (přidejte úkol s termínem a nastavte termín úkolu)
Nyní **přidáme data termínu úkolu** nastavením vlastnosti *Deadline* u konkrétního úkolu.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` instance určuje přesný okamžik termínu.  
- `set(Tsk.DEADLINE, …)` **nastavuje termín úkolu** pro vybraný úkol.

### Krok 4: Uložte projekt (manipulujte souborem Microsoft Project)
Nakonec **manipulujeme Microsoft Project** souborem tím, že změny uložíme do MPP souboru.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Můžete otevřít `SaveFile.mpp` v Microsoft Project a vidět vlastní pole, výsledek vzorce a termín zobrazené v harmonogramu.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Formula not evaluating** | Ujistěte se, že řetězec `Formula` atributu používá správná jména polí (např. `[Deadline]`, `[Finish]`). |
| **Task not found** | Ověřte, že ID úkolu (`1` v příkladu) existuje; použijte `project.getRootTask().getChildren().size()` pro ladění. |
| **License exception** | Aplikujte platnou Aspose.Tasks licenci před voláním jakýchkoli API metod (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks poskytuje API pro .NET, Java a další platformy, což vám umožní **manipulovat Microsoft Project** soubory v jazyce dle vašeho výběru.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Samozřejmě. Stáhněte si plně funkční zkušební verzi ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci k Aspose.Tasks?**  
A: Oficiální dokumentace je dostupná na [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Jak mohu získat podporu pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a sdílet zkušenosti s komunitou.

**Q: Potřebuji dočasnou licenci pro hodnocení?**  
A: Dočasná licence je k dispozici pro krátkodobé testování; můžete ji požádat [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2025-12-07  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}