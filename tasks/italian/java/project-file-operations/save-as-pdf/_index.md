---
date: 2025-12-20
description: Scopri come esportare PDF in Aspose.Tasks per Java, una guida semplice
  per convertire MPP in PDF e salvare i tuoi file di progetto in modo efficiente.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come esportare PDF in Aspose.Tasks – Salva come PDF
url: /it/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come esportare PDF in Aspose.Tasks – Salva come PDF

## Introduzione
In questo tutorial, ti mostreremo **come esportare PDF** in Aspose.Tasks per Java, guidandoti attraverso il processo di salvataggio di un progetto come PDF. Con Aspose.Tasks, puoi convertire in modo efficiente **MPP in PDF**, garantendo compatibilità e facilità di condivisione tra team e stakeholder. Immergiamoci nei passaggi così potrai ottenere rapidamente un PDF stampabile da qualsiasi file di progetto.

## Risposte Rapide
- **Cosa significa “export PDF” in Aspose.Tasks?** Significa convertire un file di progetto (ad es., MPP) in un documento PDF che preserva il layout visuale.  
- **Quale versione della libreria è necessaria?** Qualsiasi versione di Aspose.Tasks per Java che supporti `PdfSaveOptions` (si consiglia l'ultima release).  
- **È necessaria una licenza per questa conversione?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per l'uso in produzione.  
- **Posso personalizzare l'aspetto del PDF?** Sì – è possibile impostare la scala temporale, le legende e altre `PdfSaveOptions`.  
- **La conversione è veloce per progetti di grandi dimensioni?** Tipicamente pochi secondi; le prestazioni dipendono dalle dimensioni del progetto e dalle opzioni scelte.

## Cos'è “come esportare pdf” nel contesto di Aspose.Tasks?
Esportare un PDF con Aspose.Tasks significa prendere un file di progetto (come `.mpp`, `.xml` o `.xlsx`) e generare un PDF che riproduce il diagramma di Gantt, la vista utilizzo attività o qualsiasi altro formato di presentazione configurato. Questo è utile per report, documentazione o per condividere visualizzazioni in sola lettura con stakeholder non tecnici.

## Perché esportare i file di progetto in PDF?
- **Leggibilità universale:** Il PDF funziona su qualsiasi dispositivo senza richiedere il software di progetto originale.  
- **Presentazione professionale:** Preserva formattazione, colori e layout per report destinati ai clienti.  
- **Distribuzione facile:** Condividi via email, intranet o storage cloud senza preoccupazioni di controllo versione.  
- **Conformità e archiviazione:** I PDF sono ideali per l'archiviazione a lungo termine e la conformità normativa.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

1. **Java Development Kit (JDK):** JDK 8 o successivo installato sulla tua macchina.  
2. **Libreria Aspose.Tasks per Java:** Scarica la libreria dal sito ufficiale [qui](https://releases.aspose.com/tasks/java/).  
3. **Un file di progetto:** Disponi di un file di progetto esistente (ad es., `HomeMovePlan.mpp`) pronto per la conversione.

## Importa Pacchetti
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Guida passo‑passo

### Passo 1: Leggi il file di progetto di input
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Sostituisci `"Your Data Directory"` con il percorso assoluto dove si trova il tuo file `.mpp`. Questo carica il progetto in memoria così potrai manipolarlo o esportarlo.

### Passo 2: Salva il progetto come PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
La riga sopra esegue un'operazione semplice di **salvataggio del progetto come PDF**, creando `Project5.pdf` nella stessa cartella.

### Passo 3: Adatta i contenuti alla dimensione della cella (Opzioni avanzate di salvataggio PDF)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Qui dimostriamo l'uso delle **pdf save options** per controllare il layout:
- `setFitContent(true)` forza il contenuto ad adattarsi alla larghezza della cella.  
- `setTimescale(Timescale.Months)` cambia la scala temporale in mesi.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` seleziona la vista Utilizzo attività.

### Passo 4: Nascondi le legende (Output più pulito)
```java
o.setLegendOnEachPage(false);
```
Disabilitare le legende può rendere il PDF più compatto, soprattutto per progetti di grandi dimensioni.

### Passo 5: Salva il progetto con le opzioni applicate
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Questo passaggio finale scrive il PDF usando le opzioni personalizzate definite sopra, producendo un documento pulito, scalato per mesi, senza legende per pagina.

## Problemi comuni e consigli
- **File non trovato:** Assicurati che `dataDir` termini con un separatore di file (`/` o `\\`) e punti alla directory corretta.  
- **Pagine vuote:** Verifica che il `PresentationFormat` selezionato corrisponda alla vista desiderata (ad es., Gantt, Utilizzo attività).  
- **I file grandi richiedono più tempo:** Considera di impostare `o.setFitContent(false)` per progetti molto grandi per ridurre i tempi di elaborazione.  

## Domande frequenti

**Q: Aspose.Tasks è compatibile con tutte le versioni di Java?**  
A: Sì, Aspose.Tasks supporta le versioni Java a partire da JDK 6 e successive.

**Q: Posso personalizzare l'aspetto dell'output PDF?**  
A: Assolutamente! Aspose.Tasks offre numerose **pdf save options**—come la scala temporale, la visibilità della legenda e il formato di presentazione—per adattare il PDF alle tue esigenze.

**Q: Aspose.Tasks supporta altri formati di file per la conversione?**  
A: Sì, è possibile convertire tra MPP, XML, XLSX e molti altri formati, rendendolo uno strumento versatile per **convert mpp to pdf** e altre trasformazioni.

**Q: È disponibile una versione di prova per Aspose.Tasks?**  
A: Sì, puoi ottenere una versione di prova gratuita di Aspose.Tasks da [qui](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto per Aspose.Tasks?**  
A: Per supporto e assistenza, visita il forum ufficiale [Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Conclusione
Seguendo questa guida, ora sai **come esportare PDF** da qualsiasi progetto Java usando Aspose.Tasks, da un semplice salvataggio a una riga a una personalizzazione avanzata con `PdfSaveOptions`. Usa queste tecniche per produrre PDF curati e condivisibili per report, presentazioni ai clienti o scopi di archiviazione.

---

**Last Updated:** 2025-12-20  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}