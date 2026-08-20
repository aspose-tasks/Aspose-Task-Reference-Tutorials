---
date: 2026-03-08
description: Scopri come importare un file di progetto usando Aspose.Tasks per .NET,
  incluso come specificare la codifica del file e caricare il file Microsoft Project
  in modo efficiente.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Importa file di progetto – Opzioni di caricamento in Aspose.Tasks
url: /it/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Importazione di file di progetto – Opzioni di caricamento in Aspose.Tasks

## Introduzione

Aspose.Tasks for .NET semplifica l'**importazione di file di progetto** da Microsoft Project, Primavera e altri formati. Che tu debba leggere un file protetto da password, impostare una codifica personalizzata o gestire errori di parsing, la libreria ti offre un controllo dettagliato tramite le opzioni di caricamento. In questo tutorial esamineremo gli scenari più comuni così potrai **caricare file Microsoft Project** nelle tue applicazioni .NET.

## Risposte rapide
- **Qual è il modo principale per importare un file di progetto?** Usa il costruttore `Project` con un'istanza di `LoadOptions`.  
- **Posso aprire file protetti da password?** Sì—imposta la proprietà `Password` su `LoadOptions`.  
- **Come specifico la codifica del file?** Assegna un oggetto `Encoding` a `LoadOptions.Encoding`.  
- **La gestione degli errori è personalizzabile?** Assolutamente—fornisci un delegato a `LoadOptions.ErrorHandler`.  
- **Queste opzioni funzionano con i file Primavera?** Sì, tramite `PrimaveraReadOptions` all'interno di `LoadOptions`.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Visual Studio** (o qualsiasi IDE .NET preferito).  
2. **Aspose.Tasks for .NET** – scaricalo dal [sito web](https://releases.aspose.com/tasks/net/).  
3. Una conoscenza di base della sintassi **C#** e della struttura del progetto.

Ora che siamo pronti, importiamo gli spazi dei nomi necessari.

## Importazione degli spazi dei nomi

Nel tuo progetto C#, aggiungi le seguenti istruzioni `using` in modo che le classi API siano disponibili:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Come importare un file di progetto con le opzioni di caricamento

Di seguito sono riportati quattro esempi pratici che coprono gli scenari di caricamento più frequenti.

### Step 1: Carica un progetto protetto da password

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

### Step 2: Carica un progetto Primavera con opzioni personalizzate

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

### Step 3: **Specificare la codifica del file** durante l'importazione di un file XER

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

### Step 4: Carica un progetto Primavera con gestione degli errori personalizzata

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

Seguendo questi passaggi potrai importare con precisione i dati **project file**, personalizzare il processo di caricamento secondo le tue esigenze e mantenere la tua applicazione robusta.

## Problemi comuni e suggerimenti

- **Password errata** – la proprietà `Password` genererà un'eccezione; verifica le credenziali prima del caricamento.  
- **Codifica non supportata** – assicurati che la pagina di codice specificata esista sulla macchina di destinazione (`Encoding.GetEncoding(1251)` funziona per il cirillico).  
- **Opzioni Primavera mancanti** – se è necessario preservare gli UID dei task, imposta `PreserveUids = true`; altrimenti potrebbero comparire ID duplicati.  
- **Il gestore degli errori restituisce null** – restituire `null` segnala al parser di saltare l'elemento problematico; personalizza secondo necessità.

## Domande frequenti

**D: Aspose.Tasks for .NET è compatibile con tutte le versioni di Microsoft Project?**  
R: Sì, supporta un'ampia gamma di versioni di Microsoft Project, quindi puoi **caricare file Microsoft Project** da vecchi file MPP fino ai formati più recenti.

**D: Posso integrare Aspose.Tasks for .NET con altre librerie di terze parti?**  
R: Assolutamente. La libreria funziona senza problemi con altri pacchetti .NET, consentendoti di combinarla con framework di reporting, UI o di accesso ai dati.

**D: Aspose.Tasks for .NET fornisce documentazione e risorse di supporto?**  
R: Sì, puoi fare riferimento alla completa [documentazione](https://reference.aspose.com/tasks/net/) e accedere al supporto tramite il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**D: Sono disponibili opzioni di licenza per Aspose.Tasks for .NET?**  
R: Sì, puoi esplorare diverse opzioni di licenza, incluse prove gratuite e licenze temporanee, sul [sito web Aspose.Tasks](https://purchase.aspose.com/buy).

**D: Con quale frequenza vengono rilasciati aggiornamenti e nuove funzionalità per Aspose.Tasks for .NET?**  
R: Aspose.Tasks riceve aggiornamenti regolari che aggiungono funzionalità, migliorano le prestazioni e mantengono la compatibilità con le ultime versioni di Microsoft Project.

---

**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** Aspose.Tasks 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}