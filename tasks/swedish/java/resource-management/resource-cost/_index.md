---
date: 2026-01-15
description: Lär dig hur du arbetar med budgeterad kostnadsarbete som är schemalagt
  i Microsoft Project‑filer med Aspose.Tasks för Java. Följ vår steg‑för‑steg‑guide.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Budgeterad kostnadsarbete schemalagt med Aspose.Tasks för Java
url: /sv/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# budgeterad kostnad för planerat arbete med Aspose.Tasks för Java

## Introduktion

Att hantera **budgeterad kostnad för planerat arbete** (BCWS) är avgörande för att hålla ett projekt på rätt spår och säkerställa att den finansiella prognosen stämmer överens med det planerade arbetet. I Microsoft Project representerar BCWS den mängd pengar som skulle ha spenderats för det arbete som är planerat fram till ett specifikt datum. Aspose.Tasks för Java ger dig full programmatisk kontroll över dessa värden, så att du kan läsa, ändra och rapportera om resurskostnader utan att någonsin öppna .mpp‑filen manuellt. I den här handledningen går vi igenom ett komplett exempel som visar hur du laddar ett projekt, itererar över dess resurser och visar den budgeterade kostnaden för planerat arbete tillsammans med andra viktiga kostnadsmått.

## Snabba svar
- **Vad betyder BCWS?** Budgeted Cost Work Scheduled – den planerade kostnaden för arbete som är schemalagt fram till datumet.  
- **Vilken API‑egenskap hämtar BCWS?** `Rsc.BCWS` på ett `Resource`‑objekt.  
- **Behöver jag en licens för att köra exemplet?** En gratis utvärderingslicens fungerar för testning; en full licens krävs för produktion.  
- **Kan jag ändra BCWS‑värden?** Ja, du kan sätta `Rsc.BCWS` precis som vilket annat numeriskt fält som helst.  
- **Vilka Project‑versioner stöds?** Alla Microsoft Project‑versioner från 2000 till det senaste .mpp‑formatet.

## Vad är budgeterad kostnad för planerat arbete?

**Budgeted Cost Work Scheduled (BCWS)** är ett prestationsmått som visar den kostnad som borde ha uppkommit för det arbete som planerats fram till en viss tidpunkt. Det är en hörnsten i Earned Value Management (EVM) och hjälper projektledare att jämföra planerad mot faktisk utgift.

## Förutsättningar

Innan du dyker ner i koden, se till att du har:

1. En solid förståelse för Java‑grunderna.  
2. Aspose.Tasks för Java tillagt i ditt projekt (Maven/Gradle eller JAR).  
3. En Microsoft Project‑fil (`.mpp`) som innehåller resurser med kostnadsdata (t.ex. *ResourceCosts.mpp*).

## Importera paket

Först importerar du de Aspose.Tasks‑klasser som behövs för att hantera projekt och resurser:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Steg 1: Definiera datakatalogen

```java
String dataDir = "Your Data Directory";
```

Byt ut `"Your Data Directory"` mot den absoluta eller relativa sökvägen där *ResourceCosts.mpp* finns.

## Steg 2: Ladda MS Project‑filen

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

`Project`‑konstruktorn läser .mpp‑filen och bygger en minnesrepresentation som du kan fråga.

## Steg 3: Iterera genom resurser

```java
for (Resource res : prj.getResources()) {
```

Denna loop går igenom varje resurs som definierats i projektet och ger dig åtkomst till dess kostnadsfält.

## Steg 4: Kontrollera resursnamn och kostnader

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Inuti `if`‑blocket:

* Skriv ut **total kostnad** (`Rsc.COST`).  
* Skriv ut **faktisk kostnad för utfört arbete** (`Rsc.ACWP`).  
* Skriv ut **budgeterad kostnad för planerat arbete** (`Rsc.BCWS`) – det primära måttet vi fokuserar på.  
* Skriv ut **budgeterad kostnad för utfört arbete** (`Rsc.BCWP`).

Dessa fyra värden ger dig en snabb överblick över projektets ekonomiska status.

## Varför övervakning av budgeterad kostnad för planerat arbete är viktigt

* **Tidigt varningssystem:** Om BCWS är avsevärt högre än den faktiska kostnaden kan du ha överallokerat resurser.  
* **Earned Value‑analys:** BCWS är en nyckelindata för att beräkna Cost Variance (CV) och Schedule Variance (SV).  
* **Prognostisering:** Korrekt BCWS‑data hjälper till att förutsäga framtida kassaflödesbehov och underlättar rapportering till intressenter.

## Vanliga problem & felsökning

| Symtom | Trolig orsak | Åtgärd |
|--------|--------------|-------|
| `null` skrivs ut för BCWS | Resursen har ingen kostnadsräntetabell definierad | Definiera en kostnadsräntetabell för resursen i Microsoft Project eller sätt den programatiskt via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` vid iteration av resurser | Projektfilen är korrupt eller innehåller tomma resursposter | Validera .mpp‑filen i Microsoft Project och ta bort tomma resurser |
| Oväntade värden (t.ex. negativ BCWS) | Anpassade fält som överskuggar standardkostnadsfält | Säkerställ att du åtkommer till standard `Rsc.BCWS` och inte ett anpassat fält med samma namn |

## Vanliga frågor

**Q: Kan jag uppdatera BCWS‑värdet programatiskt?**  
A: Ja. Använd `res.set(Rsc.BCWS, newValue)` och spara sedan projektet med `prj.save("Updated.mpp")`.

**Q: Stöder Aspose.Tasks projekt med flera valutor?**  
A: Absolut. Kostnadsfält respekterar de valutainställningar som definierats i projektfilen.

**Q: Finns det ett sätt att exportera dessa kostnadsmått till CSV?**  
A: Du kan iterera över resurserna och skriva värdena till en `StringBuilder` eller använda ett CSV‑bibliotek för att generera filen.

**Q: Hur skiljer sig BCWS från BCWP?**  
A: BCWS är den planerade kostnaden för schemalagt arbete, medan BCWP (Budgeted Cost Work Performed) visar den planerade kostnaden för arbete som faktiskt har slutförts.

**Q: Behöver jag en speciell licens för att läsa kostnadsdata?**  
A: Utvärderingslicensen ger full läs‑/skriv‑åtkomst; en kommersiell licens krävs för produktionsmiljöer.

## Slutsats

Genom att utnyttja Aspose.Tasks för Java får du exakt, programmatisk åtkomst till **budgeterad kostnad för planerat arbete** och andra viktiga kostnadsmått. Detta gör det möjligt att bygga anpassade instrumentpaneler, automatisera Earned Value‑rapporter och hålla dina projekt ekonomiskt på rätt spår – utan manuell interaktion med Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-15  
**Testad med:** Aspose.Tasks för Java 24.12 (senaste)  
**Författare:** Aspose