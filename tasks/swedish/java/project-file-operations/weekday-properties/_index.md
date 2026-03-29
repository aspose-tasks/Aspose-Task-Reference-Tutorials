---
date: 2026-03-29
description: Lär dig hur du ändrar dagar per månad och hanterar andra veckodagsegenskaper
  i Aspose.Tasks för Java. Anpassa veckostartdatum, ändra projektkalender och spara
  projektet som XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ändra dagar per månad med Aspose.Tasks veckodagsegenskaper
url: /sv/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändra dagar per månad med Aspose.Tasks veckodags‑egenskaper

## Introduktion
Aspose.Tasks för Java låter dig **ändra dagar per månad** och finjustera andra veckodagsinställningar utan att behöva Microsoft Project installerat. Oavsett om du anpassar en projektkalender till en icke‑standardiserad räkenskapsmånad eller bara behöver justera veckans startdag, guidar den här handledningen dig genom de vanligaste scenarierna — hämta den aktuella veckans startdag, anpassa startdatumet för veckan, ändra projektkalendern och spara projektet som XML.

## Snabba svar
- **Kan jag ändra antalet dagar per månad?** Ja, använd `Prj.DAYS_PER_MONTH` på `Project`‑objektet.  
- **Hur anpassar jag veckans startdatum?** Sätt `Prj.WEEK_START_DAY` till ett `DayType`‑värde (t.ex. `DayType.Monday`).  
- **Vilket format kan jag använda för att exportera projektet?** Exemplet sparar filen som XML med `SaveFileFormat.Xml`.  
- **Krävs en licens för produktionsanvändning?** En giltig Aspose.Tasks‑licens behövs för icke‑utvärderingsdistributioner.  
- **Vilka IDE‑miljöer stöds?** Alla Java‑IDE:er som IntelliJ IDEA, Eclipse eller NetBeans fungerar.

## Vad betyder “change days per month” i Aspose.Tasks?
Att ändra dagar per månad innebär att uppdatera egenskapen `Prj.DAYS_PER_MONTH` för en `Project`‑instans. Denna egenskap talar om för motorn hur många arbetsdagar den ska räkna med i varje månad, vilket direkt påverkar uppgiftsschemaläggning och kostnadsberäkningar.

## Varför ändra projektkalenderns egenskaper?
Att anpassa projektkalendern — som att ange en annan veckostartdag eller ändra minuter per dag — hjälper dig att:

- Anpassa scheman efter regionala arbetsveckor.  
- Modellera icke‑standard arbetsmönster (t.ex. 4‑dagarsveckor).  
- Säkerställa korrekt rapportering för kontrakt som använder anpassade kalendrar.

## Förutsättningar
- **Java Development Kit (JDK)** – Installera den senaste JDK:n från Oracle.  
- **Aspose.Tasks for Java‑bibliotek** – Ladda ner det från den officiella webbplatsen [här](https://releases.aspose.com/tasks/java/).  
- **IDE efter eget val** – IntelliJ IDEA, Eclipse eller NetBeans.

## Importera paket
Först, importera de nödvändiga Aspose.Tasks‑klasserna:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Steg 1: Ladda projektfil
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Detta laddar en befintlig Microsoft Project‑fil (`project.mpp`) från den mapp du anger.

## Steg 2: Visa veckodags‑egenskaper
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Här hämtar och skriver vi ut de aktuella veckodagsinställningarna, inklusive **veckans startdag** och **dagar per månad**.

## Steg 3: Ställa in veckodags‑egenskaper
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
I detta steg **ändrar vi dagar per månad** till 24, sätter veckan att börja på måndag och justerar minuter per dag/vecka. Detta visar hur man programatiskt **ändrar projektkalender**‑värden.

## Steg 4: Spara projekt
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Det modifierade projektet sparas med formatet **save project as XML**, vilket är praktiskt för integration med andra verktyg eller för versionskontrollerad lagring.

## Steg 5: Visa resultat
```java
System.out.println("Process completed Successfully");
```
En enkel bekräftelse på att operationerna avslutades utan fel.

## Hur man anpassar veckans startdatum
Om din organisation följer en söndag‑först‑kalender, ersätt `DayType.Monday` med `DayType.Sunday`. Samma egenskap (`Prj.WEEK_START_DAY`) används, vilket gör ändringen enkel.

## Hur man hämtar veckans startdag
Du kan anropa `project.get(Prj.WEEK_START_DAY)` när som helst för att **hämta veckans startdag**‑information, som visas i Steg 2.

## Hur man ändrar projektkalendern
Utöver veckans startdag kan du även justera `Prj.MINUTES_PER_DAY` och `Prj.MINUTES_PER_WEEK` för att spegla anpassade arbetstimmar eller skiftmönster.

## Vanliga problem och lösningar
- **Felaktigt dagtyp‑värde** – Se till att du använder `DayType`‑enumet (t.ex. `DayType.Monday`).  
- **Fel i filsökväg** – Verifiera att `dataDir` slutar med rätt filseparator (`/` eller `\`).  
- **Licens ej satt** – Om du ser licensvarningar, registrera din Aspose.Tasks‑licens innan du skapar `Project`‑objektet.

## Vanliga frågor

**Q: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?**  
A: Ja, Aspose.Tasks för Java erbjuder omfattande stöd för att hantera komplexa projektstrukturer med lätthet.

**Q: Är Aspose.Tasks för Java kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Absolut, Aspose.Tasks för Java stöder olika versioner av Microsoft Project‑filer, vilket säkerställer kompatibilitet över plattformar.

**Q: Kan jag integrera Aspose.Tasks för Java i mina befintliga Java‑applikationer?**  
A: Ja, Aspose.Tasks för Java erbjuder sömlösa integrationsmöjligheter, så att du kan förbättra dina Java‑applikationer med kraftfulla projektledningsfunktioner.

**Q: Tillhandahåller Aspose.Tasks för Java dokumentation och support?**  
A: Ja, du kan få tillgång till omfattande dokumentation och community‑support för Aspose.Tasks för Java på deras [webbplats](https://releases.aspose.com/).

**Q: Finns det en gratis provversion av Aspose.Tasks för Java?**  
A: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks för Java från deras [webbplats](https://reference.aspose.com/tasks/java/) för att utforska funktionerna innan du gör ett köp.

---

**Senast uppdaterad:** 2026-03-29  
**Testat med:** Aspose.Tasks för Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}