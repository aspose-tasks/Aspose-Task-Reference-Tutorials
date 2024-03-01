---
title: Procento dokončených výpočtů pro úkoly v Aspose.Tasks
linktitle: Procento dokončených výpočtů pro úkoly v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte Aspose.Tasks pro Javu a zefektivněte sledování průběhu projektu. Bez námahy vypočítávejte procenta úkolů pro efektivní řízení projektu.
type: docs
weight: 25
url: /cs/java/task-properties/percentage-complete-calculations/
---
## Úvod
Vítejte v našem podrobném průvodci pro zvládnutí výpočtů procenta úkolů pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonná Java knihovna navržená pro práci se soubory Microsoft Project, která nabízí robustní sadu funkcí pro správu projektů. V tomto tutoriálu se zaměříme na výpočty procenta kompletní, které vám poskytnou znalosti pro efektivní sledování a analýzu postupu projektu.
## Předpoklady
Než začnete, ujistěte se, že máte splněny následující předpoklady:
- Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou Javu.
-  Aspose.Tasks Library: Stáhněte si knihovnu Aspose.Tasks pro Javu z[tento odkaz](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Začněme importem potřebných balíčků pro váš projekt Aspose.Tasks for Java. Zahrňte do svého projektu následující fragment kódu:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Nyní si rozeberme každý krok podrobným vysvětlením.
## Krok 1: Import balíčků
V prvním kroku naimportujeme potřebné balíčky pro nastavení našeho projektu Aspose.Tasks.
## Krok 2: Nastavení adresáře dokumentů
 Definujte cestu k adresáři dokumentů pomocí`dataDir`variabilní. Ujistěte se, že váš soubor aplikace Microsoft Project, například „Software Development.mpp“, je v tomto adresáři.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
```
## Krok 3: Načtení projektu
 Inicializujte nový`Project` objekt a načtěte soubor Microsoft Project do instance projektu.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Krok 4: Načtení kolekce úkolů
 Získejte kořenovou úlohu projektu a načtěte jeho potomky jako kolekci pomocí`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Krok 5: Procento tisku dokončeno
Projděte si každý úkol v kolekci a vytiskněte Procento dokončeno, Procento dokončené práce a Fyzické procento dokončeno.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Opakujte tyto kroky pro každý úkol ve vašem projektu, abyste získali přehled o průběhu každého z nich.
## Závěr
Gratulujeme! Úspěšně jste zvládli výpočty procent úkolů pomocí Aspose.Tasks for Java. Tato výkonná knihovna umožňuje vývojářům efektivně řídit a analyzovat průběh projektu.
## Nejčastější dotazy
### Otázka: Kde najdu dokumentaci Aspose.Tasks?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/tasks/java/).
### Otázka: Jak si mohu stáhnout knihovnu Aspose.Tasks pro Javu?
 Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/java/).
### Otázka: Je k dispozici bezplatná zkušební verze?
Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Kde mohu získat podporu pro Aspose.Tasks?
 Navštivte fórum podpory[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Jak získám dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).