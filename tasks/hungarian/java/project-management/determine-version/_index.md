---
date: 2026-05-31
description: Ismerje meg, hogyan szerezheti meg a projekt verzióját és hogyan kérheti
  le az utolsó mentés dátumát az MS Project fájlokból az Aspose.Tasks for Java használatával.
  Lépésről‑lépésre útmutató kódrészletekkel.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Projekt verzió meghatározása az Aspose.Tasks segítségével
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan szerezze meg a projekt verzióját – Aspose Tasks Java bemutató
url: /hu/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan lehet lekérni a projekt verzióját – Aspose Tasks Java útmutató

Ebben a **Aspose Tasks Java útmutatóban** megtanulja, **hogyan lehet lekérni a projekt verzióját** egy Microsoft Project fájlból, valamint hogyan **kérhető le az utolsó mentés dátuma** az Aspose.Tasks Java könyvtár segítségével. A fájl verziójának és a mentés időbélyegének ismerete segít elkerülni a kompatibilitási problémákat, érvényesíteni a migrációs irányelveket, és pontos audit naplókat vezetni. Lépésről lépésre végigvezetjük – a környezet beállításától a verzió és dátum kiírásáig –, hogy magabiztosan beépíthesse ezt az ellenőrzést bármely Java alkalmazásba.

## Gyors válaszok
- **Mi a tutorial témája?** A MS Project fájl verziójának és az utolsó mentés dátumának meghatározása az Aspose.Tasks for Java segítségével.  
- **Szükségem van a Microsoft Project telepítésére?** Nem, az Aspose.Tasks függetlenül működik a Microsoft Projecttől.  
- **Mely fájlformátumok támogatottak?** XML‑alapú Project fájlok, például MPP és XML teljes mértékben támogatottak.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alap verzióellenőrzéshez.  
- **Szükséges licenc?** Az ingyenes próba a kiértékeléshez elegendő; a termelésben való használathoz kereskedelmi licenc szükséges.

## Mi az Aspose Tasks Java útmutató?
`Aspose.Tasks` Java útmutató egy tömör, gyakorlati útmutató, amely bemutatja, hogyan lehet programozott módon interakcióba lépni a Microsoft Project adatokkal. Megmutatja, hogyan lehet olvasni, módosítani és elemezni a projektinformációkat anélkül, hogy a szerveren telepített Microsoft Projectre lenne szükség. Emellett lefedi a fájlok betöltését, a tulajdonságok elérését és a módosítások mentését, lehetővé téve a fejlesztők számára a projektmenedzsment feladatok hatékony automatizálását.

## Miért használja az Aspose.Tasks‑t a projekt verziójának meghatározásához?
Az Aspose.Tasks **pontos verzió metaadatokat** és **az utolsó mentés időbélyegét** biztosít, miközben bármely, Java‑t támogató operációs rendszeren fut. **500 oldalig** képes **2 másodpercnél kevesebb idő alatt** feldolgozni egy szabványos 2,5 GHz CPU‑n, ami ideálissá teszi kötegelt automatizáláshoz és nagyszabású migrációs forgatókönyvekhez.

## Előkövetelmények
Before we begin, ensure you have:

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java JAR** – töltsd le a [weboldalról](https://releases.aspose.com/tasks/java/) és add hozzá a projekt osztályútvonalához.  
3. **MS Project fájl** – egy XML‑alapú Project fájl (például `input.xml`), amelyet ellenőrizni szeretnél.  

> **Pro tipp:** Tárold a Project fájlt egy dedikált `data` mappában, hogy az útvonalak rendezettek legyenek, és elkerüld a véletlen felülírásokat.

## Csomagok importálása
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Hogyan állítsuk be a projekt könyvtárát
Ahhoz, hogy helyesen megtaláld a projektfájlokat, hozz létre egy dedikált könyvtárat az alkalmazás struktúrájában, és tárold ott az összes bemeneti fájlt. Ez tisztán tartja a kódot, és elkerüli az útvonalakkal kapcsolatos hibákat a fájlok betöltésekor. Használj egyértelmű változónevet a könyvtár útvonalához, amely lehet abszolút vagy a projekt gyökeréhez relatív.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## Hogyan töltsük be a projektet
`Project` az Aspose.Tasks elsődleges objektuma, amely egy Microsoft Project fájlt reprezentál a memóriában, és hozzáférést biztosít minden projekt tulajdonsághoz és gyűjteményhez. A `Project` példány létrehozása után lekérdezheted a mezőket, iterálhatsz a feladatokon, vagy módosíthatod az adatokat, mielőtt a fájlt vissza mentenéd a lemezre.

```java
Project project = new Project(dataDir + "input.xml");
```

## Hogyan határozzuk meg a projekt verzióját
`Prj.SAVE_VERSION` egy olyan tulajdonság, amely a fájlt mentő Microsoft Project verziószámát jelzi. `Prj.LAST_SAVED` egy olyan tulajdonság, amely a fájl legutóbbi mentésének dátumát és időpontját tárolja. `Prj.SAVE_VERSION` visszaadja a Microsoft Project alkalmazás numerikus verzióját, amely a fájlt mentette (például 12 a Project 2010‑hez). `Prj.LAST_SAVED` a legutóbbi mentési művelet pontos dátumát és időpontját biztosítja.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

## Hogyan jelenítsük meg az eredményt
Miután lekérted a verziót és a legutóbbi mentés információját, általában a konzolra vagy egy naplófájlba szeretnéd kiírni. Használd a `System.out.println`‑t az értékek megjelenítéséhez, a dátumot szükség szerint formázva. Ez megerősíti, hogy a kinyerés sikeres volt, és azonnali visszajelzést ad a fejlesztés vagy az automatizált szkriptek során.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| `NullPointerException` on `project.get(...)` | A fájl nem található vagy az útvonal helytelen | Ellenőrizd a `dataDir` és a fájlnév helyességét; teszteléshez használj abszolút útvonalat. |
| Váratlan verziószám (pl. 0) | Nem Project XML fájl betöltése | Győződj meg arról, hogy a fájl érvényes Microsoft Project fájl (MPP/XML). |
| Licenc kivétel | A próba használata érvényes licenc nélkül a termelésben | Alkalmazd az Aspose.Tasks licencet (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Tasks‑t más programozási nyelvekkel?**  
A: Igen, az Aspose.Tasks támogatja a .NET, Java és C++ nyelveket, többek között.

**Q: Alkalmas az Aspose.Tasks nagy‑léptékű projektekhez?**  
A: Teljes mértékben; képes több száz oldalas projekteket másodpercek alatt feldolgozni, anélkül, hogy a teljes fájlt a memóriába töltené.

**Q: Testreszabhatom a projekt adatait az Aspose.Tasks segítségével?**  
A: Igen, módosíthatod a feladatokat, erőforrásokat, naptárakat és bármely más projekt elemet az API-n keresztül.

**Q: Szükséges a Microsoft Project telepítése az Aspose.Tasks használatához?**  
A: Nem, a könyvtár önállóan működik, és nem igényel Microsoft Projectet a gépen.

**Q: Elérhető technikai támogatás az Aspose.Tasks‑hez?**  
A: Igen, segítséget kaphatsz az Aspose.Tasks fórumon [itt](https://forum.aspose.com/c/tasks/15).

**További GYIK**

**Q: Hogyan kérhetem le más projekt tulajdonságokat (pl. szerző, cég)?**  
A: Használd a `project.get(Prj.AUTHOR)` vagy `project.get(Prj.COMPANY)` hívásokat ugyanúgy, ahogy a verziót lekéred.

**Q: Ellenőrizhetem egy MPP (bináris) fájl verzióját?**  
A: Igen, az Aspose.Tasks közvetlenül betölti a `.mpp` fájlokat; a `Prj.SAVE_VERSION` tulajdonság bináris formátumokra is működik.

**Q: Van mód arra, hogy programozottan frissítsem egy régi projektfájlt egy újabb verzióra?**  
A: Töltsd be a régi fájlt, majd mentsd el a `project.save("newfile.mpp", SaveFileFormat.MPP);` paranccsal – az Aspose.Tasks alapértelmezés szerint a legújabb formátumban írja a fájlt.

## Következtetés
Most már elsajátítottad, **hogyan kell lekérni a projekt verzióját** és **az utolsó mentés dátumát** az MS Project fájlokból az Aspose.Tasks for Java segítségével. Illeszd be ezeket a kódrészleteket automatizálási folyamatokba, jelentéskészítő eszközökbe vagy migrációs segédeszközökbe, hogy mindig pontosan tudd, melyik Project verzióval dolgozol.

---

**Utolsó frissítés:** 2026-05-31  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Projekt kezdő dátum beállítása MS Projectben az Aspose.Tasks for Java használatával](/tasks/java/project-properties/write-project-info/)
- [Microsoft Project adatbázis olvasása az Aspose.Tasks for Java segítségével](/tasks/java/project-data-reading/read-project-database/)
- [Projekt mentése sablonként, CSV‑ként és szövegként az Aspose.Tasks for Java használatával](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}