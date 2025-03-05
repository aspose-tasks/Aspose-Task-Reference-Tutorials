---
title: Personalizza le impostazioni di visualizzazione della pagina di MS Project in Aspose.Tasks
linktitle: Configurazione delle impostazioni di visualizzazione della pagina in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come configurare le impostazioni di visualizzazione della pagina in Aspose.Tasks per .NET per personalizzare il formato di stampa dei tuoi documenti Microsoft Project.
type: docs
weight: 21
url: /it/net/outline-code-page-settings/page-view-settings/
---
## introduzione
Microsoft Project è un potente strumento per la gestione dei progetti, ma a volte è necessario personalizzare il modo in cui il progetto viene visualizzato e stampato. Con Aspose.Tasks per .NET, puoi configurare facilmente le impostazioni di visualizzazione della pagina per soddisfare i tuoi requisiti specifici. In questo tutorial ti guideremo attraverso il processo passo dopo passo.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Aspose.Tasks per .NET: assicurati di aver scaricato e installato la libreria Aspose.Tasks per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: tieni pronto un file Microsoft Project per il quale desideri configurare le impostazioni di visualizzazione della pagina.

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari per lavorare con Aspose.Tasks nel tuo progetto .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Passaggio 1: caricare il file di progetto
 Inizia caricando il file Microsoft Project in un'istanza di`Project` classe.
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Passaggio 2: imposta il conteggio delle prime colonne
Specificare il numero delle prime colonne da stampare su tutte le pagine.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Passaggio 3: stampare le note
Scegli se stampare le note insieme al progetto.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Passaggio 4: adatta la scala cronologica alla fine della pagina
Decidere se adattare la scala temporale alla fine di una pagina durante la stampa.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Passaggio 5: stampa tutte le colonne del foglio
Specificare se stampare tutte le colonne del foglio di una vista.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Passaggio 6: stampare pagine vuote
Scegli se stampare le pagine vuote di una vista.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Passaggio 7: stampa le prime colonne su tutte le pagine
Imposta se stampare un numero specificato di prime colonne su tutte le pagine.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Passaggio 8: salva il progetto con le impostazioni configurate
Infine, salva il progetto con le impostazioni di visualizzazione della pagina configurate, specificando il formato di output, come PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Conclusione
La configurazione delle impostazioni di visualizzazione della pagina di Microsoft Project in Aspose.Tasks per .NET è semplice e consente di personalizzare il formato di stampa in base alle proprie esigenze. Seguendo i passaggi delineati in questo tutorial, puoi assicurarti che i documenti del tuo progetto siano presentati esattamente come richiesto.
## Domande frequenti
### D: Posso configurare le impostazioni di visualizzazione della pagina per altri formati di file oltre al PDF?
R: Sì, Aspose.Tasks supporta vari formati di file per il salvataggio di progetti, inclusi XLSX, MPP e HTML.
### D: Esistono limitazioni al numero di colonne che posso stampare?
R: Aspose.Tasks ti consente di personalizzare il numero di colonne da stampare in base alle tue esigenze.
### D: Posso applicare impostazioni di visualizzazione della pagina diverse per progetti diversi?
R: Sì, puoi regolare le impostazioni di visualizzazione della pagina in modo indipendente per ciascun file di progetto con cui lavori.
### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?
R: Aspose.Tasks offre compatibilità con Microsoft Project 2003 e versioni successive.
### D: Dove posso trovare ulteriore assistenza o supporto per Aspose.Tasks?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi richiesta o problema riscontrato durante l'utilizzo.