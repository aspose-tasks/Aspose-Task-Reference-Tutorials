---
date: 2026-01-13
description: Naučte se, jak vytvořit vlastní atribut, načíst soubor Microsoft Project,
  nastavit číselnou hodnotu v Javě a uložit projekt jako XML pomocí Aspose.Tasks pro
  Javu.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak vytvořit vlastní atribut v MS Project pomocí Aspose.Tasks
url: /cs/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit vlastní atribut v MS Project pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu **se dozvíte, jak vytvořit vlastní atribut** pro zdroje v souboru Microsoft Project pomocí Aspose.Tasks pro Java. Provedeme vás načtením souboru Microsoft Project, definováním nového číselného atributu, přiřazením hodnoty a nakonec uložením projektu jako XML. Na konci budete mít jasný praktický příklad, který můžete přizpůsobit svým řešením pro řízení projektů.

## Rychlé odpovědi
- **Co znamená „custom attribute“?**  
  Uživatelem definované pole, které ukládá další informace (např. Age, Skill Level) pro zdroj nebo úkol.  
- **Která knihovna to řeší?**  
  Aspose.Tasks for Java poskytuje plynulé API pro vytváření a správu custom attributes.  
- **Potřebuji licenci?**  
  Bezplatná dočasná licence funguje pro hodnocení; pro produkci je vyžadována plná licence.  
- **Mohu nastavit číselné hodnoty?**  
  Ano – použijte `setNumericValue` s `BigDecimal` (např. `30.5345`).  
- **Jak se projekt ukládá?**  
  Upravený soubor lze uložit jako XML pomocí `SaveFileFormat.Xml`.

## Co je custom attribute?
**Custom attribute** (také nazývaný rozšířený atribut) je další sloupec, který můžete přidat ke zdrojům nebo úkolům v Microsoft Project. Umožňuje zachytit data, která nejsou pokryta vestavěnými poli, jako je věk zaměstnance, úroveň certifikace nebo jakýkoli obchodně specifický ukazatel.

## Proč vytvořit custom attribute v MS Project?
- **Přizpůsobit data projektu** potřebám vaší organizace.  
- **Umožnit pokročilé reportování** ukládáním hodnot, které lze později dotazovat.  
- **Zachovat konzistenci** napříč více projekty programovým použitím stejné definice atributu.

## Předpoklady
Předtím, než začnete, ujistěte se, že máte:

1. **Java Development Environment** – nainstalovaný JDK 8 nebo vyšší.  
2. **Aspose.Tasks for Java** – Stáhněte nejnovější verzi z [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA nebo jakékoli Java‑kompatibilní IDE.  

## Průvodce krok za krokem

### Import balíčků
Nejprve importujte třídy Aspose.Tasks, které budete potřebovat. Ty poskytují základní funkčnost pro práci s projekty, zdroji a rozšířenými atributy.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Krok 1: Definovat adresář dat
Nastavte složku, kde se nachází váš zdrojový soubor projektu a kam bude zapisován výstup.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Načíst soubor Microsoft Project
Vytvořte instanci `Project` načtením existujícího souboru. Toto je krok **load Microsoft project file**, který vám poskytuje plný přístup k jeho obsahu.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Krok 3: Definovat custom attribute
Definujeme nový číselný atribut nazvaný **Age**. API kontroluje, zda definice již existuje; pokud ne, vytvoří ji.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Krok 4: Nastavit číselnou hodnotu v Javě
Vytvořte instanci atributu pro konkrétní zdroj a přiřaďte číselnou hodnotu pomocí `setNumericValue`. Toto ukazuje **set numeric value java** v praxi.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Krok 5: Přidat zdroj a připojit custom attribute
Přidejte nový zdroj pojmenovaný **R1** a připojte k němu dříve vytvořený custom attribute.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Krok 6: Uložit projekt jako XML
Nakonec uložte změny uložením projektu. Toto je krok **save project as xml**, který vytvoří čistou XML reprezentaci aktualizovaného souboru.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Krok 7: Zobrazit výsledek
Vytiskněte přátelské potvrzení, abyste věděli, že proces byl dokončen bez chyb.

```java
System.out.println("Process completed Successfully");
```

Podle těchto kroků jste úspěšně **vytvořili custom attribute**, načetli soubor Microsoft Project, nastavili číselnou hodnotu pomocí Javy a uložili projekt jako XML.

## Časté úskalí a tipy
- **Konflikty ID atributu:** Vždy před vytvořením nové definice zkontrolujte `getById`, abyste se vyhnuli duplicitním ID.  
- **Zpracování přesnosti:** `BigDecimal` zachovává desetinnou přesnost; vyhněte se používání `float` nebo `double` pro přesné hodnoty.  
- **Cesty k souborům:** Používejte absolutní cesty nebo nakonfigurujte pracovní adresář IDE, aby nedošlo k `FileNotFoundException`.  

## Často kladené otázky

**Q: Mohu vytvářet custom attributes i pro úkoly stejně jako pro zdroje?**  
A: Ano – při definování atributu použijte `ExtendedAttributeTask` místo `ExtendedAttributeResource`.

**Q: Je možné přidat více custom attributes najednou?**  
A: Rozhodně. Vytvořte samostatné objekty `ExtendedAttributeDefinition` pro každý atribut a připojte je k požadovaným zdrojům nebo úkolům.

**Q: V jakých formátech mohu projekt uložit?**  
A: Aspose.Tasks podporuje XML, MPP a několik dalších formátů jako PDF a HTML. V tomto příkladu jsme použili `SaveFileFormat.Xml`.

**Q: Potřebuji licenci pro Aspose.Tasks pro vývojové sestavy?**  
A: Dočasná licence stačí pro hodnocení. Pro produkční nasazení je vyžadována plná licence.

**Q: Jak mohu později načíst hodnoty custom attribute?**  
A: Použijte `resource.getExtendedAttributes()` k iteraci přes připojené atributy a získání jejich hodnot pomocí `getNumericValue()` nebo `getTextValue()`.

## Závěr
Vytvoření **custom attribute** v Microsoft Project pomocí Aspose.Tasks pro Java je jednoduché, jakmile pochopíte pracovní postup: načíst projekt, definovat atribut, nastavit jeho hodnotu, připojit jej ke zdroji a uložit soubor. Tento přístup vám umožní programově rozšířit datové modely projektu, což umožňuje bohatší reportování a těsnější integraci s vašimi obchodními procesy.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}