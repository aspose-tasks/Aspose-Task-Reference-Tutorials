---
title: Získejte informace o kalendáři MS Project v Aspose.Tasks
linktitle: Získejte informace o kalendáři v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak získat informace z kalendáře MS Project pomocí Aspose.Tasks pro Java. Podrobný průvodce pro programový přístup k podrobnostem kalendáře.
weight: 14
url: /cs/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Získejte informace o kalendáři MS Project v Aspose.Tasks

## Úvod
V tomto tutoriálu prozkoumáme, jak načíst informace kalendáře ze souborů Microsoft Project pomocí knihovny Aspose.Tasks for Java. Aspose.Tasks poskytuje výkonné funkce pro manipulaci s daty projektu, včetně přístupu k podrobnostem kalendáře, jako jsou pracovní dny a hodiny.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Tasks pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Nejprve musíte do kódu Java importovat potřebné balíčky, abyste mohli používat funkce Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Nyní si pro lepší pochopení rozdělíme poskytnutý příklad do několika kroků.
## Krok 1: Nastavte Data Directory
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` s cestou k adresáři souborů projektu.
## Krok 2: Definujte časové jednotky
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Tyto konstanty představují časové jednotky v mikrosekundách.
## Krok 3: Vytvořte instanci projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
 Tento řádek vytvoří instanci souboru`Project` třída, inicializuje ji s cestou k souboru projektu (`project.mpp`).
## Krok 4: Získejte informace o kalendářích
```java
CalendarCollection alCals = project.getCalendars();
```
Zde načteme kolekci kalendářů přítomných v souboru projektu.
## Krok 5: Iterujte kalendáře
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Informace o kalendáři
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterujte přes týdenní dny
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Čas v milisekundách
            double time = ts / (OneHour); // Převést na hodiny
            if (wd.getDayWorking()) {
                // Zobrazení pracovních dnů a hodin
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Tato smyčka prochází každý kalendář a vytiskne jeho UID, název a pracovní dny s příslušnou pracovní dobou.
## Krok 6: Zobrazte zprávu o dokončení
```java
System.out.println("Process completed Successfully");
```
Nakonec se zobrazí zpráva oznamující dokončení procesu.
## Závěr
V tomto tutoriálu jsme se naučili, jak načíst informace kalendáře ze souborů MS Project pomocí Aspose.Tasks for Java. Pomocí těchto kroků můžete efektivně přistupovat a manipulovat s daty projektu ve vašich aplikacích Java.

## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Odpověď: Ano, Aspose.Tasks podporuje více platforem a programovacích jazyků, včetně .NET, C++, Python a Java.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks?
Odpověď: Podporu můžete získat na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks?
 Odpověď: Ano, dočasné licence je možné zakoupit[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde najdu podrobnou dokumentaci k Aspose.Tasks?
 Odpověď: Můžete se podívat do dokumentace[tady](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
