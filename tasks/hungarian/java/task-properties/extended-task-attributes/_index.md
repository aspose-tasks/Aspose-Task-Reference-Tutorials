---
date: 2026-01-28
description: Tanulja meg, hogyan olvassa el a kiterjesztett feladatattribútumokat
  az Aspose.Tasks for Java használatával, és hogyan válthat hatékonyan egyéni mező
  típust.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Kiterjesztett feladatattribútumok olvasása az Aspose.Tasks for Java-val
url: /hu/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kiterjesztett feladatattribútumok olvasása az Aspose.Tasks for Java segítségével

## Bevezetés
Ebben az átfogóoktatóanyagban megtanulja, hogyan **olvassa ki a kiterjesztett feladataitribútumokat** a Microsoft Project fájlokból az Aspose.Tasks Java könyvtárat használja. Akár jelentéskész eszközt épít, adatot szinkronizál, vagy egyszerűen csak mélyebb betekintést igényel az egyéni mezőkbe, ennek a funkciónak az elsajátításának lehetővé tétele teszi, hogy minden, a projektben tárolt információkat kinyerjen. Bemutatjuk a szükséges beállításokat, megmutatjuk, hogyan válthat egyéni mező típust az attribútumok feldolgozása során, és gyakorlati tippeket adunk a gyakori buktatók elkerüléséhez.

## Gyors válaszok
- **Mit jelent a „kiterjesztett feladatatribútumok”?** Ez a projektolvasási fájlban a telepített feladattulajdonságokon túlmutató egyéni mezőértékek kinyerését jelenti.
- **Melyik osztály biztosít hozzáférést ezekhez az attribútumokhoz?** Az `ExtendedAttribute` osztály az Aspose.Tasks-ben.
- **Szükségem van licencre a kód futtatásához?** Fejlesztéshez egy ingyenes próbaverzió elegendő; a termeléshez kereskedelmi licenc szükséges.
- **Válthatok az attribútum típusát futásidőben?** Igen – használja az utasítást a `switch` a **custom field type váltásához** a `CustomFieldType` alapján.
- **Kompatibilis ez a Java8 és újabb verziókkal?** Teljesen, az API támogatja a JDK8+ verziókat.

## Mi az a kiterjesztett feladat attribútumainak olvasása?
A kiterjesztett feladattribútumok felhasználó által meghatározott mezők (szöveg, dátum, szám, jelző stb.), valamint kiegészítik a Microsoft Project szabványos feladattulajdonságait. Az Aspose.Tasks a `ExtendedAttribute` gyűjteményen keresztül teszi elérhetővé ezeket, amelyek minden `Task` objektumhoz csatolva van, lehetővé téve az értékek programozott olvasását vagy módosítását.

## Miért érdemes a kiterjesztett feladat attribútumait olvasni?
- **Teljes átláthatóság:** Megismerheti a projekt ütemtervéhez a résztvevők által hozzáadott egyéni adatokat.
- **Automatizálás:** Töltsön fel irányítópultokat, generáljon egyéni jelentéseket, vagy migrálja az adatokat más rendszerekbe manuális export nélkül.
- **Rugalmasság:** Bármilyen egyéni mezőtípus kezelhető – szöveg, dátum, határidő, költség, jelző – a megfelelő esetek szerinti kezelés révén.

## Előfeltételek
Mielőtt elkezdenénk, g meg róla, hogy rendelkezik:
- Alapvető Java programozási ismeretekkel.
- Telepített Java Development Kit (JDK) környezettel.
- Egy IDE-vel, például IntelliJ IDEA vagy Eclipse.

## Csomagok importálása
Kezdje a szükséges osztályok importálásával az Aspose.Tasks projekthez:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## 1. lépés: Feladat és bővített attribútumok elérése
Töltsön be egy Project fájlt, és iteráljon végig minden feladaton, hogy elérje azok kiterjesztett attribútumait:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## 2. lépés: Mezőazonosító és érték GUID lekérése
Írassa ki a belső azonosítókat, amelyek segítenek megérteni, melyik egyéni mezővel dolgozik:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## 3. lépés: Egyéni mezőtípus váltása bővített feladatattribútumok olvasása közben
Használjon `switch` utasítást a `CustomFieldType` alapján, hogy minden lehetséges adattípust helyesen kezeljen:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Ismételje meg ezeket a lépéseket minden feladatra a projektben, hogy felfedezze és manipulálja a kiterjesztett feladatattribútumokat.

## Gyakori problémák és megoldások
| Kiadás | Megoldás |
|-------|-----------|
| **Null értékek visszaadása** | hogy az egyéni mező valóban ki van-e töltve a forrás .mpp fájlban. |
| **Nem megfelelő típus jelenik meg** | G mind meg róla, hogy a `switch` utasításban a megfelelő `CustomFieldType`-ot használja; a nem egyező típusok megállapított értékeket meghatároznak. |
| **A nagy projektek teljesítményének lassulása** | Feldolgozza a feladatokat kötegekben, vagy csak a szükséges feladatokat a `project.getRootTask().getChildren().stream()` megfelelő predikátumokkal. |

## Gyakran Ismételt Kérdések
### Módosíthatom a kiterjesztett feladat attribútumait programozottan?
Igen, az Aspose.Tasks for Java segítségével módosíthatja a kiterjesztett feladattribútumokat. Részletes útmutatásért tekintse meg a dokumentációt.

### Elérhető próbaverzió?
Igen, az ingyenes próbaverziót **[itt](https://releases.aspose.com/) ** érheti el.

### Hol találok támogatást az Aspose.Tasks for Java számára?
Támogatásért látogasson el az **[Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15) **.

### Hogyan szerezhetek ideiglenes engedélyt?
Ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/) ** szerezhet be.

### Hol vásárolhatom meg az Aspose.Tasks for Java teljes verzióját?
A teljes verziót **[itt](https://purchase.aspose.com/buy) ** vásárolhatja meg.

---

**Utolsó frissítés:** 2026. 01. 28
**Tesztelve:** Aspose.Tasks Java API (legújabb stabil kiadás)
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}