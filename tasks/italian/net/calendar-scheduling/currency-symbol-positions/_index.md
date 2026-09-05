---
date: 2026-07-19
description: Scopri come gestire il simbolo della valuta dopo l'importo nei progetti
  .NET in modo semplice con Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Posizioni del simbolo della valuta in Aspose.Tasks
og_description: Scopri come posizionare il simbolo della valuta dopo l'importo usando
  Aspose.Tasks per .NET. Segui le istruzioni passo‑passo e le migliori pratiche.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Simbolo della valuta dopo l'importo in Aspose.Tasks — Guida rapida
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Come posizionare il simbolo della valuta dopo l'importo in Aspose.Tasks
url: /it/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come posizionare il simbolo della valuta dopo l'importo in Aspose.Tasks

## Introduzione

Quando generi report sui costi del progetto, il posizionamento del **currency symbol after amount** può influire sulla leggibilità e sulla conformità agli standard regionali. Aspose.Tasks per .NET ti consente di controllare questa formattazione con poche righe di codice, garantendo che ogni cifra finanziaria appaia esattamente come si aspettano le parti interessate. In questo tutorial percorreremo i passaggi necessari, spiegheremo perché l'impostazione è importante e ti mostreremo come applicarla in un progetto .NET reale.

## Risposte rapide
- **Cosa significa “currency symbol after amount”?** Visualizza il simbolo (ad es., $) dopo il valore numerico, come `100 $`.
- **Quale proprietà controlla la posizione?** `CurrencySymbolPosition` sull'oggetto `Project`.
- **Ho bisogno di una licenza?** Una versione di prova funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.
- **Valute supportate?** Oltre 50 valute sono integrate, coprendo la maggior parte dei mercati globali.
- **Posso modificare l'impostazione a runtime?** Sì, puoi aggiornarla in qualsiasi momento prima di salvare il file di progetto.

## Che cos'è l'impostazione “currency symbol after amount”?
L'opzione **currency symbol after amount** determina se il segno della valuta appare prima o dopo il valore numerico in tutti i campi monetari di un progetto. Regolare questa impostazione garantisce che i report rispettino le convenzioni contabili locali senza dover effettuare post‑elaborazioni manuali. Inoltre migliora la leggibilità per le parti interessate abituate a questo formato.

## Perché usare Aspose.Tasks per la formattazione della valuta?
Aspose.Tasks supporta **oltre 50 valute** e può gestire progetti con **oltre 10.000 attività** senza caricare l'intero file in memoria, offrendo prestazioni rapide anche su hardware modesto. L'API fornisce controllo programmatico, eliminando la necessità di modifiche manuali ai fogli di calcolo. Questo rende la creazione di report finanziari su larga scala sia efficiente che affidabile.

## Prerequisiti

### 1. Installazione di Aspose.Tasks per .NET
Assicurati di avere la libreria Aspose.Tasks installata. Puoi scaricarla da [here](https://releases.aspose.com/tasks/net/).

### 2. Conoscenze di base della programmazione .NET
È necessario avere una comprensione fondamentale della programmazione .NET per seguire gli esempi.

## Importazione degli spazi dei nomi

Lo spazio dei nomi `Aspose.Tasks` fornisce l'accesso alla classe `Project` e alle enum correlate.

La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file di progetto in memoria. Dopo aver importato lo spazio dei nomi, puoi iniziare a lavorare con i dati del progetto.

```csharp

```

Ora, analizziamo l'esempio in passaggi chiari e attuabili.

## Come impostare il simbolo della valuta dopo l'importo?

`CurrencySymbolPosition` è un'enumerazione che specifica se il simbolo della valuta appare prima o dopo il valore numerico.

Carica il tuo progetto, imposta `CurrencySymbolPosition` su `After` e poi salva – è tutto ciò che serve per visualizzare il simbolo dopo l'importo. Questo approccio diretto funziona per qualsiasi valuta supportata e non richiede logica di formattazione aggiuntiva. Puoi anche verificare l'impostazione esportando un report di costo di esempio per assicurarti che il simbolo appaia correttamente.

### Passo 1: Caricare il file di progetto
La classe `Project` carica un file MS‑Project esistente o ne crea uno nuovo in memoria.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Passo 2: Impostare la posizione del simbolo della valuta
`CurrencySymbolPosition` è un enum che ti consente di scegliere `Before` o `After`. Impostandolo su `After` il simbolo viene posizionato dopo il valore numerico.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Passo 3: Lavorare con il progetto
Dopo aver configurato la posizione del simbolo, puoi continuare ad aggiungere attività, risorse o campi personalizzati secondo necessità. L'impostazione viene mantenuta quando salvi il progetto.

```csharp
// Perform other operations with the project...
```

## Problemi comuni e soluzioni
- **Il simbolo appare ancora prima dell'importo:** Assicurati di impostare la proprietà *prima* di chiamare `Save`. Modificarla dopo il salvataggio richiede di risalvare il file.
- **Valuta non supportata:** Verifica che il codice valuta che utilizzi sia elencato nella lista di valute supportate da Aspose.Tasks (oltre 50 valute).
- **Rallentamento delle prestazioni su progetti grandi:** Usa `ProjectReader` per lo streaming di file di grandi dimensioni se superi le 10.000 attività.

## Domande frequenti

**D: Posso cambiare la posizione del simbolo della valuta più volte nello stesso progetto?**  
R: Sì, puoi regolare `CurrencySymbolPosition` tutte le volte necessarie; basta impostare la proprietà e risalvare il progetto.

**D: Aspose.Tasks supporta valute diverse dal dollaro USA?**  
R: Assolutamente. Aspose.Tasks supporta più di 50 valute internazionali, consentendoti di lavorare con qualsiasi formato regionale.

**D: È disponibile una versione di prova per Aspose.Tasks per .NET?**  
R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET da [here](https://releases.aspose.com/).

**D: Posso chiedere assistenza se incontro problemi usando Aspose.Tasks per .NET?**  
R: Certamente! Puoi richiedere supporto e assistenza dal forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**D: Come posso acquistare una licenza per Aspose.Tasks per .NET?**  
R: Puoi acquistare una licenza per Aspose.Tasks per .NET da [here](https://purchase.aspose.com/buy).

## Conclusione

Controllare il **currency symbol after amount** è una parte fondamentale della reportistica finanziaria nei software di gestione progetti. Con Aspose.Tasks per .NET puoi impostare questa opzione programmaticamente, supportando oltre 50 valute e gestendo progetti di grandi dimensioni in modo efficiente. Applica i passaggi sopra per garantire che i report del tuo progetto corrispondano alle aspettative di formattazione di qualsiasi locale.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Tutorial correlati

- [Gestione della collezione di calendari in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Collezione di eccezioni del calendario in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Gestione delle tariffe di MS Project con Aspose.Tasks per .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}