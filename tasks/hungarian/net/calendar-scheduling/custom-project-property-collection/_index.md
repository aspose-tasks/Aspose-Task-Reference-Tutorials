---
date: 2026-10-15
description: Ismerje meg, hogyan adhat hozzá egyedi tulajdonságot, és kezelheti az
  egyedi projekt tulajdonságokat az Aspose.Tasks for .NET-ben, ezáltal növelve a projekt
  metaadatok irányítását.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Egyedi projekt tulajdonsággyűjtemény kezelése az Aspose.Tasks-ben
og_description: Adj hozzá egyedi tulajdonságot a projektfájlokhoz az Aspose.Tasks
  for .NET segítségével. Ez az útmutató bemutatja, hogyan kezelheted az egyedi tulajdonságokat,
  olvashatod őket, és hatékonyan hozzáadhatsz logikai vagy szöveges értékeket.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Egyedi tulajdonság hozzáadása az Aspose.Tasks .NET API-val projektekhez
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Hogyan adjon hozzá egyedi tulajdonságot az Aspose.Tasks for .NET-ben
url: /hu/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjon hozzá egyéni tulajdonságot az Aspose.Tasks for .NET-ben

## Bevezetés

Az egyéni tulajdonságok támogatása lehetővé teszi, hogy a beépített mezők által nem lefedett projekt‑specifikus metaadatokat tároljon. Ebben az oktatóanyagban megtanulja, hogyan **adjon hozzá egyéni tulajdonságot**, hogyan olvassa vissza, és hogyan kezelje az egész egyéni tulajdonsággyűjteményt az Aspose.Tasks for .NET segítségével. A végére képes lesz Boolean, DateTime, Double és String értékekkel testreszabni a projektfájlokat, amelyek megfelelnek az üzleti szabályainak.

## Gyors válaszok
- **Hozzáadhatok Boolean egyéni tulajdonságot?** Igen – használja a `CustomPropertyType.Boolean`-t.
- **Hány egyéni tulajdonság típust támogat?** Négy: Boolean, DateTime, Double, String.
- **A egyéni tulajdonsággyűjtemény csak olvasható?** Olvasható lehet, ha a projekt csak‑olvasású forrásból van betöltve.
- **Szükségem van licencre a funkció használatához?** Ideiglenes licenc elegendő értékeléshez; teljes licenc szükséges a termeléshez.
- **Mely .NET verziók kompatibilisek?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi az egyéni tulajdonság?

Az egyéni tulajdonság egy felhasználó által definiált metaadatmező, amelyet egy Project objektumhoz csatol. Lehetővé teszi olyan extra információk tárolását, mint például a „Kockázati szint”, a „Vevő azonosító”, vagy bármely Boolean jelző, amelyet a szabványos MS‑Project mezők nem fednek le.

## Miért adjunk hozzá egyéni tulajdonságot az Aspose.Tasks-ben?

Az Aspose.Tasks **50+ bemeneti és kimeneti formátumot** támogat, és akár **10 000 feladatot** is kezelhet anélkül, hogy a teljes fájlt memóriába töltené. Az egyéni tulajdonságok hozzáadása lehetővé teszi, hogy az üzletileg kritikus adatokat közvetlenül a projektfájlba ágyazza, ezzel kiküszöbölve a külső adatbázisok szükségességét és biztosítva, hogy az adatok a projekttel együtt utazzanak.

## Előfeltételek

- Visual Studio (bármelyik újabb kiadás) telepítve a munkaállomáson.  
- Aspose.Tasks for .NET – letöltheti a [download link](https://releases.aspose.com/tasks/net/) oldalról.  
- Alapvető ismeretek a C# szintaxisról és a .NET projektstruktúráról.

## Névterek importálása

A következő névterek biztosítják a hozzáférést a projektmodell alapjához és az egyéni tulajdonság API‑khoz.

```csharp
using Aspose.Tasks;
using System;


```

## Hogyan adjon hozzá egyéni tulajdonságot az Aspose.Tasks-ben?

Az egyéni tulajdonság hozzáadásához először töltse be a projektet, majd hozza létre a `CustomProperty` objektumot, állítsa be a nevét, típusát és értékét, végül adja hozzá a projekt `CustomProperties` gyűjteményéhez. Ez a művelet közvetlenül a projektfájlba ágyazza be a metaadatokat, és a változások mentésre kerülnek, amikor meghívja a `project.Save(...)` metódust.

`CustomProperty` egyetlen felhasználó által definiált mezőt képvisel, amely egy projekthez van csatolva.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### 1. lépés: projekt inicializálása

`Project` az elsődleges osztály, amely egy projektfájlt képvisel az Aspose.Tasks-ben.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### 2. lépés: egyéni tulajdonságok gyűjteményének készenlétének ellenőrzése

`CustomProperties` a gyűjtemény, amely egy projekt összes egyéni tulajdonság objektumát tartalmazza.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### 3. lépés: egyéni tulajdonságok hozzáadása

`Add` metódus egy új egyéni tulajdonságot szúr be a projekt gyűjteményébe.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### 4. lépés: egyéni tulajdonságok elérése

`CustomProperties` gyűjtemény implementálja az IEnumerable-t, lehetővé téve az egyes `CustomProperty` elemek iterálását.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### 5. lépés: egyéni tulajdonság értékének lekérése

`Get` metódus visszaadja egy egyéni tulajdonság értékét a neve alapján.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### 6. lépés: egyéni tulajdonságnevek iterálása

`Names` tulajdonság a gyűjteményben lévő összes egyéni tulajdonság nevét adja vissza.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### 7. lépés: egyéni tulajdonságok eltávolítása vagy törlése

`Remove` metódus egy adott tulajdonságot töröl, míg a `Clear` kiüríti az egész gyűjteményt.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Gyakori buktatók és hibaelhárítás

- **Csak‑olvasható gyűjtemény** – Ha a `project.CustomProperties.IsReadOnly` `true`‑t ad vissza, győződjön meg róla, hogy a forrásfájl nincs kizárólagos olvasási módban megnyitva, vagy másolja át egy írható helyre a szerkesztés előtt.  
- **Típuseltérés** – Ha olyan értéket ad meg, amely nem egyezik a deklarált `CustomPropertyType`‑nal, `ArgumentException` keletkezik. Mindig a megfelelő `Type` meghatározása után állítsa be a `Value`‑t.  
- **Módosítások mentése** – Egyéni tulajdonságok hozzáadása vagy eltávolítása után hívja a `project.Save("output.mpp")`‑t a módosítások mentéséhez; különben a változások csak memóriában maradnak.

## Gyakran feltett kérdések

**Q: Hozzáadhatok egyéni tulajdonságokat bármilyen adat típussal a projektemhez az Aspose.Tasks for .NET használatával?**  
A: Igen, hozzáadhat egyéni tulajdonságokat, amelyek Boolean, DateTime, Double és String típusokat támogatják.

**Q: Lehet-e iterálni az egyéni tulajdonságneveken az Aspose.Tasks for .NET‑ben?**  
A: Természetesen, iterálhat az egyéni tulajdonságneveken a `Names` tulajdonság használatával.

**Q: Hogyan távolíthatok el egy adott egyéni tulajdonságot a projektemből?**  
A: Egyéni tulajdonságot a neve alapján a `Remove` metódussal távolíthatja el.

**Q: Az Aspose.Tasks for .NET biztosít-e támogatást ideiglenes licencekhez?**  
A: Igen, ideiglenes licencet szerezhet az Aspose weboldaláról értékelési célokra.

**Q: Hol találok támogatást vagy további segítséget az Aspose.Tasks for .NET‑hez?**  
A: Látogasson el az Aspose.Tasks fórumra: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) bármilyen kérdés vagy segítség esetén.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan olvassuk be a beépített projekt tulajdonságokat az Aspose.Tasks for .NET használatával](/tasks/net/advanced-features/built-in-project-property-collection/)
- [MS Project attribútumgyűjtemény kezelése az Aspose.Tasks-ben](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks egyéni mezőtípusok – Naptár és ütemezés](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}