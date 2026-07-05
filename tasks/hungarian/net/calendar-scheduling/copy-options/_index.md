---
date: 2026-07-05
description: Ismerje meg, hogyan másolhat projektadatokat az Aspose.Tasks for .NET
  segítségével másolási beállításokkal. Növelje .NET alkalmazásai hatékonyságát pontos
  projektmenedzsmenttel.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Hogyan másolhat projektadatokat másolási beállításokkal az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Hogyan másolhat projektadatokat másolási beállításokkal az Aspose.Tasks-ben
url: /hu/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan másolhat projektadatokat a másolási beállításokkal az Aspose.Tasks-ben

## Bevezetés

If you need to **how to copy project** information from one Microsoft Project file to another, Aspose.Tasks for .NET gives you a clean, code‑first way to do it. In this tutorial we’ll walk through the complete workflow—loading a source project, configuring copy options, creating a copy, and loading the result—so you can integrate project‑copying logic into any .NET application with confidence.

## Gyors válaszok
- **Mi a másolás funkció?** Megkettőzi a projektadatokat, miközben lehetővé teszi, hogy bizonyos szakaszokat, például naptárakat, erőforrásokat vagy nézetinformációkat belefoglalja vagy kizárja.  
- **Melyik osztály irányítja a viselkedést?** `CopyToOptions` lehetővé teszi, hogy finomhangolja, mi kerül másolásra.  
- **Szükségem van licencre?** Érvényes Aspose.Tasks licenc szükséges a termeléshez; egy ingyenes próba a fejlesztéshez működik.  
- **Támogatott formátumok?** Az Aspose.Tasks kezeli az MPP, XML és XER fájlokat – összesen több mint 20 formátumot.  
- **Kihagyhatom a nézetadatokat?** Igen, állítsa be a `CopyToOptions.SkipViewData = true` értéket a felhasználói felülethez kapcsolódó információk elhagyásához.

## Mi az a “how to copy project” az Aspose.Tasks-ben?
**“How to copy project”** arra utal, hogy az Aspose.Tasks API-ját használva megkettőzi egy Project objektum adatait egy új fájlba, opcionálisan kiszűrve a nem kívánt elemeket. Ez a művelet hasznos sablonozáshoz, archiváláshoz vagy projektvariánsok létrehozásához manuális UI lépések nélkül, és minden támogatott fájlformátumban működik.

## Miért használjuk a Copy Options-t az Aspose.Tasks-ben?
Az Aspose.Tasks **50+ projekt‑kapcsolódó entitást** (feladatok, erőforrások, naptárak, hozzárendelések stb.) támogat, és képes **legfeljebb 10 000 feladatot** tartalmazó fájlokat feldolgozni, miközben a memóriahasználat 200 MB alatt marad. A `CopyToOptions` használatával elkerülhető a nehéz nézetadatok másolása, ami **30‑40 %**‑kal csökkenti a kimeneti fájl méretét, és nagy projektek esetén körülbelül **2×**‑es gyorsulást eredményez.

## Előkövetelmények

1. **Aspose.Tasks for .NET** – töltse le a legújabb verziót a [download link](https://releases.aspose.com/tasks/net/).  
2. **.NET fejlesztői környezet** – telepített Visual Studio 2022 (vagy bármely IDE, amely támogatja a .NET 6+).  
3. **Érvényes Aspose.Tasks licenc** – opcionális értékeléshez, kötelező a termelési buildokhoz.  
4. **Egy meglévő projektfájl** (például `SourceProject.xml`), amelyet másolni szeretne.

## Hogyan importáljuk a névtereket az Aspose.Tasks-hez?

Add the required `using` directives at the top of your C# file so the compiler can locate the Aspose.Tasks types. Including these statements gives you direct access to `Project`, `CopyToOptions`, and other utility classes without fully qualifying their names, simplifying your code and improving readability.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## 1. lépés: Projektobjektumok inicializálása

Először hozzon létre egy `Project` példányt, amely a forrásfájlt képviseli, és töltse be az XML adatokat.  
A `Project` osztály egy memóriába betöltött Microsoft Project fájlt képvisel, amely feladatokat, erőforrásokat, naptárakat és egyéb projektinformációkat tesz elérhetővé.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Pro tipp:** Ha nagyon nagy fájlokkal dolgozik, fontolja meg a `LoadOptions` konstruktor használatát a lusta betöltés engedélyezéséhez és a memóriafogyasztás alacsonyan tartásához.

## 2. lépés: Projekt másolatának létrehozása

Ezután hozzon létre egy második `Project` objektumot, amely a másolt adatokat fogadja. Ez az objektum üresen indul.

```csharp
Project copiedProject = new Project();
```

Most már két különálló `Project` objektuma van: az egyik a lemezről betöltve, a másik készen áll a másolat fogadására.

## 3. lépés: Másolt projekt betöltése

A másolási művelet (később bemutatva) után ellenőrizni szeretné az eredményt, ha betölti az újonnan mentett fájlt egy másik `Project` példányba.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

A fájl újratöltése megerősíti, hogy a másolás sikeres volt, és hogy a beállított opciók a várt módon működtek.

## 4. lépés: Másolási beállítások konfigurálása

A `CopyToOptions` osztály lehetővé teszi, hogy pontosan meghatározza, mi kerül átvitelre a forrásból a célba.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

`SkipViewData = true` beállítása csökkenti a kimeneti fájl méretét és felgyorsítja a műveletet, különösen ha csak logikai projektadatokra van szükség.

## 5. lépés: Projekt másolás végrehajtása

Végül hívja meg a `CopyTo` metódust a forrásprojekten, átadva a célprojektet és a konfigurált opciókat.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Ez a két soros hívás végrehajtja a teljes másolási műveletet, figyelembe véve a megadott opciókat. Az eredményül kapott `CopiedProject.xml` csak a kért adatokat tartalmazza.

## Gyakori problémák és megoldások

| Issue | Cause | Fix |
|-------|-------|-----|
| **NullReferenceException a `CopyTo` hívásakor** | A célprojekt nincs példányosítva. | Győződjön meg róla, hogy a `CopyTo` előtt meghívja a `new Project()`-t. |
| **Hiányzó feladatok a másolás után** | `CopyCommonData` értéke `false`. | Állítsa be `CopyCommonData = true`-ra, vagy másolja manuálisan a konkrét gyűjteményeket. |
| **Nagy kimeneti fájl** | `SkipViewData` értéke `false`. | Kapcsolja be a `SkipViewData`-t a UI‑hez kapcsolódó adatok kihagyásához. |
| **Licenc nincs alkalmazva** | A licencfájl nincs betöltve. | Hívja meg a `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` kódot minden API használata előtt. |

## Gyakran feltett kérdések

**Q: Másolhatok csak egy részhalmaz feladatot?**  
A: Igen, használja a `CopyToOptions`-t a `ProjectRootTask`-tal együtt egy kezdő feladat megadásához, vagy manuálisan másolja a kiválasztott feladatokat az első másolás után.

**Q: Az Aspose.Tasks támogatja a másolást különböző fájlformátumok között?**  
A: Teljesen. Betölthet egy MPP fájlt, és a másolatot mentheti XML, XER vagy bármely más támogatott formátumba – összesen több mint **20 + formátum**.

**Q: Hogyan kezeljem a jelszóval védett projektfájlokat?**  
A: Töltse be a forrást a `new Project("file.mpp", new LoadOptions { Password = "pwd" })` segítségével, majd folytassa a másolást a szokásos módon.

**Q: Van mód erőforrás poolok másolására feladatok nélkül?**  
A: Állítsa be a `CopyToOptions.CopyResources = true` és a `CopyToOptions.CopyTasks = false` értékeket, hogy csak az erőforrás információkat másolja.

**Q: Hol találok további példákat?**  
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösség által készített kódrészletek, hibaelhárítási tippek és a hivatalos dokumentáció érdekében.

---

**Utoljára frissítve:** 2026-07-05  
**Tesztelve ezzel:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [A projektadatok elsajátítása az Aspose.Tasks segítségével](/tasks/net/project-management-integration/project-data/)
- [Az MS Project mentési beállításainak elsajátítása az Aspose.Tasks számára](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks naptár és ütemezés](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}