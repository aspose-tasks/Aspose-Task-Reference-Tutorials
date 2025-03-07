---
title: Přečtěte si pracovní týdny z kalendáře MS Project s Aspose.Tasks
linktitle: Přečtěte si pracovní týdny z kalendáře s Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se číst pracovní týdny z kalendáře MS Project pomocí Aspose.Tasks for Java. Získejte podrobné pokyny v tomto komplexním tutoriálu.
weight: 15
url: /cs/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přečtěte si pracovní týdny z kalendáře MS Project s Aspose.Tasks

## Úvod
tomto tutoriálu prozkoumáme, jak používat Aspose.Tasks pro Javu ke čtení informací o pracovních týdnech z kalendáře Microsoft Project. Aspose.Tasks je výkonná knihovna Java, která vám umožňuje programově manipulovat a spravovat dokumenty Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Aspose.Tasks pro knihovnu Java staženy a nainstalovány. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Nejprve importujme potřebné balíčky, abychom mohli začít s naším kódem:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Krok 1: Nastavte svůj datový adresář
Nastavte cestu k adresáři, kde se nachází váš soubor MS Project:
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Vytvořte instanci projektu a kalendář přístupu
Vytvořte novou instanci třídy Project a získejte přístup ke kolekci kalendáře a pracovních týdnů:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Krok 3: Projděte si pracovní týdny
Projděte si sbírku pracovních týdnů a zobrazte jejich informace:
```java
for (WorkWeek workWeek : collection) {
    // Zobrazte název pracovního týdne, data od a do
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Přístup ke dnům v týdnu a pracovní době
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // V případě potřeby další pracovní doby zpracování
    }
}
```
## Závěr
tomto tutoriálu jsme se naučili, jak číst informace o pracovních týdnech z kalendáře Microsoft Project pomocí Aspose.Tasks for Java. Tato výkonná knihovna umožňuje bezproblémovou manipulaci se soubory projektu a umožňuje vývojářům efektivně automatizovat různé úkoly.
## FAQ
### Mohu upravit informace o pracovních týdnech pomocí Aspose.Tasks for Java?
Ano, Aspose.Tasks poskytuje API pro úpravu, přidání nebo odstranění pracovních týdnů a souvisejících informací.
### Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?
Ano, Aspose.Tasks podporuje různé verze souborů Microsoft Project, včetně formátů MPP a XML.
### Mohu integrovat Aspose.Tasks s jinými frameworky Java?
Aspose.Tasks lze bez problémů integrovat s jinými frameworky a knihovnami Java pro vylepšenou funkčnost.
### Je k dispozici zkušební verze pro Aspose.Tasks?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).
### Kde najdu podporu pro Aspose.Tasks?
Podporu a pomoc můžete najít na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
