---
date: 2026-03-08
description: Leer hoe u een projectbestand importeert met Aspose.Tasks voor .NET,
  inclusief hoe u de bestandscodering opgeeft en een Microsoft Project‑bestand efficiënt
  laadt.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projectbestand importeren – Opties voor het laden in Aspose.Tasks
url: /nl/net/advanced-concepts/loading-options/
weight: 16
---

 all shortcodes exactly.

Now ensure we didn't miss any markdown formatting. The code block placeholders are fine.

Check bullet list formatting: Use "- " as original.

Check that we kept all links unchanged.

Now produce final output with all translated content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projectbestand importeren – Opties voor laden in Aspose.Tasks

## Inleiding

Aspose.Tasks for .NET maakt het eenvoudig om **projectbestand** gegevens te importeren vanuit Microsoft Project, Primavera en andere formaten. Of u nu een met wachtwoord beveiligd bestand moet lezen, een aangepaste codering moet instellen, of parse‑fouten moet afhandelen, de bibliotheek biedt u fijnmazige controle via laadopties. In deze tutorial lopen we de meest voorkomende scenario's door zodat u met vertrouwen **Microsoft Project‑bestand laden** kunt in uw .NET‑applicaties.

## Snelle antwoorden
- **Wat is de primaire manier om een projectbestand te importeren?** Gebruik de `Project` constructor met een `LoadOptions` instantie.  
- **Kan ik wachtwoord‑beveiligde bestanden openen?** Ja—stel de `Password`‑eigenschap in op `LoadOptions`.  
- **Hoe specificeer ik de bestandscodering?** Wijs een `Encoding`‑object toe aan `LoadOptions.Encoding`.  
- **Is foutafhandeling aanpasbaar?** Absoluut—lever een delegate aan `LoadOptions.ErrorHandler`.  
- **Werken deze opties met Primavera‑bestanden?** Ja, via `PrimaveraReadOptions` binnen `LoadOptions`.

## Vereisten

Voordat u begint, zorg ervoor dat u het volgende heeft:

1. **Visual Studio** (of een andere gewenste .NET‑IDE).  
2. **Aspose.Tasks for .NET** – download het van de [website](https://releases.aspose.com/tasks/net/).  
3. Een basisbegrip van **C#**‑syntaxis en projectstructuur.

Nu we klaar zijn, laten we de benodigde namespaces importeren.

## Namespaces importeren

Voeg in uw C#‑project de volgende `using`‑statements toe zodat de API‑klassen beschikbaar zijn:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Hoe een projectbestand te importeren met laadopties

Hieronder staan vier praktische voorbeelden die de meest voorkomende laadscenario's behandelen.

### Stap 1: Een wachtwoord‑beveiligd project laden

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

### Stap 2: Een Primavera‑project laden met aangepaste opties

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

### Stap 3: **Bestandscodering specificeren** bij het importeren van een XER‑bestand

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

### Stap 4: Een Primavera‑project laden met aangepaste foutafhandeling

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

Door deze stappen te volgen kunt u nauwkeurig **projectbestand**‑gegevens importeren, het laadproces afstemmen op uw behoeften, en uw applicatie robuust houden.

## Veelvoorkomende problemen & tips

- **Onjuist wachtwoord** – de `Password`‑eigenschap zal een uitzondering werpen; controleer de inloggegevens vóór het laden.  
- **Niet‑ondersteunde codering** – zorg ervoor dat de opgegeven code‑pagina bestaat op de doelmachine (`Encoding.GetEncoding(1251)` werkt voor Cyrillisch).  
- **Ontbrekende Primavera‑opties** – als u taak‑UID's wilt behouden, stel `PreserveUids = true` in; anders kunnen dubbele ID's verschijnen.  
- **Error handler retourneert null** – het retourneren van `null` geeft de parser aan het problematische element over te slaan; pas aan indien nodig.

## Veelgestelde vragen

**Q: Is Aspose.Tasks for .NET compatibel met alle versies van Microsoft Project?**  
A: Ja, het ondersteunt een breed scala aan Microsoft Project‑versies, zodat u **Microsoft Project‑bestand laden** kunt van oudere MPP‑bestanden tot de nieuwste formaten.

**Q: Kan ik Aspose.Tasks for .NET integreren met andere bibliotheken van derden?**  
A: Absoluut. De bibliotheek werkt naadloos samen met andere .NET‑pakketten, waardoor u het kunt combineren met rapportage‑, UI‑ of data‑toegangs‑frameworks.

**Q: Biedt Aspose.Tasks for .NET documentatie en ondersteuningsbronnen?**  
A: Ja, u kunt de uitgebreide [documentatie](https://reference.aspose.com/tasks/net/) raadplegen en ondersteuning krijgen via het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15).

**Q: Zijn er licentie‑opties beschikbaar voor Aspose.Tasks for .NET?**  
A: Ja, u kunt verschillende licentie‑opties verkennen, inclusief gratis proefversies en tijdelijke licenties, op de [Aspose.Tasks‑website](https://purchase.aspose.com/buy).

**Q: Hoe vaak worden updates en nieuwe functies uitgebracht voor Aspose.Tasks for .NET?**  
A: Aspose.Tasks ontvangt regelmatige updates die functies toevoegen, de prestaties verbeteren en de compatibiliteit met de nieuwste Microsoft Project‑releases behouden.

---

**Laatst bijgewerkt:** 2026-03-08  
**Getest met:** Aspose.Tasks 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}