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

## Introduction
Ebben az átfogó oktatóanyagban megtanulja, hogyan **olvassa ki a kiterjesztett feladatattribútumokat** a Microsoft Project fájlokból az Aspose.Tasks Java könyvtár használatával. Akár jelentéskészítő eszközt épít, adatot szinkronizál, vagy egyszerűen csak mélyebb betekintést igényel az egyéni mezőkbe, ennek a funkciónak a elsajátítása lehetővé teszi, hogy minden, a projektben tárolt információt kinyerjen. Bemutatjuk a szükséges beállításokat, megmutatjuk, hogyan válthat egyéni mező típust az attribútumok feldolgozása során, és gyakorlati tippeket adunk a gyakori buktatók elkerüléséhez.

## Quick Answers
- **Mit jelent a „kiterjesztett feladatattribútumok olvasása”?** Ez a projektfájlban a alapértelmezett feladattulajdonságokon túlmutató egyéni mezőértékek kinyerését jelenti.  
- **Melyik osztály biztosít hozzáférést ezekhez az attribútumokhoz?** Az `ExtendedAttribute` osztály az Aspose.Tasks-ben.  
- **Szükségem van licencre a kód futtatásához?** Fejlesztéshez egy ingyenes próba verzió elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Válthatok az attribútum típusát futásidőben?** Igen – használja a `switch` utasítást a **custom field type váltásához** a `CustomFieldType` alapján.  
- **Kompatibilis ez a Java 8 és újabb verziókkal?** Teljesen, az API támogatja a JDK 8+ verziókat.

## What is read extended task attributes?
A kiterjesztett feladatattribútumok felhasználó által definiált mezők (szöveg, dátum, szám, jelző stb.), amelyek kiegészítik a Microsoft Project szabványos feladattulajdonságait. Az Aspose.Tasks a `ExtendedAttribute` gyűjteményen keresztül teszi elérhetővé ezeket, amely minden `Task` objektumhoz csatolva van, lehetővé téve az értékek programozott olvasását vagy módosítását.

## Why read extended task attributes?
- **Teljes átláthatóság:** Megismerheti a projekt ütemtervéhez a résztvevők által hozzáadott egyéni adatokat.  
- **Automatizálás:** Töltsön fel irányítópultokat, generáljon egyéni jelentéseket, vagy migrálja az adatokat más rendszerekbe manuális export nélkül.  
- **Rugalmasság:** Bármilyen egyéni mezőtípus kezelhető – szöveg, dátum, időtartam, költség, jelző – a megfelelő esetek szerinti kezelés révén.

## Prerequisites
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:
- Alapvető Java programozási ismeretekkel.  
- Telepített Java Development Kit (JDK) környezettel.  
- Egy IDE-vel, például IntelliJ IDEA vagy Eclipse.

## Import Packages
Kezdje a szükséges osztályok importálásával az Aspose.Tasks projekthez:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Step 1: Accessing Task and Extended Attributes
Töltsön be egy Project fájlt, és iteráljon végig minden feladaton, hogy elérje azok kiterjesztett attribútumait:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Step 2: Retrieving Field ID and Value GUID
Írassa ki a belső azonosítókat, amelyek segítenek megérteni, melyik egyéni mezővel dolgozik:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Step 3: How to switch custom field type when reading extended task attributes
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

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Null values returned** | Ellenőrizze, hogy az egyéni mező valóban ki van-e töltve a forrás .mpp fájlban. |
| **Incorrect type displayed** | Győződjön meg róla, hogy a `switch` utasításban a megfelelő `CustomFieldType`-ot használja; a nem egyező típusok alapértelmezett értékeket eredményeznek. |
| **Performance slowdown on large projects** | Feldolgozza a feladatokat kötegekben, vagy szűrje csak a szükséges feladatokat a `project.getRootTask().getChildren().stream()` megfelelő predikátumokkal. |

## Frequently Asked Questions
### Can I modify extended task attributes programmatically?
Igen, az Aspose.Tasks for Java segítségével módosíthatja a kiterjesztett feladatattribútumokat. Részletes útmutatásért tekintse meg a dokumentációt.

### Is there a trial version available?
Igen, a ingyenes próbaverziót **[itt](https://releases.aspose.com/)** érheti el.

### Where can I find support for Aspose.Tasks for Java?
Támogatásért látogasson el az **[Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15)**.

### How can I obtain a temporary license?
Ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/)** szerezhet be.

### Where can I purchase the full version of Aspose.Tasks for Java?
A teljes verziót **[itt](https://purchase.aspose.com/buy)** vásárolhatja meg.

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks Java API (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}