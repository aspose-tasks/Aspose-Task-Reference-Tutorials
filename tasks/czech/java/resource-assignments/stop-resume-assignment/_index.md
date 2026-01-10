---
date: 2026-01-10
description: Naučte se, jak zastavit přiřazení, spravovat přiřazení zdrojů a zobrazit
  příklad přiřazení zdroje v Aspose.Tasks pro Javu pomocí tohoto krok‑za‑krokem tutoriálu.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak zastavit přiřazení a obnovit přiřazení zdrojů v Aspose.Tasks
url: /cs/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zastavit přiřazení a obnovit přiřazení zdrojů v Aspose.Tasks

## Úvod
V tomto tutoriálu **objevíte, jak zastavit přiřazení** a později jej obnovit pomocí Aspose.Tasks pro Java. Aspose.Tasks je výkonné Java API, které vám umožní číst soubory projektů v Java formátech, manipulovat s daty Microsoft Project a spravovat přiřazení zdrojů bez nutnosti mít nainstalovaný Microsoft Project. Provedeme vás každým krokem, vysvětlíme, proč je každý řádek důležitý, a poskytneme praktické tipy, které můžete použít v reálných projektech.

## Rychlé odpovědi
- **Co znamená „stop assignment“?** Označuje přiřazení zdroje jako dočasně neaktivní od konkrétního data zastavení.  
- **Mohu později obnovit stejné přiřazení?** Ano, nastavením data obnovení u stejného přiřazení.  
- **Potřebuji Microsoft Project k použití tohoto API?** Ne, Aspose.Tasks funguje nezávisle na Microsoft Project.  
- **Jaká verze Javy je požadována?** Doporučuje se Java 8 nebo vyšší.  
- **Kde si mohu stáhnout knihovnu?** Na oficiální stránce ke stažení Aspose.Tasks Java.

## Co je „zastavení přiřazení“ v kontextu Aspose.Tasks?
Zastavení přiřazení říká plánovači, aby po **datumu zastavení** ignoroval práci přidělenou zdroji až do **data obnovení** (pokud je nastaveno). To je užitečné při řešení dovolených, odstávek zařízení nebo jakéhokoli období, kdy by zdroj neměl být považován za aktivní.

## Proč používat Aspose.Tasks pro správu přiřazení zdrojů?
- **Není potřeba Microsoft Project** – pracujte přímo se soubory .mpp.  
- **Plná kontrola nad daty** – můžete programově kontrolovat datum zastavení, datum obnovení a upravovat je.  
- **Cross‑platform** – běží na libovolném OS, který podporuje Javu.  
- **Bohaté API** – poskytuje *příklad přiřazení zdroje*, který můžete rozšířit pro vlastní reportování.

## Požadavky
- Java Development Kit (JDK) nainstalovaný ve vašem systému.  
- Knihovna Aspose.Tasks pro Java stažená. Můžete ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  
- Základní znalost programování v Javě.  

## Import balíčků
Nejprve importujeme potřebné balíčky do našeho Java projektu:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Krok 1: Načtení souboru projektu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Zde **načteme soubor projektu** ve formátu Java (`.mpp`) a vytvoříme objekt `Project`, který nám poskytuje přístup ke všem datům projektu, včetně přiřazení zdrojů.

## Krok 2: Procházení přiřazení zdrojů
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Nastavíme **minimální datum**, abychom odfiltrovali zástupná data, a poté projdeme každé přiřazení. Jedná se o typický *příklad přiřazení zdroje*, který se používá, když potřebujete přiřazení zkontrolovat nebo upravit.

## Krok 3: Kontrola dat zastavení a obnovení
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

V tomto bloku **kontrolujeme datum zastavení** a **datum obnovení** pro každé přiřazení. Pokud je datum před naším `minDate`, považujeme jej za nenastavené (`"NA"`); jinak vypíšeme skutečné datum. Tato logika je nezbytná pro **správnou správu přiřazení zdrojů**.

## Časté problémy a řešení
- **Null data** – `ra.get(Asn.STOP)` může vrátit `null`. Ochráníte to přidáním kontroly na null před voláním `.before(minDate)`.  
- **Nesprávná cesta k souboru** – Ujistěte se, že `dataDir` končí oddělovačem cesty (`/` nebo `\\`) vhodným pro váš OS.  
- **Neshoda verzí** – Použijte nejnovější verzi Aspose.Tasks pro Java, aby nedošlo k chybějícím hodnotám výčtu.

## Často kladené otázky
### Mohu používat Aspose.Tasks bez nainstalovaného Microsoft Project?
Ano, Aspose.Tasks vám umožní pracovat se soubory Microsoft Project, aniž byste potřebovali mít Microsoft Project nainstalovaný ve vašem systému.

### Kde najdu další dokumentaci?
Podrobnou dokumentaci najdete [zde](https://reference.aspose.com/tasks/java/).

### Je k dispozici bezplatná zkušební verze?
Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

### Jak mohu získat podporu, pokud narazím na problémy?
Podporu od komunity můžete získat [zde](https://forum.aspose.com/c/tasks/15).

### Mohu zakoupit dočasnou licenci?
Ano, dočasnou licenci můžete zakoupit [zde](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: Jak programově nastavit datum zastavení pro přiřazení?**  
A: Použijte `ra.set(Asn.STOP, yourDateObject);`, kde `yourDateObject` je `java.util.Date`.

**Q: Co se stane, pokud je datum obnovení dříve než datum zastavení?**  
A: API nevyžaduje chronologické pořadí; plánovač však bude považovat přiřazení za aktivní až po pozdějším z těchto dvou dat, takže byste měli data validovat sami.

**Q: Mohu filtrovat přiřazení pouze na ta, která mají nastavené datum zastavení?**  
A: Ano, projděte `prj.getResourceAssignments()` a zkontrolujte, že `ra.get(Asn.STOP) != null`.

**Q: Je možné odstranit datum zastavení po jeho nastavení?**  
A: Nastavte datum zastavení na `null` pomocí `ra.set(Asn.STOP, null);` a poté projekt uložte.

**Q: Podporuje Aspose.Tasks i další pole související s daty, jako je start, finish nebo actual start?**  
A: Rozhodně. Výčet `Asn` poskytuje konstanty pro všechna pole přiřazení, například `Asn.START`, `Asn.FINISH` a další.

## Závěr
Postupným sledováním těchto kroků nyní víte **jak zastavit přiřazení**, jak zkontrolovat data zastavení/obnovení a jak přiřazení v případě potřeby obnovit. Tato funkce vám umožní **přesněji spravovat přiřazení zdrojů**, zejména v situacích jako jsou dovolené zdrojů nebo odstávky zařízení. Neváhejte rozšířit příklad o aktualizaci dat, generování reportů nebo integraci s vaší vlastní logikou plánování.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}