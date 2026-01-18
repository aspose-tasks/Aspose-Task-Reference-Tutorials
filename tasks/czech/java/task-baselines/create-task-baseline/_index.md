---
date: 2026-01-18
description: Naučte se, jak vytvořit seznam úkolů v Javě a přidat úkol do Microsoft
  Projectu, nastavit základní linii bez MS Projectu pomocí Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Vytvořit seznam úkolů v Javě – základní plán MS Project pomocí Aspose.Tasks
url: /cs/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření seznamu úkolů v Javě – Základní linie projektu MS Project s Aspose.Tasks

## Úvod
V tomto tutoriálu **vytvoříte seznam úkolů v Javě** vytvořením základní linie úkolu Microsoft Project pomocí Aspose.Tasks pro Javu. Aspose.Tasks vám umožňuje pracovat se soubory Projectu bez nutnosti mít nainstalovaný Microsoft Project, takže můžete **přidat úkol do Microsoft Project**, manipulovat s prostředky a dokonce **nastavit základní linii bez MS Project** — vše z čistého Java kódu.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks?** Poskytuje Java API pro vytváření, čtení a úpravu souborů Microsoft Project bez MS Project.  
- **Potřebuji mít nainstalovaný Microsoft Project?** Ne, Aspose.Tasks funguje samostatně.  
- **Jaká verze Javy je požadována?** JDK 8 nebo vyšší.  
- **Mohu nastavit základní linii pro jediný úkol?** Ano, použijte `setBaseline` s listem úkolů.  
- **Je pro produkci potřeba licence?** Ano, komerční licence odstraňuje omezení zkušební verze.

## Co je základní linie úkolu?
Základní linie úkolu zaznamenává původní plánované hodnoty startu, konce a práce pro úkol. Slouží jako referenční bod pro porovnání skutečného postupu s původním plánem.

## Proč použít Aspose.Tasks k vytvoření seznamu úkolů v Javě?
- **Žádná závislost na MS Project** – ideální pro automatizaci na straně serveru.  
- **Plná kontrola** nad úkoly, prostředky a kalendáři pomocí Java kódu.  
- **Kompatibilita napříč verzemi** se soubory Project 2007‑2024.

## Předpoklady
1. **Java Development Kit (JDK)** – nainstalujte JDK 8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte knihovnu z [odkaz ke stažení](https://releases.aspose.com/tasks/java/).

## Import balíčků
Pro zahájení práce s Aspose.Tasks ve vašem Java projektu importujte potřebné balíčky:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Krok 1: Vytvořte objekt Project
```java
Project project = new Project();
```
Zde vytvoříme novou instanci objektu `Project` – představuje soubor MS Project, který bude obsahovat náš seznam úkolů.

## Krok 2: Přidejte úkol do projektu
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Pomocí `getRootTask()` získáme kořen hierarchie projektu a **přidáme úkol do Microsoft Project**. Řetězec `"Task"` je název úkolu; můžete jej nahradit libovolným popisem, který potřebujete.

## Krok 3: Nastavte základní linii pro určené úkoly
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Pro **nastavení základní linie bez MS Project** vytvořte seznam úkolů, které chcete zahrnout do základní linie (zde `myList`) a předávejte jej metodě `setBaseline`. Naplňte `myList` úkoly, které jste přidali, pokud potřebujete jen selektivní základní linii.

## Krok 4: Nastavte základní linii pro celý projekt
```java
project.setBaseline(BaselineType.Baseline);
```
Pokud chcete nastavit základní linii pro celý projekt najednou, jednoduše zavolejte `setBaseline` s požadovaným `BaselineType`.

## Jak přidat úkol do Microsoft Project pomocí Aspose.Tasks
Mimo jediný úkol uvedený výše můžete přidávat více úkolů, podúkoly a přiřazovat prostředky. Každé volání `add()` vrací objekt `Task`, který můžete dále konfigurovat (délka trvání, datum zahájení atd.).

## Jak nastavit základní linii bez MS Project
Aspose.Tasks umožňuje vytvoření základní linie kompletně pomocí kódu. Můžete nastavit různé typy základních linií (Baseline, Baseline1‑Baseline10) změnou výčtu `BaselineType`, což vám umožní sledovat více revizí základních linií, aniž byste kdykoliv otevírali MS Project.

## Časté problémy a řešení
- **Základní linie se nezobrazuje:** Ujistěte se, že po nastavení základní linie zavoláte `project.save("output.mpp")` (krok ukládání byl zde vynechán pro stručnost).  
- **Seznam úkolů je prázdný:** Ověřte, že úkoly přidáváte ke správnému rodiči (`getRootTask()` nebo podúkolu).  
- **Chyby nesouladu verzí:** Použijte nejnovější Aspose.Tasks JAR, aby byla zajištěna kompatibilita s novějšími formáty .mpp.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks pro Javu bez nainstalovaného Microsoft Project?**  
A: Ano, Aspose.Tasks funguje samostatně a nevyžaduje Microsoft Project na hostitelském počítači.

**Q: Je Aspose.Tasks pro Javu kompatibilní s různými verzemi Microsoft Project?**  
A: Rozhodně. Knihovna podporuje soubory Project od verze 2007 až po nejnovější vydání z roku 2024.

**Q: Mohu pomocí Aspose.Tasks pro Javu manipulovat s prostředky projektu?**  
A: Ano, můžete programově přidávat, aktualizovat i mazat prostředky, stejně jako úkoly.

**Q: Podporuje Aspose.Tasks pro Javu nastavení závislostí úkolů?**  
A: Ano, můžete definovat vztahy předchůdce‑následník pomocí třídy `TaskLink`.

**Q: Je k dispozici technická podpora pro Aspose.Tasks pro Javu?**  
A: Ano, můžete získat pomoc prostřednictvím [fóra podpory](https://forum.aspose.com/c/tasks/15), kde reagují zaměstnanci Aspose i komunita.

## Závěr
Postupným sledováním těchto kroků jste se naučili, jak **vytvořit seznam úkolů v Javě**, **přidat úkol do Microsoft Project** a **nastavit základní linii bez MS Project** pomocí Aspose.Tasks. Tento přístup zjednodušuje automatizaci projektů, eliminuje potřebu instalace desktopové verze Projectu a poskytuje vám plnou programovou kontrolu nad vašimi projektovými daty.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-18  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose