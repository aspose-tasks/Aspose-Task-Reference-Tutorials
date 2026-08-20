---
date: 2026-03-08
description: Ismerje meg, hogyan importálhat projektfájlt az Aspose.Tasks for .NET
  használatával, beleértve a fájl kódolásának megadását és a Microsoft Project fájl
  hatékony betöltését.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projektfájl importálása – Betöltési lehetőségek az Aspose.Tasks-ben
url: /hu/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektfájl importálása – Betöltési beállítások az Aspose.Tasks-ben

## Bevezetés

Aspose.Tasks for .NET megkönnyíti a **import project file** adatok beolvasását a Microsoft Project, Primavera és egyéb formátumokból. Akár jelszóval védett fájlt kell olvasnia, egyedi kódolást kell beállítania, vagy a feldolgozási hibákat szeretné kezelni, a könyvtár finomhangolt vezérlést biztosít a betöltési beállításokon keresztül. Ebben az útmutatóban a leggyakoribb forgatókönyveken vezetünk végig, hogy magabiztosan **load Microsoft Project file** objektumokat tudjon betölteni .NET alkalmazásaiban.

## Gyors válaszok
- **Mi a legfőbb módja egy projektfájl importálásának?** Használja a `Project` konstruktort egy `LoadOptions` példánnyal.  
- **Megnyithatok jelszóval védett fájlokat?** Igen—állítsa be a `Password` tulajdonságot a `LoadOptions`-on.  
- **Hogyan adhatom meg a fájl kódolását?** Rendeljen egy `Encoding` objektumot a `LoadOptions.Encoding`-hez.  
- **Testreszabható-e a hibakezelés?** Teljesen—adjon meg egy delegáltat a `LoadOptions.ErrorHandler`-nek.  
- **Működnek ezek a beállítások Primavera fájlokkal?** Igen, a `LoadOptions`-on belüli `PrimaveraReadOptions` segítségével.

## Előfeltételek

Mielőtt belemerülne, győződjön meg róla, hogy rendelkezik a következőkkel:

1. **Visual Studio** (vagy bármelyik kedvelt .NET IDE).  
2. **Aspose.Tasks for .NET** – töltse le a [weboldalról](https://releases.aspose.com/tasks/net/).  
3. Alapvető ismeretek a **C#** szintaxisról és a projekt struktúrájáról.

Most, hogy minden készen áll, importáljuk a szükséges névtereket.

## Névterek importálása

A C# projektjében adja hozzá a következő `using` utasításokat, hogy az API osztályok elérhetők legyenek:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Projektfájl importálása betöltési beállításokkal

Az alábbiakban négy gyakorlati példát talál, amelyek a leggyakoribb betöltési forgatókönyveket fedik le.

### 1. lépés: Jelszóval védett projekt betöltése

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### 2. lépés: Primavera projekt betöltése egyéni beállításokkal

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### 3. lépés: **Fájl kódolásának megadása** XER fájl importálásakor

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### 4. lépés: Primavera projekt betöltése egyéni hibakezeléssel

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Ezeket a lépéseket követve pontosan **import project file** adatokat tud betölteni, a betöltési folyamatot igényeihez igazíthatja, és alkalmazását robusztusnak tarthatja.

## Gyakori problémák és tippek

- **Helytelen jelszó** – a `Password` tulajdonság kivételt dob; ellenőrizze a hitelesítő adatot a betöltés előtt.  
- **Nem támogatott kódolás** – győződjön meg róla, hogy a megadott kódlap létezik a célgépen (`Encoding.GetEncoding(1251)` működik cirill esetén).  
- **Hiányzó Primavera beállítások** – ha meg kell őrizni a feladat UID-eket, állítsa be a `PreserveUids = true` értéket; ellenkező esetben duplikált azonosítók jelenhetnek meg.  
- **A hibakezelő null értéket ad vissza** – a `null` visszaadása jelzi a parsernek, hogy hagyja ki a problémás elemet; igény szerint testreszabható.

## Gyakran feltett kérdések

**Q: Az Aspose.Tasks for .NET kompatibilis minden Microsoft Project verzióval?**  
A: Igen, széles körű Microsoft Project verziókat támogat, így **load Microsoft Project file** formátumokat tud betölteni a régebbi MPP fájloktól a legújabb formátumokig.

**Q: Integrálhatom az Aspose.Tasks for .NET-et más harmadik féltől származó könyvtárakkal?**  
A: Teljesen. A könyvtár zökkenőmentesen működik más .NET csomagokkal, lehetővé téve, hogy jelentéskészítő, UI vagy adat-hozzáférési keretrendszerekkel kombinálja.

**Q: Az Aspose.Tasks for .NET dokumentációt és támogatási forrásokat biztosít?**  
A: Igen, hivatkozhat a részletes [documentation](https://reference.aspose.com/tasks/net/) oldalra, és elérheti a támogatást a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15).

**Q: Elérhetők licencelési lehetőségek az Aspose.Tasks for .NET-hez?**  
A: Igen, különböző licencelési opciókat fedezhet fel, beleértve az ingyenes próbaverziókat és ideiglenes licenceket, a [Aspose.Tasks weboldalon](https://purchase.aspose.com/buy).

**Q: Milyen gyakran jelennek meg frissítések és új funkciók az Aspose.Tasks for .NET-hez?**  
A: Az Aspose.Tasks rendszeres frissítéseket kap, amelyek új funkciókat adnak hozzá, javítják a teljesítményt, és fenntartják a kompatibilitást a legújabb Microsoft Project kiadásokkal.

---

**Utoljára frissítve:** 2026-03-08  
**Tesztelve a következővel:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}