---
date: 2026-06-10
description: Naučte se, jak vytvořit rozšířený atribut v Javě, načíst soubor Microsoft
  Project, nastavit číselné hodnoty a uložit projekt jako XML pomocí Aspose.Tasks
  pro Javu.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Práce s rozšířenými atributy zdrojů v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak vytvořit rozšířený atribut v Javě s Aspose.Tasks
url: /cs/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit rozšířený atribut v Javě pomocí Aspose.Tasks

## Úvod
V tomto praktickém průvodci **vytvoříte rozšířený atribut v Javě** pro soubor Microsoft Project pomocí Aspose.Tasks. Provedeme vás načtením existujícího projektu, definováním nového číselného atributu, přiřazením hodnoty ke zdroji a nakonec uložením změn jako XML souboru. Na konci budete mít znovupoužitelný kódový vzor, který lze vložit do jakéhokoli řešení pro řízení projektů založeného na Javě.

## Rychlé odpovědi
- **Co je rozšířený atribut?**  
  Uživatelem definované pole (např. Věk, Úroveň dovedností), které ukládá dodatečná data pro zdroje nebo úkoly.  
- **Které API jej vytváří?**  
  Aspose.Tasks for Java poskytuje třídu `ExtendedAttributeDefinition` pro definování a správu vlastních atributů.  
- **Potřebuji licenci?**  
  Dočasná evaluační licence funguje pro vývoj; plná licence je vyžadována pro produkční nasazení.  
- **Mohu ukládat čísla?**  
  Ano – použijte `setNumericValue(BigDecimal)` pro přiřazení přesných desetinných hodnot.  
- **Jak změny uložit?**  
  Zavolejte `project.save("output.xml", SaveFileFormat.Xml)` pro zápis aktualizovaného projektu ve formátu XML.

## Co je vlastní atribut?
**Vlastní atribut** (také známý jako rozšířený atribut) je další sloupec, který můžete přidat ke zdrojům nebo úkolům v Microsoft Project. Umožňuje zachytit data, která nejsou pokryta vestavěnými poli, jako je věk zaměstnance, úroveň certifikace nebo jakýkoli obchodně specifický ukazatel.

## Proč vytvořit rozšířený atribut v Javě?
Vytvoření rozšířeného atributu v Javě vám umožní programově obohatit projektová data, zajistit konzistenci napříč soubory a umožnit automatizované reportování. Definováním atributu jednou jej můžete použít na libovolný počet zdrojů nebo úkolů bez ručního zadávání, což šetří čas a snižuje chyby.

- **Přizpůsobte data své organizaci** – uložte jakýkoli metrický údaj, který je pro vás důležitý, bez ručních řešení v Excelu.  
- **Umožněte bohatší reportování** – později dotazujte vlastní pole pro dashboardy nebo analytiku.  
- **Udržujte konzistenci** – programově aplikujte stejnou definici napříč desítkami projektů, čímž eliminujete lidské chyby.  
- **Testováno na výkon** – Aspose.Tasks zpracovává projekty až s 10 000 úkoly a 5 000 zdroji, aniž by načítalo celý soubor do paměti, podle benchmarků produktu.

## Požadavky
1. **Java Development Kit** – nainstalovaný JDK 8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější verzi z [zde](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA nebo jakékoli Java‑kompatibilní vývojové prostředí.  

## Jak vytvořit rozšířený atribut v Javě?
Načtěte svůj projekt, definujte atribut, přiřaďte jej ke zdroji a uložte soubor – vše během několika jednoduchých kroků. Následující sekce rozdělují každý krok na stručné vysvětlení a místo, kde bude váš skutečný kód.

### Průvodce krok za krokem

#### Import balíčků
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` a související třídy se nacházejí v namespace `com.aspose.tasks`. Importujte je na začátku svého Java souboru.

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

#### Krok 1: Definovat datový adresář
`Paths` je pomocná třída, která poskytuje metody pro získání cesty v souborovém systému nezávisle na platformě.

```java
String dataDir = "Your Data Directory";
```

#### Krok 2: Načíst soubor Microsoft Project
`Project` představuje soubor Microsoft Project v paměti a umožňuje čtení i zápis jeho obsahu.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Krok 3: Definovat vlastní atribut
`ExtendedAttributeDefinition` definuje schéma nového vlastního pole, které může být přiřazeno ke zdrojům nebo úkolům.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Krok 4: Nastavit číselnou hodnotu v Javě
`ExtendedAttributeResource` obsahuje hodnotu vlastního atributu pro konkrétní instanci zdroje.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Krok 5: Přidat zdroj a přiřadit vlastní atribut
`Resource` modeluje projektový zdroj, jako je osoba, vybavení nebo materiál.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Krok 6: Uložit projekt jako XML
`SaveFileFormat` vyjmenovává podporované výstupní formáty pro ukládání projektu, včetně XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Krok 7: Zobrazit výsledek
`System.out.println` vypíše řádek textu na standardní výstup konzole.

```java
System.out.println("Process completed Successfully");
```

## Časté úskalí a tipy
- **Konflikty ID atributu:** Vždy zavolejte `project.getExtendedAttributes().getById(id)` před vytvořením nové definice, aby se předešlo duplicitním identifikátorům.  
- **Zpracování přesnosti:** Upřednostněte `BigDecimal` před `float`/`double` pro přesné číselné hodnoty; tím se zabrání zaokrouhlovacím chybám v reportování.  
- **Spolehlivost cesty k souboru:** Použijte `Paths.get(...).toAbsolutePath()` nebo nakonfigurujte pracovní adresář IDE, aby se eliminovala `FileNotFoundException`.  

## Často kladené otázky

**Q: Mohu vytvářet vlastní atributy jak pro úkoly, tak pro zdroje?**  
A: Ano – použijte `ExtendedAttributeTask` místo `ExtendedAttributeResource` při definování schématu atributu.

**Q: Je možné přidat více vlastních atributů najednou?**  
A: Ano. Vytvořte samostatné objekty `ExtendedAttributeDefinition` pro každý atribut a přiřaďte je požadovaným zdrojům nebo úkolům.

**Q: Do jakých formátů mohu projekt uložit?**  
A: Aspose.Tasks podporuje XML, MPP, PDF, HTML a více než 30 dalších formátů. V tomto příkladu jsme použili `SaveFileFormat.Xml`.

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Dočasná evaluační licence stačí pro testování. Pro jakékoli produkční nasazení je vyžadována plná komerční licence.

**Q: Jak později načíst hodnoty vlastních atributů?**  
A: Zavolejte `resource.getExtendedAttributes()` a iterujte přes kolekci; získáte uloženou hodnotu pomocí `getNumericValue()` nebo `getTextValue()`.

---

**Poslední aktualizace:** 2026-06-10  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit zdroje – Správa zdrojů s Aspose.Tasks pro Java](/tasks/java/resource-management/)
- [Vytvořit vlastní pole Aspose – Práce s rozšířenými atributy](/tasks/java/project-management/extended-attributes/)
- [Jak vytvořit projekt – Nastavit nové atributy úkolů s Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}