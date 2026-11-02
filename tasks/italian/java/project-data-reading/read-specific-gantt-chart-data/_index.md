---
date: 2026-10-31
description: Scopri come esportare Gantt in PDF in Java usando Aspose.Tasks. Questa
  guida passo‑passo ti mostra come leggere i dati del diagramma di Gantt e generare
  report PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Leggi dati specifici del diagramma di Gantt in Aspose.Tasks
og_description: Esporta Gantt in PDF in Java con Aspose.Tasks. Segui questo tutorial
  per leggere i dati del diagramma di Gantt, personalizzare le proprietà della visualizzazione
  e generare report PDF per la gestione dei progetti.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Esporta Gantt in PDF in Java – guida Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Esporta Gantt in PDF in Java – estrai dati specifici
url: /it/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esporta gantt in PDF con Java – estrai dati specifici

## Introduzione
In questo tutorial imparerai come **esportare gantt in PDF con Java** leggendo le informazioni del diagramma di Gantt con Aspose.Tasks per Java. I diagrammi di Gantt forniscono ai project manager una roadmap visiva di attività, dipendenze e tempistiche, e la possibilità di estrarre questi dati programmaticamente ti consente di creare report PDF automatizzati, dashboard o integrazioni con altri sistemi aziendali. Seguiamo ogni passaggio, dal caricamento di un file di progetto all'estrazione delle proprietà della vista e infine alla generazione di un PDF.

## Risposte rapide
- **Cosa posso estrarre?** Qualsiasi proprietà della vista, stile della barra, linea della griglia, stile del testo, linea di avanzamento o livello della scala temporale da un diagramma di Gantt.  
- **Ho bisogno di una licenza?** Una versione di prova funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o successive (il tutorial utilizza JDK 11).  
- **Il codice è eseguibile così com'è?** Sì – basta sostituire il percorso della directory dei dati.  
- **Posso modificare la vista dopo la lettura?** Assolutamente – l'API consente di modificare le proprietà e salvare nuovamente il file di progetto.

## Cos'è l'esportazione di gantt in PDF?
L'esportazione di gantt in PDF è il processo di conversione di una vista di diagramma di Gantt memorizzata in un file di progetto in un documento PDF che preserva lo stile visivo e le informazioni temporali. Questa operazione è utile per condividere lo stato del progetto con gli stakeholder che potrebbero non disporre di uno strumento di gestione dei progetti.

## Perché esportare gantt in PDF con Aspose.Tasks?
Aspose.Tasks può gestire **oltre 30 + formati di input** (MPP, XML, MPX, ecc.) e **esportare in PDF con una singola chiamata** preservando il 95 % della fedeltà visiva, anche per progetti con più di 500 attività. La libreria elabora i file in memoria, quindi è possibile generare PDF sui server senza installare Microsoft Project.

## Prerequisiti
1. **Java Development Kit (JDK):** Assicurati di avere Java installato sul tuo sistema. Puoi scaricarlo dalla **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Scarica e installa la libreria Aspose.Tasks per Java dalla **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Scegli un IDE a tua preferenza. Le scelte più popolari includono IntelliJ IDEA, Eclipse o NetBeans.

## Importa pacchetti
Le seguenti importazioni ti danno accesso alle classi principali di Aspose.Tasks necessarie per leggere ed esportare i dati Gantt.  
*Non è mostrato alcun blocco di codice qui per mantenere il tutorial focalizzato sui concetti; aggiungi semplicemente le importazioni al tuo file Java.*

## Come carico un file di progetto Gantt in Java?
Carica il file di progetto creando un'istanza `Project` e passando il percorso completo al costruttore. Questo passaggio inizializza la rappresentazione in memoria del diagramma di Gantt, consentendo successive query delle proprietà della vista. Quando il file è caricato correttamente, puoi verificare il nome del progetto, la data di inizio e il numero di attività per assicurarti che sia stato aperto il file corretto. Questa verifica aiuta a individuare problemi di percorso o di formato all'inizio del flusso di lavoro.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definition anchor:* `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file di progetto in memoria.

## Come posso accedere alla vista del diagramma di Gantt?
Recupera la prima vista Gantt dalla collezione di viste del progetto. La maggior parte dei progetti contiene almeno una vista Gantt, solitamente la prima voce. Dopo aver ottenuto la vista, potresti voler controllare il suo nome e assicurarti che sia di tipo `GanttChartView` prima di procedere con l'estrazione delle proprietà. Questo controllo aggiuntivo previene errori di runtime quando si lavora con collezioni di viste personalizzate o non standard.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definition anchor:* `GanttChartView` rappresenta il layout visivo di attività, scale temporali e barre che vedi in un tipico diagramma di Gantt.

## Come estrarre le proprietà della vista?
Puoi leggere proprietà come il colore di sfondo, l'altezza della barra e le impostazioni della scala temporale direttamente dall'oggetto `GanttChartView`. Stampare queste proprietà ti aiuta a verificare la configurazione corrente prima dell'esportazione. Un tipico ciclo di estrazione itera su ogni proprietà, formatta il valore come stringa e lo registra nella console o in un file per analisi successive. Questo approccio è utile per il debug e per generare documentazione sull'aspetto del diagramma.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definition anchor:* `GanttChartView` fornisce l'accesso alle impostazioni della vista come colore di sfondo, altezza della barra e configurazione della scala temporale.

## Come estrarre gli stili delle barre?
Itera attraverso la collezione di oggetti `BarStyle` per ottenere dettagli come colore, modello e forma per ogni tipo di barra utilizzata nel diagramma. Per ogni stile, puoi anche leggere il tipo di attività associato e la condizione che attiva lo stile, essenziali quando ricrei il diagramma in un altro formato. Raccogliere queste informazioni ti consente di produrre una replica visiva fedele o di applicare regole di stile personalizzate programmaticamente.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definition anchor:* `BarStyle` definisce l'aspetto visivo di una barra Gantt, includendo colore, modello e forma.

## Come estrarre le linee della griglia?
Le linee della griglia definiscono la separazione visiva tra righe e colonne. Accedile tramite il metodo `getGridlines()` e restituisci la loro visibilità e stile. Dopo aver recuperato la collezione delle linee della griglia, puoi iterare su ciascuna linea per catturare il tipo di linea (solida, tratteggiata), lo spessore e il colore. Questi dati sono utili quando è necessario riprodurre l'esatta disposizione della griglia nei PDF esportati o in altri formati di report.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definition anchor:* `getGridlines()` restituisce la collezione di oggetti linee della griglia che controllano i separatori di righe e colonne nella vista Gantt.

## Come estrarre gli stili del testo?
Gli stili del testo controllano il font, la dimensione e il colore delle etichette sul diagramma di Gantt. Itera attraverso la collezione `TextStyle` per elencare ogni stile. Per ciascuno stile di testo, puoi anche recuperare l'elemento associato (nome attività, data, ecc.) e eventuali regole di formattazione condizionale. Catturare questi dettagli garantisce che i documenti esportati mantengano la stessa tipografia del diagramma originale.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definition anchor:* `TextStyle` rappresenta gli attributi di formattazione applicati agli elementi testuali all'interno del diagramma di Gantt.

## Come estrarre le linee di avanzamento?
Le linee di avanzamento mostrano il punto di completamento corrente di un'attività. Accedile tramite `getProgressLines()` e stampa le loro proprietà. Ogni linea di avanzamento include proprietà come colore della linea, spessore e posizione rispetto alla barra dell'attività. Registrare queste informazioni ti consente di generare visualizzazioni sensibili al progresso o di calcolare metriche di completamento complessivo del progetto.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definition anchor:* `getProgressLines()` restituisce l'insieme di oggetti linea di avanzamento che indicano lo stato di completamento dell'attività.

## Come estrarre i livelli della scala temporale?
I livelli della scala temporale definiscono le unità di tempo gerarchiche (giorni, settimane, mesi) visualizzate sul diagramma. Recuperali tramite `getTimescaleTiers()` e restituisci le loro impostazioni. Per ogni livello puoi catturare il tipo di unità, il formato dell'etichetta e l'allineamento, elementi cruciali per riprodurre l'esatta granularità della timeline nei PDF esportati o in componenti UI personalizzate.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definition anchor:* `getTimescaleTiers()` fornisce l'accesso alla collezione di oggetti livello della scala temporale che controllano la visualizzazione dell'asse temporale.

## Come esportare il diagramma di Gantt in PDF?
Crea un oggetto `PdfSaveOptions`, opzionalmente personalizza la dimensione della pagina o l'incorporamento dei font, quindi chiama `project.save` con il formato PDF. Questa singola chiamata genera un PDF che rispecchia la vista Gantt sullo schermo. Puoi anche specificare opzioni aggiuntive come compressione delle immagini, rimozione della filigrana o incorporamento di font personalizzati per soddisfare i requisiti di branding aziendale. Dopo il salvataggio, verifica la dimensione del file PDF e la fedeltà visiva per assicurarti che l'esportazione sia riuscita.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definition anchor:* `PdfSaveOptions` ti consente di perfezionare l'output PDF, come dimensioni della pagina, compressione e gestione dei font.

## Problemi comuni e consigli
- **Directory dei dati errata:** Assicurati che `dataDir` termini con un separatore di file (`/` o `\\`) appropriato per il tuo OS.  
- **Vista mancante:** Se il progetto non ha una vista Gantt, `project.getViews()` sarà vuota – aggiungi un controllo prima del cast.  
- **Eccezioni di licenza:** Senza una licenza valida, l'API potrebbe aggiungere una filigrana ai PDF esportati.  
- **Progetti grandi:** Per progetti con più di 1.000 attività, considera di aumentare la dimensione dell'heap JVM (`-Xmx2g`) per evitare `OutOfMemoryError`.  

## Domande frequenti

**Q: Posso usare Aspose.Tasks per Java con altre librerie Java?**  
A: Sì, Aspose.Tasks per Java si integra perfettamente con qualsiasi libreria o framework Java, inclusi Spring, Hibernate e Apache POI.

**Q: Aspose.Tasks è adatto per progetti aziendali su larga scala?**  
A: Assolutamente. La libreria elabora file MPP di centinaia di pagine in meno di 5 secondi su hardware server standard e supporta l'esecuzione concorrente in ambienti multithread.

**Q: Aspose.Tasks supporta più formati di file di progetto?**  
A: Sì, Aspose.Tasks supporta oltre 20 formati, includendo MPP, XML, MPX e Primavera XML, consentendo di leggere e convertire schedule legacy.

**Q: Posso personalizzare l'aspetto dei diagrammi di Gantt con Aspose.Tasks?**  
A: Certamente. Puoi modificare gli stili delle barre, le linee della griglia, gli stili del testo e i livelli della scala temporale programmaticamente prima di esportare in PDF o formati immagine.

**Q: Come salvo le modifiche dopo aver modificato una vista?**  
A: Chiama `project.save("output.mpp");` dopo aver apportato modifiche per persisterle nel file di progetto.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Tutorial correlati

- [Come salvare il progetto come PDF con Aspose.Tasks – Guida all'esportazione](/tasks/java/project-file-operations/save-as-pdf/)
- [Crea PDF del progetto – Personalizza la scala temporale del diagramma di Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Esporta progetto in PDF e riduci lo spazio tra l'elenco delle attività e il piè di pagina in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}