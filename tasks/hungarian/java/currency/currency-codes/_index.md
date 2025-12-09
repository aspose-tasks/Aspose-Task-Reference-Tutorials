---
date: 2025-12-09
description: Ismerje meg, hogyan olvashat MS Project fájlt, és kezelheti hatékonyan
  a pénznemkódokat az Aspose.Tasks for Java segítségével. Egyszerűen optimalizálja
  projektmenedzsment feladatait.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan olvassuk be az MS Project fájlt, és kezeljük a pénznemkódokat az Aspose.Tasks
  segítségével
url: /hu/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan olvassuk be az MS Project fájlt és kezeljük a pénznemkódokat az Aspose.Tasks segítségével

## Bevezetés
Welcome! In this tutorial you'll discover **how to read MS Project file** data and specifically **manage currency codes** using the Aspose.Tasks Java API. Whether you're generating reports, consolidating multi‑currency projects, or simply need to ensure the correct financial symbols appear, this guide walks you through every step— from setting up your environment to retrieving the currency code programmatically. By the end, you’ll be comfortable reading MS Project files and extracting the currency information you need.

## Gyors válaszok
- **Mi a API feladata?** Az MS Project fájlokat olvassa be, és elérhetővé teszi a tulajdonságokat, például a pénznemkódot.  
- **Melyik nyelvet használja?** Java, az Aspose.Tasks for Java könyvtáron keresztül.  
- **Szükségem van licencre?** A fejlesztéshez ingyenes próba verzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Lekérhetem a kódot egy sorban?** Igen—`prj.get(Prj.CURRENCY_CODE)` visszaadja a pénznemkód karakterláncot.  
- **Kompatibilis-e minden Project verzióval?** Az Aspose.Tasks támogatja a régebbi (MPP) és az újabb (XML, XER) formátumokat is.

## Mi az a **read ms project file**?
Reading an MS Project file means programmatically opening a *.mpp* (or other supported) project document and accessing its data structures—tasks, resources, calendars, and financial settings—without manual interaction with Microsoft Project itself.

## Miért használjuk az Aspose.Tasks-et **read msproject** fájlokhoz?
- **Teljes formátumtámogatás** – fájlokkal működik a Project 98-tól a legújabb Office kiadásokig.  
- **Nincs szükség COM vagy Office telepítésre** – tiszta Java, tökéletes szerveroldali automatizáláshoz.  
- **Gazdag API** – közvetlen hozzáférést biztosít olyan tulajdonságokhoz, mint a `Prj.CURRENCY_CODE`, lehetővé téve a **how to retrieve currency** információ azonnali lekérését.  
- **Teljesítmény** – könnyű súlyú elemzés, ideális sok projekt kötegelt feldolgozásához.

## Prerequisites
Before we dive into the code, ensure you have the following:

### Java Development Kit (JDK) telepítve
Make sure a recent JDK is available on your machine. You can download and install the latest JDK version from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java könyvtár
Download and set up the Aspose.Tasks for Java library. Detailed documentation and the latest binaries are available [here](https://reference.aspose.com/tasks/java/).

## Csomagok importálása
To get started, let's import the necessary packages in your Java project:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Adatkönyvtár beállítása
Define the folder that contains your *.mpp* file. Adjust the path to match your environment.
```java
String dataDir = "Your Data Directory";
```

### 2. lépés: Projektfájl betöltése
Create a `Project` instance by loading the MS Project file. This is the point where you **read msproject** data into memory.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### 3. lépés: Pénznemkód lekérése
Now that the project is loaded, you can **how to retrieve currency** information with a single call. This demonstrates **get currency code java** usage.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
The output will be the three‑letter ISO currency code (e.g., `USD`, `EUR`, `GBP`) that the project is configured to use.

### 4. lépés: (Opcionális) A pénznemkód használata
You might want to apply the retrieved code elsewhere—such as formatting cost values in a custom report or passing it to a financial API. Here’s a quick illustration (no additional code block needed):
- Store the code in a variable.  
- Use it when constructing monetary strings.  
- Pass it to downstream services that require a currency identifier.

## Gyakori problémák és megoldások
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | A projektfájl nem határoz meg pénznemet (alapértelmezés szerint üres). | Set the currency in Microsoft Project or assign it via `prj.set(Prj.CURRENCY_CODE, "USD");` before reading. |
| **File not found** | Helytelen `dataDir` útvonal. | Verify the path and ensure the file name matches exactly, including case sensitivity. |
| **Unsupported file version** | Nagyon régi vagy sérült *.mpp* fájl. | Use the latest Aspose.Tasks version or convert the file to a newer format in Microsoft Project first. |

## Gyakran feltett kérdések

**Q: Can Aspose.Tasks handle complex project structures?**  
A: Yes, the API can read and manipulate multi‑level task hierarchies, resource pools, and custom fields without issue.

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: Absolutely. It supports MPP, XML, XER, and other formats across many Microsoft Project releases.

**Q: Does Aspose.Tasks provide documentation and support?**  
A: Comprehensive documentation, code examples, and dedicated support are available on the Aspose website.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: A free trial is offered so you can evaluate all features, including reading currency codes.

**Q: Where can I get temporary licenses for Aspose.Tasks?**  
A: Temporary licenses can be obtained from the [website](https://purchase.aspose.com/temporary-license/) for short‑term evaluation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Legutóbb frissítve:** 2025-12-09  
**Tesztelve:** Aspose.Tasks for Java (latest version)  
**Szerző:** Aspose