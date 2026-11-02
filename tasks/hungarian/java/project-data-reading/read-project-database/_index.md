---
date: 2026-10-31
description: Ismerje meg, hogyan mentheti a projektet PDF-ként és olvashatja a Microsoft
  Project adatbázist az Aspose.Tasks for Java használatával, valamint hogyan csatlakozhat
  a Project Serverhez, konvertálhatja a projektet HTML-re, és exportálhatja XML-be.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Projektadatok olvasása a Microsoft Project adatbázisból az Aspose.Tasks-ben
og_description: Projekt mentése PDF-ként és a Microsoft Project adatbázis olvasása
  az Aspose.Tasks for Java segítségével. Ismerje meg, hogyan csatlakozhat a Project
  Serverhez, és exportálhat HTML, XML és CSV formátumokba.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Projekt mentése PDF-ként és a Microsoft Project adatbázis olvasása az Aspose.Tasks
  for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Projekt mentése PDF-ként és a Microsoft Project adatbázis olvasása az Aspose.Tasks
  for Java segítségével
url: /hu/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt mentése PDF-ként és Microsoft Project adatbázis olvasása az Aspose.Tasks for Java segítségével

## Bevezetés
Ebben az útmutatóban megtudja, hogyan **olvassa a Microsoft Project adatbázist** közvetlenül egy Microsoft Project Serverről, majd **menti a projektet PDF‑ként** az Aspose.Tasks Java API használatával. Akár nyomtatható jelentéseket kell generálnia, örökölt adatokat migrálnia, vagy projektinformációkat beágyaznia egy egyedi portálba, ez az útmutató minden lépésen végigvezet – a JDBC kapcsolat konfigurálásától a projekt PDF, XML vagy HTML formátumba exportálásáig. A végére egy termelésre kész megoldást kap, amely bármely Java szerveren futtatható a Microsoft Project telepítése nélkül.

## Gyors válaszok
- **Mi a feladata az Aspose.Tasks‑nek?** Egy tiszta Java API‑t biztosít a Microsoft Project fájlok és adatbázisok olvasásához, írásához és manipulálásához.  
- **Szükségem van a Microsoft Project telepítésére?** Nem, az Aspose.Tasks független a Microsoft Project‑től.  
- **Milyen adatbázistípus támogatott?** Microsoft SQL Server, a Project Server háttérrendszere.  
- **Exportálhatok más formátumokba?** Igen – PDF, XML, HTML, CSV, PNG, JPEG és továbbiak.  
- **Mik a fő előfeltételek?** JDK 8 vagy újabb, Aspose.Tasks for Java könyvtár, a SQL Server JDBC driver, és érvényes Project Server hitelesítő adatok.

## Mi az a „Microsoft Project adatbázis olvasása”?
A Microsoft Project adatbázis olvasása azt jelenti, hogy csatlakozunk a Project Server SQL Server tárolójához, kinyerjük a tárolt projektadatokat, és betöltjük őket egy `Project` objektumba, amelyet az Aspose.Tasks manipulálni tud. Ez a megközelítés ideális automatizált jelentéskészítéshez, adatátalakításhoz vagy egyedi elemzésekhez.

## Miért használjuk az Aspose.Tasks for Java‑t?
Az Aspose.Tasks for Java lehetővé teszi, hogy a Microsoft Project adatokat a asztali alkalmazás nélkül kezelje, egy tiszta Java megoldást kínálva, amely bármely platformon futtatható. Átfogó objektummodellt biztosít feladatok, erőforrások, naptárak és egyéni mezők számára, és nagy vállalati projekteket is hatékonyan kezel, így ideális automatizált jelentéskészítéshez, migrációhoz és integrációs forgatókönyvekhez.

- **Nincs Microsoft Project függőség** – futtatható bármely szerveren vagy CI környezetben.  
- **Gazdag objektummodell** – programozottan hozzáférhet feladatokhoz, erőforrásokhoz, hozzárendelésekhez, naptárakhoz és egyéni mezőkhöz.  
- **Több exportálási lehetőség** – az Aspose.Tasks támogatja a **20+ fájlformátumba** történő exportálást, beleértve a PDF‑t, XML‑t, HTML‑t, CSV‑t, PNG‑t és JPEG‑t, egyetlen API hívással.  
- **Magas teljesítmény** – a könyvtár egy perc alatt képes feldolgozni **akár 10 000 feladatot** tartalmazó projekteket, és adatfolyamot használ, hogy elkerülje a teljes fájl memóriába töltését.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik a következőkkel:

1. Egy működő Java fejlesztői környezet (JDK 8 vagy újabb).  
2. Az Aspose.Tasks for Java könyvtár hozzáadva a projekt classpath‑jához.  
3. Hozzáférési hitelesítő adatok a Project Server SQL adatbázishoz (szerver neve, port, adatbázis neve, felhasználónév, jelszó) a Project Serverhez való csatlakozáshoz.  
4. A Microsoft JDBC driver a SQL Serverhez (például `sqljdbc4.jar`).

## Csomagok importálása
Először importálja a szükséges osztályokat. A lista tartalmazza az Aspose.Tasks alap osztályait és a standard Java segédeszközöket.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Hogyan csatlakozzunk a Project Serverhez
A megbízható kapcsolat kiépítése a projektadatok olvasásának alapja. Győződjön meg róla, hogy a SQL Server példány elérhető a Java gépről, és a bejelentkezésnek **SELECT** jogosultsága van a Project Server sémára. Ellenőrizze a hálózati késleltetést, és konfigurálja a szükséges SSL beállításokat a biztonságos kommunikáció érdekében.

## 1. lépés: adatbázis kapcsolat beállítása
Az `MspDbSettings` osztály tartalmazza a JDBC kapcsolat részleteit, amelyek a Microsoft Project Server adatbázis eléréséhez szükségesek. Hozzon létre egy `MspDbSettings` példányt, amely a JDBC kapcsolat‑stringet tárolja. Cserélje le a helyőrző értékeket a saját szerveradataira.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Tárolja a kapcsolat‑stringet egy biztonságos konfigurációs fájlban vagy környezeti változóban, ahelyett, hogy a hitelesítő adatokat kódba ágyazná.

## 2. lépés: JDBC driver hozzáadása
Töltse be a Microsoft SQL Server JDBC drivert futásidőben, hogy a JVM kommunikálni tudjon az adatbázissal.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Győződjön meg róla, hogy a driver verziója megfelel az SQL Server verziójának. Egy nem kompatibilis driver kapcsolat‑hibákat okozhat.

## 3. lépés: projektadatok olvasása
Az `Project` osztály egy memóriába betöltött Microsoft Project fájlt képvisel, amely feladatokat, erőforrásokat és hozzárendeléseket tesz elérhetővé. Hozzon létre egy `Project` objektumot az `MspDbSettings` átadásával. Az Aspose.Tasks automatikusan lekéri a projektadatokat az adatbázisból.

```java
Project project = new Project(settings);
```

Ekkor már felfedezheti a `project` objektumot – listázhat feladatokat, erőforrásokat, vagy szükség szerint módosíthat mezőket.

## 4. lépés: projekt mentése PDF‑ként
Az `SaveFileFormat` felsorolás meghatározza a `Project.save` metódus kimeneti formátumát, például PDF, XML vagy HTML. Exportálja a betöltött projektet a kívánt fájlformátumba. Az alábbi példa a projektet **PDF‑ként** menti, ami tökéletes nyomtatható jelentésekhez. A `SaveFileFormat` enum módosításával **exportálhatja a projektet XML‑be** vagy **konvertálhatja HTML‑re** is.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Ha XML‑t szeretne, egyszerűen cserélje le a `SaveFileFormat.Pdf` értéket `SaveFileFormat.Xml`‑re. HTML kimenethez használja a `SaveFileFormat.Html`‑t.

## Gyakori problémák és megoldások
| Probléma | Tipikus ok | Megoldás |
|----------|------------|----------|
| **Kapcsolati időtúllépés** | Helytelen szerver/port vagy tűzfal blokkolja | Ellenőrizze a szerver címét, nyissa meg a 1433‑as portot, és tesztelje a kapcsolatot egy egyszerű JDBC tesztprogrammal. |
| **Hitelesítési hiba** | Érvénytelen felhasználónév/jelszó vagy a SQL Server nincs beállítva SQL hitelesítésre | Használjon érvényes SQL bejelentkezést vagy engedélyezze a vegyes módú hitelesítést a szerveren. |
| **Driver nem található** | A JDBC jar nincs a classpath‑ban | Győződjön meg róla, hogy az `addJDBCDriver` a megfelelő `.jar` fájlra mutat, és az útvonal dupla visszaperjeleket (`\\`) használ. |
| **Üres projekt a betöltés után** | Nem elegendő jogosultság a Project Server táblák olvasásához | Adjon a bejelentkezésnek SELECT jogot a Project Server adatbázis sémájára. |

## Gyakran ismételt kérdések

**Q: Használható az Aspose.Tasks más adatbázisokból is projektadatok olvasására a Microsoft Projecten kívül?**  
A: Igen, az Aspose.Tasks támogatja a projektadatok olvasását XML fájlokból, Primavera adatbázisokból és más szabványos projektformátumokból.

**Q: Kompatibilis az Aspose.Tasks a Microsoft Project különböző verzióival?**  
A: Igen, a könyvtár a Microsoft Project 2007-től a legújabb 2024-es kiadásokig működik, biztosítva a zökkenőmentes integrációt a verziók között.

**Q: Manipulálhatom a projektadatokat mentés előtt?**  
A: Természetesen, a gazdag API segítségével hozzáadhat, frissíthet vagy törölhet feladatokat, erőforrásokat és egyéni mezőket exportálás előtt.

**Q: Támogatja az Aspose.Tasks a többféle kimeneti formátumot?**  
A: Igen, a projekteket mentheti PDF, XML, HTML, CSV, PNG, JPEG és további formátumokba – összesen több mint 20 formátumba.

**Q: Hol találok további támogatást vagy segítséget az Aspose.Tasks-hez?**  
A: További segítségért látogassa meg az Aspose.Tasks fórumot, vagy tekintse meg a weboldalon elérhető dokumentációt: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Következtetés
A lépésről‑lépésre útmutató követésével most már tudja, hogyan **olvassa a Microsoft Project adatbázist**, **mentse a projektet PDF‑ként**, és exportálja más formátumokba az Aspose.Tasks for Java segítségével. Ez a megközelítés megszünteti a Microsoft Project függőségét, egyszerűsíti az automatizált jelentéskészítést, és lehetővé teszi a hatékony egyedi integrációkat.

---

**Legutóbb frissítve:** 2026-10-31  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan mentse a projektet PDF‑ként az Aspose.Tasks‑el – Export útmutató](/tasks/java/project-file-operations/save-as-pdf/)
- [Projekt mentése PDF‑ként – Feladatlapon megjelenítés az Aspose.Tasks for Java‑val](/tasks/java/task-properties/render-task-sheet/)
- [Projekt exportálása PDF‑be és a feladatlista és lábléc közti hézag csökkentése az Aspose.Tasks‑ben](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}