---
title: Kibővített feladatattribútumok az Aspose.Tasks-ban
linktitle: Kibővített feladatattribútumok az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Fedezze fel a kiterjesztett feladatattribútumokat az Aspose.Tasks for Java programban. Lépésről lépésre útmutató, GYIK és támogatás. Optimalizálja projektmenedzsmentjét még ma!
type: docs
weight: 16
url: /hu/java/task-properties/extended-task-attributes/
---
## Bevezetés
Üdvözöljük átfogó útmutatónkban az Aspose.Tasks for Java kiterjesztett feladatattribútumainak kihasználásáról. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a Microsoft Project dokumentumokkal való zökkenőmentes kezelést. Ebben az oktatóanyagban a kibővített feladatattribútumokba fogunk beleásni, és bemutatjuk, hogyan használhatja őket projektmenedzsmenti képességei fejlesztésére.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java programozási alapismeretek.
- Java Development Kit (JDK) telepítése a gépen.
- Integrált fejlesztői környezet (IDE), például IntelliJ vagy Eclipse.
## Csomagok importálása
Kezdje a szükséges csomagok importálásával az Aspose.Tasks projekt elindításához:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Most bontsuk le a példát több lépésre, hogy végigvezetjük a folyamaton:
## 1. lépés: A feladat és a kiterjesztett attribútumok elérése
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## 2. lépés: Mezőazonosító és érték GUID lekérése
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## 3. lépés: Különböző attribútumtípusok kezelése
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
Ismételje meg ezeket a lépéseket a projekt minden egyes feladatánál a kiterjesztett feladatattribútumok felfedezéséhez és kezeléséhez.
## Következtetés
Összefoglalva, az Aspose.Tasks for Java kiterjesztett feladatattribútumainak megértése és használata jelentősen javíthatja projektkezelési képességeit. Ez az útmutató szilárd alapot nyújt ahhoz, hogy elinduljon ezen az úton.
## Gyakran Ismételt Kérdések
### Módosíthatom programozottan a kiterjesztett feladatattribútumokat?
Igen, az Aspose.Tasks for Java segítségével módosíthatja a kiterjesztett feladatattribútumokat. A részletes utasításokat a dokumentációban találja.
### Létezik próbaverzió?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### Hol találok támogatást az Aspose.Tasks for Java számára?
 Támogatásért keresse fel a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### Hogyan szerezhetek ideiglenes engedélyt?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Hol vásárolhatom meg az Aspose.Tasks for Java teljes verzióját?
 Megvásárolhatja a teljes verziót[itt](https://purchase.aspose.com/buy).