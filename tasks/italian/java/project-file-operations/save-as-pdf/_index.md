---
date: 2026-03-27
description: Scopri come salvare un progetto in PDF usando Aspose.Tasks per Java,
  una guida semplice per convertire MPP in PDF ed esportare efficacemente i file di
  progetto.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come salvare un progetto in PDF con Aspose.Tasks – Guida all'esportazione
url: /it/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come salvare un progetto in PDF con Aspise.Tasks – Guida all'esportazione

## Introduzione
In questo tutorial scoprirai **come salvare un progetto in pdf** utilizzando Aspose.Tasks per Java. Ti guideremo passo passo, dalla conversione a una riga fino alla personalizzazione avanzata del PDF, così potrai trasformare qualsiasi MPP (o altro formato supportato) in un documento PDF rifinito e condivisibile. Che tu abbia bisogno di un rapido report stampabile o di un diagramma di Gantt completamente stilizzato, questi passaggi ti porteranno al risultato in modo veloce.

## Risposte rapide
- **Cosa significa “esportare PDF” in Aspose.Tasks?** Significa convertire un file di progetto (ad es., MPP) in un documento PDF che conserva il layout visivo.  
- **Quale versione della libreria è necessaria?** Qualsiasi versione di Aspose.Tasks per Java che supporti `PdfSaveOptions` (si consiglia l'ultima release).  
- **È necessaria una licenza per questa conversione?** Una versione di prova gratuita è sufficiente per lo sviluppo; per l'uso in produzione è richiesta una licenza commerciale.  
- **Posso personalizzare l'aspetto del PDF?** Sì – è possibile impostare la scala temporale, le legende e altre `PdfSaveOptions`.  
- **La conversione è veloce per progetti di grandi dimensioni?** Tipicamente pochi secondi; le prestazioni dipendono dalla dimensione del progetto e dalle opzioni scelte.

## Che cosa significa “salvare un progetto come pdf” nel contesto di Aspose.Tasks?
Salvare un progetto come PDF con Aspose.Tasks significa prendere un file di progetto (come `.mpp`, `.xml` o `.xlsx`) e generare un PDF che rispecchia il diagramma di Gantt, la vista utilizzo attività o qualsiasi altro formato di presentazione configurato. Questo è utile per report, documentazione o per condividere visualizzazioni in sola lettura con stakeholder non tecnici.

## Perché esportare il diagramma di Gantt in PDF?
- **Leggibilità universale:** i PDF si aprono su qualsiasi dispositivo senza necessità del software di progetto originale.  
- **Presentazione professionale:** mantengono colori, caratteri e layout per report destinati ai clienti.  
- **Distribuzione semplice:** condividi via email, intranet o cloud storage senza preoccupazioni di controllo versioni.  
- **Conformità e archiviazione:** i PDF sono ideali per la conservazione a lungo termine e per la conformità normativa.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

1. **Java Development Kit (JDK):** JDK 8 o successivo installato sulla tua macchina.  
2. **Libreria Aspose.Tasks per Java:** Scarica la libreria dal sito ufficiale [qui](https://releases.aspose.com/tasks/java/).  
3. **Un file di progetto:** Disponi di un file di progetto esistente (ad es., `HomeMovePlan.mpp`) pronto per la conversione.

## Importare i pacchetti
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Guida passo‑passo

### Passo 1: Leggere il file di progetto di input
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Sostituisci `"Your Data Directory"` con il percorso assoluto in cui si trova il tuo file `.mpp`. Questo carica il progetto in memoria così da poterlo manipolare o esportare.

### Passo 2: Salvare il progetto come PDF (conversione di base)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
La riga sopra esegue un'operazione semplice di **salvare progetto come pdf**, creando `Project5.pdf` nella stessa cartella.

### Passo 3: Adattare i contenuti alla dimensione della cella (opzioni PDF avanzate)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Qui dimostriamo l'uso delle **pdf save options** per controllare il layout:
- `setFitContent(true)` forza il contenuto a adattarsi alla larghezza della cella.  
- `setTimescale(Timescale.Months)` imposta la scala temporale su mesi.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` seleziona la vista Utilizzo attività.

### Passo 4: Nascondere le legende (output più pulito)
```java
o.setLegendOnEachPage(false);
```
Disabilitare le legende può rendere il PDF più compatto, specialmente per progetti di grandi dimensioni.

### Passo 5: Salvare il progetto con le opzioni applicate
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Questo passaggio finale scrive il PDF usando le opzioni personalizzate definite sopra, producendo un documento pulito, con scala mensile e senza legende per pagina.

## Esportare il diagramma di Gantt in PDF – Stile personalizzato
Se desideri esportare solo il diagramma di Gantt con un aspetto specifico, imposta `PresentationFormat` su `GanttChart` e regola opzioni aggiuntive come `setBarColor` o `setShowCriticalTasks`. Questo approccio ti consente di **export gantt chart to pdf** con pieno controllo sugli elementi visivi.

## Problemi comuni e suggerimenti
- **File non trovato:** Verifica che `dataDir` termini con un separatore di file (`/` o `\\`) e punti alla directory corretta.  
- **Pagine vuote:** Accertati che il `PresentationFormat` selezionato corrisponda alla vista che ti aspetti (ad es., Gantt, Utilizzo attività).  
- **File di grandi dimensioni richiedono più tempo:** Considera di impostare `o.setFitContent(false)` per progetti molto grandi, così da ridurre i tempi di elaborazione.  

## Domande frequenti

**D: Aspose.Tasks è compatibile con tutte le versioni di Java?**  
R: Sì, Aspose.Tasks supporta le versioni di Java a partire da JDK 6 in poi.

**D: Posso personalizzare l'aspetto dell'output PDF?**  
R: Assolutamente! Aspose.Tasks offre numerose **pdf save options**—come scala temporale, visibilità della legenda e formato di presentazione—per adattare il PDF alle tue esigenze.

**D: Aspose.Tasks supporta altri formati di file per la conversione?**  
R: Sì, è possibile convertire tra MPP, XML, XLSX e molti altri formati, rendendolo uno strumento versatile per **convert mpp to pdf** e altre trasformazioni.

**D: È disponibile una versione di prova di Aspose.Tasks?**  
R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks da [qui](https://releases.aspose.com/).

**D: Dove posso ottenere supporto per Aspose.Tasks?**  
R: Per supporto e assistenza, visita il forum ufficiale [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusione
Seguendo questa guida, ora sai **come salvare un progetto in pdf** da qualsiasi progetto Java usando Aspose.Tasks, dalla semplice riga di salvataggio alla personalizzazione avanzata con `PdfSaveOptions`. Usa queste tecniche per produrre PDF rifiniti e condivisibili per report, presentazioni ai clienti o archiviazione.

---

**Ultimo aggiornamento:** 2026-03-27  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}