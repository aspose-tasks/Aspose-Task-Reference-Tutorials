---
date: 2026-07-19
description: Ismerje meg, hogyan adhat hozzá custom field types-ot az Aspose.Tasks
  for .NET-ben step‑by‑step kóddal, előfeltételekkel és GYIK‑kel.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Custom Field Types az Aspose.Tasks-ben
og_description: Ismerje meg, hogyan adhat hozzá custom field types-ot az Aspose.Tasks
  for .NET-ben. Kövesse ezt a step‑by‑step útmutatót a extended attributes hatékony
  létrehozásához, meghatározásához és használatához.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Hogyan adjon hozzá Custom Field Types-t az Aspose.Tasks for .NET-hez
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Hogyan adjon hozzá Custom Field Types-t az Aspose.Tasks for .NET-hez
url: /hu/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni mezőtípusok hozzáadása az Aspose.Tasks-ben

## Bevezetés

Ebben az oktatóanyagban megismerheti, hogyan adhat **egyéni mező hozzáadása** típusokat egy Microsoft Project fájlhoz az Aspose.Tasks for .NET használatával. Az egyéni mezők lehetővé teszik további információk tárolását – például kockázati pontszámok, részlegkódok vagy egyéni megjegyzések – közvetlenül a feladatokon, erőforrásokon vagy magán a projekten. Végigvezetjük a teljes folyamaton, a környezet beállításától a definícióig, a hozzáadáson és egy egyéni szöveges mező ellenőrzéséig.

## Gyors válaszok
- **Mi az egyéni mező?** Egy felhasználó által definiált oszlop, amely szöveget, számokat, dátumokat vagy jelzőket tárolhat feladatokon/erőforrásokon.  
- **Melyik osztály definiál egy egyéni mezőt?** `ExtendedAttributeDefinition`.  
- **Hozzáadhatok egy egyéni mezőt egy meglévő projekthez?** Igen—töltse be a projektet, hozza létre a definíciót, majd adja hozzá a gyűjteményhez.  
- **Szükségem van licencre az Aspose.Tasks-hez?** Licenc szükséges a termeléshez; egy ingyenes próba a kiértékeléshez megfelelő.  
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi az „how to add custom field” az Aspose.Tasks-ben?

**How to add custom field** a folyamatra utal, amely során létrehozzuk az `ExtendedAttributeDefinition`-t, és a projekt `ExtendedAttributes` gyűjteményéhez csatoljuk. Ez lehetővé teszi további metaadatok tárolását, amelyek nem részei a szabványos Project séma. Használható feladatokhoz, erőforrásokhoz vagy a projekthez, lehetővé téve olyan információk rögzítését, mint a kockázati szintek, részlegkódok vagy egyéni megjegyzések, amelyek az alapértelmezett mezőkben nem érhetők el.

## Miért használjunk egyéni mezőket a projektmenedzsmentben?

Aspose.Tasks támogat **50+ beépített kiterjesztett attribútumtípust**, és lehetővé teszi **tetszőleges számú egyéni mező** definiálását anélkül, hogy jelentősen befolyásolná a fájlméretet. Egyéni mezők használatával:  
Ezek a mezők további oszlopként jelennek meg a Microsoft Projectben, és hivatkozhatók képletekben, jelentésekben és szűrőkben. A projektfájlban tárolódnak, és a fájllal együtt utaznak, biztosítva, hogy a downstream eszközök megőrizzék az egyéni adatokat.

## Előfeltételek

### 1. Visual Studio telepítve
Győződjön meg róla, hogy a Visual Studio (2019 vagy újabb) telepítve van a gépén. Letöltheti a Microsoft weboldaláról.

### 2. Aspose.Tasks for .NET
Adja hozzá az Aspose.Tasks NuGet csomagot a projektjéhez. Töltse le a legújabb verziót [itt](https://releases.aspose.com/tasks/net/).

### 3. Alap C# ismeretek
Jól kell ismernie a C# szintaxist, osztályokat és a .NET projektstruktúrát.

## Névtér importálása

`Project`, `ExtendedAttributeDefinition` és a kapcsolódó enumok az `Aspose.Tasks` névtérben találhatók. Importálja a fájl tetején:

Az `Aspose.Tasks` névtér biztosítja az összes alapvető típust a Microsoft Project fájlok kezeléséhez.

```csharp

```

## Hogyan adjon hozzá egyéni mezőt egy projekthez?

Töltse be a meglévő projektet, hozza létre az egyéni mező definíciót, és adja hozzá a projekt kiterjesztett attribútumok gyűjteményéhez—mindhárom lépésben. Ez a minta működik feladatok, erőforrások és a projekt esetén is, és biztosítja, hogy az egyéni mező megmaradjon a fájl mentésekor.

### 1. lépés: Projekt objektum létrehozása
`Project` az Aspose.Tasks legfelső szintű objektuma, amely egyetlen Project fájlt képvisel a memóriában. Példányosítása betölti a fájlt, és hozzáférést biztosít a feladatokhoz, erőforrásokhoz és a kiterjesztett attribútumokhoz.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 2. lépés: Egyéni mező definiálása
`ExtendedAttributeDefinition` egy új oszlopot ír le. Ebben a példában **Text** típusú egyéni mezőt hozunk létre feladatokhoz, és az aliasát “MyText”-nek állítjuk. Az `ExtendedAttributeTask.Text1` enum érték megmondja az Aspose.Tasks-nek, hol tárolja az értéket.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### 3. lépés: Egyéni mező definíció hozzáadása a projekthez
A projekt `ExtendedAttributes` gyűjteménye tartalmazza az összes egyéni mező definíciót. A definíció hozzáadása elérhetővé teszi azt a projekt minden feladata számára.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Gyakori problémák és megoldások
- **A mező nem jelenik meg a MS Project felhasználói felületén** – Győződjön meg róla, hogy beállította az `Alias` tulajdonságot; a MS Project az alias-t oszlopfejlécként jeleníti meg.  
- **Mentéskor kivétel keletkezik** – Ellenőrizze, hogy a projektfájl nem csak olvasható, és hogy rendelkezik érvényes licenccel.  
- **Az egyéni mező értékek elvesznek újratöltés után** – Győződjön meg róla, hogy a feladatok értékeinek beállítása után meghívja a `project.Save("output.mpp")` metódust.

## Gyakran feltett kérdések

**K: Használhatom az Aspose.Tasks-et más .NET keretrendszerekkel?**  
A: Igen, az Aspose.Tasks működik .NET Framework, .NET Core és .NET 5/6/7 verziókkal.

**K: Az Aspose.Tasks alkalmas vállalati szintű alkalmazásokra?**  
A: Teljesen. Támogatja a projektek feldolgozását **akár 10 000 feladattal**, és több szálon futó szerverkörnyezetekben is működik.

**K: Az Aspose.Tasks támogat több projektfájl formátumot?**  
A: Igen—az Aspose.Tasks olvas és ír MPP, XML, HTML és CSV formátumokat, lefedve **az összes fő Microsoft Project verziót**.

**K: Manipulálhatom az erőforrás adatokat az Aspose.Tasks segítségével?**  
A: Igen, hozzáadhat, frissíthet és törölhet erőforrásokat, valamint egyéni mezőket is hozzárendelhet hozzájuk.

**K: Van közösségi fórum az Aspose.Tasks felhasználók számára?**  
A: Igen, felkeresheti a [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15), ahol más felhasználókkal léphet kapcsolatba, és az Aspose csapattól kaphat támogatást.

---

**Utoljára frissítve:** 2026-07-19  
**Tesztelve ezzel:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Az Extended Attribute definíciók mesteri kezelése MS Projectben az Aspose.Tasks-ben](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [MS Project kiterjesztett attribútumok kezelése az Aspose.Tasks segítségével](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper MS Project integráció az Aspose.Tasks-ben](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}