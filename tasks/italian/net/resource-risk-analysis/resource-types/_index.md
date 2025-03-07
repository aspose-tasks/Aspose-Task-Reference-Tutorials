---
title: Tipi di risorse in Aspose.Tasks
linktitle: Tipi di risorse in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come lavorare con diversi tipi di risorse in Aspose.Tasks per .NET, incluse risorse di lavoro, materiali e costi, attraverso un tutorial passo passo.
weight: 14
url: /it/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tipi di risorse in Aspose.Tasks

## introduzione
Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice. Che tu stia gestendo attività, risorse o pianificazioni, Aspose.Tasks semplifica il processo fornendo un set completo di API. In questo tutorial, approfondiremo i diversi tipi di risorse che puoi utilizzare nei tuoi progetti utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Visual Studio: installa Visual Studio, un potente ambiente di sviluppo integrato (IDE) per lo sviluppo .NET.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarizza con C#, il linguaggio di programmazione utilizzato per lo sviluppo .NET.

## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari per accedere alle funzionalità di Aspose.Tasks per .NET:
```csharp
    
```

## Passaggio 1: crea una nuova istanza del progetto
```csharp
var project = new Project();
```
Questa riga inizializza un nuovo oggetto Progetto, che funge da contenitore per tutti i dati e le operazioni relative al progetto.
## Passaggio 2: aggiungi una risorsa lavoro
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Qui creiamo una nuova risorsa di lavoro denominata "Risorsa di lavoro" e ne specifichiamo il tipo come ResourceType.Work.
## Passaggio 3: aggiungere una risorsa materiale
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Questo passaggio aggiunge una risorsa materiale denominata "Risorsa materiale" con il tipo impostato su ResourceType.Material. Inoltre, specifichiamo l'etichetta del materiale come "kg" per indicare l'unità di misura.
## Passaggio 4: aggiungere una risorsa costo
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Infine, aggiungiamo una risorsa costo denominata "Risorsa costo" e ne impostiamo il tipo come ResourceType.Cost. Inoltre, impostiamo il valore del costo su 59,99, che rappresenta il valore monetario associato a questa risorsa.

## Conclusione
In questo tutorial, abbiamo esplorato come lavorare con diversi tipi di risorse in Aspose.Tasks per .NET, incluse risorse di lavoro, materiali e costi. Seguendo la guida passo passo, puoi gestire in modo efficace le risorse all'interno dei tuoi progetti in modo programmatico.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con altri formati di software di gestione dei progetti?
R: Sì, Aspose.Tasks supporta vari formati, tra cui Microsoft Project (MPP), Primavera P6 e altri.
### D: È disponibile una prova gratuita per Aspose.Tasks per .NET?
 R: Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto tecnico per Aspose.Tasks per .NET?
 R: È possibile visitare il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15) per assistenza tecnica.
### D: Posso acquistare una licenza temporanea per Aspose.Tasks per .NET?
 R: Sì, puoi acquistare una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### D: Aspose.Tasks per .NET fornisce documentazione di riferimento?
 R: Sì, puoi trovare la documentazione[Qui](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
