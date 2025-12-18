---
date: 2025-12-18
description: Naučte se, jak vytvořit zobrazení v Aspose.Tasks pro Javu, včetně toho,
  jak uložit zobrazení projektu a nastavit vlastnosti zobrazení. Zvyšte efektivitu
  řízení projektů pomocí přizpůsobených vlastních zobrazení MS Project.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Jak vytvořit zobrazení: Vlastní zobrazení MS Project v Aspose.Tasks'
url: /cs/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit zobrazení: Vlastní zobrazení MS Project v Aspose.Tasks

## Úvod
Pokud hledáte **how to create view**, která odpovídá jedinečným potřebám reportování vašeho projektu, jste na správném místě. Ve správě projektů může přizpůsobení zobrazení dramaticky zlepšit přehlednost a efektivitu při práci s úkoly a zdroji. **Aspose.Tasks for Java** vám poskytuje bohaté API pro **add custom view java**‑stylová řešení, což vám umožní přizpůsobit zobrazení MS Project přesně tak, jak potřebujete. V tomto tutoriálu vás provedeme procesem krok za krokem, od nastavení projektu až po uložení zobrazení projektu.

## Rychlé odpovědi
- **Jaký je hlavní účel?** To create and persist a custom MS Project view using Aspose.Tasks for Java.  
- **Která třída vytváří zobrazení?** `GanttChartView` (or other view types).  
- **Jak zajistit, aby se zobrazení objevilo v nabídce?** Set `view.setShowInMenu(true)`.  
- **Jak mohu uložit zobrazení s projektem?** Use `MPPSaveOptions` with `setWriteViewData(true)`.  
- **Potřebuji licenci?** Yes, a valid Aspose.Tasks license is required for production use.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:

### Prostředí pro vývoj v Javě
Ujistěte se, že máte na svém systému nainstalovanou Javu.

### Aspose.Tasks pro Javu
Stáhněte a nainstalujte Aspose.Tasks for Java z [here](https://releases.aspose.com/tasks/java/).

## Import balíčků
Nejprve importujte potřebné balíčky do svého Java projektu:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Krok 1: Nastavení projektu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Krok 2: Vytvoření zobrazení
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Krok 3: Přizpůsobení vlastností zobrazení *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### Jak zobrazit menu zobrazení
Volání `view.setShowInMenu(true)` zajišťuje, že nově vytvořené zobrazení se objeví v MS Project **view menu**, což uživatelům poskytuje rychlý přístup.

## Krok 4: Ladění nastavení zobrazení
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Krok 5: Přidání zobrazení do projektu *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Krok 6: Uložení projektu *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Proč je důležité ukládat zobrazení projektu
Nastavení `options.setWriteViewData(true)` říká Aspose.Tasks, aby **save project view** informace uložil uvnitř souboru MPP, takže vlastní zobrazení přetrvá mezi relacemi.

## Krok 7: Kontrola vlastností zobrazení
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Běžné případy použití
- **Stakeholder Reporting:** Vytvořte zobrazení, které zobrazuje pouze vysoce‑úrovňové milníky a kritické úkoly.  
- **Resource Allocation:** Vytvořte zobrazení, které uvádí zdroje vedle jejich přiřazených úkolů pro rychlé kontroly kapacity.  
- **Print‑Ready Documents:** Laděním nastavení stránky (jako v Kroku 4) vytvoříte tisknutelné snímky projektu.

## Tipy pro řešení problémů
- **View Not Appearing in Menu:** Verify `view.setShowInMenu(true)` is called before saving.  
- **Missing Columns in Printout:** Ensure `setFirstColumnsCount` matches the columns you need and `setPrintFirstColumnsCountOnAllPages(true)` is enabled.  
- **License Exceptions:** If you encounter licensing errors, confirm that a valid Aspose.Tasks license file is loaded before creating the `Project` object.

## Často kladené otázky
### Q1: Mohu přizpůsobit zobrazení i mimo Gantt diagramy?
A: Yes, Aspose.Tasks for Java provides flexibility to customize various types of views beyond Gantt charts, including tables and graphs.

### Q2: Je Aspose.Tasks for Java vhodný pro rozsáhlé projekty?
A: Absolutely. The library is engineered to handle projects of any size, offering robust performance and memory management.

### Q3: Podporuje Aspose.Tasks for Java export zobrazení do různých formátů?
A: Yes, you can export views to PDF, XLSX, HTML, and other formats, ensuring seamless sharing across platforms.

### Q4: Mohu automatizovat tvorbu vlastních zobrazení pomocí Aspose.Tasks for Java?
A: Certainly. The API enables full automation, allowing you to programmatically generate and manage custom views.

### Q5: Existuje komunitní fórum pro podporu Aspose.Tasks for Java?
A: Yes, you can find assistance and engage with other users in the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for Java‑related queries and discussions.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}