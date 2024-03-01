---
title: Spravujte výjimky kalendáře v Aspose.Tasks
linktitle: Přidat a odebrat výjimky kalendáře v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně přidávat a odstraňovat výjimky kalendáře v Aspose.Tasks for Java. Vylepšete pracovní postupy projektového řízení bez námahy.
type: docs
weight: 10
url: /cs/java/calendar-exceptions/add-remove/
---

## Úvod
Při řízení projektů je zpracování výjimek v kalendářích zásadní pro přesné plánování úkolů a správu zdrojů. Aspose.Tasks for Java poskytuje výkonné funkce pro snadné přidávání a odstraňování výjimek kalendáře. V tomto tutoriálu vás provedeme procesem krok za krokem.
#### Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému
- Aspose.Tasks pro knihovnu Java staženou a nakonfigurovanou ve vašem projektu
- Základní znalost programovacího jazyka Java a konceptů projektového řízení

## Importujte balíčky
Nejprve se ujistěte, že do své třídy Java importujete potřebné balíčky, abyste mohli efektivně využívat funkce Aspose.Tasks.
```java
import com.aspose.tasks.*;
```
## Krok 1: Načtěte projekt a otevřete kalendář
Začněte načtením souboru projektu a přístupem ke kalendáři, do kterého chcete přidat nebo odebrat výjimky.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## Krok 2: Odstraňte výjimku
Chcete-li odstranit existující výjimku z kalendáře, zkontrolujte, zda existují nějaké výjimky, a poté požadovanou výjimku odstraňte.
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## Krok 3: Přidejte výjimku
 Chcete-li do kalendáře přidat novou výjimku, vytvořte a`CalendarException` objektu a definovat jeho počáteční a koncové datum.
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## Krok 4: Zobrazení výjimek
Nakonec můžete zobrazit přidané výjimky pro ověření nebo další zpracování.
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## Závěr
Správa výjimek kalendáře je nezbytná pro přesné plánování projektu a alokaci zdrojů. S Aspose.Tasks for Java můžete bez námahy přidávat a odstraňovat výjimky, abyste zajistili efektivní udržování časových plánů vašich projektů.

## FAQ
### Otázka: Mohu přidat více výjimek do kalendáře pomocí Aspose.Tasks for Java?

Odpověď: Ano, do kalendáře můžete přidat více výjimek procházením seznamu výjimek a přidáním každé zvlášť.

### Otázka: Je Aspose.Tasks for Java kompatibilní se všemi verzemi souborů Microsoft Project?

Odpověď: Aspose.Tasks for Java poskytuje kompatibilitu s různými verzemi souborů Microsoft Project a zajišťuje bezproblémovou integraci s vašimi pracovními postupy projektového řízení.

### Otázka: Jak mohu zpracovat opakující se výjimky v kalendářích projektu?

Odpověď: Aspose.Tasks for Java nabízí robustní funkce pro zpracování opakujících se výjimek v projektových kalendářích, což vám umožňuje snadno definovat složité vzorce opakování.

### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?

 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Aspose.Tasks for Java z webu[webová stránka](https://releases.aspose.com/) k prozkoumání jeho funkcí před nákupem.

### Otázka: Kde mohu hledat podporu pro jakékoli problémy nebo dotazy související s Aspose.Tasks for Java?

 Odpověď: Můžete navštívit fórum Aspose.Tasks pro Javu na webu[webová stránka](https://reference.aspose.com/tasks/java/) požádat o pomoc komunitu nebo přímo kontaktovat tým podpory pro personalizovanou pomoc.
