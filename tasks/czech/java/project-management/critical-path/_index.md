---
date: 2025-12-23
description: Naučte se, jak vytvořit závislosti úkolů a vypočítat kritickou cestu
  v MS Project pomocí Aspose.Tasks pro Javu. Krok za krokem průvodce pro řízení projektů.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Vytvořte závislosti úkolů a vypočítejte kritickou cestu v Aspose.Tasks
url: /cs/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření závislostí úkolů a výpočet kritické cesty v Aspose.Tasks

## Úvod
V tomto tutoriálu **se naučíte, jak vytvořit závislosti úkolů** a vypočítat kritickou cestu v souboru MS Project pomocí Aspose.Tasks pro Java. Porozumění a vizualizace kritické cesty vám pomáhá udržet projekt v termínu, zatímco správné propojení úkolů zajišťuje, že jakékoli zpoždění je okamžitě viditelné. Projdeme celý proces, od nastavení prostředí až po zobrazení finální kritické cesty.

## Rychlé odpovědi
- **Jaký je první krok?** Nastavte svůj Java projekt a přidejte knihovnu Aspose.Tasks.  
- **Který režim musí být povolen?** `CalculationMode.Automatic` (nastavte automatický výpočet).  
- **Jak propojit úkoly?** Použijte `project.getTaskLinks().add(...)` k vytvoření závislostí úkolů.  
- **Jak mohu zobrazit kritickou cestu?** Projděte `project.getCriticalPath()` a vytiskněte název každého úkolu.  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.

## Co znamená „vytvořit závislosti úkolů“?
Vytvoření závislostí úkolů znamená definování vztahů (např. Finish‑to‑Start) mezi úkoly tak, aby rozvrh odrážel reálná omezení. V Aspose.Tasks se to provádí pomocí objektů `TaskLink`.

## Proč vypočítat kritickou cestu v MS Project?
**Kritická cesta v MS Project** ukazuje nejdelší sekvenci závislých úkolů, která určuje minimální dobu trvání projektu. Výpočtem můžete rychle identifikovat úkoly, které nesmí být posunuty, aniž by to ovlivnilo celkový časový plán — což je zásadní pro efektivní **project management Java** aplikace.

## Požadavky
Než začnete, ujistěte se, že máte:

1. Java Development Kit (JDK) nainstalovaný ve vašem systému.  
2. Knihovnu Aspose.Tasks pro Java staženou a přidanou do vašeho projektu. Můžete ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  

## Import balíčků
Pro začátek importujte potřebné balíčky ve své Java třídě:
```java
import com.aspose.tasks.*;
```

## Jak nastavit automatický výpočet?
Nastavení režimu výpočtu na automatické zajišťuje, že jakákoli změna úkolů nebo odkazů okamžitě aktualizuje rozvrh, včetně kritické cesty.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Krok‑za‑krokem průvodce

### Krok 1: Nastavení adresáře s daty
Definujte cestu ke složce, která obsahuje váš soubor MS Project.
```java
String dataDir = "Your Data Directory";
```

### Krok 2: Načtení souboru MS Project
Načtěte existující soubor projektu (např. *New project 2013.mpp*) pomocí Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Krok 3: Přidání úkolů
Vytvořte tři jednoduché podúkoly, které později propojíme.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Krok 4: Vytvoření odkazů úkolů (vytvořit závislosti úkolů)
Definujte závislosti mezi úkoly. Zde používáme odkaz Finish‑to‑Start, který je nejčastější.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Krok 5: Zobrazení kritické cesty (zobrazit kritickou cestu)
Získejte a vytiskněte kritickou cestu. Metoda `getCriticalPath()` vrací seznam úkolů, které tvoří kritický řetězec.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Krok 6: Potvrzení dokončení
Zobrazte přátelskou zprávu po dokončení procesu.
```java
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Kritická cesta je prázdná** | Ujistěte se, že `CalculationMode.Automatic` je nastaveno před přidáním odkazů. |
| **Úkoly nejsou propojeny** | Ověřte, že jste pro každou závislost přidali objekty `TaskLink`. |
| **Výjimka licence** | Načtěte platnou licenci Aspose.Tasks před vytvořením instance `Project`. |

## Často kladené otázky

### Q: Mohu používat Aspose.Tasks pro Java s libovolnou verzí souborů MS Project?
A: Ano, Aspose.Tasks pro Java podporuje různé verze souborů MS Project, včetně .mpp souborů od MS Project 2003 do MS Project 2019.  

### Q: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
A: Ano, můžete si stáhnout bezplatnou zkušební verzi [zde](https://releases.aspose.com/).  

### Q: Kde mohu najít podporu pro Aspose.Tasks pro Java?
A: Podporu najdete na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).  

### Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?
A: Ano, můžete zakoupit dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).  

### Q: Jak mohu zakoupit Aspose.Tasks pro Java?
A: Můžete zakoupit Aspose.Tasks pro Java na webu [zde](https://purchase.aspose.com/buy).

## Závěr
Postupným dodržením těchto kroků jste **vytvořili závislosti úkolů**, nastavili **automatický výpočet** a úspěšně **zobrazili kritickou cestu** pro váš soubor MS Project. Tento pracovní postup vám dává plnou kontrolu nad logikou rozvrhu a pomáhá udržet projekty v termínu pomocí Java‑založeného **project management** kódu.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}