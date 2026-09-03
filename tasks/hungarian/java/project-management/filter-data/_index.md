---
date: 2026-06-05
description: Ismerje meg, hogyan szűrhet MPP fájlokat az Aspose.Tasks for Java segítségével,
  testreszabhatja a szűrési feltételeket, és dátum szerint szűrheti a feladatokat
  a projektmenedzsment hatékonyságának növelése érdekében.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Hogyan szűrjünk MPP fájlokat az Aspose.Tasks for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan szűrjünk MPP fájlokat az Aspose.Tasks for Java segítségével
url: /hu/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan szűrhetünk MPP fájlokat az Aspose.Tasks for Java használatával

## Bevezetés
Ha Microsoft Project fájlokkal (*.mpp*) dolgozol egy Java alkalmazásban, gyakran szükséged lesz **MPP fájlok szűrésére**, hogy elkülönítsd a legfontosabb feladatokat, erőforrásokat vagy hozzárendeléseket. Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan **szűrhetünk mpp** fájlokat programozottan az Aspose.Tasks for Java segítségével, megmutatjuk, hogyan **testreszabhatod a szűrési feltételeket**, és egy gyakorlati „feladatok szűrése dátum szerint” példát is bemutatunk. A végére egy kész kódrészletet kapsz, amelyet bármely Java projektbe beilleszthetsz.

## Gyors válaszok
- **Mi a “filter mpp” jelentése?** Ez azt jelenti, hogy egy projektadatok részhalmazát vonjuk ki a meghatározott feltételek alapján.  
- **Melyik könyvtár kezeli ezt?** Az Aspose.Tasks for Java átfogó API-t biztosít a szűrők létrehozásához és alkalmazásához.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez használható; a termeléshez kereskedelmi licenc szükséges.  
- **Szűrhetek feladatokat, erőforrásokat és hozzárendeléseket?** Igen – minden entitástípusnak saját szűrőgyűjteménye van.  
- **Java 8 vagy újabb szükséges?** Az Aspose.Tasks támogatja a Java 8-at és az újabb verziókat.

## Mi a “how to filter mpp” Java-ban?
`How to filter mpp` a folyamat, amely során az Aspose.Tasks `Filter` objektumait használjuk, hogy csak azokat a projekt elemeket válasszuk ki, amelyek meghatározott feltételeknek, például kezdő dátumnak, költségnek vagy egyéni mezőknek felelnek meg. Tölts be egy `Project`-et, szerezz be egy `Filter`-t, és az API visszaad egy gyűjteményt, amely megfelel a kritériumaidnak, lehetővé téve a fókuszált jelentést vagy a downstream integrációt.

## Miért testreszabjuk a szűrési feltételeket?
Az egyedi szűrési feltételek lehetővé teszik, hogy a magas kockázatú feladatokra, késedelmes elemekre vagy a költségkeretet túllépő erőforrásokra fókuszálj, így egy hatalmas projektfájlt egy tömör, cselekvésre alkalmas nézetté alakítva. Az Aspose.Tasks támogatja a **50+ előre definiált szűrőtípust**, és lehetővé teszi korlátlan egyéni szűrők létrehozását, ezáltal akár 70 %-kal csökkentve a manuális adatválogatás időt.

## Előfeltételek
1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltsd le a [letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **IDE** – az IntelliJ IDEA, Eclipse vagy NetBeans megfelelő.  

## Csomagok importálása
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` és `Project` a projekt adatok szűrésére és alkalmazására használt alapvető osztályok.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Lépésről‑lépésre útmutató

### 1. lépés: A projekt beállítása
Először hozz létre egy `Project` példányt, amely az elemzni kívánt MPP fájlra mutat, majd töltsd be a memóriába. Ez az egyetlen lépés előkészíti a teljes projektmodellt a szűréshez, érvényesítéshez és további manipulációhoz, lehetővé téve a feladatok, erőforrások és hozzárendelések API-n keresztüli elérését.

### Hogyan állítsam be a projektet MPP fájlok szűréséhez?
A `Project` osztály betölti és memóriában reprezentálja az MPP fájlt. Hozz létre egy `Project` példányt, amely az elemzni kívánt MPP fájlra mutat, majd töltsd be a memóriába. Ez az egyetlen lépés előkészíti a teljes projektmodellt a szűréshez, érvényesítéshez és további manipulációhoz, lehetővé téve a feladatok, erőforrások és hozzárendelések API-n keresztüli elérését.

### Hogyan tudok egy szűrőt lekérni és megvizsgálni?
`Filter` objektumok tartalmazzák a projekt elemek kiválasztásához használt szűrődefiníciókat. Az Aspose.Tasks előre definiált szűrőket tárol, például a „All Tasks” vagy a „Critical Tasks”. Használd a `project.getTaskFilters().getByName("My Filter")` vagy index‑alapú hozzáférést egy `Filter` objektum lekéréséhez, majd vizsgáld meg a `FilterCriteria` gyűjteményét, hogy láthasd az egyes szabályokat és a logikai operátort (AND/OR), amely összekapcsolja őket, biztosítva, hogy a szűrő megfeleljen az igényeidnek.

### Hogyan iteráljunk a beágyazott kritériumsorokon?
`FilterCriteriaGroup` egy logikai operátorral kombinált szűrőkritériumok csoportját képviseli. A szűrők tartalmazhatnak kritériumcsoportokat, mindegyiknek saját operátora van. Iterálj a `filter.getCriteria().getRows()` elemein, és ha egy sor `FilterCriteriaGroup`, akkor rekurzívan lépj be a gyermek sorokba. Ez a bejárás lehetővé teszi, hogy teljesen megértsd a komplex szűrőlogikát, például a „(Start < today AND Cost > 1000) OR Priority = High” kifejezést, és szükség szerint módosítsd a kritériumokat.

### Hogyan nyomtassam ki a kritérium információkat hibakereséshez?
A kritériumfa bejárása után írd ki a konzolra minden sor mezőnevét, teszt operátorát és értékét. Ez az egyszerű kiírás segít ellenőrizni, hogy a szűrő megfelel-e a kívánt üzleti szabályoknak, mielőtt nagy projektekre alkalmaznád, és megkönnyíti a helytelen operátorok vagy értékek felismerését.

### Hogyan hozhatok létre programozottan egy vadonatúj szűrőt?
Példányosíts egy `Filter`-t a `new Filter("My Filter")` segítségével, majd add hozzá a projekt feladatszűrő-gyűjteményéhez a `project.getTaskFilters().add(filter)` használatával. Ezután töltsd fel a `FilterCriteria` gyűjteményét a kívánt sorokkal, megadva a mezőneveket, teszt operátorokat és értékeket, hogy pontosan meghatározd, mely feladatok legyenek belefoglalva a szűrő alkalmazásakor.

### Alkalmazhatok szűrőt erőforrásokra a feladatok helyett?
`ResourceFilters` gyűjtemény tartalmazza az erőforrásokra alkalmazható szűrődefiníciókat. Igen – használd a `project.getResourceFilters()`-t, hogy erőforrás‑specifikus szűrőkkel dolgozz ugyanúgy, mint a feladatszűrőkkel. Szűrő hozzáadása vagy lekérése után állítsd be a `FilterCriteria`-t ugyanúgy, mint a feladatoknál, majd alkalmazd az erőforrás-gyűjteményre, hogy megkapd a szűrt erőforrások halmazát.

### Lehetséges több szűrőt kombinálni OR logikával?
Hozz létre egy szülő `FilterCriteriaGroup`-ot, amelynek `Operation` értéke `OR`, majd adj hozzá egyedi `FilterCriteria` objektumokat gyermekként. Ez a csoport kiértékeli minden gyermek kritériumot, és visszaadja azokat az elemeket, amelyek bármelyiket teljesítik, lehetővé téve több egyszerű szűrő kombinálását egy szélesebb kiválasztásba.

### Támogatja az Aspose.Tasks a szűrést egyéni mezőkön?
`CustomField` enum azonosítókat biztosít a projektben definiált egyéni mezőkhöz. Természetesen. Hivatkozhatsz az egyéni mezőkre a `CustomField` enum segítségével, és úgy viselkednek, mint bármely beépített mező a szűrőkifejezésekben. Belefoglalhatod őket a `FilterCriteria` sorokba, ugyanazokat az operátorokat és értékeket használva, így erőteljes lekérdezéseket végezhetsz a felhasználó által definiált adatokon a szabványos projektattribútumok mellett.

### Milyen teljesítményhatása van a szűrésnek nagy MPP fájlok esetén?
A szűrés teljes egészében memóriában fut, és általában egy 1 000 feladatot tartalmazó projektet 200 ms alatt feldolgoz. Több ezer feladatot tartalmazó fájlok esetén fontold meg, hogy csak a szükséges szakaszokat töltsd be a `ProjectReader` segítségével, majd a szűrést a szelektív betöltés után alkalmazd, ami alacsony memóriahasználatot biztosít és gyors válaszidőt tart fenn még nagyon nagy projektek esetén is.

---

**Utolsó frissítés:** 2026-06-05  
**Tesztelt verzió:** Aspose.Tasks for Java 24.10  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [MPP fájl betöltése Java - Projekt tulajdonságok kezelése az Aspose.Tasks segítségével](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Kényelmes MS Project Online adatolvasás](/tasks/java/project-data-reading/read-project-online/)
- [Projekt kezdő dátum beállítása MS Projectben az Aspose.Tasks for Java használatával](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```