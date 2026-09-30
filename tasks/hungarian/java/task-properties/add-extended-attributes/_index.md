---
date: 2026-09-30
description: Ismerje meg, hogyan hozhat létre feladat kiterjesztett attribútumot az
  Aspose.Tasks for Java segítségével, a vezető Java projektmenedzsment könyvtárat
  az egyedi feladatterületek hozzáadásához.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Hogyan hozhatunk létre feladat kiterjesztett attribútumot az Aspose.Tasks
  Java segítségével
og_description: Ismerje meg, hogyan hozhat létre feladat kiterjesztett attribútumot
  az Aspose.Tasks for Java segítségével, a vezető Java projektmenedzsment könyvtárat
  az egyedi feladatterületek hozzáadásához.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Hogyan hozhatunk létre feladat kiterjesztett attribútumot az Aspose.Tasks
  Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Hogyan hozhatunk létre feladat kiterjesztett attribútumot az Aspose.Tasks Java
  segítségével
url: /hu/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozhatunk létre feladat kiterjesztett attribútumot az Aspose.Tasks Java-val

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan **hozzon létre feladat kiterjesztett attribútumot** egy Microsoft Project fájlban az Aspose.Tasks for Java használatával. Egyedi mezők hozzáadásával rögzítheti a projektre szabott adatokat, amelyek nincsenek lefedve a beépített oszlopokkal, ezáltal finomabb vezérlést biztosít a jelentéskészítés és az erőforrás-tervezés felett. A útmutató végére képes lesz egyszerű szöveges, keresési lehetőséggel rendelkező és időtartam attribútumokat hozzáadni bármely feladathoz.

## Gyors válaszok
- **Mi a „kiterjesztett attribútum” jelentése?** Ez egy egyedi mező, amelyet definiál és feladatokhoz, erőforrásokhoz vagy hozzárendelésekhez csatol.  
- **Melyik könyvtár biztosítja ezt a képességet?** Aspose.Tasks for Java, egy java projektmenedzsment könyvtár.  
- **Szükségem van licencre a kipróbáláshoz?** Igen – egy ingyenes 30 napos próba elérhető az Aspose weboldaláról.  
- **Hozzáadhatok keresési értékeket?** Természetesen; megadhat egy listát az engedélyezett értékekről szöveg vagy időtartam mezőkhöz.  
- **Az API kompatibilis a Java 8 és újabb verziókkal?** Igen, támogatja a Java 8+ verziókat, és minden főbb operációs rendszeren fut.

## Mi az a feladat kiterjesztett attribútum?
A feladat kiterjesztett attribútum egy felhasználó által definiált oszlop, amely további információkat tárol minden feladatról egy Project fájlban. Úgy viselkedik, mint egy beépített mező, de bármilyen adat típust tárolhat, például szöveget, számokat, dátumokat vagy időtartamokat.

## Miért használjuk az Aspose.Tasks for Java-t?
Az Aspose.Tasks támogat **50+ fájlformátumot**, és képes **10 000+ feladattal** rendelkező projekteket feldolgozni anélkül, hogy a Microsoft Project telepítve lenne. A könyvtár teljesen offline működik, garantálva az adatvédelmet és a determinisztikus teljesítményt vállalati méretű megoldásokhoz.

## Előfeltételek
- Alapvető Java programozási ismeretek.  
- Az Aspose.Tasks for Java könyvtár telepítve van. Letöltheti a [weboldalról](https://releases.aspose.com/tasks/java/).  
- Egy Java IDE (IntelliJ IDEA, Eclipse vagy VS Code) beállítva a gépén.

## Csomagok importálása
A `import` utasítások hozzáférést biztosítanak a szükséges alap osztályokhoz, például a `Project`, `ExtendedAttributeDefinition` és `ExtendedAttribute` osztályokhoz.

A `Project` egy Microsoft Project fájlt képvisel, és metódusokat biztosít annak olvasásához, módosításához és mentéséhez.  
Az `ExtendedAttributeDefinition` egy egyedi mezőt definiál, amely feladatokhoz, erőforrásokhoz vagy hozzárendelésekhez csatolható.  
Az `ExtendedAttribute` egy definíció példánya, amely a konkrét entitás tényleges értékét tárolja.

## Hogyan adhatunk hozzá egyszerű szöveges kiterjesztett attribútumot egy feladathoz?
Egy egyszerű szöveges kiterjesztett attribútum hozzáadásához először betölti a projektet, majd létrehoz egy Text típusú definíciót, hozzáadja a projekt gyűjteményéhez, létrehoz egy feladatot, példányosítja az attribútumot a definícióból, beállítja a szöveges értékét, csatolja a feladathoz, és végül menti a projektet.

### 1. Állítsa be a dokumentum könyvtár útvonalát
Adja meg, hol találhatók a forrás- és kimeneti fájlok.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Hozzon létre egy új projektet
Példányosítson egy `Project` objektumot, opcionálisan betöltve egy meglévő .mpp fájlt.

```java
String dataDir = "Your Document Directory";
```

### 3. Hozzon létre egy Text1 típusú kiterjesztett attribútum definíciót
Definiálja az egyedi mezőt egyszerű szöveges oszlopként, a neve “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Adja hozzá a definíciót a projekt kiterjesztett attribútumok gyűjteményéhez
Regisztrálja az új definíciót, hogy a projekt felismerje.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Adjon hozzá egy feladatot a projekthez
Hozzon létre egy feladatot, amely megkapja az egyedi mezőt.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Hozzon létre egy kiterjesztett attribútumot a definícióból
Generáljon egy példányt, amelyet egy adott feladathoz köthet.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Rendeljen értéket a generált kiterjesztett attribútumhoz
Állítsa be a tényleges szöveget, amelyet tárolni szeretne, például “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Adja hozzá a kiterjesztett attribútumot a feladathoz
Csatolja az attribútum példányt a feladat `ExtendedAttributes` gyűjteményéhez.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Mentse a projektet
Írja vissza a frissített projektet a lemezre a kívánt formátumban.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Hogyan adhatunk hozzá szöveges attribútumot keresési lehetőséggel?
Szöveges attribútum keresési lehetőséggel történő hozzáadásakor ugyanazokat a lépéseket követi, mint az egyszerű szöveges attribútumnál, de a definíció hozzáadása előtt feltölti a `LookupValues` gyűjteményt a megengedett karakterláncokkal. Ezek az értékek legördülő listaként jelennek meg a Microsoft Projectben, biztosítva az adatkonzisztenciát.

## Hogyan adhatunk hozzá időtartam attribútumot keresési lehetőséggel?
Időtartam attribútum keresési lehetőséggel történő hozzáadásához cserélje le a `Text1` típust `Duration2`-re a definíció létrehozásakor, majd töltse fel a `LookupValues` gyűjteményt időtartam karakterláncokkal, például “1 day”, “2 days” stb. Miután a definíció hozzá lett adva a projekthez, hozza létre az attribútum példányt, állítson be egy időtartam értéket, csatolja egy feladathoz, és mentse a fájlt.

## Gyakori problémák és hibaelhárítás
- **A keresési értékek nem jelennek meg** – Győződjön meg róla, hogy minden keresési bejegyzést a `LookupValues` gyűjteményhez *előtt* ad hozzá, mielőtt meghívná a `project.getExtendedAttributes().add(definition)` metódust.  
- **Az attribútum értéke nem lett mentve** – Ellenőrizze, hogy a `ExtendedAttribute` példányt a feladathoz *az érték beállítása után* adja hozzá.  
- **A fájlméret váratlanul nő** – Nagyon nagy projektek esetén fontolja meg a `project.setSaveOptions(new ProjectSaveOptions())` hívását az inkrementális mentés engedélyezéséhez.

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Tasks for Java-t más Java könyvtárakkal?**  
A: Igen, az Aspose.Tasks for Java zökkenőmentesen integrálódik bármely Java ökoszisztémával, beleértve a Spring, Hibernate és Apache POI könyvtárakat.

**Q: Alkalmas az Aspose.Tasks for Java nagy‑léptékű projektmenedzsment alkalmazásokra?**  
A: Teljes mértékben. A könyvtár úgy lett tervezve, hogy több ezer feladatos projekteket kezeljen, és támogatja a streaminget a memóriahasználat alacsonyan tartása érdekében.

**Q: Vannak licencelési szempontok az Aspose.Tasks for Java kereskedelmi projektben való használatához?**  
A: Igen, érvényes kereskedelmi licencre van szükség. A részleteket megtekintheti a [Aspose.Tasks weboldalon](https://purchase.aspose.com/buy).

**Q: Hogyan kaphatok támogatást vagy segítséget az Aspose.Tasks for Java-hoz?**  
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi segítségért, vagy nyisson egy támogatási jegyet az Aspose fiókján keresztül.

**Q: Kipróbálhatom az Aspose.Tasks for Java-t vásárlás előtt?**  
A: Igen, ingyenes próbaverziót érhet el a [Aspose.Tasks ingyenes próba](https://releases.aspose.com/) oldalon.

**Legutóbb frissítve:** 2026-09-30  
**Tesztelve:** Aspose.Tasks for Java 24.10  
**Szerző:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Kapcsolódó oktatóanyagok

- [Egyéni oszlopok és kiterjesztett attribútumok Java projektmenedzsmentben](/tasks/java/project-management/extended-attributes/)
- [Kiterjesztett feladat attribútumok olvasása az Aspose.Tasks for Java-val](/tasks/java/task-properties/extended-task-attributes/)
- [Hogyan hozzunk létre projektet az Aspose.Tasks‑tel – Új feladat attribútumok beállítása](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}