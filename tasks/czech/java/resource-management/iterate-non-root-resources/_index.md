---
date: 2026-01-13
description: Naučte se, jak iterovat nekořenové zdroje v souborech Microsoft Project
  pomocí Aspose.Tasks pro Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Iterovat nekořenové zdroje pomocí Aspose.Tasks pro Javu
url: /cs/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Iterovat ne‑kořenové zdroje pomocí Aspose.Tasks pro Java

## Úvod
Aspose.Tasks for Java je výkonná knihovna, která vývojářům poskytuje čistý, objektově orientovaný způsob práce se soubory Microsoft Project. V tomto tutoriálu se naučíte **jak iterovat ne‑kořenové zdroje**, abyste mohli číst, upravovat nebo analyzovat data zdrojů, aniž byste se museli zabývat kořenovým zástupcem. Ať už vytváříte nástroj pro reportování, migrační skript nebo vlastní plánovač, zvládnutí této techniky učiní váš kód přesnějším a efektivnějším.

## Rychlé odpovědi
- **Co znamená „ne‑kořenový zdroj“?** Zdroj, který není výchozí zástupce „Project“ (kořenový uzel).  
- **Proč filtrovat kořenový zdroj?** Kořen neobsahuje užitečná data pro plánování a může zahlcovat zprávy.  
- **Která třída Aspose.Tasks poskytuje kolekci zdrojů?** `Project.getResources()`.  
- **Potřebuji licenci pro tento kód?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Mohu to použít s Java 17?** Ano – Aspose.Tasks podporuje Java 8 a novější.

## Předpoklady
Předtím, než se pustíte do kódu, se ujistěte, že máte:

1. **Java Development Kit (JDK)** – Nainstalujte nejnovější JDK z [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java library** – Stáhněte nejnovější JAR ze [download page](https://releases.aspose.com/tasks/java/).  

## Importovat balíčky
Ve svém Java projektu importujte potřebné třídy Aspose.Tasks:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Krok 1: Nastavení adresáře s daty
```java
String dataDir = "Your Data Directory";
```
Nahraďte `"Your Data Directory"` absolutní cestou, kde se nacházejí vaše soubory `.mpp`.

## Krok 2: Načtení souboru projektu
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Tím se vytvoří instance `Project` načtením **ResourceCosts.mpp** z adresáře, který jste určili.

## Krok 3: Iterace přes ne‑kořenové zdroje
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Smyčka prochází každý objekt `Resource` v projektu. Kontrola `isRoot()` přeskočí vestavěný kořenový zdroj a příkaz `System.out.println` vypíše název každého **ne‑kořenového zdroje**.

## Jak iterovat ne‑kořenové zdroje
Ukázka výše demonstruje základní vzor:

1. Získejte celou kolekci pomocí `prj.getResources()`.  
2. Použijte `isRoot()` k odfiltrování zástupce.  
3. Přistupujte k libovolnému poli zdroje (např. `Rsc.NAME`, `Rsc.COST`) podle potřeby.

## Časté úskalí a tipy
- **Kontroly na null** – Některé zdroje mohou mít volitelná pole; vždy se chraňte před `null` při volání `get()`.  
- **Výkon** – U velmi velkých projektů zvažte iteraci pomocí smyčky s indexem, abyste se vyhnuli vytváření mezikolekcí.  
- **Licencování** – Spuštění kódu bez platné licence přidá vodoznak do exportovaných souborů; licenci aktivujte co nejdříve v aplikaci.

## Závěr
Po absolvování těchto kroků nyní víte **jak iterovat ne‑kořenové zdroje** pomocí Aspose.Tasks pro Java. Tato technika vám pomůže soustředit se na skutečné zdroje projektu, vyčistit extrahovaná data a vytvořit spolehlivější řešení pro řízení projektů.

## Často kladené otázky
### Můžu použít Aspose.Tasks pro Java k vytvoření nových souborů projektu?
Ano, Aspose.Tasks poskytuje kompletní CRUD (Create, Read, Update, Delete) funkce pro formáty MPP, MPT a XML.

### Podporuje Aspose.Tasks všechny verze souborů Microsoft Project?
Rozhodně. Zpracovává soubory Project 2003‑2019, včetně nejnovějších specifikací MPP.

### Je Aspose.Tasks kompatibilní s Java frameworky jako Spring?
Ano, knihovnu můžete injektovat do Spring beanů nebo použít v jakékoli standardní Java aplikaci.

### Můžu přizpůsobit pole dat projektu pomocí Aspose.Tasks?
Určitě. API vám umožní přidávat, upravovat nebo mazat vlastní pole u úkolů, zdrojů i přiřazení.

### Poskytuje Aspose.Tasks podporu a dokumentaci pro vývojáře?
Produkt zahrnuje rozsáhlou API dokumentaci, ukázkové kódy a vyhrazené fórum podpory pro rychlou pomoc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-13  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose