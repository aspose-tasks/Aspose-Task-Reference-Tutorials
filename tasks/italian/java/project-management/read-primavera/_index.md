---
date: 2026-04-24
description: Scopri come utilizzare Aspose.Tasks per Java per importare file XML di
  Primavera in MS Project, consentendo uno scambio di dati fluido e un miglioramento
  della gestione del progetto.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Leggi il progetto da Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Leggi XML Primavera in MS Project
url: /it/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi MS Project da Primavera con Aspose.Tasks per Java

## Introduzione
Nel frenetico mondo della gestione dei progetti, spesso è necessario spostare i piani tra Primavera P6 e Microsoft Project senza perdere alcun dettaglio. Questo tutorial mostra **come leggere i file Primavera XML** e importarli in MS Project usando **aspose tasks java**. Alla fine della guida sarai in grado di estrarre le proprietà specifiche di Primavera delle attività in un'applicazione Java, fornendo una fonte unica di verità per analisi, reportistica o ulteriori automazioni.

## Risposte rapide
- **Che cosa fa Aspose.Tasks per Java?** Legge e scrive molti formati di file di progetto, inclusi Primavera XML e Microsoft Project (MPP).  
- **Ho bisogno di una licenza?** Una prova gratuita è sufficiente per la valutazione; è necessaria una licenza per l'uso in produzione.  
- **Quale versione di Java è supportata?** È richiesto Java 8 o superiore.  
- **Posso importare altri formati oltre a Primavera XML?** Sì, aspose tasks java supporta anche MPP, XML e molti altri.  
- **Questo approccio è adatto a grandi progetti aziendali?** Assolutamente—Aspose.Tasks è progettato per scenari ad alte prestazioni e di livello enterprise.

## aspose tasks java – Lettura di Primavera XML
Leggere Primavera XML significa analizzare l'esportazione XML da Oracle Primavera P6 per recuperare i dati del programma di progetto—attività, durate, risorse e attributi specifici di Primavera—così da poterli utilizzare in altri strumenti come Microsoft Project.

## Perché usare Aspose.Tasks per Java per leggere Primavera XML?
- **Fedele al 100%:** Tutte le proprietà specifiche di Primavera sono preservate.  
- **Nessuna dipendenza esterna:** Libreria Java pura, non è necessario installare Primavera o MS Project.  
- **Scalabile:** Gestisce progetti di grandi dimensioni con migliaia di attività in modo efficiente.  
- **Cross‑platform:** Funziona su Windows, Linux e macOS.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. **Java Development Kit (JDK)** – Java 8 o più recente installato.  
2. **Aspose.Tasks for Java** – Scaricalo da [qui](https://releases.aspose.com/tasks/java/).  
3. Un file Primavera XML (ad es., `PrimaveraProject.xml`) che desideri leggere.

## Come leggere un file di progetto java con Aspose.Tasks?
Di seguito trovi una guida passo‑a‑passo che ti accompagna attraverso l’intero processo.

### Importazione dei pacchetti
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
Aggiorna `"PrimaveraProject.xml"` con il nome effettivo del file di esportazione Primavera.

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
Questo ciclo stampa i dettagli specifici di Primavera di ciascuna attività, come ID attività, sequenza WBS, tipi di durata, ripartizione dei costi e altro ancora.

## Problemi comuni e soluzioni
- **Errore file non trovato:** Verifica che `dataDir` termini con un separatore di percorso (`/` o `\\`) e che il nome del file XML sia corretto.  
- **Proprietà Primavera mancanti:** Assicurati che l'XML sia stato esportato con tutti i campi richiesti; le versioni più vecchie di Primavera potrebbero omettere alcune attributi.  
- **Prestazioni su file di grandi dimensioni:** Considera di aumentare la dimensione dell'heap JVM (`-Xmx2g` o superiore) per progetti con decine di migliaia di attività.

## Domande frequenti
### D: Posso modificare le proprietà specifiche di Primavera delle attività usando Aspose.Tasks per Java?
R: Sì, Aspose.Tasks per Java fornisce API per modificare le proprietà specifiche di Primavera delle attività secondo necessità.

### D: Aspose.Tasks per Java supporta la lettura di altri formati di file di progetto?
R: Sì, Aspose.Tasks per Java supporta la lettura di vari formati di file di progetto, inclusi MPP, XML e Primavera XML.

### D: Aspose.Tasks per Java è adatto per applicazioni di gestione progetti a livello enterprise?
R: Assolutamente, Aspose.Tasks per Java offre funzionalità robuste e scalabilità, rendendolo adatto per applicazioni di gestione progetti a livello enterprise.

### D: Posso estrarre informazioni sulle risorse dai progetti Primavera usando Aspose.Tasks per Java?
R: Sì, Aspose.Tasks per Java consente di estrarre le informazioni sulle risorse insieme ai dettagli delle attività dai progetti Primavera.

### D: Dove posso trovare supporto aggiuntivo o documentazione per Aspose.Tasks per Java?
R: Puoi trovare una documentazione completa e accedere ai forum di supporto nella pagina della [documentazione di Aspose.Tasks per Java](https://reference.aspose.com/tasks/java/).

## Conclusione
Hai ora imparato **come leggere i file primavera xml** e importare informazioni dettagliate sulle attività in un'applicazione Java usando **aspose tasks java**. Questa capacità colma il divario tra Primavera e Microsoft Project, offrendoti piena visibilità su entrambe le piattaforme e migliorando l’efficienza complessiva della gestione dei progetti.

---

**Ultimo aggiornamento:** 2026-04-24  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}