---
date: 2025-12-23
description: Naučte se, jak vytvořit souhrn MPP a aktualizovat autora projektu pomocí
  Aspose.Tasks pro Javu. Nastavujte a získávejte informace o projektu bez námahy.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak vytvořit souhrn MPP a aktualizovat autora projektu pomocí Aspose.Tasks
url: /cs/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte souhrn MPP projektu v Aspose.Tasks

## Úvod
V tomto tutoriálu **vytvoříte souhrn MPP** informací pro soubor Microsoft Project a naučíte se, jak pomocí knihovny Aspose.Tasks pro Javu **aktualizovat autora projektu**. Ať už vytváříte nástroj pro řízení projektů nebo automatizujete reportování, programové řízení souhrnných vlastností šetří čas a zajišťuje konzistenci napříč vašimi projekty.

## Rychlé odpovědi
- **Co znamená „vytvořit souhrn MPP“?** Znamená to nastavení vysoce‑úrovňových vlastností projektu (autor, revize, klíčová slova atd.), které se zobrazují v dialogu Project Summary Information v Microsoft Project.  
- **Která knihovna to řeší?** Aspose.Tasks pro Javu poskytuje plynulé API pro čtení a zápis těchto vlastností.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze, ale pro produkční použití je vyžadována komerční licence.  
- **Mohu také změnit autora po uložení souboru?** Ano – můžete **aktualizovat autora projektu** voláním `project.set(Prj.AUTHOR, "New Author")` a následným opětovným uložením souboru.  
- **Jaké formáty souborů jsou podporovány?** Jak MPP, tak XML (SaveFileFormat.Xml) jsou plně podporovány.

## Co je vytvoření souhrnu MPP?
Vytvoření souhrnu MPP zahrnuje vyplnění metadat projektu – autor, číslo revize, klíčová slova, komentáře, datum vytvoření a datum tisku. Tato metadata jsou uložena v záznamu Project Summary Information a jsou zobrazena v sekci **File → Info** v Microsoft Project.

## Proč aktualizovat autora projektu?
Udržování přesných informací o **autorovi projektu** je nezbytné pro auditní stopy, spolupráci a reportování. Když do projektu přispívá více členů týmu, může být nutné **aktualizovat autora projektu**, aby odrážel poslední změny nebo správně přiřadil práci.

## Předpoklady
1. Java Development Kit (JDK) nainstalovaný na vašem počítači.  
2. Aspose.Tasks pro Javu – stáhněte jej z [zde](https://releases.aspose.com/tasks/java/).  
3. IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.

## Import balíčků
Nejprve importujte potřebné balíčky do vaší Java třídy:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Krok 1: Nastavení projektu a definice souhrnných informací
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
V kódu výše **vytváříme souhrn MPP** pole jako autor, revize a klíčová slova. Můžete také později **aktualizovat autora projektu** voláním `project.set(Prj.AUTHOR, "New Name")`.

## Krok 2: Uložení souhrnných informací projektu
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Uložení projektu zachová všechna souhrnná data, která jste právě definovali.

## Krok 3: Načtení souhrnných informací projektu
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Tento úryvek ukazuje, jak **znovu načíst** souhrnné informace a potvrdit, že operace **vytvoření souhrnu MPP** byla úspěšná.

## Časté problémy a řešení
- **Null hodnoty po načtení:** Ujistěte se, že projekt byl úspěšně uložen před opětovným načtením. Zkontrolujte cesty k souborům a oprávnění.  
- **Rozdíly ve formátování data:** `project.get(Prj.CREATION_DATE)` vrací `java.util.Date`. Použijte `SimpleDateFormat`, pokud potřebujete vlastní formát zobrazení.  
- **Licence není nastavena:** Bez platné licence běží Aspose.Tasks v evaluačním režimu a může vkládat vodoznak. Zaregistrujte licenci co nejdříve v kódu.

## Často kladené otázky
**Q: Mohu používat Aspose.Tasks pro Javu s jinými Java knihovnami?**  
A: Ano, Aspose.Tasks pro Javu lze bez problémů integrovat s dalšími Java knihovnami a rozšířit tak vaše schopnosti řízení projektů.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro Javu?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

**Q: Jak často je Aspose.Tasks pro Javu aktualizováno?**  
A: Aspose.Tasks pro Javu je pravidelně aktualizováno, aby bylo zajištěno kompatibilita s nejnovějšími verzemi Javy a souborů Microsoft Project.

**Q: Mohu dále přizpůsobit souhrnné informace projektu?**  
A: Rozhodně, Aspose.Tasks pro Javu poskytuje rozsáhlé možnosti přizpůsobení souhrnných informací projektu podle vašich konkrétních požadavků.

**Q: Kde mohu získat podporu pro Aspose.Tasks pro Javu?**  
A: Podporu můžete získat na komunitním fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

## Závěr
V tomto tutoriálu jsme vám ukázali, jak **vytvořit souhrn MPP** data, **aktualizovat autora projektu** a ověřit tyto změny pomocí Aspose.Tasks pro Javu. Automatizací těchto kroků získáte plnou kontrolu nad metadaty projektu, což vaše aplikace učiní robustnějšími a vaše projektové zprávy přesnějšími.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}