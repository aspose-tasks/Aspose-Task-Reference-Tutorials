---
date: 2026-08-29
description: Naučte se, jak přidat úkol do projektu v Javě, vytvořit seznam úkolů
  a nastavit základní linii bez Microsoft Project pomocí Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Vytvoření základní linie úkolu v Aspose.Tasks
og_description: Naučte se, jak přidat úkol do projektu v Javě a nastavit základní
  linii pomocí Aspose.Tasks. Tento průvodce ukazuje krok za krokem kód bez potřeby
  Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Jak přidat úkol do projektu v Javě a nastavit základní linii
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Jak přidat úkol do projektu v Javě a nastavit základní linii
url: /cs/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat úkol do projektu v Javě a nastavit základní linii

## Úvod
V tomto tutoriálu **přidáte úkol do projektu** programově, vygenerujete základní linii úkolu v Microsoft Project a soubor uložíte – vše bez nutnosti otevírat Microsoft Project. Aspose.Tasks pro Javu vám poskytuje čisté Java API, které funguje na jakékoli platformě, což je ideální pro automatizované sestavovací pipeline, reportingové služby nebo jakékoli server‑side řešení, které potřebuje manipulovat se soubory .mpp.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks?** Poskytuje Java API pro vytváření, čtení a úpravu souborů Microsoft Project bez nutnosti Microsoft Project.  
- **Potřebuji mít nainstalovaný Microsoft Project?** Ne, knihovna funguje zcela nezávisle.  
- **Která verze Javy je vyžadována?** JDK 8 nebo vyšší.  
- **Mohu nastavit základní linii pro jediný úkol?** Ano – zavolejte `setBaseline` na seznam, který obsahuje pouze požadované úkoly.  
- **Je pro produkci potřeba licence?** Ano, komerční licence odstraňuje omezení zkušební verze a odemyká všechny funkce.

## Co je základní linie úkolu?
Základní linie úkolu zachycuje původně plánovaný datum zahájení, datum dokončení a pracovní úsilí úkolu v okamžiku, kdy je rozvrh poprvé uložen. Tento snímek slouží jako referenční bod, který umožňuje projektovým manažerům porovnat skutečný postup a náklady s původním plánem a vypočítat odchylky pro analýzu výkonnosti.

## Proč použít Aspose.Tasks k přidání úkolu do projektu v Javě?
Můžete vytvářet, upravovat a nastavovat základní linie úkolů bez jakékoli desktopové instalace, což umožňuje plně automatizované pracovní postupy. Aspose.Tasks podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat projekty se **stovkami úkolů**, přičemž spotřeba paměti zůstává pod 200 MB, což je ideální pro cloudové služby a CI/CD pipeline.

## Požadavky
1. **Java Development Kit (JDK)** – nainstalujte JDK 8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte knihovnu z [download link](https://releases.aspose.com/tasks/java/).

## Import balíčků
Pro zahájení práce s Aspose.Tasks ve vašem Java projektu importujte potřebné balíčky:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Krok 1: vytvořit objekt projektu
`Project` třída je nejvyšší objekt Aspose.Tasks, který v paměti představuje soubor Microsoft Project. Jeho vytvoření vám poskytne prázdný projekt, který můžete naplnit úkoly, zdroji a kalendáři.

```java
Project project = new Project();
```
Zde vytváříme novou instanci objektu `Project` – představuje soubor MS Project, který bude obsahovat náš seznam úkolů.

## Krok 2: přidat úkol do projektu
`Task` třída představuje jednotlivou pracovní položku v harmonogramu projektu. Každý `Task` může mít vlastní dobu trvání, datum zahájení a přiřazení zdrojů.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Pomocí `getRootTask()` získáme kořen hierarchie projektu a **přidáme úkol do Microsoft Project**. Řetězec `"Task"` je název úkolu; můžete jej nahradit libovolným popisem, který potřebujete.

## Krok 3: nastavit základní linii pro vybrané úkoly
`BaselineType` je výčtový typ, který určuje, kterou slot základní linie (Baseline, Baseline1 … Baseline10) chcete zapsat. Předáním seznamu úkolů můžete nastavit základní linii pouze pro vybrané položky.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Pro **nastavení základní linie bez MS Project** vytvořte seznam úkolů, které chcete zahrnout do základní linie (zde `myList`) a předávejte jej metodě `setBaseline`. Naplňte `myList` úkoly, které jste přidali, pokud potřebujete jen selektivní základní linii.

## Krok 4: nastavit základní linii pro celý projekt
`setBaseline` zapíše vybrané hodnoty základní linie do každého úkolu v projektu.  
Pokud chcete nastavit základní linii pro celý projekt jedním voláním, jednoduše zavolejte `setBaseline` s požadovaným `BaselineType`.

```java
project.setBaseline(BaselineType.Baseline);
```
Toto volání zapíše zvolené hodnoty základní linie pro **každý úkol** v projektu, čímž zajistí kompletní snímek původního harmonogramu.

## Jak přidat úkol do Microsoft Project pomocí Aspose.Tasks
`add()` vytvoří nový podúkol pod zadaným nadřazeným úkolem a vrátí nově vytvořený objekt `Task`.  
Úkol přidáte zavoláním `add()` na nadřazený objekt `Task` (obvykle kořenový úkol). Metoda vrátí novou instanci `Task`, kterou můžete dále konfigurovat – dobu trvání, datum zahájení, zdroje nebo vlastní pole – před uložením souboru projektu.

## Jak nastavit základní linii bez MS Project
Aspose.Tasks umožňuje vytvoření základní linie zcela pomocí kódu. Vyberte `BaselineType` (např. `BaselineType.Baseline`) a zavolejte `setBaseline`. Můžete to opakovat s `Baseline1`‑`Baseline10` pro udržení více revizních základních linií, vše bez otevírání Microsoft Project.

## Časté problémy a řešení
- **Základní linie se nezobrazuje:** Ujistěte se, že po nastavení základní linie zavoláte `project.save("output.mpp")` (krok ukládání byl zde vynechán pro stručnost).  
- **Seznam úkolů je prázdný:** Ověřte, že úkoly přidáváte ke správnému nadřazenému objektu (`getRootTask()` nebo podúkolu).  
- **Chyby nesouladu verzí:** Použijte nejnovější Aspose.Tasks JAR, aby byla zajištěna kompatibilita s novějšími formáty .mpp.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks pro Javu bez nainstalovaného Microsoft Project?**  
A: Ano, Aspose.Tasks funguje nezávisle a nevyžaduje Microsoft Project na hostitelském počítači.

**Q: Je Aspose.Tasks pro Javu kompatibilní s různými verzemi Microsoft Project?**  
A: Rozhodně. Knihovna podporuje soubory Project od verze 2007 až po nejnovější vydání z roku 2024.

**Q: Mohu pomocí Aspose.Tasks pro Javu manipulovat se zdroji projektu?**  
A: Ano, můžete přidávat, aktualizovat a mazat zdroje programově, stejně jako úkoly.

**Q: Podporuje Aspose.Tasks pro Javu nastavení závislostí úkolů?**  
A: Ano, můžete definovat vztahy předchůdce‑následník pomocí třídy `TaskLink`.

**Q: Je k dispozici technická podpora pro Aspose.Tasks pro Javu?**  
A: Ano, můžete získat pomoc prostřednictvím [support forum](https://forum.aspose.com/c/tasks/15), kde odpovídají zaměstnanci Aspose a komunita.

## Závěr
Po provedení těchto kroků jste se naučili, jak **přidat úkol do projektu** v Javě, vytvořit seznam úkolů a **nastavit základní linii bez MS Project** pomocí Aspose.Tasks. Tento přístup zjednodušuje automatizaci projektů, odstraňuje potřebu instalací desktopové verze Project a poskytuje vám plnou programovou kontrolu nad každým aspektem vašeho harmonogramu.

---

**Poslední aktualizace:** 2026-08-29  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit projekt aspose.tasks – Nastavit nové atributy úkolu](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Jak nastavit dobu trvání základní linie v Aspose.Tasks pro Javu](/tasks/java/task-baselines/task-baseline-duration/)
- [Vytvořit úkoly Aspose Java – Vlastnosti úkolu](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}