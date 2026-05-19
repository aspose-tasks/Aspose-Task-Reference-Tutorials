---
date: 2026-01-15
description: Scopri come gestire il lavoro a costo preventivato pianificato nei file
  Microsoft Project utilizzando Aspose.Tasks per Java. Segui la nostra guida passo
  passo.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lavoro a costo preventivato programmato con Aspose.Tasks per Java
url: /it/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# budgeted cost work scheduled con Aspose.Tasks per Java

## Introduzione

Gestire **budgeted cost work scheduled** (BCWS) è fondamentale per mantenere un progetto in linea e garantire che le previsioni finanziarie siano coerenti con il lavoro pianificato. In Microsoft Project, BCWS rappresenta l'importo di denaro che avrebbe dovuto essere speso per il lavoro programmato fino a una data specifica. Aspose.Tasks per Java ti offre il pieno controllo programmatico su questi valori, consentendoti di leggere, modificare e generare report sui costi delle risorse senza aprire manualmente il file .mpp. In questo tutorial vedremo un esempio completo che mostra come caricare un progetto, iterare le sue risorse e visualizzare il budgeted cost work scheduled insieme ad altre metriche di costo chiave.

## Risposte rapide
- **Cosa significa BCWS?** Budgeted Cost Work Scheduled – il costo pianificato per il lavoro programmato fino alla data corrente.  
- **Quale proprietà API restituisce BCWS?** `Rsc.BCWS` su un oggetto `Resource`.  
- **È necessaria una licenza per eseguire il campione?** Una licenza di valutazione gratuita è sufficiente per i test; è richiesta una licenza completa per la produzione.  
- **Posso modificare i valori BCWS?** Sì, puoi impostare `Rsc.BCWS` come qualsiasi altro campo numerico.  
- **Versioni di Project supportate?** Tutte le versioni di Microsoft Project dal 2000 al più recente formato .mpp.

## Che cos'è il budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** è una misura di performance che riflette il costo che sarebbe dovuto essere sostenuto per il lavoro pianificato fino a un determinato momento. È un pilastro della Earned Value Management (EVM) e aiuta i project manager a confrontare la spesa pianificata con quella reale.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

1. Una solida conoscenza dei fondamenti di Java.  
2. Aspose.Tasks per Java aggiunto al tuo progetto (Maven/Gradle o JAR).  
3. Un file Microsoft Project (`.mpp`) che contenga risorse con dati di costo (ad es., *ResourceCosts.mpp*).

## Importare i pacchetti

Per prima cosa, importa le classi Aspose.Tasks necessarie per gestire progetti e risorse:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Passo 1: Definire la directory dei dati

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso assoluto o relativo dove risiede *ResourceCosts.mpp*.

## Passo 2: Caricare il file MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Il costruttore `Project` legge il file .mpp e crea una rappresentazione in memoria su cui è possibile eseguire query.

## Passo 3: Iterare le risorse

```java
for (Resource res : prj.getResources()) {
```

Questo ciclo attraversa ogni risorsa definita nel progetto, fornendoti l'accesso ai suoi campi di costo.

## Passo 4: Verificare nome della risorsa e costi

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

All'interno del blocco `if` noi:

* Stampiamo il **costo totale** (`Rsc.COST`).  
* Stampiamo il **costo effettivo del lavoro eseguito** (`Rsc.ACWP`).  
* Stampiamo il **budgeted cost work scheduled** (`Rsc.BCWS`) – la metrica principale su cui ci concentriamo.  
* Stampiamo il **budgeted cost work performed** (`Rsc.BCWP`).

Questi quattro valori forniscono una rapida panoramica della situazione finanziaria del progetto.

## Perché è importante monitorare il budgeted cost work scheduled

* **Allarme precoce:** Se BCWS è significativamente più alto del costo reale, potresti stare sovrallocando le risorse.  
* **Analisi Earned Value:** BCWS è un input chiave per calcolare Cost Variance (CV) e Schedule Variance (SV).  
* **Previsione:** Dati BCWS accurati aiutano a prevedere le esigenze di flusso di cassa future e a informare i report per gli stakeholder.

## Problemi comuni e risoluzione

| Sintomo | Probabile causa | Soluzione |
|---------|-----------------|-----------|
| `null` stampato per BCWS | La risorsa non ha una tabella dei tassi di costo definita | Definisci una tabella dei tassi di costo per la risorsa in Microsoft Project o impostala programmaticamente tramite `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` durante l'iterazione delle risorse | File di progetto corrotto o contiene voci di risorsa vuote | Convalida il file .mpp in Microsoft Project e rimuovi le risorse vuote |
| Valori inattesi (es. BCWS negativo) | Campi personalizzati che sovrascrivono i campi di costo standard | Assicurati di accedere al campo standard `Rsc.BCWS` e non a un campo personalizzato con lo stesso nome |

## Domande frequenti

**D: Posso aggiornare il valore BCWS programmaticamente?**  
R: Sì. Usa `res.set(Rsc.BCWS, newValue)` e poi salva il progetto con `prj.save("Updated.mpp")`.

**D: Aspose.Tasks supporta progetti multivaluta?**  
R: Assolutamente. I campi di costo rispettano le impostazioni di valuta definite nel file di progetto.

**D: È possibile esportare queste metriche di costo in CSV?**  
R: Puoi iterare le risorse e scrivere i valori in un `StringBuilder` oppure utilizzare una libreria CSV per generare il file.

**D: In che modo BCWS differisce da BCWP?**  
R: BCWS è il costo pianificato per il lavoro programmato, mentre BCWP (Budgeted Cost Work Performed) riflette il costo pianificato per il lavoro effettivamente completato.

**D: È necessaria una licenza speciale per leggere i dati di costo?**  
R: La licenza di valutazione fornisce pieno accesso in lettura/scrittura; una licenza commerciale è richiesta per le distribuzioni in produzione.

## Conclusione

Sfruttando Aspose.Tasks per Java, ottieni un accesso preciso e programmatico al **budgeted cost work scheduled** e ad altre metriche di costo vitali. Questo ti consente di creare dashboard personalizzate, automatizzare i report di Earned Value e mantenere i tuoi progetti finanziariamente sotto controllo, il tutto senza interagire manualmente con Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione)  
**Autore:** Aspose