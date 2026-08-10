---
date: 2026-06-05
description: Naučte se, jak vytvořit resource assignment s Aspose.Tasks pro Java,
  přidat zdroje do projektu a spravovat leveling delay properties.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Zpracovat Leveling Delay Properties pro Resource Assignments v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Vytvořit Resource Assignment s Aspose.Tasks pro Java
url: /cs/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření přiřazení zdroje pomocí Aspose.Tasks pro Java

V tomto komplexním průvodci se naučíte **jak vytvořit přiřazení zdroje aspotasks** pomocí knihovny Aspose.Tasks pro Java. Ať už vytváříte vlastní plánovací engine, automatizujete hromadné aktualizace projektů, nebo jednoduše potřebujete manipulovat se soubory Microsoft Project bez desktopové aplikace, zvládnutí těchto kroků vám umožní udržet data projektu přesná a plně kontrolovatelná.

## Rychlé odpovědi
- **Co znamená „add resource to project“?** Vytvoří nový záznam zdroje, který může být později přiřazen úkolům.  
- **Mohu po přiřazení nastavit zpoždění vyrovnání?** Ano, pomocí polí `Asn.DELAY` nebo `Asn.LEVELING_DELAY`.  
- **Potřebuji licenci pro spuštění tohoto kódu?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována placená licence.  
- **Která verze Javy je podporována?** Java 8 nebo novější.  
- **Je to kompatibilní se všemi formáty souborů MS Project?** Aspose.Tasks podporuje více než 12 formátů – včetně .MPP, .XML, .XER, .CSV, .PDF a dalších.

## Co znamená „add resource to project“ v Aspose.Tasks?
Přidání zdroje do projektu znamená vytvoření objektu `Resource` uvnitř modelu `Project`. Tento objekt může být později propojen s úkoly pomocí `ResourceAssignment`, což vám umožní sledovat práci, náklady a nastavení vyrovnání. Vložení zdroje poskytne plánovači něco, co může alokovat, a později můžete dotazovat nebo měnit jeho vlastnosti, jako je dostupnost, sazby a přiřazení kalendáře.

## Proč zpracovávat vlastnosti zpoždění vyrovnání?
Zpoždění vyrovnání říká plánovači, aby odložil zahájení přeplánovaného přiřazení, čímž rozloží práci rovnoměrněji po časové ose. Nastavením tohoto zpoždění se vyhnete nereálným datům zahájení, snížíte varování o přetížení a vytvoříte plán, který odráží reálná omezení zdrojů. Úprava zpoždění vám také poskytuje detailní kontrolu nad tím, kolik rezervy může engine vložit, což vám pomáhá splnit termíny projektu při respektování limitů zdrojů.

## Jak vytvořit přiřazení zdroje aspotasks?
Načtěte svůj objekt `Project`, přidejte úkol, vytvořte zdroj a poté je spojte pomocí `ResourceAssignment`. Tento end‑to‑end tok vám umožní programově vytvořit kompletní strukturu projektu a okamžitě řídit zpoždění vyrovnání při přiřazení. Proces demonstruje hlavní workflow: inicializaci projektu, definici úkolu, vytvoření zdroje, propojení přiřazení a nakonec aplikaci plánovacích parametrů, jako je zpoždění vyrovnání.

## Předpoklady
1. Java Development Kit (JDK): Ujistěte se, že máte na svém systému nainstalovaný Java JDK. Můžete jej stáhnout a nainstalovat z [webové stránky](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Knihovna Aspose.Tasks pro Java: Stáhněte knihovnu Aspose.Tasks pro Java ze [stránky ke stažení](https://releases.aspose.com/tasks/java/).

## Import balíčků
Následující importy přinášejí základní třídy Aspose.Tasks potřebné pro manipulaci s projektem.  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Jak vytvořit přiřazení zdroje aspotasks?
Načtěte svůj objekt `Project`, přidejte úkol, vytvořte zdroj a poté je spojte pomocí `ResourceAssignment`. Tento end‑to‑end tok vám umožní programově vytvořit kompletní strukturu projektu a okamžitě řídit zpoždění vyrovnání při přiřazení. Proces demonstruje hlavní workflow: inicializaci projektu, definici úkolu, vytvoření zdroje, propojení přiřazení a nakonec aplikaci plánovacích parametrů, jako je zpoždění vyrovnání.

## Krok 1: Vytvořit objekt Project
`Project` třída je nejvyšší kontejner Aspose.Tasks, který představuje celý soubor projektu v paměti. Její vytvoření vám poskytne čistý základ pro přidání úkolů, zdrojů a přiřazení.
```java
Project prj = new Project();
```

## Krok 2: Vytvořit úkol
Třída `Task` představuje jedinou pracovní položku v rozvrhu. Přidání úkolu demonstruje **jak přidat úkol** programově a poskytuje cíl pro nadcházející přiřazení zdroje.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Krok 3: Nastavit datum zahájení úkolu a dobu trvání
Definujte, kdy úkol začíná a jak dlouho bude probíhat. Správná data zahájení jsou nezbytná, protože výpočty vyrovnání je používají jako základ pro jakékoli zpoždění, které později zadáte.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Krok 4: Přidat zdroj
Nyní **přidáváme zdroj do projektu** vytvořením nového záznamu `Resource`. Třída `Resource` představuje osobu, zařízení nebo materiál, který může být přiřazen k úkolům.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Krok 5: Vytvořit přiřazení zdroje
`ResourceAssignment` propojuje `Task` a `Resource`. Toto spojení vám umožní zaznamenat práci, náklady a podrobnosti o vyrovnání pro konkrétní zdroj na konkrétním úkolu.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Krok 6: Nastavit zpoždění vyrovnání
Nastavte zpoždění vyrovnání pro přiřazení. Nastavení na nulu znamená žádné další zpoždění, ale můžete hodnotu podle potřeby upravit. Pole `Asn.DELAY` obsahuje zpoždění v minutách; `Asn.LEVELING_DELAY` je alias, který funguje stejně.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Krok 7: Zobrazit výsledky
Vytiskněte důležité vlastnosti pro ověření, že vše bylo nastaveno správně. Tento krok vám pomůže potvrdit, že hodnoty zdroje, úkolu a zpoždění jsou přesně takové, jaké očekáváte, před uložením souboru.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Časté úskalí a tipy
- **Úskalí:** Zapomenutí nastavit datum zahájení úkolu může způsobit, že přiřazení výchozí na začátek projektu.  
- **Tip:** Použijte `prj.getDuration(value, TimeUnitType.Day)` pro řízení granularitiy zpoždění.  
- **Tip:** Po přidání více zdrojů zavolejte `prj.updateResourceAssignments()`, aby plánovač přepočítal vyrovnání.  
- **Pro tip:** Pro velké projekty (10 000+ úkolů) povolte `prj.setAutoCalculate(false)` před hromadnými aktualizacemi a poté na konci jednou zavolejte `prj.calculate()`, aby se zlepšil výkon.

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks s jinými knihovnami Java?**  
A: Ano, Aspose.Tasks se hladce integruje s knihovnami jako Jackson pro práci s JSON nebo Apache POI pro další operace s tabulkami, což vám umožní vytvářet bohatší řešení pro řízení projektů.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Aspose.Tasks podporuje více než 12 formátů souborů – včetně .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML a .MPP12 – což zajišťuje bezproblémové obousměrné editování napříč všemi hlavními verzemi Projectu.

**Q: Kde mohu najít další podporu pro Aspose.Tasks?**  
A: Podporu a diskuse komunity najdete na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Můžu vyzkoušet Aspose.Tasks před zakoupením?**  
A: Ano, plně funkční bezplatná zkušební verze je k dispozici na [stránce vydání](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro hodnocení?**  
A: Požádejte o dočasnou licenci na [stránce dočasné licence](https://purchase.aspose.com/temporary-license/), abyste mohli knihovnu spouštět bez omezení hodnocení.

---

**Poslední aktualizace:** 2026-06-05  
**Testováno s:** Aspose.Tasks pro Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Spravovat rozpočet přiřazení v Javě pomocí Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Jak zastavit přiřazení a obnovit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}