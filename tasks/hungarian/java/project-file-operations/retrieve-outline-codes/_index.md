---
date: 2026-03-27
description: Tanulja meg, hogyan lehet programozottan lekérni az MS Project vázlatkódjait
  az Aspose.Tasks for Java segítségével. Fejlessze projektmenedzsment képességeit.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project vázlatkódok lekérése az Aspose.Tasks-ben
url: /hu/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project vázkódok lekérése az Aspose.Tasks segítségével

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan lehet lekérni a MS Project vázkódokat** az Aspose.Tasks for Java segítségével. A vázkódok a MS Projectben hatékony módot biztosítanak a feladatok, erőforrások és hozzárendelések kategorizálására, és programozott hozzáférésük lehetővé teszi egyedi jelentések, automatizálás vagy integrációs megoldások létrehozását. Lépésről‑lépésre bemutatunk egy teljes példát, amelyet beilleszthet a saját projektjébe.

## Gyors válaszok
- **Mi a kód feladata?** Betölti a Project fájlt, és kiír minden vázkód definíciót, azok maszkjait és értékeit.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (bármely friss verzió).  
- **Szükségem van licencre?** A próbaverzió fejlesztéshez megfelelő; a termeléshez teljes licenc szükséges.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.  
- **Módosíthatom a kódokat a lekérés után?** Igen – ugyanaz az API lehetővé teszi a vázkódok hozzáadását, szerkesztését vagy törlését.

## Mi az a MS Project vázkód?
A vázkódok egyedi mezők, amelyek lehetővé teszik a projektmenedzserek számára, hogy a feladatokat az alapértelmezett hierarchián túl csoportosítsák és szűrjék. Lehetnek egyszerű numerikus értékek, karakterláncok vagy akár vállalati szintű egyedi kódok, amelyeket a szervezet szintjén definiálnak. Ezeknek a kódoknak a beolvasásával irányíthatja a műszerfalakat, exportálhat adatokat, vagy automatikusan érvényesítheti a névadási konvenciókat.

## Miért kell lekérni a MS Project vázkódokat az Aspose.Tasks segítségével?
- **Automatizálás:** Jelentések generálása vagy munkafolyamatok indítása manuális export nélkül.  
- **Integráció:** Vázkódok szinkronizálása ERP, PPM vagy BI eszközökkel.  
- **Testreszabás:** Üzleti szabályok alkalmazása a kódértékek alapján (pl. költségelosztás).  
- **Keresztplatform:** Windows, Linux és macOS rendszereken működik, a Microsoft Project felhasználói felületétől függetlenül.

## Hogyan olvassuk be az MPP fájlokat a vázkódokhoz?
Az MPP (Microsoft Project) fájl olvasása az első lépés a vázkódok kinyeréséhez. Az Aspose.Tasks elrejti a fájlformátum részleteit, így nem kell magának a bináris struktúrát elemeznie. A `Project` osztály végzi a nehéz munkát, így Ön a ténylegesen szükséges adatokra koncentrálhat.

## Egyedi mezők a MS Projectben
A vázkódok a **custom fields** (egyedi mezők) egy típusa a MS Projectben. Míg a szabványos mezők a dátumokat, időtartamokat és erőforrásokat fedik le, az egyedi mezők lehetővé teszik szervezet‑specifikus információk tárolását. Az Aspose.Tasks-en keresztüli hozzáférés ugyanazt a programozási rugalmasságot biztosítja.

## Előfeltételek
Mielőtt elkezdjük, győződjön meg arról, hogy az alábbi előfeltételek be vannak állítva:

### 1. Java fejlesztői környezet
Győződjön meg róla, hogy a Java Development Kit (JDK) telepítve van a rendszerén. A JDK-t letöltheti és telepítheti az Oracle weboldaláról.

### 2. Aspose.Tasks könyvtár
Töltse le és vegye fel az Aspose.Tasks könyvtárat a Java projektjébe. A könyvtárat letöltheti a [Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először importálja a szükséges csomagokat az Aspose.Tasks-ből a Java kódjában:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Most bontsuk le a megadott példakódot több lépésre:

## 1. lépés: Projekt betöltése
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Ebben a lépésben betöltjük a Microsoft Project fájlt egy `Project` objektumba a megadott fájlnév használatával.

## 2. lépés: Vázkódok lekérése
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Végigiterálunk a projektben lévő minden vázkód definíción.

## 3. lépés: Vázkód tulajdonságok elérése
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Lekérjük és kiírjuk a vázkód definíció különböző tulajdonságait, mint például az Alias, Field ID és Field Name.

## 4. lépés: Vállalati egyedi kód ellenőrzése
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Ellenőrizzük, hogy a vázkód vállalati egyedi kód-e, és ennek megfelelően kiírjuk az eredményt.

## 5. lépés: Vázkód maszkok megjelenítése
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Végigiterálunk a vázkódhoz kapcsolódó minden maszkon, és kiírjuk annak szintjét és maszk értékét.

## 6. lépés: Vázkód értékek megjelenítése
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Végigiterálunk a vázkód minden értékén, és kiírjuk annak leírását, value ID-t, értékét és típusát.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Nincs kimenet** | A projektfájl útvonala helytelen | `projectName` érvényes `.mpp` fájlra mutat. |
| **Null értékek** | A vázkód nincs definiálva a fájlban | Győződjön meg róla, hogy a projektfájl valóban tartalmaz vázkódokat (ellenőrizze a MS Project UI-ban). |
| **LicenseException** | Próverzió használata megfelelő aktiválás nélkül | Alkalmazzon ideiglenes vagy teljes licencet a következővel: `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Tasks for Java-t a vázkódok módosítására egy Project fájlban?**  
A: Igen, az Aspose.Tasks for Java API-kat biztosít a vázkódok programozott módosításához. A definíciókat ugyanazzal a `Project` objektummal hozzáadhatja, szerkesztheti vagy törölheti.

**Q: Elérhető próverzió az Aspose.Tasks for Java-hoz?**  
A: Igen, letölthet egy ingyenes próverziót az Aspose.Tasks for Java-ból a [Aspose.Tasks weboldalról](https://releases.aspose.com/).

**Q: Hogyan kaphatok technikai támogatást az Aspose.Tasks for Java-hoz?**  
A: Technikai támogatást a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) keresztül kaphat, ahol bejegyezheti kérdéseit.

**Q: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java-hoz?**  
A: Igen, ideiglenes licencet vásárolhat az Aspose.Tasks for Java-hoz a [vásárlási oldalon](https://purchase.aspose.com/temporary-license/).

**Q: Hol találom meg a teljes dokumentációt az Aspose.Tasks for Java-hoz?**  
A: A részletes információkért az Aspose.Tasks for Java használatáról tekintse meg a [dokumentációt](https://reference.aspose.com/tasks/java/).

## Összegzés
Ebben az útmutatóban megtanultuk, hogyan kell lekérni a **MS Project vázkódokat** az Aspose.Tasks for Java segítségével. A megadott lépések követésével hatékonyan hozzáférhet és manipulálhatja a vázkódokat Java alkalmazásaiban, lehetővé téve fejlett projektmenedzsment funkciókat, mint például egyedi jelentések, automatizálás és integráció más vállalati rendszerekkel.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}