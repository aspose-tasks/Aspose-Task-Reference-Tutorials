---
date: 2025-12-28
description: Scopri come leggere i file XML di Primavera in MS Project usando Aspose.Tasks
  per Java, consentendo uno scambio di dati fluido e una gestione dei progetti migliorata.
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come leggere il file XML di Primavera in MS Project con Aspose.Tasks per Java
url: /it/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggere MS Project da Primavera con Aspose.Tasks per Java

## Introduzione
Nella gestione moderna dei progetti, spostare i dati tra gli strumenti senza perdita di dettagli è essenziale. Questo tutorial mostra **come leggere i file primavera xml** e importarli in Microsoft Project usando Aspose.Tasks per Java. Alla fine, sarai in grado di estrarre le proprietà specifiche di Primavera, rendendo l'analisi cross‑platform semplice ed efficiente.

## Risposte rapide
- **Cosa fa Aspose.Tasks per Java?** Legge e scrive molti formati di file di progetto, inclusi Primavera XML e Microsoft Project (MPP).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è richiesta una licenza per l'uso in produzione.  
- **Quale versione di Java è supportata?** È necessario Java 8 o superiore.  
- **Posso leggere altri formati oltre a Primavera XML?** Sì, Aspose.Tasks supporta MPP, XML e molti altri.  
- **Questo approccio è adatto a grandi progetti aziendali?** Assolutamente—Aspose.Tasks è progettato per scenari ad alte prestazioni e di livello enterprise.

## Che cosa è read primavera xml?
Leggere Primavera XML significa analizzare l'esportazione XML da Oracle Primavera P6 per recuperare i dati di programmazione del progetto—attività, durate, risorse e attributi specifici di Primavera—così da poterli utilizzare in altri strumenti come Microsoft Project.

## Perché usare Aspose.Tasks per Java per leggere primavera xml?
- **Fedele al 100 %:** Tutte le proprietà specifiche di Primavera vengono preservate.  
- **Nessuna dipendenza esterna:** Libreria Java pura, senza necessità di installazioni di Primavera o MS Project.  
- **Scalabile:** Gestisce progetti di grandi dimensioni con migliaia di attività in modo efficiente.  
- **Cross‑platform:** Funziona su Windows, Linux e macOS.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. **Java Development Kit (JDK)** – Java 8 o successiva installata.  
2. **Aspose.Tasks per Java** – Scaricala da [qui](https://releases.aspose.com/tasks/java/).  
3. Un file Primavera XML (ad es., `PrimaveraProject.xml`) che desideri leggere.

## Come leggere un file di progetto java con Aspose.Tasks?
Di seguito trovi una guida passo‑passo che ti accompagna attraverso l'intero processo.

### Importare i pacchetti
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Passo 1: Configurare la directory dei dati
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con il percorso assoluto in cui risiede il tuo file Primavera XML.

### Passo 2: Leggere il progetto da Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Aggiorna `"PrimaveraProject.xml"` con il nome effettivo del tuo file di esportazione Primavera.

### Passo 3: Iterare tra le attività e recuperare le proprietà specifiche di Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Questo ciclo stampa i dettagli specifici di Primavera per ogni attività, come ID attività, sequenza WBS, tipi di durata, ripartizione dei costi e altro ancora.

## Problemi comuni e soluzioni
- **Errore file non trovato:** Verifica che `dataDir` termini con un separatore di percorso (`/` o `\\`) e che il nome del file XML sia corretto.  
- **Proprietà di Primavera mancanti:** Assicurati che l'XML sia stato esportato con tutti i campi richiesti; versioni più vecchie di Primavera potrebbero omettere alcuni attributi.  
- **Prestazioni su file di grandi dimensioni:** Considera di aumentare la dimensione dell'heap JVM (`-Xmx2g` o superiore) per progetti con decine di migliaia di attività.

## Domande frequenti
### D: Posso modificare le proprietà specifiche di Primavera delle attività usando Aspose.Tasks per Java?
R: Sì, Aspose.Tasks per Java fornisce API per modificare le proprietà specifiche di Primavera delle attività secondo necessità.

### D: Aspose.Tasks per Java supporta la lettura di altri formati di file di progetto?
R: Sì, Aspose.Tasks per Java supporta la lettura di vari formati di file di progetto, inclusi MPP, XML e Primavera XML.

### D: Aspose.Tasks per Java è adatto a applicazioni di gestione progetti a livello enterprise?
R: Assolutamente, Aspose.Tasks per Java offre funzionalità robuste e scalabilità, rendendolo adatto a soluzioni di gestione progetti di livello enterprise.

### D: Posso estrarre informazioni sulle risorse dai progetti Primavera usando Aspose.Tasks per Java?
R: Sì, Aspose.Tasks per Java consente di estrarre le informazioni sulle risorse insieme ai dettagli delle attività dai progetti Primavera.

### D: Dove posso trovare supporto aggiuntivo o documentazione per Aspose.Tasks per Java?
R: Puoi trovare una documentazione completa e accedere ai forum di supporto nella pagina della [documentazione di Aspose.Tasks per Java](https://reference.aspose.com/tasks/java/).

## Conclusione
Ora sai **come leggere i file primavera xml** e recuperare informazioni dettagliate sulle attività in un'applicazione Java usando Aspose.Tasks. Questa capacità colma il divario tra Primavera e Microsoft Project, offrendoti piena visibilità su più piattaforme e migliorando l'efficienza complessiva della gestione dei progetti.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Tasks per Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}