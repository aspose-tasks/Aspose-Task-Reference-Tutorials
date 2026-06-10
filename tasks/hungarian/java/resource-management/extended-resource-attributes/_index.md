---
date: 2026-06-10
description: Ismerje meg, hogyan hozhat létre kiterjesztett attribútumot Java-ban,
  hogyan tölthet be egy Microsoft Project fájlt, hogyan állíthat be numerikus értékeket,
  és hogyan mentheti a projektet XML formátumban az Aspose.Tasks for Java segítségével.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Kiterjesztett erőforrás attribútumok kezelése az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan hozhat létre kiterjesztett attribútumot Java-ban az Aspose.Tasks használatával
url: /hu/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre kiterjesztett attribútumot Java-ban az Aspose.Tasks segítségével

## Bevezetés
Ebben a gyakorlati útmutatóban **kiterjesztett attribútumot Java-ban létrehozni** fogsz a Microsoft Project fájlhoz az Aspose.Tasks használatával. Végigvezetünk egy meglévő projekt betöltésén, egy új numerikus attribútum definiálásán, egy erőforrás értékének hozzárendelésén, és végül a változások XML fájlba mentésén. A végére egy újrahasználható kódmintát kapsz, amely bármely Java‑alapú projektmenedzsment megoldásba beilleszthető.

## Gyors válaszok
- **Mi az a kiterjesztett attribútum?**  
  Felhasználó által definiált mező (pl. Kor, Készségszint), amely további adatokat tárol erőforrások vagy feladatok számára.  
- **Melyik API hozza létre?**  
  Az Aspose.Tasks for Java biztosítja az `ExtendedAttributeDefinition` osztályt a saját attribútumok definiálásához és kezeléséhez.  
- **Szükségem van licencre?**  
  Egy ideiglenes értékelő licenc elegendő a fejlesztéshez; a termelési környezethez teljes licenc szükséges.  
- **Tárolhatok számokat?**  
  Igen – használja a `setNumericValue(BigDecimal)` metódust a pontos decimális értékek hozzárendeléséhez.  
- **Hogyan menthetem a változásokat?**  
  Hívja a `project.save("output.xml", SaveFileFormat.Xml)` metódust a frissített projekt XML formátumban történő írásához.

## Mi az az egyéni attribútum?
Az **egyéni attribútum** (más néven kiterjesztett attribútum) egy további oszlop, amelyet hozzáadhatsz a Microsoft Project erőforrásaihoz vagy feladataihoz. Lehetővé teszi olyan adatok rögzítését, amelyek nincsenek lefedve a beépített mezőkkel, például a munkavállaló kora, a tanúsítvány szintje vagy bármely üzleti specifikus mutató.

## Miért hozzunk létre kiterjesztett attribútumot Java-ban?
A kiterjesztett attribútum Java-ban történő létrehozása lehetővé teszi, hogy programozottan gazdagítsd a projektadatokat, biztosítva a konzisztenciát a fájlok között és az automatizált jelentéskészítést. Az attribútum egyszeri definiálásával bármennyi erőforráshoz vagy feladathoz alkalmazhatod manuális beviteli munka nélkül, időt takarítva meg és csökkentve a hibákat.

- **Az adatok testreszabása a szervezeted számára** – tárolj bármilyen mérőszámot, amely számodra fontos, manuális Excel megoldások nélkül.  
- **Gazdagabb jelentések engedélyezése** – később lekérdezheted az egyéni mezőt irányítópultokhoz vagy elemzésekhez.  
- **Konzisztencia fenntartása** – programozottan alkalmazd ugyanazt a definíciót tucatnyi projekten, kiküszöbölve az emberi hibákat.  
- **Teljesítmény‑tesztelt** – az Aspose.Tasks akár 10 000 feladatot és 5 000 erőforrást is képes feldolgozni anélkül, hogy a teljes fájlt a memóriába töltené, a termék benchmarkjai szerint.

## Előfeltételek
1. **Java Development Kit** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java** – töltsd le a legújabb kiadást innen: [itt](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA vagy bármely Java‑kompatibilis fejlesztői környezet.  

## Hogyan hozzunk létre kiterjesztett attribútumot Java-ban?
Töltsd be a projektet, definiáld az attribútumot, csatold egy erőforráshoz, és mentsd el a fájlt – mindezt néhány egyszerű lépésben. Az alábbi szakaszok minden lépést egy rövid magyarázattal és a tényleges kódot tartalmazó helykitöltővel mutatják be.

### Lépésről‑lépésre útmutató

#### Csomagok importálása
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` és a kapcsolódó osztályok a `com.aspose.tasks` névtérben találhatók. Importáld őket a Java fájlod tetején.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### 1. lépés: Adatkönyvtár meghatározása
`Paths` egy segédosztály, amely módszereket biztosít a fájlrendszer útvonalának platform‑független megszerzéséhez.

```java
String dataDir = "Your Data Directory";
```

#### 2. lépés: Microsoft Project fájl betöltése
`Project` egy Microsoft Project fájlt reprezentál a memóriában, lehetővé téve a tartalom olvasását és írását.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### 3. lépés: Az egyéni attribútum definiálása
`ExtendedAttributeDefinition` definiálja egy új egyéni mező sémáját, amely erőforrásokhoz vagy feladatokhoz csatolható.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### 4. lépés: Numerikus érték beállítása Java-ban
`ExtendedAttributeResource` egy adott erőforrás példányhoz tartozó egyéni attribútum értékét tárolja.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### 5. lépés: Erőforrás hozzáadása és az egyéni attribútum csatolása
`Resource` egy projekt erőforrást modellez, például személyt, felszerelést vagy anyagot.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### 6. lépés: Projekt mentése XML-ként
`SaveFileFormat` felsorolja a projekt mentéséhez támogatott kimeneti formátumokat, beleértve az XML-t.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### 7. lépés: Eredmény megjelenítése
`System.out.println` egy szövegsort ír ki a szabványos konzol kimenetre.

```java
System.out.println("Process completed Successfully");
```

## Általános buktatók és tippek
- **Attribútum ID ütközések:** Mindig hívd meg a `project.getExtendedAttributes().getById(id)` metódust új definíció létrehozása előtt, hogy elkerüld a duplikált azonosítókat.  
- **Pontosság kezelése:** Használd a `BigDecimal`-t a `float`/`double` helyett a pontos numerikus értékekhez; ez elkerüli a kerekítési hibákat a jelentésekben.  
- **Fájlútvonal megbízhatósága:** Használd a `Paths.get(...).toAbsolutePath()`-t vagy állítsd be az IDE munkakönyvtárát, hogy elkerüld a `FileNotFoundException`-t.  

## Gyakran ismételt kérdések

**Q: Létrehozhatok egyéni attribútumokat feladatokhoz is, nem csak erőforrásokhoz?**  
A: Igen – használja az `ExtendedAttributeTask`-ot az `ExtendedAttributeResource` helyett az attribútum séma definiálásakor.

**Q: Lehetséges egyszerre több egyéni attribútumot hozzáadni?**  
A: Természetesen. Hozzon létre külön `ExtendedAttributeDefinition` objektumokat minden attribútumhoz, és csatolja őket a kívánt erőforrásokhoz vagy feladatokhoz.

**Q: Milyen formátumokba menthetem a projektet?**  
A: Az Aspose.Tasks támogatja az XML, MPP, PDF, HTML és több mint 30 további formátumot. Ebben a példában a `SaveFileFormat.Xml`-t használtuk.

**Q: Szükségem van licencre a fejlesztői build-ekhez?**  
A: Egy ideiglenes értékelő licenc elegendő a teszteléshez. Bármely termelési környezethez teljes kereskedelmi licenc szükséges.

**Q: Hogyan olvashatom vissza később az egyéni attribútum értékeket?**  
A: Hívd meg a `resource.getExtendedAttributes()` metódust és iterálj a gyűjteményen; a tárolt értéket a `getNumericValue()` vagy `getTextValue()` segítségével érheted el.

---

**Legutóbb frissítve:** 2026-06-10  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre erőforrásokat – Erőforrás-kezelés az Aspose.Tasks for Java segítségével](/tasks/java/resource-management/)
- [Egyéni mező létrehozása Aspose - Kiterjesztett attribútumok kezelése](/tasks/java/project-management/extended-attributes/)
- [Hogyan hozzunk létre projektet – Új feladat attribútumok beállítása az Aspose.Tasks segítségével](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}