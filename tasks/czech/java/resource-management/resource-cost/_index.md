---
date: 2026-01-15
description: Naučte se pracovat s rozpočtovanými náklady na práci naplánovanými v
  souborech Microsoft Project pomocí Aspose.Tasks pro Javu. Postupujte podle našeho
  krok‑za‑krokem průvodce.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Plánovaná práce s rozpočtovanými náklady pomocí Aspose.Tasks pro Javu
url: /cs/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Plánovaná rozpočtová cena práce (BCWS) s Aspose.Tasks for Java

## Úvod

Správa **budgeted cost work scheduled** (BCWS) je nezbytná pro udržení projektu na správné cestě a zajištění, že finanční prognóza odpovídá plánované práci. V Microsoft Project představuje BCWS částku peněz, která měla být do určitého data vynaložena na naplánovanou práci. Aspose.Tasks for Java vám poskytuje úplnou programovou kontrolu nad těmito hodnotami, umožňuje číst, upravovat a reportovat náklady zdrojů, aniž byste museli ručně otevírat soubor .mpp. V tomto tutoriálu projdeme kompletním příkladem, který ukazuje, jak načíst projekt, iterovat přes jeho zdroje a zobrazit plánovanou rozpočtovou cenu práce spolu s dalšími klíčovými nákladovými metrikami.

## Rychlé odpovědi
- **Co znamená BCWS?** Budgeted Cost Work Scheduled – plánovaná cena za práci naplánovanou k datu.  
- **Která vlastnost API získává BCWS?** `Rsc.BCWS` na objektu `Resource`.  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební licence funguje pro testování; pro produkci je vyžadována plná licence.  
- **Mohu upravit hodnoty BCWS?** Ano, můžete nastavit `Rsc.BCWS` stejně jako jakékoli jiné číselné pole.  
- **Podporované verze Projectu?** Všechny verze Microsoft Project od roku 2000 po nejnovější formát .mpp.

## Co je plánovaná rozpočtová cena práce (BCWS)?

**Budgeted Cost Work Scheduled (BCWS)** je měřítko výkonnosti, které odráží náklady, které měly být vynaloženy na práci naplánovanou do daného okamžiku. Jedná se o základní prvek Earned Value Management (EVM) a pomáhá projektovým manažerům porovnávat plánované a skutečné výdaje.

## Požadavky

1. Pevné základy jazyka Java.  
2. Přidání Aspose.Tasks for Java do vašeho projektu (Maven/Gradle nebo JAR).  
3. Soubor Microsoft Project (`.mpp`) obsahující zdroje s nákladovými údaji (např. *ResourceCosts.mpp*).

## Import balíčků

Nejprve importujte třídy Aspose.Tasks potřebné pro práci s projekty a zdroji:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Krok 1: Definujte adresář s daty

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní nebo relativní cestou, kde se nachází *ResourceCosts.mpp*.

## Krok 2: Načtěte soubor MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Konstruktor `Project` načte soubor .mpp a vytvoří v‑paměti reprezentaci, kterou můžete dotazovat.

## Krok 3: Procházejte zdroje

```java
for (Resource res : prj.getResources()) {
```

Tato smyčka prochází každý zdroj definovaný v projektu a poskytuje vám přístup k jeho nákladovým polím.

## Krok 4: Zkontrolujte název zdroje a náklady

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Uvnitř bloku `if` provádíme:

* Vytiskne **celkové náklady** (`Rsc.COST`).  
* Vytiskne **skutečné náklady na vykonanou práci** (`Rsc.ACWP`).  
* Vytiskne **plánovanou rozpočtovou cenu práce (BCWS)** (`Rsc.BCWS`) – hlavní metrika, na kterou se zaměřujeme.  
* Vytiskne **plánovanou rozpočtovou cenu vykonané práce (BCWP)** (`Rsc.BCWP`).

Tyto čtyři hodnoty vám poskytnou rychlý přehled o finanční situaci projektu.

## Proč je důležité sledovat plánovanou rozpočtovou cenu práce (BCWS)

* **Včasné varování:** Pokud je BCWS výrazně vyšší než skutečné náklady, můžete přetěžovat zdroje.  
* **Analýza Earned Value:** BCWS je klíčovým vstupem pro výpočet odchylky nákladů (CV) a odchylky harmonogramu (SV).  
* **Forecasting (Předpověď):** Přesná data BCWS pomáhají předpovídat budoucí potřeby cash‑flow a informují zprávy pro zainteresované strany.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| `null` vytištěno pro BCWS | Zdroj nemá definovanou tabulku sazeb nákladů | Definujte tabulku sazeb nákladů pro zdroj v Microsoft Project nebo ji nastavte programově pomocí `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` při iteraci zdrojů | Soubor projektu je poškozený nebo obsahuje prázdné záznamy zdrojů | Ověřte soubor .mpp v Microsoft Project a odstraňte prázdné zdroje |
| Neočekávané hodnoty (např. záporné BCWS) | Vlastní pole přepisují standardní nákladová pole | Ujistěte se, že přistupujete ke standardnímu `Rsc.BCWS` a ne k vlastnímu poli se stejným názvem |

## Často kladené otázky

**Q: Mohu upravit hodnotu BCWS programově?**  
A: Ano. Použijte `res.set(Rsc.BCWS, newValue)` a poté projekt uložte pomocí `prj.save("Updated.mpp")`.

**Q: Podporuje Aspose.Tasks projekty s více měnami?**  
A: Rozhodně. Nákladová pole respektují nastavení měny definovaná v souboru projektu.

**Q: Existuje způsob, jak exportovat tyto nákladové metriky do CSV?**  
A: Můžete iterovat přes zdroje a zapisovat hodnoty do `StringBuilder` nebo použít knihovnu pro CSV k vygenerování souboru.

**Q: Jak se BCWS liší od BCWP?**  
A: BCWS je plánovaná cena za naplánovanou práci, zatímco BCWP (Budgeted Cost Work Performed) odráží plánovanou cenu za práci, která byla skutečně dokončena.

**Q: Potřebuji speciální licenci pro čtení nákladových dat?**  
A: Zkušební licence poskytuje plný přístup ke čtení i zápisu; pro produkční nasazení je vyžadována komerční licence.

## Závěr

Využitím Aspose.Tasks for Java získáte přesný programový přístup k **budgeted cost work scheduled** a dalším důležitým nákladovým metrikám. To vám umožní vytvářet vlastní dashboardy, automatizovat zprávy Earned Value a udržet projekty finančně na správné cestě – vše bez ručního zásahu do Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-15  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose