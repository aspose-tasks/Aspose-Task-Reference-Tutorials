---
date: 2026-05-20
description: Scopri come gestire le variazioni di progetto con Aspose.Tasks per Java,
  inclusi i metodi per ottenere variazioni di costo, di lavoro e di data in modo efficiente.
keywords:
- handle project variances
- get cost variance
- Aspose.Tasks Java
linktitle: Gestisci le variazioni in Aspense.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  headline: How to Handle Project Variances with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  name: How to Handle Project Variances with Aspose.Tasks for Java
  steps:
  - name: Iterate through Resource Assignments
    text: 'To deal with variances, we need to iterate through resource assignments
      in the project. This is achieved using a simple loop:'
  - name: Retrieve Work Variance
    text: 'Work variance represents the deviation between planned work and actual
      work performed by a resource. To retrieve work variance for each resource assignment,
      use the following code snippet:'
  - name: Retrieve Start Variance
    text: 'Start variance signifies the variance between planned and actual start
      dates for a task. To fetch start variance, utilize the following code:'
  - name: Retrieve Finish Variance
    text: 'Finish variance denotes the difference between planned and actual finish
      dates for a task. To acquire finish variance, employ the following code:'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with libraries such as Jackson
      for JSON, Apache POI for Excel, and JFreeChart for reporting.
    question: Can I integrate Aspose.Tasks with other Java libraries?
  - answer: Absolutely. It efficiently processes projects containing up to 10,000
      tasks and 5,000 resources without loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Certainly. Use the variance values you retrieve to feed custom PDF, Excel,
      or HTML reports via Aspose.Words, Aspose.Cells, or standard Java templating
      engines.
    question: Can I customize reports based on variance analysis?
  - answer: Yes, users can access technical support through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Is technical support available for Aspose.Tasks users?
  - answer: Yes, you can avail of a free trial of Aspose.Tasks from [here](https://releases.aspose.com/)
      to evaluate its features before making a purchase.
    question: Can I try Aspose.Tasks before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come gestire le variazioni di progetto con Aspose.Tasks per Java
url: /it/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come gestire le variazioni di progetto con Aspose.Tasks per Java

## Introduzione
In questo tutorial, imparerai **come gestire le variazioni di progetto** usando Aspose.Tasks per Java. Le variazioni—differenze tra il lavoro, il costo, le date di inizio o di fine pianificate e quelle effettive—sono segnali essenziali che indicano se un progetto è in linea. Aspose.Tasks ti offre un modo pulito e programmatico per recuperare e analizzare questi numeri, così da poter apportare rapidamente aggiustamenti basati sui dati.

## Risposte rapide
- **Qual è la classe principale per accedere alle variazioni?** `ResourceAssignment` fornisce proprietà come `WorkVariance`, `CostVariance`, `StartVariance` e `FinishVariance`.  
- **Quale metodo restituisce la variazione di costo?** Usa `getCostVariance()` su un'istanza di `ResourceAssignment`.  
- **È necessaria una licenza per questa funzionalità?** Sì, una licenza valida di Aspose.Tasks sblocca tutte le API delle variazioni.  
- **È possibile elaborare progetti di grandi dimensioni?** Aspose.Tasks gestisce progetti con fino a 10.000 attività senza caricare l'intero file in memoria.  
- **Quale versione di Java è richiesta?** È supportata Java 8 o versioni successive.

## Cos'è “gestire le variazioni di progetto”?
Gestire le variazioni di progetto comporta l'estrazione delle differenze tra i valori di baseline (pianificati) e i risultati effettivi per lavoro, costo, date di inizio e di fine. Analizzando queste discrepanze, i project manager possono valutare le prestazioni, identificare ritardi o superamenti di budget e prendere decisioni informate per ripianificare o regolare le risorse, garantendo che il progetto rimanga in linea.

## Perché usare Aspose.Tasks per l'analisi delle variazioni?
Aspose.Tasks supporta **oltre 30 formati di file in ingresso/uscita** e può elaborare programmi di centinaia di pagine in meno di un secondo su hardware server tipico. La sua API restituisce direttamente i valori delle variazioni, eliminando la necessità di calcoli manuali o componenti aggiuntivi di terze parti.

## Prerequisiti
Prima di procedere, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK) installato sul tuo sistema.  
2. Libreria Aspose.Tasks per Java scaricata e aggiunta al tuo progetto. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).  
3. Conoscenza di base del linguaggio di programmazione Java.

## Importare i pacchetti
La classe `ResourceAssignment` si trova nello spazio dei nomi `com.aspose.tasks`. Importa i pacchetti necessari prima di iniziare a scrivere codice:

La classe `ResourceAssignment` rappresenta il collegamento tra una risorsa e un'attività, esponendo le proprietà di variazione che puoi interrogare.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;

```

## Come gestire le variazioni di progetto in Aspose.Tasks?
Carica il tuo progetto con `new Project("yourfile.mpp")`, quindi itera su ogni `ResourceAssignment` per leggere i suoi campi di variazione. Questo unico passaggio ti fornisce le variazioni di lavoro, costo, inizio e fine per ogni assegnazione, consentendo dashboard di prestazioni istantanee.

### Passo 1: Iterare attraverso le assegnazioni delle risorse
Per gestire le variazioni, dobbiamo iterare attraverso le assegnazioni delle risorse nel progetto. Questo si ottiene usando un semplice ciclo:

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

### Passo 2: Recuperare la variazione del lavoro
La variazione del lavoro rappresenta la deviazione tra il lavoro pianificato e quello effettivamente svolto da una risorsa. Per recuperare la variazione del lavoro per ogni assegnazione di risorsa, utilizza il seguente frammento di codice:

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

### Come ottenere la variazione di costo per un'assegnazione di risorsa?
Per ottenere la variazione di costo per una specifica assegnazione, invoca il metodo `getCostVariance()` su un'istanza di `ResourceAssignment`. Questo metodo calcola la differenza monetaria tra il costo di baseline e il costo effettivo sostenuto, restituendo un valore `double` che riflette la variazione nella valuta predefinita del progetto. Puoi quindi utilizzare questo valore per l'analisi del budget.

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

### Passo 4: Recuperare la variazione di inizio
La variazione di inizio indica la differenza tra le date di inizio pianificate e quelle effettive per un'attività. Per recuperare la variazione di inizio, utilizza il seguente codice:

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

### Passo 5: Recuperare la variazione di fine
La variazione di fine indica la differenza tra le date di fine pianificate e quelle effettive per un'attività. Per ottenere la variazione di fine, utilizza il seguente codice:

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## Problemi comuni e soluzioni
- **Valori null:** Se un'attività non ha una baseline, le proprietà di variazione restituiscono `null`. Controlla sempre `null` prima di usare il valore.  
- **Mismatches di fuso orario:** Le date sono memorizzate in UTC; convertile al tuo fuso locale se le mostri agli utenti.  
- **File di grandi dimensioni:** Per progetti con migliaia di assegnazioni, considera di elaborare le assegnazioni in batch per mantenere basso l'uso della memoria.

## Domande frequenti

**Q: Posso integrare Aspose.Tasks con altre librerie Java?**  
A: Sì, Aspose.Tasks si integra perfettamente con librerie come Jackson per JSON, Apache POI per Excel e JFreeChart per la generazione di report.

**Q: Aspose.Tasks è adatto a progetti su larga scala?**  
A: Assolutamente. Elabora efficientemente progetti contenenti fino a 10.000 attività e 5.000 risorse senza caricare l'intero file in memoria.

**Q: Posso personalizzare i report basati sull'analisi delle variazioni?**  
A: Certamente. Usa i valori di variazione che recuperi per alimentare report PDF, Excel o HTML personalizzati tramite Aspose.Words, Aspose.Cells o motori di templating Java standard.

**Q: È disponibile supporto tecnico per gli utenti di Aspose.Tasks?**  
A: Sì, gli utenti possono accedere al supporto tecnico tramite il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Sì, puoi usufruire di una prova gratuita di Aspose.Tasks da [qui](https://releases.aspose.com/) per valutare le sue funzionalità prima di effettuare l'acquisto.

**Ultimo aggiornamento:** 2026-05-20  
**Testato con:** Aspose.Tasks 24.12 per Java  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Monitoraggio dei costi del progetto con Aspose.Tasks - Straordinario e Lavoro](/tasks/java/resource-assignments/overtime-remaining-costs-work/)
- [Gestire i costi delle risorse di MS Project con Aspose.Tasks per Java](/tasks/java/resource-management/resource-cost/)
- [Impostare la data di inizio del progetto in MS Project usando Aspose.Tasks per Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}