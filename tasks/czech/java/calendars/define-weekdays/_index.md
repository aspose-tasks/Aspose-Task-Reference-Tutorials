---
title: Definujte pracovní dny v kalendáři pomocí Aspose.Tasks
linktitle: Definujte pracovní dny v kalendáři pomocí Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se definovat pracovní dny v MS Project Calendar pomocí Aspose.Tasks pro Javu. Přizpůsobte si pracovní dny a načasování bez námahy.
weight: 12
url: /cs/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definujte pracovní dny v kalendáři pomocí Aspose.Tasks

## Úvod
tomto tutoriálu projdeme procesem definování pracovních dnů v kalendáři MS Project pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonná knihovna Java, která umožňuje vývojářům programově manipulovat se soubory aplikace Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[Web společnosti Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) pokud jste to ještě neudělali.
2.  Aspose.Tasks for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java z[stránka ke stažení](https://releases.aspose.com/tasks/java/). Postupujte podle pokynů k instalaci uvedených v dokumentaci.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky potřebné pro práci s Aspose.Tasks ve vašem projektu Java:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Krok 1: Vytvořte instanci projektu
Vytvořte instanci objektu Project, který představuje soubor MS Project, se kterým budete pracovat:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Krok 2: Definujte kalendář
Vytvořte novou instanci kalendáře a přidejte ji do projektu:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Krok 3: Přidejte pracovní dny
Definujte pracovní dny přidáním pondělí do čtvrtka s výchozím načasováním:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Krok 4: Nastavte vlastní pracovní den
Definujte sobotu a neděli jako pracovní dny:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Krok 5: Nastavte krátký pracovní den
Nastavte pátek jako krátký pracovní den s vlastní pracovní dobou:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## Krok 6: Uložte projekt
Uložte upravený projekt do souboru XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Závěr
Gratulujeme! Úspěšně jste definovali pracovní dny v kalendáři MS Project pomocí Aspose.Tasks for Java. Nyní můžete tuto funkci integrovat do svých aplikací Java a programově manipulovat se soubory MS Project.
## FAQ
### Q1: Mohu definovat vlastní nepracovní dny pomocí Aspose.Tasks for Java?
 Odpověď: Ano, můžete definovat vlastní nepracovní dny nastavením`DayWorking` majetek do`false` pro příslušný všední den.
### Q2: Jak mohu přidat svátky do kalendáře?
 Odpověď: Můžete přidat svátky vytvořením instancí`CalendarExceptions` upřesnění nepracovních termínů.
### Q3: Je Aspose.Tasks kompatibilní s různými verzemi souborů MS Project?
Odpověď: Ano, Aspose.Tasks podporuje různé verze souborů MS Project, včetně formátů MPP, MPT a XML.
### Q4: Mohu upravit existující kalendáře v souboru MS Project?
Odpověď: Ano, můžete načíst existující projekt s kalendáři, provést úpravy a poté uložit změny zpět do původního souboru.
### Q5: Poskytuje Aspose.Tasks podporu pro opakující se úkoly?
Odpověď: Ano, Aspose.Tasks vám umožňuje pracovat s opakujícími se úkoly, včetně definování vzorců a trvání jejich opakování.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
