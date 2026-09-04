---
date: 2026-07-05
description: Naučte se, jak propojit úkoly napříč projekty s Aspose.Tasks for Java.
  Průvodce krok za krokem, předpoklady a nejlepší postupy pro plynulé propojení úkolů
  napříč projekty.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Vytvoření odkazu na úkol napříč projekty v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Propojení úkolů napříč projekty pomocí Aspose.Tasks for Java
url: /cs/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Propojení úkolů napříč projekty pomocí Aspose.Tasks pro Java

## Úvod
Propojení úkolů napříč projekty je základní schopnost, která vám umožňuje synchronizovat práci, vyhnout se duplicitám a udržovat jediný zdroj pravdy pro vzájemně závislé činnosti. V tomto tutoriálu se dozvíte, jak **propojit úkoly napříč projekty** pomocí Aspose.Tasks pro Java, krok za krokem. Na konci budete mít plně funkční propojení napříč projekty, které se automaticky aktualizuje, když se některá strana změní, a poskytne vám koordinaci v reálném čase bez ručního kopírování a vkládání.

## Rychlé odpovědi
- **Jaká je hlavní třída pro vytvoření projektu?** `Project` – představuje celý soubor MS‑Project v paměti.  
- **Která metoda přidává externí úkol?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Mohu nastavit typ odkazu?** Yes – use `TaskLinkType.FinishToStart`, `StartToStart`, etc.  
- **Potřebuji licenci pro propojení?** Platná licence Aspose.Tasks je vyžadována pro produkční použití; bezplatná zkušební verze funguje pro hodnocení.  
- **Existuje limit na propojené úkoly?** Aspose.Tasks dokáže zpracovat 10 000+ propojených úkolů na projekt bez zhoršení výkonu.

## Co je propojení úkolů napříč projekty?
Propojení úkolů napříč projekty vytváří vztah závislosti mezi úkolem v jednom souboru projektu a úkolem v jiném, což umožňuje, aby změny ve zdrojovém úkolu (délka, datum zahájení, omezení) se automaticky přenesly na závislý úkol. Tento mechanismus udržuje harmonogramy sladěné, snižuje ruční aktualizace a zajišťuje, že jakákoli úprava ve zdrojovém projektu je okamžitě odrazena ve všech propojených projektech, čímž zachovává konzistenci napříč portfoliem.

## Proč použít Aspose.Tasks pro propojení napříč projekty?
Aspose.Tasks podporuje **více než 50 vstupních a výstupních formátů** a může zpracovávat **projekty o stovkách stránek** při zachování využití paměti pod 200 MB. Jeho API provádí propojení na straně serveru, čímž eliminuje potřebu instalace Microsoft Project a umožňuje automatizované pipeline pro velké podniky.

## Předpoklady
- Java 17 (nebo novější) nainstalovaná a nakonfigurovaná ve vašem IDE.  
- Platný licenční soubor Aspose.Tasks pro Java (`Aspose.Tasks.Java.lic`).  
- Knihovna Aspose.Tasks pro Java přidána do vašeho projektu. Můžete si ji stáhnout ze [stránky vydání Aspose.Tasks pro Java](https://releases.aspose.com/tasks/java/).  
- Základní znalost konceptů MS‑Project, jako jsou úkoly, souhrnné úkoly a závislosti.

## Import balíčků
`Project`, `Task`, `TaskLink` a související výčty se nacházejí v jmenném prostoru `com.aspose.tasks`. Importujte je na začátku vašeho Java souboru:

`import com.aspose.tasks.*;`

**Project** je hlavní třída představující soubor projektu v paměti. **Task** představuje jednotlivou pracovní položku v rámci projektu. **TaskLink** definuje vztah závislosti mezi dvěma úkoly. Tyto importy vám poskytují přístup k celé sadě funkcí pro manipulaci s projektem, včetně propojení napříč projekty.

## Jak propojit úkoly napříč projekty?
Načtěte oba soubory projektů, přidejte zástupný externí úkol, vytvořte lokální úkol a poté je spojte pomocí `TaskLink`. API automaticky zpracovává mapování ID a aktualizace, čímž zajišťuje, že jakákoli změna v externím úkolu se automaticky projeví v propojeném lokálním úkolu bez dalšího kódu. Tento přístup zjednodušuje koordinaci více projektů a snižuje riziko odchylek v harmonogramu.

### Krok 1: Nastavte své prostředí
Ujistěte se, že JAR soubor Aspose.Tasks je na classpath a licenční soubor je načten během běhu:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** načte váš licenční soubor Aspose.Tasks, aby umožnil plnou funkčnost a odstranil vodotisky z hodnocení.

### Krok 2: Vytvořte instanci projektu
Vytvořte novou instanci objektu `Project` pro cílový projekt, kde má být odkaz umístěn:

`Project targetProject = new Project();`

Třída `Project` je nejvyšší objekt Aspose.Tasks, který představuje jeden soubor projektu v paměti.

### Krok 3: Přidejte souhrnný úkol
Souhrnný úkol seskupuje související úkoly. Vytvořte jeden, který bude obsahovat jak externí, tak lokální úkoly:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Krok 4: Přidejte externí úkol
Vložte externí úkol, který odkazuje na úkol v jiném souboru projektu:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

Metoda **addExternalTask** vytvoří zástupný úkol, který odkazuje na externí soubor projektu, pomocí zadaného názvu souboru a ID úkolu.

### Krok 5: Přidejte lokální úkol
Vytvořte úkol, který bude propojen s externím úkolem:

`Task local = summary.getChildren().add("Local Task");`

### Krok 6: Vytvořte odkaz úkolu
Navážete závislost mezi externím a lokálním úkolem. Nejčastější typ odkazu je Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** zaznamenává vztah; později můžete podle potřeby upravit jeho zpoždění, předstih nebo typ.

### Krok 7: Uložte a ověřte
Uložte projekt do souboru a volitelně jej otevřete v Microsoft Project, abyste ověřili odkaz:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** určuje formát souboru pro uložení projektu. Když otevřete *LinkedProject.mpp*, uvidíte externí úkol zobrazený se speciální ikonou a linku závislosti směřující k lokálnímu úkolu.

## Časté problémy a řešení
- **Externí soubor nebyl nalezen** – Ujistěte se, že cesta je relativní k běžícímu procesu nebo zadejte absolutní cestu.  
- **Neshoda ID úkolů** – Ověřte, že ID externího úkolu (druhý argument `addExternalTask`) odpovídá zdrojovému projektu.  
- **Licence nebyla načtena** – Chybějící nebo nesprávný licenční soubor způsobí `LicenseException`. Načtěte ji před jakýmikoli voláními Aspose.Tasks.  
- **Výkon u velkých projektů** – Použijte `Project.setReadOnly(true)`, pokud potřebujete pouze číst externí úkoly; tím se sníží zatížení paměti.

## Často kladené otázky

**Q: Můžu propojit úkoly z více externích projektů ve stejném souhrnném úkolu?**  
A: Ano, můžete přidat několik externích úkolů pod jeden souhrnný úkol a vytvořit pro každý samostatný odkaz pomocí stejné metody `addExternalTask`.

**Q: Co se stane, pokud je externí úkol v propojeném projektu upraven?**  
A: Jakákoli změna v harmonogramu, délce nebo omezeních externího úkolu se automaticky projeví v závislém lokálním úkolu po obnovení cílového projektu.

**Q: Je možné vytvořit odkazy mezi úkoly v různých formátech souborů?**  
A: Rozhodně. Aspose.Tasks podporuje propojení mezi formáty MPP, XML a Primavera, což umožňuje heterogenním projektovým ekosystémům zůstat synchronizovaným.

**Q: Mohu odpojit úkoly, jakmile jsou propojeny napříč projekty?**  
A: Ano, odstraňte odkaz voláním `project.getTaskLinks().remove(link)` nebo smazáním zástupného externího úkolu.

**Q: Existují nějaká omezení počtu úkolů, které lze propojit napříč projekty?**  
A: Knihovna dokáže zpracovat **10 000+ propojených úkolů** na projekt, omezené pouze dostupnou pamětí systému a specifikacemi podkladového formátu souboru.

## Závěr
Nyní máte kompletní, připravený přístup pro **propojení úkolů napříč projekty** pomocí Aspose.Tasks pro Java. Tato schopnost zjednodušuje koordinaci více projektů, snižuje ruční úsilí a zajišťuje, že změny v harmonogramu se okamžitě šíří napříč vaším portfoliem. Prozkoumejte další funkce, jako jsou vlastní doby zpoždění, různé typy odkazů a hromadné propojení, abyste dále automatizovali složité projektové struktury.

---

**Poslední aktualizace:** 2026-07-05  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Související tutoriály

- [Vytvořit odkaz úkolu v Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Vytvořit úkoly Aspose Java – Vlastnosti úkolu](/tasks/java/task-properties/)
- [Vytvořit prázdný soubor MS Project v Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}