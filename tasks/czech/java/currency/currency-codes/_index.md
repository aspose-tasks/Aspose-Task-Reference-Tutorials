---
date: 2026-02-10
description: Naučte se, jak získat kódy měn ze souborů MS Project pomocí Aspose.Tasks
  pro Javu – rychlý způsob, jak získat kód měny, který potřebují vývojáři Javy.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak získat měnu z MS Project pomocí Aspose.Tasks
url: /cs/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak získat měnu z MS Project pomocí Aspise.Tasks

## Introduction
Vítejte! V tomto tutoriálu se dozvíte **jak získat měnu** kódy z MS Project souboru pomocí Aspose.Tasks Java API. Ať už vytváříte více‑měnové finanční zprávy, konsolidujete projekty z různých regionů, nebo jednoduše potřebujete správné měnové symboly pro následné zpracování, tento průvodce vás provede každým krokem – od nastavení prostředí až po programové získání kódu měny. Na konci budete pohodlně číst MS Project soubory a používat volání **get currency code java** k získání ISO identifikátoru měny.

## Quick Answers
- **What does the API do?** Čte soubory MS Project a zpřístupňuje vlastnosti jako kód měny.  
- **Which language is used?** Java, prostřednictvím knihovny Aspose.Tasks for Java.  
- **Do I need a license?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Can I retrieve the code in one line?** Ano — `prj.get(Prj.CURRENCY_CODE)` vrací řetězec s kódem měny.  
- **Is it compatible with all Project versions?** Aspose.Tasks podporuje jak starší (MPP), tak novější (XML, XER) formáty.

## What is **read ms project file**?
Čtení souboru MS Project znamená programově otevřít *.mpp* (nebo jiný podporovaný) projektový dokument a přistupovat k jeho datovým strukturám — úkolům, zdrojům, kalendářům a finančním nastavením — bez ruční interakce s Microsoft Project.

## Why use Aspose.Tasks to **read msproject** files?
- **Full format support** – funguje se soubory od Project 98 až po nejnovější verze Office.  
- **No COM or Office installation needed** – čistě Java, ideální pro server‑side automatizaci.  
- **Rich API** – poskytuje přímý přístup k vlastnostem jako `Prj.CURRENCY_CODE`, což vám umožní **how to retrieve currency** informace okamžitě.  
- **Performance** – lehké parsování, ideální pro dávkové zpracování mnoha projektů.

## Prerequisites
Než se ponoříme do kódu, ujistěte se, že máte následující:

### Java Development Kit (JDK) Installed
Ujistěte se, že na vašem počítači je k dispozici aktuální JDK. Nejnovější verzi JDK můžete stáhnout a nainstalovat z [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java Library
Stáhněte a nastavte knihovnu Aspose.Tasks for Java. Podrobná dokumentace a nejnovější binární soubory jsou k dispozici [here](https://reference.aspose.com/tasks/java/).

## Import Packages
Abychom mohli začít, naimportujte potřebné balíčky ve vašem Java projektu:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
Definujte složku, která obsahuje váš *.mpp* soubor. Přizpůsobte cestu tak, aby odpovídala vašemu prostředí.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Vytvořte instanci `Project` načtením souboru MS Project. Toto je okamžik, kdy **read msproject** data načtete do paměti.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
Nyní, když je projekt načten, můžete **how to retrieve currency** informace získat jediným voláním. Toto ukazuje použití **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Výstup bude třípísmenný ISO kód měny (např. `USD`, `EUR`, `GBP`), který je v projektu nastaven.

### Step 4: How to Retrieve Currency Code in Java (Additional Context)
Pokud potřebujete hodnotu uložit pro pozdější použití, jednoduše ji přiřaďte do proměnné:

*No extra code block is required* – stačí si ponechat řetězec vrácený `prj.get(Prj.CURRENCY_CODE)` a předat jej libovolné finanční službě, reportovacímu enginu nebo UI komponentě.

### Step 5: (Optional) Use the Currency Code
Můžete chtít získaný kód použít jinde — například pro formátování nákladových hodnot v vlastním reportu nebo jeho předání finančnímu API. Typické scénáře zahrnují:

- **Report generation** – přidat kód před sloupce nákladů (`USD 1,200`).  
- **API integration** – odeslat ISO kód platebním branám, které vyžadují identifikátor měny.  
- **Data consolidation** – seskupit více projektů podle měny pro analýzu portfolia.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | Projektový soubor nedefinuje měnu (výchozí je prázdná). | Nastavte měnu v Microsoft Project nebo ji přiřaďte pomocí `prj.set(Prj.CURRENCY_CODE, "USD");` před čtením. |
| **File not found** | Nesprávná cesta `dataDir`. | Ověřte cestu a ujistěte se, že název souboru přesně odpovídá, včetně velikosti písmen. |
| **Unsupported file version** | Velmi starý nebo poškozený *.mpp* soubor. | Použijte nejnovější verzi Aspose.Tasks nebo nejprve soubor v Microsoft Project převést do novějšího formátu. |

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle complex project structures?**  
A: Yes, the API can read and manipulate multi‑level task hierarchies, resource pools, and custom fields without issue.

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: Absolutely. It supports MPP, XML, XER, and other formats across many Microsoft Project releases.

**Q: Does Aspose.Tasks provide documentation and support?**  
A: Comprehensive documentation, code examples, and dedicated support are available on the Aspose website.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: A free trial is offered so you can evaluate all features, including reading currency codes.

**Q: Where can I get temporary licenses for Aspose.Tasks?**  
A: Temporary licenses can be obtained from the [website](https://purchase.aspose.com/temporary-license/) for short‑term evaluation.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}