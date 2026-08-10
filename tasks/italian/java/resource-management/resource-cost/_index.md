---
date: 2026-06-15
description: Scopri come gestire i costi nei file di MS Project utilizzando Aspose.Tasks
  per Java, incluso come caricare un file MPP e leggere il lavoro a costo reale e
  il programma di costo preventivato.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Gestisci il costo delle risorse in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come gestire i costi in MS Project con Aspose.Tasks per Java
url: /it/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come gestire i costi in MS Project con Aspose.Tasks per Java

## Introduzione

Gestire i budget di progetto è una responsabilità fondamentale per qualsiasi project manager, e **come gestire i costi** in modo efficace può fare la differenza tra il successo e il fallimento di un progetto. Aspose.Tasks per Java ti offre un controllo programmatico sui file Microsoft Project, consentendoti di leggere e aggiornare i dati dei costi delle risorse senza mai aprire manualmente il file .mpp. In questo tutorial vedrai passo‑passo come caricare un file MPP, ispezionare il lavoro di costo reale e estrarre il programma di costo preventivato per ogni risorsa.

## Risposte rapide
- **Che cosa fa Aspose.Tasks per Java?** Legge e scrive file Microsoft Project (.mpp) senza richiedere l'installazione di Microsoft Project.  
- **Come posso caricare un file MPP?** Usa `new Project("path/to/file.mpp")` – l'API analizza il file in memoria.  
- **Quali campi di costo sono disponibili?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) e Budgeted Cost of Work Performed (BCWP).  
- **Ho bisogno di una licenza per lo sviluppo?** Una licenza temporanea gratuita funziona per i test; è necessaria una licenza completa per la produzione.  
- **Quali versioni di Java sono supportate?** Java 8 e successive, inclusa Java 17 LTS.

## Come gestire i costi in MS Project?

Carica il tuo progetto con `new Project("yourFile.mpp")`, quindi itera su ogni oggetto `Resource` per leggere le proprietà relative ai costi come ACWP, BCWS e BCWP. Aspose.Tasks converte automaticamente i valori di costo interni nella valuta del progetto, così puoi visualizzarli o memorizzarli direttamente. Questo approccio elimina i calcoli manuali su fogli di calcolo e garantisce la coerenza dei dati in tutti i report di progetto.

## Prerequisiti

1. Conoscenza di base della programmazione Java.  
2. Libreria Aspose.Tasks per Java aggiunta al tuo progetto (Maven/Gradle o JAR manuale).  
3. Accesso a un file Microsoft Project (`.mpp`) che desideri analizzare.  

## Importare i pacchetti

Le classi `Project` e `Resource` sono i punti di ingresso per lavorare con i dati del progetto.

La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file Microsoft Project in memoria.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Passo 1: Definire la directory dei dati

Innanzitutto, specifica la cartella che contiene il tuo file `.mpp`. Questo percorso può essere assoluto o relativo alla directory di lavoro della tua applicazione.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Passo 2: Caricare il file MS Project

`Project` carica il file e costruisce un modello di oggetti che puoi interrogare. L'API analizza il file senza necessità di Microsoft Project installato, supportando oltre 30 formati di input.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Passo 3: Iterare attraverso le risorse

Gli oggetti `Resource` rappresentano persone, attrezzature o materiali che consumano il budget. Puoi scorrere la collezione `project.getResources()` per accedere a ciascuno.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Passo 4: Verificare il nome della risorsa e i costi

Per ogni risorsa, verifica che il nome sia definito, quindi leggi i campi di costo. Il metodo `getActualCost()` restituisce il **lavoro di costo reale** (ACWP), mentre `getBudgetedCost()` fornisce il **programma di costo preventivato** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Perché usare Aspose.Tasks per Java per caricare un file MPP?

Aspose.Tasks supporta **oltre 30 formati di file** (inclusi `.mpp`, `.xml` e `.xlsx`) e può elaborare progetti con **fino a 10.000 attività** utilizzando meno di 200 MB di RAM. La libreria esegue tutti i calcoli sul lato server, eliminando la necessità di una copia con licenza di Microsoft Project.

## Problemi comuni e soluzioni

- **Nomi risorsa null:** Alcuni file legacy contengono risorse segnaposto. Controlla sempre `resource.getName() != null` prima di accedere alle proprietà di costo.  
- **File di grandi dimensioni che causano pressione sulla memoria:** LoadOptions è una classe di configurazione che ti permette di specificare quali dati del progetto caricare. Usa `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` per caricare solo i dati necessari, poi abilitalo più tardi se richiesto.  
- **Incongruenze di valuta:** L'API rispetta le impostazioni di valuta del progetto; puoi sovrascriverle con `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` se necessario. CostRateTableType enumera le diverse tabelle di tassi di costo che possono essere applicate a un'attività.

## Domande frequenti

**D: Aspose.Tasks per Java può gestire strutture di progetto complesse?**  
R: Sì, supporta pienamente attività di riepilogo nidificate, più calendari di risorsa e campi personalizzati in tutte le versioni di Project supportate.

**D: La libreria è compatibile con diverse versioni dei file Microsoft Project?**  
R: Assolutamente. Aspose.Tasks legge e scrive file da Microsoft Project 2000 fino all'ultimo formato 2023.

**D: Posso integrare Aspose.Tasks per Java con altre librerie Java?**  
R: Sì, l'API restituisce oggetti Java standard, consentendo un'integrazione fluida con framework di logging, strumenti ORM o librerie di reporting.

**D: Aspose.Tasks per Java offre supporto clienti?**  
R: Aspose fornisce supporto dedicato tramite forum, documentazione dettagliata e assistenza via email reattiva per gli utenti con licenza.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?**  
R: Puoi scaricare una licenza di valutazione di 30 giorni dal sito Aspose per esplorare tutte le funzionalità senza costi.

---

**Ultimo aggiornamento:** 2026-06-15  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Come calcolare la varianza dei costi e gestire i costi delle assegnazioni con Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Gestione di budget, lavoro e costi per le attività in Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Aggiungere risorse al progetto con Aspose.Tasks per Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}