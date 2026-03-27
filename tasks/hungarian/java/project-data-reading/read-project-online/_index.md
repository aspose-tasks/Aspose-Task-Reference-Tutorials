---
date: 2026-02-18
description: Tanulja meg, hogyan olvassa be az MS Project Online adatokat az Aspose.Tasks
  Java használatával. Ez az útmutató bemutatja, hogyan lehet lekérni a projektlistát,
  a SharePoint projektek listáját, és az erőforrások számát.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Könnyed MS Project Online adatolvasás'
url: /hu/java/project-data-reading/read-project-online/
weight: 13
---

18  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

Translate labels.

**Last Updated:** -> **Utolsó frissítés:** etc.

**Tested With:** -> **Tesztelve:** etc.

**Author:** -> **Szerző:** etc.

Then closing shortcodes.

Also backtop button shortcode unchanged.

Now produce final content with same markdown.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Gondtalan MS Project Online adatok olvasása

## Bevezetés
A projektmenedzsment világában a Microsoft Project Online adatok hatékony kezelése elengedhetetlen a zökkenőmentes működéshez. **aspose tasks java** egy robusztus, könnyen használható API-t biztosít, amely lehetővé teszi a Project Online adatok olvasását anélkül, hogy alacsony szintű HTTP hívásokkal kellene küzdeni. Ebben az útmutatóban végigvezetünk a projektlista lekérésén, a **SharePoint projektek listázásán**, és az egyes projektek **erőforrás-számának** meghatározásán – mindezt csak néhány Java sorral.

## Gyors válaszok
- **Mit csinál az aspose tasks java?** Programozott módon olvassa és módosítja a Microsoft Project fájlokat és a Project Online adatokat.  
- **Szükségem van licencre a kipróbáláshoz?** Elérhető ingyenes próba; licenc szükséges a termelési használathoz.  
- **Milyen hitelesítő adatokra van szükség?** SharePoint domain, felhasználónév és jelszó (vagy Azure AD token).  
- **Listázhatok SharePoint projekteket?** Igen – használja a `ProjectServerManager.getProjectList()` metódust a lekéréshez.  
- **Hogyan kapom meg az erőforrások számát?** Töltse be minden `Project` objektumot, és hívja a `project.getResources().size()` metódust.

## Mi az aspose tasks java?
**aspose tasks java** egy fejlesztőközpontú könyvtár, amely elrejti a Microsoft Project fájlformátumok és a Project Server REST API összetettségét. Lehetővé teszi a projektadatok olvasását, létrehozását és módosítását közvetlenül Java alkalmazásokból, megkönnyítve az integrációt a meglévő vállalati rendszerekkel.

## Miért használjuk az aspose tasks java-t MS Project Online olvasásához?
- **Nincs manuális HTTP kezelés** – a könyvtár gondoskodik a hitelesítésről és a REST hívásokról.  
- **Erős típusbiztonság** – dolgozzon `Project`, `ProjectInfo` és más POJO-kkal a nyers JSON helyett.  
- **Keresztplatformos** – bármely JVM‑kompatibilis környezetben fut.  
- **Gazdag funkciókészlet** – az olvasás mellett feladatokat, erőforrásokat és ütemterveket is frissíthet.  
- **Belsőleg a Project Server REST API-t használja**, így stabil, támogatott kommunikációs réteget kap.

## Előkövetelmények
Mielőtt belevágna, győződjön meg róla, hogy rendelkezik a következőkkel:

1. **Java Development Kit (JDK)** – telepített JDK 8 vagy újabb.  
2. **Aspose.Tasks for Java könyvtár** – letölthető [itt](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online fiók** – projektek olvasásához szükséges jogosultságokkal.  
4. **SharePoint domain cím** – ahol a Project Online példány található.  
5. **Felhasználónév és jelszó** – vagy megfelelő Azure AD hitelesítő adatok a bejelentkezéshez.

## Csomagok importálása
Először importálja azokat az alapvető Aspose.Tasks osztályokat, amelyeket a teljes útmutató során használni fog:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 1. lépés: SharePoint domain, felhasználónév és jelszó beállítása
Határozza meg a kapcsolati adatokat a Project Online környezetéhez. Cserélje le a helyőrző értékeket a saját hitelesítő adataira.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## 2. lépés: Hitelesítés a Project Server hitelesítő adatokkal
Hozzon létre egy `ProjectServerCredentials` objektumot, és inicializáljon egy `ProjectServerManager`‑t. Ez a menedzser kezeli majd a további hívásokat a Project Online felé.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## 3. lépés: Projektlista lekérése és információk megjelenítése
Használja a menedzsert a **projektlista lekéréséhez** (azaz a SharePoint projektek listázásához), és írja ki az alapvető adatokat, például a nevet, a létrehozás dátumát és az utolsó mentés dátumát.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## 4. lépés: Egyedi projektek betöltése és erőforrás-szám kiírása
Az előző lépésben kapott minden projekthez töltse be a teljes `Project` objektumot – ez a hívás **betölti a projekt adatokat** a megadott azonosítóhoz – és jelenítse meg a **erőforrás-számot**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Gyakori problémák és megoldások
| Issue | Reason | Fix |
|-------|--------|-----|
| **Hitelesítés sikertelen** | Helytelen domain, felhasználónév vagy jelszó. | Ellenőrizze a hitelesítő adatokat, és győződjön meg róla, hogy a fióknak van Project Online olvasási jogosultsága. |
| **SSLHandshakeException** | A Java futtatókörnyezet nem rendelkezik a szükséges TLS verzióval. | Frissítse a JDK-t a legújabb kiadásra, vagy engedélyezze a TLS 1.2+ támogatást. |
| ``reader.getProjectList()`` üres eredményt ad | A fióknak nincs hozzáférése projektekhez. | Ellenőrizze a Project Online jogosultságokat, vagy használjon admin fiókot. |
| **Nagy projektek OutOfMemoryError-t okoznak** | Sok projekt egyidejű betöltése memóriát fogyaszt. | Töltse be a projekteket egyenként, és használat után szabadítsa fel a hivatkozásokat. |

## Gyakran Ismételt Kérdések
**Q:** Használhatom az aspose tasks java-t MS Project Online adatok módosítására?  
**A:** Igen, az Aspose.Tasks kiterjedt lehetőségeket biztosít mind az olvasásra, **mind** a Project Online adatok programozott módon történő módosítására.

**Q:** Támogatja az Aspose.Tasks más projektmenedzsment fájlformátumokat is?  
**A:** Teljes mértékben. Támogatja az MPP, XML, Primavera és még sok más formátumot, biztosítva a kompatibilitást a különböző projektökoszisztémák között.

**Q:** Elérhető ingyenes próba az Aspose.Tasks for Java-hoz?  
**A:** Igen, egy ingyenes próbát igényelhet [itt](https://releases.aspose.com/), hogy felfedezze az Aspose.Tasks funkcióit és lehetőségeit.

**Q:** Hol találok átfogó dokumentációt az Aspose.Tasks for Java-hoz?  
**A:** Részletes dokumentációt találsz [itt](https://reference.aspose.com/tasks/java/), amely átfogó útmutatót nyújt az Aspose.Tasks Java projektekben való használatához.

**Q:** Milyen támogatási lehetőségek állnak rendelkezésre az Aspose.Tasks for Java-hoz?  
**A:** Ha bármilyen problémába ütközik vagy kérdése van, segítséget kérhet az Aspose.Tasks közösségi fórumon [itt](https://forum.aspose.com/c/tasks/15).

---

**Utolsó frissítés:** 2026-02-18  
**Tesztelve:** Aspose.Tasks for Java 24.11 (a legújabb a kiírás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}