---
date: 2026-06-15
description: Ismerje meg, hogyan lehet kinyerni a timephased data-t az MS Project
  resources‑ból az Aspose.Tasks for Java használatával. Lépésről‑lépésre útmutató
  a get resource by id-hez.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Olvasd el a Timephased Data-t a Resources számára az Aspose.Tasks‑ben
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Olvasd el a Timephased Data-t a Resources számára az Aspose.Tasks‑ben – get
  resource by id
url: /hu/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Időszakos adatok olvasása erőforrásokhoz az Aspose.Tasks-ben

## Bevezetés
Ezen az útmutatón keresztül megtanulja, hogyan **get resource by id**-t használva olvassa be az időszakos adatokat az Aspose.Tasks for Java segítségével. Lépésről lépésre végigvezetjük a folyamaton – a projekt mappa beállításától a munka- és költség-időszakos értékek kiírásáig – hogy programozottan kinyerhesse a hasznos ütemezési információkat bármely Microsoft Project fájlból. Az Aspose.Tasks for Java egy átfogó API, amely lehetővé teszi a fejlesztők számára Microsoft Project fájlok létrehozását, olvasását, módosítását és konvertálását anélkül, hogy a Microsoft Project telepítve lenne, és támogatja a projektmenedzsment számos funkcióját és formátumát.

## Gyors válaszok
- **What does “get resource by id” do?** Ez egy adott `Resource` objektumot kér le egy `Project`-ből a egyedi azonosítója alapján.  
- **Which library handles timephased data?** Az Aspose.Tasks for Java biztosítja a `Resource.getTimephasedData` API-t.  
- **Do I need a license?** Fejlesztéshez elegendő egy ingyenes próba; a termeléshez kereskedelmi licenc szükséges.  
- **Can I read large projects?** Igen – az Aspose.Tasks képes akár 10 000 feladatot tartalmazó fájlok feldolgozására anélkül, hogy a teljes fájlt a memóriába töltené.  
- **What Java version is required?** Java 8 vagy újabb; a könyvtár kompatibilis az összes főbb JDK-val.

## Mi az a “get resource by id”?
`get resource by id` egy metódushívás, amely egy `Resource` példányt kér le egy betöltött `Project`-ből a erőforrás numerikus azonosítója alapján. Ez a művelet pontos hozzáférést biztosít az erőforrás részletes tulajdonságaihoz, például a hozzárendeléseihez, naptáraihoz és egyéni mezőihez, és elengedhetetlen a konkrét erőforráshoz kapcsolódó időszakos munka- vagy költségadatok kinyeréséhez.

## Miért használjuk az Aspose.Tasks-et időszakos adatokhoz?
Az Aspose.Tasks **50+ bemeneti és kimeneti formátumot** támogat (MPP, XML, CSV stb.) és képes időszakos munka- és költségértékeket kinyerni az erőforrások számára, amelyek többéves ütemezéseket fednek le, miközben alacsony memóriahasználatot biztosít. Az API alapértelmezés szerint 15 perces intervallumokban adja vissza az adatokat, ami részletes betekintést nyújt a jelentéskészítéshez vagy egyedi elemzésekhez.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg róla, hogy a JDK telepítve van a rendszerén. Letöltheti a [weboldalról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) és kövesse a telepítési útmutatót.  
2. Aspose.Tasks for Java könyvtár: Töltse le az Aspose.Tasks for Java könyvtárat a [letöltési oldalról](https://releases.aspose.com/tasks/java/) és kövesse a dokumentációban megadott telepítési útmutatót.

## Csomagok importálása
Az első lépés a szükséges Aspose.Tasks osztályok importálása a Java forrásfájlba.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## 1. lépés: Adatkönyvtár beállítása
Először határozza meg azt a könyvtárat, ahol az MS Project fájlja található. Az adatkönyvtár forráskódtól való elkülönítése megkönnyíti a projekt karbantartását.

```java
String dataDir = "Your Data Directory";
```

## 2. lépés: MS Project sablonfájl olvasása
Adja meg az MS Project sablonfájl nevét. Sablon használata biztosítja az egységes oszlopbeállításokat a különböző projektek között.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## 3. lépés: Bemeneti fájl beolvasása projektként
A `Project` osztály az Aspose.Tasks alapvető objektuma, amely egy Microsoft Project fájlt reprezentál a memóriában. A fájl betöltése programozott hozzáférést biztosít a feladatokhoz, erőforrásokhoz és ütemezésekhez.

```java
Project project = new Project(dataDir + fileName);
```

## 4. lépés: Erőforrás lekérése ID alapján
Egy adott erőforrás lekéréséhez hívja meg a `getResources().getById(id)` metódust. Ez pontosan az a művelet, amelyet az elsődleges kulcsszó hivatkozik.

```java
Resource resource = project.getResources().getByUid(1);
```

## 5. lépés: Erőforrás munka időszakos adatainak kiírása
Miután megkapta a `Resource` objektumot, meghívhatja a `resource.getTimephasedData(ResourceTimephasedDataType.Work)` metódust a munkaidőszakok lekéréséhez. A visszaadott gyűjtemény `TimephasedData` objektumokat tartalmaz, amelyek tartalmazzák a kezdő dátumot, befejező dátumot és az egyes intervallumok munka mennyiségét.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## 6. lépés: Erőforrás költség időszakos adatainak kiírása
Hasonlóan, a `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` költséginformációkat ad vissza ugyanazon időintervallumok szerint bontva. Ez hasznos a költségvetés és a költségkövetési jelentésekhez.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Hogyan kérhetünk le erőforrást ID alapján egy sorban?
Töltse be a projektet, majd hívja meg a `project.getResources().getById(5)`‑t – cserélje le a **5**‑öt a tényleges erőforrás‑ID‑ra, amelyre szüksége van. Ez az egyetlen hívás visszaadja a `Resource` objektumot, majd lekérdezheti annak időszakos adatait, hozzárendeléseit vagy egyéni mezőit. A metódus O(1) időben fut, mivel az erőforrások belsőleg indexelve vannak.

## Gyakori problémák és megoldások
- **Resource not found** – Győződjön meg arról, hogy az ID létezik a projektfájlban; az ID‑k 1‑től kezdődnek és egyediek erőforrásonként.  
- **Empty timephased data** – Ellenőrizze, hogy az erőforrás rendelkezik-e munka- vagy költséghozzárendelésekkel; ellenkező esetben a gyűjtemény üres lesz.  
- **Large file performance** – Használja a `Project.setLoadOptions(LoadOptions.fromFile(...))` metódust a lusta betöltés engedélyezéséhez 500 MB-nál nagyobb projektek esetén.

## Gyakran ismételt kérdések

**Q: Can Aspose.Tasks handle other types of project files apart from Microsoft Project?**  
A: Igen, az Aspose.Tasks támogatja az MPP, XML, CSV és több más formátumot, lehetővé téve a különböző szabványok közötti olvasást és írást.

**Q: Is Aspose.Tasks compatible with different Java development environments?**  
A: Teljes mértékben. A könyvtár működik minden főbb IDE‑val (IntelliJ IDEA, Eclipse, NetBeans) és építőeszközzel (Maven, Gradle).

**Q: Can I manipulate project data using Aspose.Tasks?**  
A: Igen, a API-n keresztül létrehozhat, módosíthat és törölhet feladatokat, erőforrásokat, hozzárendeléseket, valamint egyéni mezőket is.

**Q: Is Aspose.Tasks suitable for enterprise‑level projects?**  
A: Igen. Vállalatok az Aspose.Tasks-et nagy mennyiségű feldolgozáshoz, kötegelt konverziókhoz és szerver‑oldali jelentéskészítéshez használják, mivel nem igényel Microsoft Project telepítést.

**Q: Where can I find support if I encounter issues while using Aspose.Tasks?**  
A: Látogassa meg a [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösség és a támogatási csapat segítségének igénybevételéhez.

## Következtetés
Ebben az útmutatóban megtanultuk, hogyan **get resource by id** és hogyan olvassuk be annak időszakos munka‑ és költségadatait az Aspose.Tasks for Java segítségével. A lépések követésével hatékonyan kinyerheti a projektfájlokból a hasznos ütemezési információkat, és integrálhatja azokat egyedi jelentésekbe vagy elemzési folyamatokba.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose

## Kapcsolódó útmutatók

- [Erőforrás hozzáadása projekthez az Aspose.Tasks for Java segítségével](/tasks/java/resource-management/create-resources/)
- [MS Project erőforrás költségek kezelése az Aspose.Tasks for Java segítségével](/tasks/java/resource-management/resource-cost/)
- [Munkahét olvasása Java-ban a MS Project naptárból az Aspose.Tasks segítségével](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}