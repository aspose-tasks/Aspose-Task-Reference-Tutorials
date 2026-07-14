---
date: 2026-07-14
description: Naučte se, jak zastavit resource assignment v Java, spravovat resource
  assignments a zobrazit příklady pomocí Aspose.Tasks pro Java v tomto krok‑za‑krokem
  průvodci.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Zastavit a obnovit Resource Assignments v Aspose.Tasks
og_description: Zastavte resource assignment v Java s Aspose.Tasks. Tento tutoriál
  ukazuje, jak pozastavit a obnovit přiřazení, pracovat s daty a integrovat API bez
  Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Zastavit Resource Assignment v Java – Průvodce Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Jak zastavit Resource Assignment v Java – Pokračovat s Aspose.Tasks
url: /cs/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zastavit přiřazení zdroje v Javě – obnovení pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíte **how to stop resource assignment java** a později jej obnovit pomocí Aspose.Tasks pro Javu. Aspose.Tasks je robustní Java API, které vám umožní číst a zapisovat soubory Microsoft Project, manipulovat s harmonogramy a řídit přiřazení zdrojů — vše bez nutnosti mít nainstalovaný Microsoft Project. Provedeme vás každým krokem, vysvětlíme, proč je každý řádek důležitý, a podělíme se o praktické tipy, které můžete použít v reálných projektových plánech.

## Rychlé odpovědi
- **What does “stop assignment” mean?** Označuje přiřazení zdroje jako dočasně neaktivní od konkrétního data zastavení.  
- **Can I resume the same assignment later?** Ano, nastavením data obnovení na stejném přiřazení.  
- **Do I need Microsoft Project to use this API?** Ne, Aspose.Tasks funguje nezávisle na Microsoft Project.  
- **Which Java version is required?** Doporučuje se Java 8 nebo novější.  
- **Where can I download the library?** Na oficiální stránce pro stažení Aspose.Tasks Java.

## Jak zastavit přiřazení zdroje v Javě?
Načtěte svůj projekt, najděte cílové `ResourceAssignment`, nastavte datum `STOP`, případně nastavte datum `RESUME` a poté soubor uložte. Tento postup pozastaví práci na zadané období a automaticky ji po datu obnovení znovu aktivuje, což vám poskytuje přesnou kontrolu nad kalendáři zdrojů bez ručních úprav souboru.

## Co znamená „how to stop assignment“ v kontextu Aspose.Tasks?
Zastavení přiřazení říká plánovači, aby ignoroval práci přidělenou zdroji po **stop date** až do **resume date** (pokud je zadáno). To je užitečné při řešení dovolených, výpadků zařízení nebo jakéhokoli období, kdy by zdroj neměl být považován za aktivní.

## Proč používat Aspose.Tasks pro správu přiřazení zdrojů?
Aspose.Tasks vám umožňuje programově řídit data přiřazení, čímž eliminuje ruční úpravy a snižuje riziko chyb. Podporuje **50+ vstupních a výstupních formátů** a dokáže zpracovat projekty s **až 10 000 úkoly**, přičemž spotřeba paměti zůstává pod 200 MB, protože data streamuje místo načítání celého souboru do paměti. API běží na jakémkoli OS, který podporuje Javu, a poskytuje tak multiplatformní flexibilitu.

## Požadavky
Než začneme, ujistěte se, že máte:

- Java Development Kit (JDK) 8 nebo novější nainstalovaný.  
- Staženou knihovnu Aspose.Tasks pro Javu. Můžete ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  
- Základní znalosti programování v Javě.  

## Import balíčků
Třídy `Project`, `ResourceAssignment` a `Asn` se nacházejí v namespace `com.aspose.tasks`. Importujte je na začátku svého zdrojového souboru:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Krok 1: Načíst soubor projektu
Třída `Project` je nejvyšší objekt Aspose.Tasks, který v paměti představuje jeden soubor Microsoft Project. Vytvořením instance načtete soubor a získáte přístup k úkolům, zdrojům a přiřazením.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Krok 2: Procházet přiřazení zdrojů
Objekty `ResourceAssignment` odhalují všechna pole související s přiřazením. Nastavíme **minimum date**, abychom odfiltrovali zástupné datumy, a poté projdeme každé přiřazení. Tento vzor je standardním *resource assignment example* pro inspekci nebo úpravu.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Krok 3: Zkontrolovat data STOP a RESUME
V tomto bloku zkoumáme pole `STOP` a `RESUME` u každého přiřazení. Pokud je datum před naším `minDate`, považujeme jej za nenastavené (`"NA"`); jinak vypíšeme skutečné datum. Tato logika je nezbytná pro **manage resource assignments** správně.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Časté problémy a řešení
- **Null dates** – `ra.get(Asn.STOP)` může vrátit `null`. Ochráníte se tím, že před voláním `.before(minDate)` přidáte kontrolu na null.  
- **Incorrect file path** – Ujistěte se, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) vhodným pro váš OS.  
- **Version mismatch** – Použijte nejnovější verzi Aspose.Tasks pro Javu, abyste se vyhnuli chybějícím hodnotám enumu.

## Často kladené otázky

**Q: How do I programmatically set a stop date for an assignment?**  
A: Použijte `ra.set(Asn.STOP, yourDateObject);`, kde `yourDateObject` je `java.util.Date`.

**Q: What happens if the resume date is earlier than the stop date?**  
A: API nevyžaduje chronologické pořadí; plánovač však bude považovat přiřazení za aktivní až po pozdějším z těchto dvou dat, takže byste měli data ověřit sami.

**Q: Can I filter assignments to only those that have a stop date set?**  
A: Ano, projděte `prj.getResourceAssignments()` a zkontrolujte `ra.get(Asn.STOP) != null`.

**Q: Is it possible to remove a stop date once set?**  
A: Nastavte datum STOP na `null` pomocí `ra.set(Asn.STOP, null);` a poté projekt uložte.

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: Rozhodně. Enum `Asn` poskytuje konstanty pro všechna pole přiřazení, například `Asn.START`, `Asn.FINISH` a další.

## Závěr
Po provedení těchto kroků nyní víte **how to stop resource assignment java**, můžete kontrolovat data STOP/RESUME a při potřebě přiřazení obnovit. Tato funkce vám umožní **manage resource assignments** přesněji, zejména v situacích jako dovolené zdrojů nebo výpadky zařízení. Neváhejte rozšířit příklad o aktualizaci dat, generování reportů nebo integraci s vaší vlastní logikou plánování.

---

**Poslední aktualizace:** 2026-07-14  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Jak vypočítat odchylku nákladů a spravovat náklady přiřazení s Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Jak přidat poznámky k přiřazením zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}