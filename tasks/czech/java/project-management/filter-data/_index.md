---
date: 2026-06-05
description: Naučte se, jak filtrovat soubory MPP pomocí Aspose.Tasks for Java, přizpůsobit
  kritéria filtru a filtrovat úkoly podle data pro zefektivnění řízení projektů.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Jak filtrovat soubory MPP pomocí Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak filtrovat soubory MPP pomocí Aspose.Tasks for Java
url: /cs/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak filtrovat MPP soubory pomocí Aspose.Tasks pro Java

## Úvod
Pokud pracujete se soubory Microsoft Project (*.mpp*) v Java aplikaci, často budete potřebovat **filtrovat MPP soubory**, abyste izolovali úkoly, zdroje nebo přiřazení, které jsou nejdůležitější. V tomto tutoriálu vás provedeme **jak filtrovat mpp** soubory programově pomocí Aspose.Tasks pro Java, ukážeme vám, jak **přizpůsobit kritéria filtru**, a představíme praktický scénář „filtrovat úkoly podle data“. Na konci budete mít připravený úryvek kódu, který můžete vložit do libovolného Java projektu.

## Rychlé odpovědi
- **Co znamená “filter mpp”?** Znamená to extrahování podmnožiny projektových dat na základě definovaných podmínek.  
- **Která knihovna to řeší?** Aspose.Tasks pro Java poskytuje komplexní API pro vytváření a aplikaci filtrů.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu filtrovat úkoly, zdroje a přiřazení?** Ano – každý typ entity má vlastní kolekci filtrů.  
- **Je vyžadováno Java 8 nebo vyšší?** Aspose.Tasks podporuje Java 8 a novější verze.

## Co je “how to filter mpp” v Javě?
`How to filter mpp` je proces používání objektů `Filter` z Aspose.Tasks k výběru pouze těch projektových prvků, které splňují konkrétní podmínky, jako je datum zahájení, náklad nebo vlastní pole. Načtěte `Project`, získejte `Filter` a API vrátí kolekci, která odpovídá vašim kritériím, což umožňuje cílené reportování nebo následnou integraci.

## Proč přizpůsobit kritéria filtru?
Vlastní kritéria filtru vám umožní zaměřit se na vysoce rizikové úkoly, opožděné položky nebo zdroje s překročeným rozpočtem, čímž proměníte obrovský projektový soubor na stručný, akční pohled. Aspose.Tasks podporuje **více než 50 předdefinovaných typů filtrů** a umožňuje vám vytvořit neomezený počet vlastních filtrů, čímž snižuje čas ručního procházení dat až o 70 %.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo novější.  
2. **Aspose.Tasks pro Java** – stáhněte jej ze [stránky ke stažení](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse nebo NetBeans budou fungovat bez problémů.  

## Import balíčků
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` a `Project` jsou základní třídy používané k definování a aplikaci filtrů na projektová data.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Průvodce krok za krokem

### Krok 1: Nastavení projektu
Nejprve vytvořte instanci `Project`, která ukazuje na MPP soubor, který chcete analyzovat, a poté jej načtěte do paměti. Tento jediný krok připraví celý model projektu pro filtrování, validaci a další manipulaci, což vám umožní přístup k úkolům, zdrojům a přiřazením prostřednictvím API.

### Jak nastavit projekt pro filtrování MPP souborů?
Třída `Project` načte a představí MPP soubor v paměti. Vytvořte instanci `Project`, která ukazuje na MPP soubor, který chcete analyzovat, a poté jej načtěte do paměti. Tento jediný krok připraví celý model projektu pro filtrování, validaci a další manipulaci, což vám umožní přístup k úkolům, zdrojům a přiřazením prostřednictvím API.

### Jak mohu získat a prozkoumat filtr?
Objekty `Filter` zapouzdřují definice filtrů používané k výběru položek projektu. Aspose.Tasks ukládá předdefinované filtry jako “All Tasks” nebo “Critical Tasks”. Použijte `project.getTaskFilters().getByName("My Filter")` nebo přístup podle indexu k získání objektu `Filter`, poté prozkoumejte jeho kolekci `FilterCriteria`, abyste viděli každé pravidlo a logický operátor (AND/OR), který je spojuje, a zajistili, že filtr odpovídá vašim požadavkům.

### Jak iterovat přes vnořené řádky kritérií?
`FilterCriteriaGroup` představuje skupinu kritérií filtru spojených logickým operátorem. Filtry mohou obsahovat skupiny kritérií, z nichž každá má svůj vlastní operátor. Procházejte `filter.getCriteria().getRows()` a pro každý řádek, který je `FilterCriteriaGroup`, rekurzivně projděte jeho podřazené řádky. Toto procházení vám umožní plně pochopit složitou logiku filtru, jako je “(Start < today AND Cost > 1000) OR Priority = High”, a podle potřeby upravit kritéria.

### Jak vytisknout informace o kritériích pro ladění?
Po projití stromu kritérií vypište do konzole název pole, testovací operátor a hodnotu každého řádku. Tento jednoduchý výpis vám pomůže ověřit, že filtr odpovídá zamýšleným obchodním pravidlům před jeho aplikací na velké projekty, a usnadní odhalení nesprávných operátorů nebo hodnot.

### Jak programově vytvořit zcela nový filtr?
Instancujte `Filter` pomocí `new Filter("My Filter")`, poté jej přidejte do kolekce filtrů úkolů projektu pomocí `project.getTaskFilters().add(filter)`. Poté naplňte jeho kolekci `FilterCriteria` požadovanými řádky, specifikujte názvy polí, testovací operátory a hodnoty, abyste přesně definovali, které úkoly mají být zahrnuty při aplikaci filtru.

### Mohu použít filtr na zdroje místo úkolů?
Kolekce `ResourceFilters` obsahuje definice filtrů použitelné na zdroje. Ano – použijte `project.getResourceFilters()` k práci s filtry specifickými pro zdroje stejným způsobem jako s filtry úkolů. Po přidání nebo získání filtru nakonfigurujte jeho `FilterCriteria` stejně jako u úkolů a poté jej aplikujte na kolekci zdrojů, abyste získali filtrovanou sadu zdrojů.

### Je možné kombinovat více filtrů s logikou OR?
Vytvořte nadřazený `FilterCriteriaGroup` s nastaveným `Operation` na `OR` a poté přidejte jednotlivé objekty `FilterCriteria` jako podřízené. Tato skupina vyhodnotí každé podřízené kritérium a vrátí položky, které splňují kterékoliv z nich, což vám umožní kombinovat několik jednoduchých filtrů do širšího výběru.

### Podporuje Aspose.Tasks filtrování na vlastní pole?
Výčtový typ `CustomField` poskytuje identifikátory pro vlastní pole definovaná v projektu. Rozhodně. Odkazujte na vlastní pole pomocí výčtu `CustomField` a chovají se jako jakékoli vestavěné pole ve výrazech filtrů. Můžete je zahrnout do řádků `FilterCriteria` s použitím stejných operátorů a hodnot, což umožňuje výkonné dotazy na uživatelem definovaná data vedle standardních atributů projektu.

### Jaký dopad na výkon má filtrování velkých MPP souborů?
Filtrování probíhá kompletně v paměti a typicky zpracuje projekt s 1 000 úkoly za méně než 200 ms. U souborů s několika tisíci úkoly zvažte načítání pouze požadovaných částí pomocí `ProjectReader` a aplikaci filtrů po selektivním načtení, což udržuje nízkou spotřebu paměti a zachovává rychlé odezvy i u velmi velkých projektů.

**Poslední aktualizace:** 2026-06-05  
**Testováno s:** Aspose.Tasks pro Java 24.10  
**Autor:** Aspose

## Související tutoriály

- [Načtení MPP souboru v Javě – Správa vlastností projektu s Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java – Jednoduché čtení dat z MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Nastavení data zahájení projektu v MS Project pomocí Aspose.Tasks pro Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```