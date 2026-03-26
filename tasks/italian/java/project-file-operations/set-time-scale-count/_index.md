---
date: 2025-12-21
description: Scopri come personalizzare le visualizzazioni del diagramma di Gantt,
  gestire la visualizzazione del progetto e salvare il progetto in PDF usando Aspose.Tasks
  per Java. Regola il conteggio della scala temporale senza sforzo.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Personalizza il diagramma di Gantt – Padroneggiare il conteggio della scala
  temporale di MS Project in Aspose.Tasks
url: /it/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalizza il diagramma di Gantt – Padronanza del conteggio della scala temporale di MS Project in Aspose.Tasks

## Introduzione
Se devi **personalizzare il diagramma di Gantt** in Microsoft Project, controllare il conteggio della scala temporale è una tecnica fondamentale. Con Aspose.Tasks per Java puoi impostare programmaticamente i livelli inferiore e intermedio della scala temporale, regolare finemente la visibilità dei segni di spunta e poi **salvare il progetto come PDF** per condividerlo con gli stakeholder. Questo tutorial ti guida attraverso l’intero processo—dalla configurazione dell’ambiente alla generazione di un PDF curato che riflette la tua visualizzazione Gantt personalizzata.

## Risposte rapide
- **Cosa significa “personalizzare il diagramma di Gantt”?** Regolare i livelli della scala temporale, i colori e il layout per soddisfare le tue esigenze di reporting.  
- **Quale metodo API imposta il conteggio del livello inferiore?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Posso generare un PDF direttamente dal progetto?** Sì—usa `project.save(..., SaveFileFormat.Pdf)`.  
- **È necessaria una licenza per l’uso in produzione?** È richiesta una licenza commerciale; è disponibile una versione di prova gratuita.  
- **Quale versione di Java è supportata?** Java 8 o superiore funziona con l’ultima libreria Aspose.Tasks.

## Cos’è “personalizzare il diagramma di Gantt” in Aspose.Tasks?
Personalizzare un diagramma di Gantt significa modificare programmaticamente i suoi componenti visivi—come gli intervalli della scala temporale, i segni di spunta e le barre delle attività—affinché il diagramma si adatti al modo in cui desideri **gestire la visualizzazione del progetto**. Cambiando il conteggio della scala temporale, controlli quanti giorni, settimane o mesi rappresenta ogni segmento, rendendo il diagramma più chiaro per diversi pubblici.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Ambiente di sviluppo Java** – JDK 8 o più recente installato.  
2. **Libreria Aspose.Tasks per Java** – Scaricala da [qui](https://releases.aspose.com/tasks/java/).  
3. **Conoscenze di base di Java** – Familiarità con la sintassi Java e i concetti di programmazione orientata agli oggetti.

## Importa i pacchetti
Importa le classi necessarie nel tuo progetto Java:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Guida passo‑passo

### Passo 1: Imposta la directory dei dati
Definisci dove i file del progetto saranno letti e scritti:

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso assoluto sulla tua macchina.

### Passo 2: Crea una nuova istanza di Project
Istanzia un nuovo oggetto `Project` che conterrà tutte le attività e le impostazioni di visualizzazione:

```java
Project project = new Project();
```

### Passo 3: Configura la visualizzazione del diagramma di Gantt
Crea un oggetto `GanttChartView`—questo è dove **genererai il codice Java per la visualizzazione Gantt** per controllare l’aspetto del diagramma:

```java
GanttChartView view = new GanttChartView();
```

### Passo 4: Imposta il conteggio della scala temporale per il livello inferiore
Regola il livello inferiore per mostrare due intervalli e nascondere i segni di spunta:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Passo 5: Imposta il conteggio della scala temporale per il livello intermedio
Applica la stessa configurazione al livello intermedio:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Passo 6: Aggiungi la visualizzazione personalizzata al progetto
Allega la visualizzazione appena configurata all’istanza `Project`:

```java
project.getViews().add(view);
```

### Passo 7: Aggiungi attività di esempio (dati di test)
Crea un paio di attività con durate specifiche per illustrare il diagramma di Gantt personalizzato:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Passo 8: Salva il progetto come PDF
Infine, esporta il progetto—compreso il tuo **diagramma di Gantt personalizzato**—in un file PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Il PDF risultante dimostra come i livelli inferiore e intermedio della scala temporale siano stati **personalizzati**, offrendo agli stakeholder una vista chiara e stampabile del programma.

## Problemi comuni e risoluzione
- **Il PDF è vuoto** – Verifica che il percorso `dataDir` termini con un separatore di file (`/` o `\`) e che la directory esista.  
- **I segni di spunta compaiono ancora** – Controlla che `setShowTicks(false)` sia stato chiamato su entrambi i livelli.  
- **Durata non applicata** – Assicurati di utilizzare `TimeUnitType.Hour` (o l’unità appropriata) quando crei le durate.

## Domande frequenti

**D: Aspose.Tasks per Java può gestire file di progetto su larga scala?**  
R: Sì, la libreria è ottimizzata per l’elaborazione ad alte prestazioni di grandi quantità di dati di progetto.

**D: Aspose.Tasks per Java è compatibile con diversi IDE Java?**  
R: Assolutamente—funziona senza problemi con Eclipse, IntelliJ IDEA, NetBeans e altri IDE popolari.

**D: Posso personalizzare l’aspetto dei diagrammi di Gantt oltre alle impostazioni della scala temporale?**  
R: Sì, Aspose.Tasks offre ampie opzioni di stile come colori delle barre, caratteri e linee della griglia.

**D: È disponibile una versione di prova per Aspose.Tasks per Java?**  
R: Sì, puoi ottenere una versione di prova gratuita da [qui](https://releases.aspose.com/).

**D: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
R: Puoi trovare supporto e assistenza sul forum Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**D: Come modifico programmaticamente il colore di sfondo del diagramma di Gantt?**  
R: Usa il metodo `view.getGanttChartProperties().setBackgroundColor(Color)` dopo aver importato `java.awt.Color`.

## Conclusione
Seguendo questi passaggi hai imparato a **personalizzare i livelli della scala temporale del diagramma di Gantt**, migliorare la **visualizzazione del progetto** e **salvare il progetto come PDF** usando Aspose.Tasks per Java. Questo approccio ti offre il pieno controllo sull’output visivo, facilitando la condivisione di programmi chiari e professionali con il tuo team o i clienti.

---

**Ultimo aggiornamento:** 2025-12-21  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}