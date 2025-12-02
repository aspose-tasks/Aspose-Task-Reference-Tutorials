---
date: 2025-12-02
description: Naučte se, jak přidat kalendář do projektu, jak vytvořit kalendář MS
  Project a jak uložit projekt jako XML pomocí Aspose.Tasks pro Javu.
language: cs
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Přidat kalendář do projektu pomocí Aspose.Tasks pro Javu
url: /java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání kalendáře do projektu pomocí Aspose.Tasks pro Java

## Úvod
V moderních pracovních postupech řízení projektů může schopnost **přidat kalendář do projektu** programově ušetřit hodiny ruční úpravy. Aspose.Tasks pro Java poskytuje vývojářům čisté, typově bezpečné API pro manipulaci se soubory Microsoft Project, aniž by bylo nutné otevírat desktopového klienta. V tomto tutoriálu se naučíte **jak přidat kalendář**, **jak vytvořit kalendář MS Project** a **uložit projekt jako XML**—vše pomocí několika řádků Java kódu.

## Rychlé odpovědi
- **Co znamená „přidat kalendář do projektu“?**  
  Znamená to vložení nové definice pracovní doby (kalendáře) do souboru Microsoft Project pomocí kódu.  
- **Která knihovna to řeší?**  
  Aspose.Tasks pro Java poskytuje třídu `Calendar` a kontejner `Project` pro správu kalendářů.  
- **Potřebuji licenci?**  
  Dočasná zkušební licence funguje pro testování; plná licence je vyžadována pro produkční použití.  
- **Mohu soubor uložit jako XML?**  
  Ano—použijte `SaveFileFormat.Xml` k exportu projektu jako XML soubor.  
- **Jaké jsou předpoklady?**  
  Java JDK 8+ a JAR knihovna Aspose.Tasks pro Java ve vaší classpath.

## Co je „přidat kalendář do projektu“?
Přidání kalendáře do projektu vytvoří vlastní rozvrh, který definuje pracovní dny, svátky a denní pracovní hodiny. Tento kalendář může být následně přiřazen úkolům, zdrojům nebo celému projektu, čímž se zajistí, že výpočty jako datum zahájení a trvání respektují definovanou pracovní dobu.

## Proč použít Aspose.Tasks pro Java k přidání kalendáře do projektu?
- **Plná kontrola** – Není vyžadováno UI; automatizujte hromadné vytváření kalendářů napříč mnoha projekty.  
- **Kompatibilita napříč verzemi** – Funguje se soubory Project 2007, 2010, 2013, 2016 a novějšími.  
- **Bez instalace Microsoft Project** – Spusťte na libovolném serveru nebo v CI pipeline.  
- **Flexibilita exportu** – Uložte jako XML, MPP nebo jiné podporované formáty.

## Předpoklady
- **Java Development Kit (JDK) 8 nebo novější** nainstalovaný a nakonfigurovaný.  
- **Aspose.Tasks pro Java** knihovna – stáhněte z [oficiálního webu](https://releases.aspose.com/tasks/java/) a přidejte JAR do classpath vašeho projektu.  
- IDE nebo buildovací nástroj (Maven/Gradle) dle vašeho výběru.

## Průvodce krok za krokem

### Krok 1: Importujte požadovaný balíček Aspose.Tasks
Nejprve přiveďte třídy Aspose.Tasks do rozsahu, abyste mohli pracovat s projekty a kalendáři.

```java
import com.aspose.tasks.*;
```

### Krok 2: Nastavte cestu k datovému adresáři
Definujte, kam bude zapsán vygenerovaný soubor projektu. Nahraďte zástupný text absolutní nebo relativní cestou na vašem počítači.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Vytvořte novou instanci Project
Instanciujte objekt `Project` – představuje prázdný soubor Microsoft Project, který můžete naplnit.

```java
Project prj = new Project();
```

### Krok 4: Definujte kalendáře, které chcete přidat
Použijte metodu `Calendars.add(String name)` k vytvoření nových položek kalendáře. V tomto příkladu přidáváme tři kalendáře, ale můžete přidat libovolný počet a později nakonfigurovat jejich pracovní časy.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Tip:** Po přidání kalendáře můžete přizpůsobit jeho pracovní dny pomocí `cal1.getWeekDays().add(...)` a nastavit denní pracovní hodiny pomocí `cal1.getBaseCalendar().setWorkingTime(...)`.

### Krok 5: Uložte projekt (uložit projekt jako XML)
Uložte projekt, včetně nově přidaných kalendářů, do XML souboru. Tento formát je snadno prohlížitelný a kompatibilní s mnoha nástroji.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Krok 6: Zobrazte zprávu o dokončení
Dejte uživateli vědět, že operace byla úspěšně dokončena.

```java
System.out.println("Process completed Successfully");
```

Postupováním těmito šesti stručnými kroky jste úspěšně **přidali kalendář do projektu** a uložili výsledek jako XML soubor.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|---------|----------|--------|
| **`NullPointerException` on `prj.getCalendars()`** | Projektový objekt nebyl správně inicializován. | Ujistěte se, že je před přístupem k kalendářům zavoláno `new Project()`. |
| **Soubor nenalezen při ukládání** | `dataDir` ukazuje na neexistující složku. | Nejprve vytvořte adresář nebo použijte absolutní cestu. |
| **Název kalendáře se zobrazuje jako “no info”** | V ukázce byly použity zástupné názvy. | Nahraďte je smysluplnými názvy, které odrážejí rozvrh (např. „Kalendář US Holiday“). |
| **Uložené XML nelze otevřít v MS Project** | Používáte zastaralou verzi Aspose.Tasks. | Aktualizujte na nejnovější verzi Aspose.Tasks pro Java. |

## Často kladené otázky

**Q: Může Aspose.Tasks zpracovat složité kalendáře s více výjimkami?**  
A: Ano – po přidání kalendáře můžete definovat výjimky, pracovní hodiny a nepracovní dny pomocí tříd `WeekDay` a `Exception`.

**Q: Je možné přiřadit nový kalendář konkrétním úkolům?**  
A: Rozhodně. Získejte úkol pomocí `prj.getRootTask().getChildren().add("Task Name")` a nastavte `task.set(Tsk.CALENDAR, cal3);`.

**Q: Podporuje knihovna ukládání do jiných formátů, jako je MPP?**  
A: Ano. Nahraďte `SaveFileFormat.Xml` za `SaveFileFormat.Mpp` nebo `SaveFileFormat.P6` podle potřeby.

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Dočasná zkušební licence stačí pro testování; plná licence je vyžadována pro produkční nasazení.

**Q: Kde mohu získat pomoc, pokud narazím na problémy?**  
A: Komunitní fórum Aspose.Tasks je vynikajícím zdrojem: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Závěr
Používáním Aspose.Tasks pro Java můžete programově **přidat kalendář do projektu**, přizpůsobit pravidla plánování a **uložit projekt jako XML** pomocí několika řádků kódu. Tato automatizace snižuje ruční úsilí, eliminuje lidské chyby a umožňuje hrom zpracování velkých portfolií projektů.

---

**Poslední aktualizace:** 2025-12-02  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}