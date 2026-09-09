---
date: 2026-09-09
description: Naučte se, jak identifikovat úkoly napříč projekty pomocí Aspose.Tasks
  pro Java. Prozkoumejte bezproblémovou integraci, efektivní správu a reálné příklady.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identifikace úkolů napříč projekty v Aspose.Tasks
og_description: Identifikujte úkoly napříč projekty v Aspose.Tasks pro Java. Naučte
  se, jak nastavit adresář dokumentů, získat ID úkolů a efektivně spravovat propojené
  projekty.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identifikace úkolů napříč projekty v Aspose.Tasks – průvodce pro Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identifikace úkolů napříč projekty v Aspose.Tasks
url: /cs/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identifikace úkolů napříč projekty v Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **jak identifikovat úkoly napříč projekty** pomocí Aspose.Tasks pro Java. Ať už spravujete portfolio vzájemně závislých harmonogramů nebo potřebujete auditovat externí závislosti, níže uvedené kroky vám ukážou, jak najít úkoly, které odkazují na jiné projektové soubory, získat jejich identifikátory a pracovat s nimi programově.

## Rychlé odpovědi
- **Co znamená „identifikovat úkoly napříč projekty“?** Znamená to vyhledání úkolů, které odkazují na úkoly v jiném souboru projektu nebo jsou na nich závislé.  
- **Která metoda vypisuje ID úkolu?** Použijte `externalTask.get(Tsk.ID)` k vypsání ID úkolu.  
- **Jak nastavit adresář dokumentu?** Přiřaďte cestu ke složce do proměnné typu `String` (např. `dataDir`).  
- **Která vlastnost načte úkol podle UID?** Zavolejte `getChildren().getByUid(yourUid)`.  
- **Potřebuji licenci pro produkční použití?** Ano, pro komerční nasazení je vyžadována platná licence Aspose.Tasks.

## Co je „identifikovat úkoly napříč projekty“?
Identifikace úkolů napříč projekty vám umožňuje sledovat vztahy mezi úkoly rozprostřenými v několika souborech Microsoft Project. Vyhledáním úkolů, které odkazují na externí harmonogramy nebo jsou na nich závislé, můžete pochopit, jak pracovní položky spolupracují napříč projektovými hranicemi, zabránit duplicitní práci a udržet přesné časové osy. Tato schopnost je nezbytná pro rozsáhlá portfolia, kde jsou úkoly sdílené nebo závislé na externích plánech.

## Proč používat Aspose.Tasks pro Java?
Aspose.Tasks pro Java podporuje **více než 50 vstupních a výstupních formátů** (včetně MPP, MPX, XML a CSV) a dokáže zpracovat projekty s **až 10 000 úkoly** bez načítání celého souboru do paměti. Knihovna funguje na jakékoli platformě kompatibilní s JVM, nevyžaduje instalaci Microsoft Project a nabízí plný přístup k API pro ID, UID, externí ID a metadata propojení.

## Požadavky
Než začnete, ujistěte se, že máte:

- Funkční vývojové prostředí Java (JDK 8 nebo vyšší).  
- Aspose.Tasks pro Java nainstalováno. Můžete jej stáhnout **[zde](https://releases.aspose.com/tasks/java/)**.  
- Platný licenční soubor Aspose.Tasks, pokud plánujete spouštět kód v produkci.

## Import balíčků
Třída `Project` představuje soubor Microsoft Project, `Task` představuje jednotlivý úkol a `Tsk` poskytuje konstanty polí úkolu.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Krok 1: nastavit adresář dokumentu
Řetězec `dataDir` obsahuje cestu ke složce, která obsahuje vaše soubory `.mpp`.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Krok 2: načíst externí projekt
`Project externalProject` načte zadaný externí soubor projektu pro kontrolu.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Krok 3: načíst externí úkol podle UID
`externalProject.getChildren().getByUid(uid)` načte úkol z kolekce úkolů externího projektu pomocí jeho jedinečného identifikátoru.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Krok 4: vypsat ID úkolu (hlavní případ použití)
`externalTask.get(Tsk.ID)` vrací interní ID přiřazené Aspose.Tasks pro daný úkol.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Krok 5: vypsat původní (externí) ID úkolu
`externalTask.get(Tsk.ExternalID)` získá původní ID úkolu, jak je definováno ve zdrojovém souboru projektu.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Opakujte výše uvedené kroky pro jakékoli další úkoly, které potřebujete sledovat napříč projekty.

## Časté problémy a tipy
- **Chyby cesty** – Ujistěte se, že `dataDir` končí správným oddělovačem souborů (`/` nebo `\\`).  
- **UID nenalezeno** – Ověřte, že UID existuje v externím projektu; použijte `externalProject.getRootTask().getChildren().size()` k výpisu dostupných UID.  
- **Výjimky licence** – Chybějící nebo neplatná licence vyvolá výjimku licence během běhu.  
- **Velké projekty** – Pro projekty s více než 5 000 úkoly zvažte použití `ProjectReader` s příznakem `LoadOptions` pro streamování dat a snížení spotřeby paměti.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks podporuje více jazyků, včetně Java, .NET a dalších.

**Q: Kde najdu podrobnou dokumentaci pro Aspose.Tasks pro Java?**  
A: Viz dokumentace **[zde](https://reference.aspose.com/tasks/java/)**.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi **[zde](https://releases.aspose.com/)**.

**Q: Jak získat dočasnou licenci pro Aspose.Tasks?**  
A: Získejte dočasnou licenci **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Potřebujete pomoc nebo máte konkrétní otázky?**  
A: Navštivte fórum podpory Aspose.Tasks **[zde](https://forum.aspose.com/c/tasks/15)**.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Související tutoriály

- [Vytvoření závislostí úkolů v řízení projektů v Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Nastavení data zahájení projektu a správa nadřazených a podřízených úkolů v Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Vytvoření MPP projektu v Javě – změna postupu úkolu pomocí Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}