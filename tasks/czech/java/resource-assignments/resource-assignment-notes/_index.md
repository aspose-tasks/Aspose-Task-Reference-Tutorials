---
date: 2026-07-19
description: Zjistěte, jak přidat aspose tasks resource notes k přiřazením zdrojů
  pomocí Aspose.Tasks pro Java. Postupujte podle tohoto krok‑za‑krokem průvodce a
  zlepšete komunikaci v projektu.
keywords:
- aspose tasks resource notes
- resource assignment notes
- aspose.tasks java
lastmod: 2026-07-19
linktitle: Jak přidat poznámky k přiřazením zdrojů v Aspose.Tasks
og_description: Zjistěte, jak přidat aspose tasks resource notes k přiřazením zdrojů
  pomocí Aspose.Tasks pro Java. Tento tutoriál vás provede každým krokem, od nastavení
  až po získání poznámek.
og_image_alt: 'Guide: Adding resource assignment notes with Aspose.Tasks for Java'
og_title: aspose tasks resource notes – Přidat poznámky k přiřazením
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  headline: aspose tasks resource notes – Add Notes to Assignments
  type: TechArticle
- description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  name: aspose tasks resource notes – Add Notes to Assignments
  steps:
  - name: Set Data Directory
    text: Set the path to your data directory where your project files are located.
  - name: Load Project File
    text: Load the project file into your Java application.
  - name: Get Task and Resource
    text: Retrieve the task and resource to which you want to add notes.
  - name: Create Resource Assignment
    text: Create a resource assignment for the task and resource.
  - name: Set Notes
    text: Set the notes for the resource assignment.
  - name: Display Notes
    text: Display the notes text and RTF format.
  - name: Process Completion
    text: Print a success message indicating the completion of the process.
  type: HowTo
- questions:
  - answer: Yes, simply call `assn.set(Asn.NOTES_TEXT, "Updated note")` again with
      the new content.
    question: Can I edit notes after they have been set?
  - answer: Absolutely. When you save the `Project` object, the notes become part
      of the assignment data inside the file.
    question: Are notes stored in the .mpp file?
  - answer: You must open the project with the correct password using the appropriate
      `Project` constructor overload before accessing assignments.
    question: Does this work with encrypted project files?
  - answer: Practically, notes can be several kilobytes long; extremely large notes
      may affect performance when loading the project.
    question: Is there a limit to the length of a note?
  - answer: Yes, iterate over `prj.getResourceAssignments()` and set `Asn.NOTES_TEXT`
      for each assignment as needed.
    question: Can I add notes to multiple assignments in a loop?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- resource notes
- java project management
- resource assignments
- aspose tasks java
title: aspose tasks resource notes – Přidat poznámky k přiřazením
url: /cs/java/resource-assignments/resource-assignment-notes/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat poznámky k přiřazením zdrojů v Aspose.Tasks

## Úvod
V tomto tutoriálu objevíte **jak přidat poznámky k přiřazením zdrojů** pomocí Aspose.Tasks pro Java – špičkové knihovny, která zpracovává soubory pro řízení projektů. Na konci průvodce budete schopni připojit poznámky v prostém textu nebo ve formátu RTF přímo k propojení úkol‑zdroj, což učiní vaše projektová data mnohem komunikativnější a připravená k auditu.

## Rychlé odpovědi
- **Co ovlivňuje „přidat poznámky“?** Ukládá poznámky v prostém textu a RTF na přiřazení zdroje.  
- **Která třída obsahuje data poznámky?** Třída `Asn` (např. `Asn.NOTES_TEXT`).  
- **Potřebuji licenci pro testování?** Ne, z webu Aspose je k dispozici bezplatná zkušební verze.  
- **Mohu získat poznámky ve formátu RTF?** Ano, použijte `Asn.NOTES_RTF`.  
- **Je to kompatibilní se všemi Java IDE?** Rozhodně – IntelliJ IDEA, Eclipse, NetBeans atd.  

## Co je přidání poznámek k přiřazení zdroje?
Přidání poznámek znamená připojení popisného textu – buď prostého textu, nebo formátovaného textu (RTF) – k propojení mezi úkolem a zdrojem. Tato funkce umožňuje projektovým manažerům vložit kontext, speciální instrukce nebo komentáře ke změnám přímo do přiřazení, což zajišťuje, že kdokoli, kdo rozvrh kontroluje, okamžitě pochopí „proč“ každého přiřazení.

## Proč přidávat poznámky?
Přidání poznámek vytváří okamžitý komunikační kanál uvnitř projektového souboru. Odstraňuje potřebu externích tabulek nebo e‑mailových vláken, poskytuje vestavěnou stopu auditu a díky podpoře RTF vám umožňuje zdůraznit důležité informace tučným nebo kurzívním stylem – vše bez opuštění prostředí řízení projektů.

## Požadavky
1. **Java Development Kit (JDK)** – version 8 nebo vyšší, správně nakonfigurovaný na vašem počítači.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR z [oficiální web](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, nebo jakýkoli Java‑kompatibilní editor, který preferujete.  

## Import balíčků
Začněte importováním potřebných balíčků do vašeho Java projektu:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## Jak přidat poznámky k přiřazení zdroje
V této sekci projdeme kompletní postup pro připojení poznámek k přiřazení zdroje. Začínáme nastavením adresáře s daty, načtením projektu, získáním příslušného úkolu a zdroje, vytvořením přiřazení a nakonec nastavením a zobrazením poznámek v prostém textu i RTF, přičemž každý krok je ilustrován zástupnými kódy, které můžete nahradit originálními úryvky.

### Krok 1: Nastavit adresář s daty
Nastavte cestu k vašemu adresáři s daty, kde jsou umístěny soubory projektu.
```java
String dataDir = "Your Data Directory";
```

### Krok 2: Načíst soubor projektu
Načtěte soubor projektu do vaší Java aplikace.
```java
Project prj = new Project(dataDir + "UpdateResourceAssignment.mpp");
```

### Krok 3: Získat úkol a zdroj
Získejte úkol a zdroj, ke kterému chcete přidat poznámky.
```java
Task task = prj.getRootTask().getChildren().getById(1);
Resource rsc = prj.getResources().getById(1);
```

### Krok 4: Vytvořit přiřazení zdroje
Vytvořte přiřazení zdroje pro úkol a zdroj.
```java
ResourceAssignment assn = prj.getResourceAssignments().add(task, rsc);
```

### Krok 5: Nastavit poznámky
Nastavte poznámky pro přiřazení zdroje.
```java
assn.set(Asn.NOTES_TEXT, "Newly added assignment");
```

### Krok 6: Zobrazit poznámky
Zobrazte text poznámek a formát RTF.
```java
System.out.println("Notes text: " + assn.get(Asn.NOTES_TEXT));
System.out.println("Notes RTF: " + assn.get(Asn.NOTES_RTF));
```

### Krok 7: Dokončení procesu
Vytiskněte úspěšnou zprávu indikující dokončení procesu.
```java
System.out.println("Process completed Successfully");
```

## Co je třída Asn?
Třída `Asn` definuje konstanty, které představují pole přiřazení zdroje, jako jsou poznámky, náklady a práce. Tyto konstanty používáte s metodami `set` a `get` na objektu `ResourceAssignment` pro čtení nebo zápis odpovídajících dat. Například `Asn.NOTES_TEXT` ukládá poznámky v prostém textu, zatímco `Asn.NOTES_RTF` obsahuje verzi ve formátu RTF.

## Časté problémy a řešení
- **NullPointerException při získávání úkolu/zdroje:** Ověřte, že ID (`1` v příkladu) skutečně existují ve vašem souboru `.mpp`.  
- **Poznámky se nezobrazují v UI:** Ujistěte se, že zobrazujete panel poznámek přiřazení v Microsoft Project nebo jiném prohlížeči, který podporuje poznámky přiřazení.  
- **Výstup RTF vypadá prázdně:** API vrací RTF pouze pokud poznámky obsahují formátování RTF; prostý text povede k prázdnému řetězci RTF.  

## Často kladené otázky
**Q: Mohu upravit poznámky po jejich nastavení?**  
A: Ano, jednoduše znovu zavolejte `assn.set(Asn.NOTES_TEXT, "Updated note")` s novým obsahem.

**Q: Jsou poznámky uloženy v souboru .mpp?**  
A: Ano. Když uložíte objekt `Project`, poznámky se stanou součástí dat přiřazení uvnitř souboru.

**Q: Funguje to s šifrovanými soubory projektu?**  
A: Musíte otevřít projekt se správným heslem pomocí vhodného přetížení konstruktoru `Project` před přístupem k přiřazením.

**Q: Existuje limit délky poznámky?**  
A: Prakticky mohou být poznámky několik kilobajtů dlouhé; extrémně velké poznámky mohou ovlivnit výkon při načítání projektu.

**Q: Mohu přidat poznámky k více přiřazením ve smyčce?**  
A: Ano, iterujte přes `prj.getResourceAssignments()` a nastavte `Asn.NOTES_TEXT` pro každé přiřazení podle potřeby.

## Závěr
Po provedení těchto kroků nyní víte **jak přidat poznámky k přiřazením zdrojů** pomocí Aspose.Tasks pro Java. Využití poznámek zdrojů v Aspose.Tasks zlepšuje přehlednost projektu, vytváří vestavěnou stopu auditu a umožňuje vkládat formátované komentáře bez opuštění souboru rozvrhu. Prozkoumejte další funkce API, jako jsou hromadné aktualizace, vlastní pole a integrace s vašimi stávajícími pipeline pro řízení projektů.

---

**Poslední aktualizace:** 2026-07-19  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Přidat zdroj do projektu pomocí Aspose.Tasks pro Java](/tasks/java/resource-management/create-resources/)
- [Jak přidat zdroj do projektu a spravovat vlastnosti zpoždění vyrovnání v Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)
- [Jak zastavit přiřazení a obnovit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}