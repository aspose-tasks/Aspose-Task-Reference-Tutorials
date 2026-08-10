---
date: 2026-06-15
description: Scopri come calcolare la percentuale di risorse java con Aspose.Tasks,
  inclusa la modalità per ottenere la percentuale di lavoro completato per le risorse
  di MS Project. Guida passo‑passo con esempi di codice.
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: Esegui calcoli percentuali per le risorse in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: calcolare la percentuale di risorse java con Aspose.Tasks
url: /it/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# calcolare la percentuale delle risorse java con Aspose.Tasks

## Introduzione
Benvenuto! In questo tutorial imparerai **come calcolare la percentuale delle risorse java** utilizzando la libreria Aspose.Tasks per Java. Ti guideremo nell'estrazione del *percent work complete* per ogni risorsa in un file Microsoft Project, spiegheremo perché questa metrica è importante e ti mostreremo il codice esatto di cui hai bisogno. Alla fine, sarai in grado di integrare i calcoli della percentuale delle risorse in qualsiasi soluzione di gestione progetti basata su Java.

## Risposte rapide
- **Cosa significa “resource percentage”?** È la percentuale di lavoro che una risorsa ha completato rispetto al totale del lavoro assegnato.  
- **Quale chiamata API restituisce questo valore?** `Rsc.PERCENT_WORK_COMPLETE` tramite la classe `Resource`.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa di Aspose.Tasks per l'uso in produzione.  
- **Posso usarla con altri framework Java?** Sì – l'API funziona con Spring, Hibernate e progetti Java standard.  
- **Quale versione di Aspose.Tasks è necessaria?** Qualsiasi versione recente che supporti l'enumerazione `Rsc` (ad es., 24.x).

## Che cos'è calcolare la percentuale delle risorse java?
Calcolare la percentuale delle risorse in Java comporta l'apertura di un file Microsoft Project, la lettura del lavoro assegnato a ciascuna risorsa e la determinazione della proporzione di quel lavoro già completata. Questa metrica aiuta i project manager a valutare l'avanzamento, bilanciare i carichi di lavoro e identificare potenziali ritardi senza calcoli manuali.

## Perché ottenere il percent work complete?
Recuperare il percent work complete per ogni risorsa fornisce una visione immediata di quanto sforzo pianificato è stato terminato, consentendo di individuare rapidamente attività in ritardo o risorse sotto‑utilizzate. Questa intuizione supporta decisioni tempestive e una segnalazione di stato più accurata.

## Prerequisiti
### Ambiente di sviluppo Java
Assicurati di avere installato il Java Development Kit (JDK). Puoi scaricare il JDK da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Libreria Aspose.Tasks
Scarica e aggiungi la libreria Aspose.Tasks al tuo progetto da [qui](https://releases.aspose.com/tasks/java/) e segui le istruzioni di installazione fornite nella documentazione [qui](https://reference.aspose.com/tasks/java/).

## Importa pacchetti
La classe `Resource` rappresenta una risorsa di progetto e fornisce l'accesso a campi come il percent work complete.  
Prima di iniziare a scrivere codice, importiamo i pacchetti necessari per questo tutorial:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Come impostare il percorso del file di progetto?
Specifica la posizione del tuo file Microsoft Project fornendo un percorso assoluto o un percorso relativo alla directory di lavoro dell'applicazione. La stringa del percorso deve puntare a un file *.mpp* valido affinché Aspose.Tasks possa individuarlo e aprirlo per ulteriori elaborazioni.
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con la cartella che contiene il tuo file Microsoft Project.

## Come caricare il progetto?
Crea una nuova istanza della classe `Project` utilizzando il percorso file definito in precedenza. La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso a attività, risorse e altri dati del progetto, caricando tutto in memoria per l'analisi.
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Questo carica il file **Software Development.mpp** dalla directory specificata.

## Come iterare attraverso le risorse?
Usa il metodo `project.getResources()` per ottenere una collezione di tutte le risorse definite nel progetto caricato. Itera su questa collezione con un classico ciclo `for` Java o con la costruzione `for‑each` avanzata, permettendoti di esaminare ogni oggetto `Resource` individualmente e recuperare i campi associati.
```java
for (Resource res : prj.getResources()) {
```
Iteriamo attraverso ogni risorsa definita nel progetto.

## Come verificare il nome della risorsa e ottenere il percent work complete?
Prima assicurati che l'oggetto `Resource` abbia un nome non vuoto per evitare di elaborare voci segnaposto. Poi chiama `res.get(Rsc.PERCENT_WORK_COMPLETE)` che restituisce un double rappresentante la percentuale di lavoro completato per quella risorsa, compresa tra 0 e 100. Puoi formattare questo valore per la visualizzazione o usarlo in ulteriori calcoli per valutare la salute complessiva del progetto.
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Il codice prima verifica che la risorsa abbia un nome, quindi stampa il valore **percent work complete** per quella risorsa.

## Problemi comuni e soluzioni
- **NullPointerException** – Assicurati che il percorso del file di progetto sia corretto e che il file venga caricato senza errori.  
- **Percentuali errate** – Verifica che la risorsa abbia effettivamente lavoro assegnato; altrimenti la percentuale sarà `0`.  
- **Errori di licenza** – Usa una licenza valida di Aspose.Tasks o una licenza di valutazione temporanea per evitare restrizioni a runtime.

## Domande frequenti (Originale)

### Posso usare Aspose.Tasks per Java con altri framework Java?
Sì, Aspose.Tasks per Java è compatibile con vari framework Java come Spring, Hibernate e altri.

### Aspose.Tasks supporta tutte le versioni dei file Microsoft Project?
Aspose.Tasks fornisce supporto per tutte le versioni dei file Microsoft Project, inclusi MPP, MPT, XML e altri.

### Posso manipolare i programmi di progetto usando Aspose.Tasks?
Assolutamente, Aspose.Tasks offre funzionalità complete per manipolare i programmi di progetto, comprese attività, risorse, calendari e altro.

### Esiste un forum della community per il supporto di Aspose.Tasks?
Sì, puoi trovare assistenza e interagire con altri utenti sul forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

### Aspose.Tasks offre licenze temporanee per scopi di valutazione?
Sì, puoi ottenere una licenza temporanea per la valutazione da [qui](https://purchase.aspose.com/temporary-license/).

## FAQ aggiuntive

**D:** Come formattare l'output per mostrare le percentuali con il simbolo %?  
**R:** Recupera il valore numerico con `res.get(Rsc.PERCENT_WORK_COMPLETE)` e formattalo usando `String.format("%.2f%%", value)`.

**D:** Posso filtrare le risorse per mostrare solo quelle con meno del 50 % completato?  
**R:** Sì, aggiungi una condizione `if` che verifichi `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` prima di stampare.

**D:** È possibile scrivere le percentuali di nuovo nel file Project?  
**R:** Il campo `Rsc.PERCENT_WORK_COMPLETE` è di sola lettura; dovresti modificare le assegnazioni delle attività invece.

**D:** Questo funziona con i file di Project Online (cloud)?  
**R:** Devi prima scaricare il file .mpp localmente; Aspose.Tasks lavora con il formato del file, non direttamente con il servizio cloud.

## Benefici quantificati dell'utilizzo di Aspose.Tasks
Aspose.Tasks supporta **30+ formati di file** (MPP, MPT, XML, CSV, ecc.) e può elaborare progetti con **fino a 10.000 attività** mantenendo l'uso di memoria sotto i 200 MB grazie allo streaming dei dati. Il campo **read‑only `Rsc.PERCENT_WORK_COMPLETE`** della libreria è calcolato in tempo O(n), garantendo un recupero rapido anche per programmi di grandi dimensioni.

## Conclusione
In questa guida abbiamo dimostrato **come calcolare la percentuale delle risorse java** usando Aspose.Tasks, concentrandoci sul recupero del *percent work complete* per ogni risorsa. Seguendo i passaggi sopra, potrai incorporare analisi precise della percentuale delle risorse nelle tue applicazioni Java, ottenendo una migliore visibilità sulla salute del progetto e sull'utilizzo delle risorse.

---

**Ultimo aggiornamento:** 2026-06-15  
**Testato con:** Aspose.Tasks for Java 24.10  
**Autore:** Aspose

## Tutorial correlati

- [Aggiungi risorsa al progetto con Aspose.Tasks per Java](/tasks/java/resource-management/create-resources/)
- [Gestisci i costi delle risorse di MS Project con Aspose.Tasks per Java](/tasks/java/resource-management/resource-cost/)
- [Calcoli della percentuale di completamento per le attività in Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}