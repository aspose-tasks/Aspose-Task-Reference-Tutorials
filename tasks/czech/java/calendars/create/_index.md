---
date: 2026-08-03
description: Naučte se, jak vytvořit kalendář ms project, přidat kalendář do projektu
  a uložit projekt jako XML pomocí Aspose.Tasks pro Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Přidat kalendář do projektu pomocí Aspose.Tasks
og_description: Vytvořte kalendář ms project programově pomocí Aspose.Tasks pro Java.
  Přidejte kalendáře, přizpůsobte plány a exportujte do XML během několika minut.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Vytvořte kalendář ms project pomocí Aspose.Tasks pro Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Vytvořte kalendář ms project pomocí Aspose.Tasks pro Java
url: /cs/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit kalendář MS Project pomocí Aspose.Tasks pro Java

## Úvod
V moderních pracovních postupech řízení projektů může schopnost **vytvořit kalendář MS Project** programově ušetřit hodiny ruční úpravy. Aspose.Tasks pro Java vám poskytuje čisté, typově bezpečné API pro manipulaci se soubory Microsoft Project, aniž byste museli otevírat desktopového klienta. V tomto tutoriálu se naučíte, jak přidat kalendář, jak vytvořit kalendář MS Project a jak uložit projekt jako XML – vše pomocí několika řádků Java kódu.

## Rychlé odpovědi
- **Co znamená “create ms project calendar”?**  
  Znamená to vložení nové definice pracovní doby (kalendáře) do souboru Microsoft Project pomocí kódu.  
- **Která knihovna to řeší?**  
  Aspose.Tasks pro Java poskytuje třídu `Calendar` a kontejner `Project` pro správu kalendářů.  
- **Potřebuji licenci?**  
  Dočasná zkušební licence funguje pro testování; pro produkční použití je vyžadována plná licence.  
- **Mohu soubor uložit jako XML?**  
  Ano — použijte `SaveFileFormat.Xml` k exportu projektu jako XML souboru.  
- **Jaké jsou předpoklady?**  
  Java JDK 8+ a JAR knihovna Aspose.Tasks pro Java ve vaší classpath.

## Co je vytvoření kalendáře MS Project?
Vytvoření kalendáře MS Project znamená programově přidat novou definici kalendáře do souboru projektu, specifikovat pracovní dny, výjimky a denní pracovní hodiny a poté přiřadit tento kalendář úkolům, zdrojům nebo celému projektu, aby výpočty harmonogramu respektovaly definovaný pracovní čas.

## Proč použít Aspose.Tasks pro Java k přidání kalendáře do projektu?
Měli byste použít Aspose.Tasks pro Java, protože poskytuje plně typově bezpečné API, které funguje bez nainstalovaného Microsoft Project, podporuje všechny hlavní verze Project (2007‑2021, více než 5 vydání) a může exportovat do XML, MPP a **10+** dalších formátů, což umožňuje automatizované hromadné vytváření kalendářů na jakémkoli serveru.

## Předpoklady
- **Java Development Kit (JDK) 8 nebo novější** nainstalovaný a nakonfigurovaný.  
- **Aspose.Tasks pro Java** knihovna – stáhněte ji z [oficiálního webu](https://releases.aspose.com/tasks/java/) a přidejte JAR do classpath vašeho projektu.  
- IDE nebo nástroj pro sestavení (Maven/Gradle) dle vašeho výběru.

## Postup krok za krokem

### Krok 1: importujte požadovaný balíček Aspose.Tasks
Nejprve načtěte třídy Aspose.Tasks do rozsahu, abyste mohli pracovat s projekty a kalendáři.

```java
import com.aspose.tasks.*;
```

### Krok 2: nastavte cestu k datovému adresáři
Definujte, kam bude vygenerovaný soubor projektu zapsán. Nahraďte zástupný text absolutní nebo relativní cestou na vašem počítači.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: vytvořte novou instanci třídy Project
`Project` je hlavní třída, která v paměti představuje soubor Microsoft Project.

```java
Project prj = new Project();
```

### Krok 4: definujte kalendáře, které chcete přidat
`Calendar` definuje rozvrh s pracovními dny, výjimkami a pracovními časy pro projekt.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Tip:** Po přidání kalendáře můžete přizpůsobit jeho pracovní dny pomocí `cal1.getWeekDays().add(...)` a nastavit denní pracovní hodiny pomocí `cal1.getBaseCalendar().setWorkingTime(...)`.

### Krok 5: uložte projekt (uložit projekt jako XML)
`SaveFileFormat.Xml` říká Aspose.Tasks, aby projekt zapsal ve formátu XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Krok 6: zobrazte zprávu o dokončení
Dejte uživateli vědět, že operace byla úspěšně dokončena.

```java
System.out.println("Process completed Successfully");
```

Po provedení těchto šesti stručných kroků jste úspěšně **přidali kalendář do projektu** a uložili výsledek jako XML soubor.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Objekt projektu není správně inicializován. | Ujistěte se, že je před přístupem k kalendářům voláno `new Project()`. |
| **Soubor nebyl nalezen při ukládání** | `dataDir` ukazuje na neexistující složku. | Nejprve vytvořte adresář nebo použijte absolutní cestu. |
| **Název kalendáře se zobrazuje jako “no info”** | V příkladu byly použity zástupné názvy. | Nahraďte je smysluplnými názvy, které odrážejí rozvrh (např. “Kalendář US Holiday”). |
| **Uložené XML nelze otevřít v MS Project** | Používáte zastaralou verzi Aspose.Tasks. | Aktualizujte na nejnovější verzi Aspose.Tasks pro Java. |

## Často kladené otázky

**Q: Dokáže Aspose.Tasks zvládat složité kalendáře s více výjimkami?**  
A: Ano — po přidání kalendáře můžete definovat výjimky, pracovní hodiny a nepracovní dny pomocí tříd `WeekDay` a `Exception`.

**Q: Je možné přiřadit nový kalendář konkrétním úkolům?**  
A: Rozhodně. Získejte úkol pomocí `prj.getRootTask().getChildren().add("Task Name")` a nastavte `task.set(Tsk.CALENDAR, cal3);`.

**Q: Podporuje knihovna ukládání do jiných formátů, například MPP?**  
A: Ano. Nahraďte `SaveFileFormat.Xml` za `SaveFileFormat.Mpp` nebo `SaveFileFormat.P6` podle potřeby; Aspose.Tasks podporuje **12** výstupních formátů.

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Dočasná zkušební licence stačí pro testování; pro produkční nasazení je vyžadována plná licence.

**Q: Kde mohu získat pomoc, pokud narazím na problémy?**  
A: Komunitní fórum Aspose.Tasks je vynikajícím zdrojem: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Poslední aktualizace:** 2026-08-03  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak definovat pracovní dny v kalendářích MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Jak nastavit kalendář projektu v Javě s Aspose.Tasks](/tasks/java/calendars/properties/)
- [Vytvořit vlastní výjimky kalendáře s Aspose.Tasks pro Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}