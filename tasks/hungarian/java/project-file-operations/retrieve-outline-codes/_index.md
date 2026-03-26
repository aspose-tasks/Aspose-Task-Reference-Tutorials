---
date: 2025-12-20
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

# MS Project vázlatkódok lekérése Aspose.Tasks segítségével

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan lehet lekérni a MS Project vázlatkódokat** az Aspose.Tasks for Java használatával. A vázlatkódok a MS Projectben erőteljes módot biztosítanak a feladatok, erőforrások és hozzárendelések kategorizálására, és programozott hozzáférésük lehetővé teszi egyedi jelentések, automatizálás vagy integrációs megoldások építését. Lépésről‑lépésre bemutatunk egy komplett példát, amelyet egyszerűen átmásolhat saját projektjébe.

## Gyors válaszok
- **Mit csinál a kód?** Betölti a Project fájlt, és kiírja minden vázlatkód definícióját, annak maszkjait és értékeit.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (bármely friss verzió).  
- **Szükség van licencre?** Fejlesztéshez a próbaverzió is működik; éles környezetben teljes licenc szükséges.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.  
- **Módosíthatom a kódokat a lekérés után?** Igen – ugyanaz az API lehetővé teszi a vázlatkódok hozzáadását, szerkesztését vagy törlését.

## Mik azok a MS Project vázlatkódok?
A vázlatkódok egyedi mezők, amelyek lehetővé teszik a projektmenedzserek számára, hogy a feladatokat a beépített hierarchián túl is csoportosítsák és szűrjék. Lehetnek egyszerű numerikus értékek, karakterláncok vagy akár vállalati szintű egyedi kódok, amelyeket a szervezet definiál. Ezeknek a kódoknak a beolvasásával irányíthatja a műszerfalakat, exportálhat adatokat, vagy automatikusan érvényesítheti a névadási konvenciókat.

## Miért kell lekérni a MS Project vázlatkódokat az Aspose.Tasks használatával?
- **Automatizálás:** Jelentések generálása vagy munkafolyamatok indítása manuális export nélkül.  
- **Integráció:** Vázlatkódok szinkronizálása ERP, PPM vagy BI eszközökkel.  
- **Testreszabás:** Üzleti szabályok alkalmazása a kódértékek alapján (pl. költségallokáció).  
- **Keresztplatformos:** Windows, Linux és macOS rendszereken működik, függetlenül a Microsoft Project felhasználói felületétől.

## Előkövetelmények
Mielőtt elkezdenénk, győződjön meg róla, hogy az alábbi előkövetelmények teljesülnek:

### 1. Java fejlesztői környezet
Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszerén. A JDK-t letöltheti és telepítheti az Oracle weboldaláról.

### 2. Aspose.Tasks könyvtár
Töltse le és adja hozzá az Aspose.Tasks könyvtárat a Java projektjéhez. A könyvtár letölthető a [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) oldalról.

## Csomagok importálása
Első lépésként importálja a szükséges Aspose.Tasks csomagokat a Java kódjában:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Most bontsuk le a megadott példakódot több lépésre:

## 1. lépés: A projekt betöltése
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Ebben a lépésben betöltjük a Microsoft Project fájlt egy `Project` objektumba a megadott fájlnév használatával.

## 2. lépés: Vázlatkódok lekérése
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Végigiterálunk a projekt minden vázlatkód definícióján.

## 3. lépés: Vázlatkód tulajdonságok elérése
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Lekérjük és kiírjuk a vázlatkód definíció különböző tulajdonságait, például az Alias, Field ID és Field Name értékeket.

## 4. lépés: Vállalati egyedi kód ellenőrzése
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Ellenőrizzük, hogy a vázlatkód vállalati egyedi kód-e, és ennek megfelelően kiírjuk az eredményt.

## 5. lépés: Vázlatkód maszkok megjelenítése
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Végigiterálunk a vázlatkódhoz tartozó minden maszkon, és kiírjuk annak szintjét és maszk értékét.

## 6. lépés: Vázlatkód értékek megjelenítése
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Végigiterálunk minden vázlatkód értéken, és kiírjuk a leírását, értékazonosítóját, értékét és típusát.

## Gyakori problémák és megoldások
| Probléma | Ok | Javítás |
|----------|----|---------|
| **Nincs kimenet** | A projektfájl útvonala helytelen | Ellenőrizze, hogy a `projectName` egy érvényes `.mpp` fájlra mutat. |
| **Null értékek** | A vázlatkód nincs definiálva a fájlban | Győződjön meg róla, hogy a projektfájl ténylegesen tartalmaz vázlatkódokat (ellenőrizze az MS Project felhasználói felületen). |
| **LicenseException** | Próbaverzió használata megfelelő aktiválás nélkül | Alkalmazzon ideiglenes vagy teljes licencet a `License license = new License(); license.setLicense("Aspose.Tasks.lic");` kóddal. |

## Gyakran ismételt kérdések

**K: Használhatom az Aspose.Tasks for Java-t a vázlatkódok módosítására egy projektfájlban?**  
V: Igen, az Aspose.Tasks for Java API-k biztosítják a vázlatkódok programozott módosítását. Definíciókat hozzáadhat, szerkeszthet vagy törölhet ugyanazzal a `Project` objektummal.

**K: Elérhető próba verzió az Aspose.Tasks for Java-hoz?**  
V: Igen, letölthet egy ingyenes próbaverziót az Aspose.Tasks for Java‑ból a [Aspose.Tasks weboldaláról](https://releases.aspose.com/).

**K: Hogyan kaphatok technikai támogatást az Aspose.Tasks for Java-hoz?**  
V: Technikai támogatást a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) keresztül kaphat, ahol kérdéseit közzéteheti.

**K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java-hoz?**  
V: Igen, ideiglenes licencet vásárolhat az Aspose.Tasks for Java‑hoz a [vásárlási oldalon](https://purchase.aspose.com/temporary-license/).

**K: Hol találom meg az Aspose.Tasks for Java teljes dokumentációját?**  
V: A részletes információkért tekintse meg a [dokumentációt](https://reference.aspose.com/tasks/java/).

## Következtetés
Ebben az útmutatóban megtanultuk, hogyan lehet **MS Project vázlatkódokat** lekérni az Aspose.Tasks for Java segítségével. A bemutatott lépések követésével hatékonyan hozzáférhet és manipulálhatja a vázlatkódokat Java alkalmazásaiban, lehetővé téve fejlett projektmenedzsment funkciókat, például egyedi jelentéseket, automatizálást és integrációt más vállalati rendszerekkel.

---

**Utolsó frissítés:** 2025-12-20  
**Tesztelve:** Aspose.Tasks for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}