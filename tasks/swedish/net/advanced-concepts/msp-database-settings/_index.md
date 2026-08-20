---
date: 2026-03-14
description: Lär dig hur du specificerar databasschema för en Microsoft Project‑databas
  med Aspose.Tasks och hur du importerar projektdata till .NET‑applikationer.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Specificera databasschema för Project DB med Aspose.Tasks
url: /sv/net/advanced-concepts/msp-database-settings/
weight: 19
---

1 etc.

- "Last Updated:" => "Senast uppdaterad:"

- "Tested With:" => "Testad med:"

- "Author:" => "Författare:"

Make sure to keep code block placeholders unchanged.

Also keep markdown links unchanged.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Inställningar för Microsoft Project-databas i Aspose.Tasks

## Introduktion

Om du arbetar med Microsoft Project‑databaser i dina .NET‑applikationer med Aspose.Tasks, måste du **specificera databasschema** och konfigurera de nödvändiga inställningarna för att **importera projekt**‑data sömlöst. Denna handledning guidar dig steg för steg genom processen och visar dig **hur du konfigurerar anslutnings**‑detaljer, **skapar .NET‑anslutningssträng**, och slutligen **sparar projekt som MPP**.

## Snabba svar
- **Vad är huvudmålet?** Att specificera databasschema och importera en Project‑databas till en .NET‑app.  
- **Vilket bibliotek krävs?** Aspose.Tasks för .NET.  
- **Hur ansluter jag till Project Server?** Genom att bygga en korrekt SQL‑anslutningssträng och använda `MspDbSettings`.  
- **Vilket filformat produceras?** En MPP‑fil sparad med `SaveFileFormat.Mpp`.  
- **Kan jag ändra schemnamnet?** Ja, sätt `Schema`‑egenskapen på `MspDbSettings`.

## Hur man specificerar databasschema för Project DB

Att förstå varför du kan behöva **specificera databasschema** är viktigt. I många företagsmiljöer ligger Project Server‑databasen under ett anpassat schema (t.ex. `dbo`, `psdata`). Genom att explicit ange schemat säkerställer du att Aspose.Tasks frågar rätt tabeller, vilket förhindrar körningsfel och garanterar korrekt dataimport.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks‑biblioteket från [here](https://releases.aspose.com/tasks/net/).  
2. Tillgång till en Microsoft Project‑databas: Du bör ha åtkomst till en Microsoft Project‑databas för att importera data från.  

## Importera namnrymder

Se först till att du importerar de nödvändiga namnrymderna till ditt projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Steg 1: Skapa anslutningssträng

Bygg anslutningssträngen till din Microsoft Project‑databas. Här **skapar du .NET‑anslutningssträng** och definierar också hur du **ansluter till Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Proffstips:** Dubbelkolla värdena för `DataSource` och `InitialCatalog`; de måste matcha din servers adress och det publicerade databasenamnet.

## Steg 2: Konfigurera MspDbSettings

Skapa en instans av `MspDbSettings`, skicka in anslutningssträngen och **specificera databasschema** genom att sätta `Schema`‑egenskapen. Detta talar om för Aspose.Tasks vilket schema som ska frågas.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Här anger vi också projekt‑GUID‑en som identifierar det specifika projekt du vill ladda.

## Steg 3: Ladda projektdata

Instansiera ett `Project`‑objekt med de konfigurerade inställningarna. Detta steg visar **hur man importerar projekt**‑data från databasen till ett .NET‑objekt.

```csharp
var project = new Project(settings);
```

## Steg 4: Spara projektdata

Till sist, skriv det laddade projektet till en MPP‑fil på disk. Detta demonstrerar **spara projekt som MPP** med Aspose.Tasks‑API:n.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Efter att koden har körts hittar du filen `ImportProjectDataFromDatabase_out.mpp` i utdata‑katalogen, klar att öppnas i Microsoft Project.

## Slutsats

I den här handledningen har du lärt dig hur du **specificerar databasschema** för en Microsoft Project‑databas, **konfigurerar anslutningen**, **importerar projekt**‑data och **sparar projektet som MPP** med Aspose.Tasks för .NET. Dessa steg möjliggör sömlös integration av Project Server‑data i dina egna applikationer och hjälper dig att bygga robusta projekt‑hanteringslösningar.

## Vanliga frågor

### Q1: Kan jag använda Aspose.Tasks med olika versioner av Microsoft Project‑databaser?
A1: Ja, Aspose.Tasks stödjer olika versioner av Microsoft Project‑databaser, vilket ger flexibilitet i integrationen.

### Q2: Hur kan jag felsöka anslutningsproblem med databasen?
A2: Säkerställ att din anslutningssträng är korrekt konfigurerad med rätt autentiseringsuppgifter och databasinformation. Du kan också hänvisa till dokumentationen eller söka stöd i [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q3: Finns det en provversion av Aspose.Tasks?
A3: Ja, du kan få en gratis provversion från [here](https://releases.aspose.com/).

### Q4: Kan jag anpassa schemat för databaskommunikation?
A4: Ja, du kan ange schemat för `MspDbSettings`‑objektet enligt din databasstruktur.

### Q5: Var kan jag hitta mer detaljerad dokumentation om hur man använder Aspose.Tasks?
A5: Du kan utforska den omfattande dokumentationen [here](https://reference.aspose.com/tasks/net/) för djupgående insikter om Aspose.Tasks‑funktioner.

**Q: Fungerar detta tillvägagångssätt med Azure SQL‑databaser?**  
A: Absolut. Justera bara `DataSource` till ditt Azure‑servernamn och se till att TLS/SSL‑inställningarna är aktiverade.

**Q: Hur hanterar jag stora Project‑databaser utan att få timeout?**  
A: Öka `ConnectTimeout`‑värdet i anslutningssträngen och överväg att ladda projekt i batchar om det behövs.

---

**Senast uppdaterad:** 2026-03-14  
**Testad med:** Aspose.Tasks 24.12 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}