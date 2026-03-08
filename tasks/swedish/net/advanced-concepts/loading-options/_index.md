---
date: 2026-03-08
description: Lär dig hur du importerar projektfil med Aspose.Tasks för .NET, inklusive
  hur du specificerar filkodning och laddar Microsoft Project-filen effektivt.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Importera projektfil – Alternativ för inläsning i Aspose.Tasks
url: /sv/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Importera projektfil – Alternativ för inläsning i Aspose.Tasks

## Introduktion

Aspose.Tasks for .NET gör det enkelt att **importera projektfil**‑data från Microsoft Project, Primavera och andra format. Oavsett om du behöver läsa en lösenordsskyddad fil, ange en anpassad kodning eller hantera parsningfel, ger biblioteket dig fin‑granulär kontroll via inläsningsalternativ. I den här handledningen går vi igenom de vanligaste scenarierna så att du tryggt kan **ladda Microsoft Project‑fil**‑objekt i dina .NET‑applikationer.

## Snabba svar
- **Vad är det primära sättet att importera en projektfil?** Använd `Project`‑konstruktorn med en `LoadOptions`‑instans.  
- **Kan jag öppna lösenordsskyddade filer?** Ja – sätt `Password`‑egenskapen på `LoadOptions`.  
- **Hur anger jag filkodning?** Tilldela ett `Encoding`‑objekt till `LoadOptions.Encoding`.  
- **Kan felhantering anpassas?** Absolut – tillhandahåll en delegat till `LoadOptions.ErrorHandler`.  
- **Fungerar dessa alternativ med Primavera‑filer?** Ja, via `PrimaveraReadOptions` i `LoadOptions`.

## Förutsättningar

Innan du dyker ner, se till att du har:

1. **Visual Studio** (eller någon annan föredragen .NET‑IDE).  
2. **Aspose.Tasks for .NET** – ladda ner den från [website](https://releases.aspose.com/tasks/net/).  
3. En grundläggande förståelse för **C#**‑syntax och projektstruktur.

Nu när vi är klara, låt oss importera de nödvändiga namnrymderna.

## Importera namnrymder

I ditt C#‑projekt, lägg till följande `using`‑satser så att API‑klasserna är tillgängliga:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Så importerar du projektfil med inläsningsalternativ

Nedan följer fyra praktiska exempel som täcker de vanligaste inläsningsscenarierna.

### Steg 1: Ladda ett lösenordsskyddat projekt

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Steg 2: Ladda ett Primavera‑projekt med anpassade alternativ

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Steg 3: **Ange filkodning** när du importerar en XER‑fil

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Steg 4: Ladda ett Primavera‑projekt med anpassad felhantering

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Genom att följa dessa steg kan du exakt **importera projektfil**‑data, anpassa inläsningsprocessen efter dina behov och hålla din applikation robust.

## Vanliga problem & tips

- **Fel lösenord** – `Password`‑egenskapen kastar ett undantag; verifiera referensen innan inläsning.  
- **Ej stödd kodning** – säkerställ att den kodsida du anger finns på målmaskinen (`Encoding.GetEncoding(1251)` fungerar för kyrilliska).  
- **Saknade Primavera‑alternativ** – om du behöver bevara uppgifts‑UIDs, sätt `PreserveUids = true`; annars kan dubblett‑ID:n uppstå.  
- **Felhanterare returnerar null** – att returnera `null` signalerar parsern att hoppa över det problematiska elementet; anpassa efter behov.

## Vanliga frågor

**Q: Är Aspose.Tasks for .NET kompatibel med alla versioner av Microsoft Project?**  
A: Ja, den stöder ett brett spektrum av Microsoft Project‑versioner, så du kan **ladda Microsoft Project‑fil**‑format från äldre MPP‑filer till de senaste formaten.

**Q: Kan jag integrera Aspose.Tasks for .NET med andra tredjepartsbibliotek?**  
A: Absolut. Biblioteket fungerar sömlöst med andra .NET‑paket, vilket gör att du kan kombinera det med rapportering, UI eller data‑access‑ramverk.

**Q: Tillhandahåller Aspose.Tasks for .NET dokumentation och supportresurser?**  
A: Ja, du kan hänvisa till den omfattande [documentation](https://reference.aspose.com/tasks/net/) och få support via [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Finns det licensalternativ för Aspose.Tasks for .NET?**  
A: Ja, du kan utforska olika licensalternativ, inklusive gratis provperioder och tillfälliga licenser, på [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: Hur ofta släpps uppdateringar och nya funktioner för Aspose.Tasks for .NET?**  
A: Aspose.Tasks får regelbundna uppdateringar som lägger till funktioner, förbättrar prestanda och bibehåller kompatibilitet med de senaste Microsoft Project‑utgåvorna.

---

**Senast uppdaterad:** 2026-03-08  
**Testad med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}