---
date: 2026-03-24
description: Scopri come impostare il calcolo in Aspose.Tasks per .NET, con esempi
  per calcolare i valori di riepilogo, definire la formula di calcolo e configurare
  il riepilogo aggregato.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come impostare il tipo di calcolo in Aspose.Tasks
url: /it/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il tipo di calcolo in Aspose.Tasks

## Introduzione

Se hai bisogno di **come impostare il calcolo** per le regole delle attività e delle righe di riepilogo in un file Microsoft Project, questo tutorial ti mostra esattamente come farlo usando Aspose.Tasks per .NET. Passeremo in rassegna un **esempio di tipo di calcolo**, dimostreremo come **calcolare i valori di riepilogo** e spiegheremo come **definire la formula di calcolo** e **configurare il riepilogo rollup** per gli attributi estesi. Alla fine, sarai in grado di aggiungere un'attività a un progetto, impostare una logica di calcolo personalizzata e controllare il comportamento di roll‑up con sicurezza.

## Risposte rapide
- **Qual è lo scopo principale?** Per controllare come i valori delle attività e dei riepiloghi vengono calcolati in un file Project.  
- **Quale classe API è usata?** `ExtendedAttributeDefinition` insieme a `CalculationType` e `SummaryRowsCalculationType`.  
- **Posso usare una formula?** Sì – imposta `CalculationType = CalculationType.Formula` e fornisci una stringa di formula.  
- **Come faccio a aggregare i valori di riepilogo?** Usa `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` e specifica un `RollupType` come `Average`.  
- **Ho bisogno di una licenza?** È necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.

## Cos'è il tipo di calcolo e come impostare il calcolo?

`CalculationType` indica ad Aspose.Tasks come calcolare il valore di un attributo esteso. Puoi scegliere un valore statico, una formula o lasciare che la libreria aggregi i valori dalle attività figlio. Impostare correttamente il calcolo è essenziale quando vuoi che il progetto rifletta regole di business personalizzate senza aggiornamenti manuali.

## Perché usare il tipo di calcolo per calcolare i valori di riepilogo?

Quando un progetto contiene attività di riepilogo, spesso è necessario che le righe di riepilogo mostrino dati aggregati (ad esempio, costo totale, durata media). Configurando **calcolare i valori di riepilogo** tramite `SummaryRowsCalculationType` e `RollupType`, Aspose.Tasks può mantenere automaticamente quegli aggregati sincronizzati mentre modifichi le singole attività.

## Prerequisiti

1. Conoscenza di base di C# e del framework .NET.  
2. Visual Studio (qualsiasi versione recente) installato sulla tua macchina.  
3. Libreria Aspose.Tasks per .NET installata – puoi scaricarla da [qui](https://releases.aspose.com/tasks/net/).  
4. Accesso alla documentazione ufficiale di Aspose.Tasks per .NET per riferimento, disponibile [qui](https://reference.aspose.com/tasks/net/).

## Importare gli spazi dei nomi

Prima di immergerti nell'esempio, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;
```

## Passo 1: Creare un nuovo Project

Per prima cosa, creiamo un oggetto `Project` vuoto che conterrà le nostre attività e gli attributi personalizzati.

```csharp
var project = new Project();
```

## Passo 2: Aggiungere un'attività al progetto

Ora **aggiungiamo dati al progetto** creando un'attività semplice, impostando la sua data di inizio e assegnandole una durata di un giorno.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Passo 3: Definire il tipo di calcolo per un attributo esteso (Esempio di formula)

Qui creiamo una definizione di attributo esteso il cui valore è calcolato da una formula. Questo dimostra un **esempio di tipo di calcolo** e mostra come **definire la formula di calcolo**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Passo 4: Definire il tipo di calcolo per le righe di riepilogo (Configurare il riepilogo rollup)

Successivamente, creiamo un'altra definizione di attributo esteso che indica ad Aspose.Tasks di **configurare il riepilogo rollup** usando il tipo di roll‑up *Average*. Questo è il modo tipico per **calcolare i valori di riepilogo** per costo, lavoro o campi personalizzati.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Problemi comuni e risoluzione

| Sintomo | Causa probabile | Soluzione |
|---------|-----------------|-----------|
| La formula restituisce `null` | Riferimento al campo errato nella formula | Verifica il nome del campo tra parentesi quadre (ad esempio, `[Start]` non `[stARt]`). |
| Le righe di riepilogo mostrano 0 | `SummaryRowsCalculationType` non impostato o `RollupType` errato | Assicurati che `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` e scegli un `RollupType` appropriato. |
| Il progetto non si carica dopo aver aggiunto gli attributi | Incongruenza tra la definizione dell'attributo e l'uso dell'attività | Aggiungi la definizione dell'attributo **prima** di assegnarla a qualsiasi attività. |

## Conclusione

In questo tutorial, abbiamo coperto **come impostare il calcolo** le regole in Aspose.Tasks per .NET, dalla creazione di un'attività semplice alla definizione di tipi di calcolo basati su formula e su roll‑up. Padroneggiando queste impostazioni ottieni un controllo fine sui **calcolare i valori di riepilogo**, consentendo analisi di progetto più ricche senza lavoro manuale su fogli di calcolo.

## FAQ

### Q1: Cos'è il tipo di calcolo in Aspose.Tasks?

Il tipo di calcolo in Aspose.Tasks determina come i valori vengono calcolati per le attività e le attività di riepilogo all'interno di un progetto, offrendo opzioni come Formula e Rollup.

### Q2: Come impostare il tipo di calcolo per un attributo esteso?

Puoi impostare il tipo di calcolo per un attributo esteso definendo la sua proprietà CalculationType di conseguenza.

### Q3: Posso personalizzare il tipo di calcolo per le righe di riepilogo in un progetto?

Sì, Aspose.Tasks consente di specificare il tipo di calcolo per le righe di riepilogo, permettendoti di personalizzare i calcoli dei valori in base alle tue esigenze.

### Q4: Esistono diversi tipi di Rollup disponibili per i calcoli delle attività di riepilogo?

Sì, Aspose.Tasks fornisce vari tipi di Rollup come Average, Sum e Count per calcolare i valori delle attività di riepilogo.

### Q5: Dove posso trovare più risorse su Aspose.Tasks per .NET?

Puoi esplorare la documentazione e i forum di supporto della community disponibili su [Aspose.Tasks per .NET](https://reference.aspose.com/tasks/net/) per una guida completa e assistenza.

---

**Ultimo aggiornamento:** 2026-03-24  
**Testato con:** Aspose.Tasks per .NET (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}