---
date: 2026-03-14
description: Tanulja meg, hogyan lehet beágyazott fájlokat kinyerni és projektfájlt
  betölteni az Aspose.Tasks for .NET segítségével. Ez az útmutató lépésről lépésre
  mutatja be az OLE-objektumok kinyerését.
linktitle: Collection of OLE Objects in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Beágyazott fájlok kinyerése OLE-objektumokból az Aspose.Tasks-ben
url: /hu/net/advanced-concepts/ole-object-collection/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beágyazott fájlok kinyerése OLE objektumokból az Aspose.Tasks-ben

## Bevezetés

Ebben az útmutatóban **beágyazott fájlokat** fogunk kinyerni, amelyek OLE objektumként vannak tárolva egy Microsoft Project fájlban az Aspose.Tasks for .NET segítségével. Akár Word dokumentumokat, Excel táblázatokat vagy rich‑text fájlokat szeretne kinyerni, az alábbi lépések megmutatják, hogyan **töltsük be a projektfájlt**, hogyan fedezzük fel az egyes OLE bejegyzéseket, és hogyan írjuk vissza a bináris tartalmat a lemezre. A végére magabiztosan tud majd egy teljes **c# extract ole** munkafolyamatot alkalmazni saját alkalmazásaiban.

## Gyors válaszok
- **Mit jelent a „beágyazott fájlok kinyerése”?** Azt jelenti, hogy elolvassuk az OLE objektumok bináris terhelését, és külön fájlokként mentjük el a lemezen.  
- **Melyik API metódus tölti be a projektet?** `new Project(filePath)` az Aspose.Tasks névtérből.  
- **Exportálhatok bármilyen típusú OLE objektumot?** Csak azokat a formátumokat, amelyeket az Aspose.Tasks felismer (pl. RTF, Word, Excel).  
- **Szükség van licencre?** Egy ingyenes próba verzió elegendő értékeléshez; a kereskedelmi licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mit jelent a „beágyazott fájlok kinyerése” OLE objektumok kontextusában?

Az OLE (Object Linking and Embedding) lehetővé teszi, hogy egy Project fájl teljes másolatokat tartalmazzon külső dokumentumokról. Ezeknek a beágyazott fájloknak a kinyerése közvetlen hozzáférést biztosít az eredeti tartalomhoz a Microsoft Project megnyitása nélkül.

## Miért érdemes beágyazott fájlokat kinyerni OLE objektumokból?

- **Az eredeti adatok megőrzése:** Minden csatolt dokumentumról készítsen biztonsági másolatot.  
- **Jelentések automatizálása:** Word vagy Excel jelentéseket nyerjen ki sok projektből egyetlen kötegben.  
- **Integráció más rendszerekkel:** A kinyert fájlokat dokumentum‑kezelő vagy analitikai csővezetékekbe táplálhatja.  

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Visual Studio** – bármely friss verzió (2019, 2022 vagy újabb).  
2. **Aspose.Tasks for .NET** – letölthető és telepíthető [innen](https://releases.aspose.com/tasks/net/).  
3. **Alap C# ismeretek** – legyen kényelmes a ciklusok, gyűjtemények és fájl‑I/O használatában.  

## Névterek importálása

A kezdéshez importálja a szükséges névtereket a projektbe:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;
```

## 1. lépés: A projektfájl betöltése

Először töltse be azt a Project fájlt, amelyik az OLE objektumokat tartalmazza:

```csharp
var project = new Project(DataDir + "Embedded.mpp");
```

> **Tipp:** A `DataDir`‑nek arra a mappára kell mutatnia, ahol a `.mpp` fájlja található. Ez a lépés teljesíti a **load project file** követelményt.

## 2. lépés: Fájlkiterjesztések meghatározása

Hozzon létre egy keresőtáblát, amely az OLE `FileFormat` azonosítókat a kívánt kimeneti fájlnevekkel párosítja. Ez megkönnyíti a **export ole objects** helyes kiterjesztésekkel történő végrehajtását:

```csharp
IDictionary<string, string> extensions = new Dictionary<string, string>
{
    { "RTF", "_rtfFile_out.rtf" },
    { "MSWordDoc", "_wordFile_out.docx" },
    { "ExcelML12", "_excelFile_out.xlsx" }
};
```

## 3. lépés: OLE objektumok bejárása és beágyazott fájlok kinyerése

Most járja végig a projekt minden OLE objektumát, ellenőrizze, hogy a formátum támogatott‑e, és írja a bináris tartalmat egy új fájlba:

```csharp
foreach (var oleObject in project.OleObjects)
{
    if (string.IsNullOrEmpty(oleObject.FileFormat) || !extensions.ContainsKey(oleObject.FileFormat))
    {
        continue;
    }

    var path = OutDir + "EmbeddedContent_" + extensions[oleObject.FileFormat];
    using (var stream = new FileStream(path, FileMode.Create))
    {
        stream.Write(oleObject.Content, 0, oleObject.Content.Length);
    }
}
```

> **Profi tipp:** Az `OutDir`‑nek írható könyvtárnak kell lennie. A fenti kód olyan fájlokat hoz létre, mint például `EmbeddedContent__wordFile_out.docx`, hatékonyan **extract ole objects** a projektből.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| Nem jönnek létre fájlok | `OutDir` nem létezik vagy nincs írási jogosultsága | Győződjön meg róla, hogy a könyvtár létezik, és az alkalmazásnak van írási hozzáférése. |
| Váratlan fájlformátum | Az OLE objektum `FileFormat` nincs a szótárban | Adja hozzá a hiányzó formátumot az `extensions` szótárhoz. |
| Nagy OLE objektumok memória‑nyomást okoznak | Sok nagy objektum egyszerre történő betöltése | Dolgozza fel az objektumokat egy‑esével, ahogy a példában látható, vagy közvetlenül streamelje őket a lemezre. |

## Gyakran feltett kérdések

**K: Mi az az OLE objektum?**  
V: Az OLE (Object Linking and Embedding) egy olyan technológia, amely lehetővé teszi fájlok beágyazását vagy hivatkozását más alkalmazásokból egy dokumentumban.

**K: Hogyan telepíthetem az Aspose.Tasks for .NET‑et?**  
V: Letöltheti az Aspose.Tasks for .NET‑et [innen](https://releases.aspose.com/tasks/net/) és kövesse a mellékelt telepítési útmutatót.

**K: Dolgozhatok OLE objektumokkal az Aspose.Tasks‑ben C#‑tudás nélkül?**  
V: Bár az alap C# ismeret ajánlott, az Aspose.Tasks átfogó dokumentációt és oktatóanyagokat biztosít, amelyek segítenek a felhasználóknak a programozási háttér függetlenül elkezdeni.

**K: Van ingyenes próba verzió az Aspose.Tasks‑hez?**  
V: Igen, ingyenes próba verziót igényelhet [innen](https://releases.aspose.com/).

**K: Hol találok támogatást az Aspose.Tasks‑hez?**  
V: Támogatást és kérdéseket a Aspose.Tasks fórumon kérhet [itt](https://forum.aspose.com/c/tasks/15).

---

**Utoljára frissítve:** 2026-03-14  
**Tesztelve:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}