---
date: 2026-03-29
description: Naučte se, jak nastavit klíčová slova a datum vytvoření v MPP projektu
  pomocí Aspose.Tasks for Java. Průvodce krok za krokem s ukázkami kódu.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak nastavit klíčová slova v souhrnu projektu MPP pomocí Aspose.Tasks
url: /cs/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit klíčová slova v souhrnu projektu MPP pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se dozvíte **jak nastavit klíčová slova** a další souhrnné informace pro soubor projektu MPP pomocí Aspose.Tasks pro Java. Ať už potřebujete vložit údaje o autorovi, čísla revizí nebo vlastní datum vytvoření, tento průvodce vás provede přesnými kroky, včetně připraveného kódu připraveného k spuštění. Na konci budete schopni nastavit klíčová slova, nastavit datum vytvoření v Javě a načíst data zpět ze souboru.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Tasks for Java  
- **Hlavní účel?** Nastavit klíčová slova, informace o autorovi a datum vytvoření v souboru MPP  
- **Kolik kroků kódu?** Tři jednoduché bloky kódu (inicializace, uložení, čtení)  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence  
- **Podporovaná verze Javy?** Java 8 a vyšší  

## Co je „jak nastavit klíčová slova“ v souboru MPP?
Klíčová slova jsou pole metadat uložená uvnitř souboru Microsoft Project (MPP). Pomáhají kategorizovat projekty, umožňují rychlé vyhledávání a poskytují kontextové informace pro následné nástroje. Aspose.Tasks zpřístupňuje vlastnost `Prj.KEYWORDS`, což usnadňuje programově zapisovat nebo aktualizovat tuto hodnotu.

## Proč použít Aspose.Tasks pro Java k nastavení klíčových slov a data vytvoření?
* **Plná kompatibilita s .MPP** – funguje se všemi formáty Project 2007‑2023.  
* **Není vyžadována instalace COM nebo Office** – čistá Java, ideální pro serverové prostředí.  
* **Bohaté API** – kromě klíčových slov můžete v jednom volání nastavit autora, revizi, komentáře a data.  
* **Optimalizovaný výkon** – rychlé čtení/zápis i pro velké soubory projektů.

## Předpoklady
1. **Java Development Kit (JDK)** – nainstalovaný JDK 8 nebo novější.  
2. **Aspose.Tasks pro Java** – stáhněte nejnovější JAR [zde](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans nebo jakýkoli editor, který preferujete.

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Tyto importy vám poskytují přístup k objektu `Project`, výčtu `Prj` pro souhrnná pole a výčtu `SaveFileFormat` pro ukládání.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Krok 1: Nastavení projektu a definice souhrnných informací
Vytvořte instanci `Project` a poté použijte metodu `set` k zápisu požadovaných metadat. Všimněte si, jak **nastavujeme klíčová slova** a **nastavujeme datum vytvoření v Javě** pomocí objektu `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Krok 2: Uložení souhrnných informací projektu
Po vyplnění polí uložte změny. Zde projekt ukládáme jako XML pro snadnou kontrolu, ale můžete také uložit zpět do MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Krok 3: Načtení souhrnných informací projektu
Pro ověření, že metadata byla správně zapsána, načtěte soubor znovu a přečtěte každou vlastnost. Tento krok ukazuje, že **jak nastavit klíčová slova** skutečně funguje od začátku do konce.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Časté problémy a řešení
| Problém | Proč k tomu dochází | Řešení |
|-------|----------------|-----|
| **NullPointerException při `project.get(Prj.CREATION_DATE)`** | Kalendář nebyl před uložením nastaven. | Ujistěte se, že před `save()` zavoláte `project.set(Prj.CREATION_DATE, cal.getTime())`. |
| **Klíčová slova se nezobrazují v uživatelském rozhraní Microsoft Project** | Soubor byl uložen jako XML a otevřen přímo v Projectu. | Uložte zpět do MPP (`SaveFileFormat.MPP`) nebo otevřete XML pomocí *Import* v Projectu. |
| **Hodnoty dat posunuté časovým pásmem** | Java `Date` obsahuje informaci o časovém pásmu. | Použijte `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`, pokud potřebujete data v UTC. |

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks pro Java s jinými knihovnami Java?**  
A: Ano, Aspose.Tasks pro Java lze bez problémů integrovat s jinými knihovnami Java a rozšířit tak vaše možnosti řízení projektů.

**Q: Je k dispozici zkušební verze pro Aspose.Tasks pro Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak často je Aspose.Tasks pro Java aktualizováno?**  
A: Aspose.Tasks pro Java je pravidelně aktualizováno, aby bylo zajištěno kompatibilita s nejnovějšími verzemi Javy a souborů Microsoft Project.

**Q: Mohu dále přizpůsobit souhrnné informace projektu?**  
A: Určitě, Aspose.Tasks pro Java poskytuje rozsáhlé možnosti přizpůsobení souhrnných informací projektu podle vašich konkrétních požadavků.

**Q: Kde mohu získat podporu pro Aspose.Tasks pro Java?**  
A: Podporu můžete získat na komunitním fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** Aspose.Tasks pro Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}