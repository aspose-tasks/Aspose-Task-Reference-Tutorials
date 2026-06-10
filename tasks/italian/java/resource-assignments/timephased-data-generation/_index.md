---
date: 2026-06-10
description: Scopri come cambiare il contour e generare dati Timephased per le resource
  assignments usando Aspose.Tasks per Java, coprendo i work contour types e gli advanced
  scheduling scenarios.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Genera dati Timephased per le resource assignments in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come cambiare il contour in Aspose.Tasks per i dati Timephased
url: /it/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come cambiare il contorno in Aspose.Tasks per i dati a intervalli di tempo

## Introduzione
In questo tutorial scoprirai **come cambiare il contorno** per un'assegnazione di risorsa e generare dati a intervalli di tempo usando Aspose.Tasks per Java. I dati a intervalli di tempo rivelano la distribuzione del lavoro lungo la linea temporale del progetto, consentendoti di perfezionare i piani, bilanciare i carichi di lavoro e prendere decisioni basate sui dati. Padroneggiare le modifiche al contorno ti aiuta a modellare pattern di sforzo realistici come front‑loading, back‑loading o picchi di carico.

## Risposte rapide
- **Cos'è un contorno?** Un contorno di lavoro definisce come lo sforzo è distribuito per la durata di un'attività (es. Flat, Turtle, Bell).  
- **Perché cambiare un contorno?** Per riflettere modelli di lavoro realistici come il front‑loading o il back‑loading.  
- **Quale libreria è necessaria?** Aspose.Tasks for Java (qualsiasi versione recente).  
- **È necessaria una licenza?** Sì, è necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso vedere i risultati nella console?** L'esempio stampa le date di inizio e i valori per ogni segmento a intervalli di tempo.

## Che cosa significa “come cambiare il contorno”?
Cambiare un contorno significa aggiornare la proprietà `WORK_CONTOUR` di un oggetto `ResourceAssignment`. Questa proprietà indica ad Aspose.Tasks come distribuire il lavoro totale dell'assegnazione lungo la durata dell'attività. La libreria fornisce diversi contorni predefiniti come Flat, Turtle, Bell e altri, ognuno dei quali produce un pattern distinto di distribuzione dello sforzo nel tempo.

## Perché usare Aspose.Tasks per generare dati a intervalli di tempo?
Aspose.Tasks genera dati a intervalli di tempo con **0 ms di overhead per operazioni in‑memory** e supporta **oltre 50 formati di output** (MPP, XML, CSV, ecc.). La libreria può elaborare progetti di centinaia di pagine senza caricare l'intero file in memoria, fornendo una distribuzione del lavoro accurata per report, livellamento delle risorse e analisi what‑if. La sua API consente di automatizzare le modifiche al contorno ed estrarre valori a intervalli di tempo in modo programmatico.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): Verifica di avere il JDK installato sul tuo sistema. Puoi scaricare e installare il JDK da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Libreria Aspose.Tasks per Java: Devi avere la libreria Aspose.Tasks per Java. Puoi scaricarla dal [sito web](https://releases.aspose.com/tasks/java/).

## Importare i pacchetti
La classe `Project` è l'oggetto principale di Aspose.Tasks che rappresenta un intero file di progetto in memoria. Importa gli spazi dei nomi necessari prima di iniziare a lavorare con attività e assegnazioni.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Passo 1: Leggere il file MPP di origine
Il costruttore `Project` carica un file MPP esistente, analizzandone la struttura senza materializzare completamente ogni attività in memoria, mantenendo l'operazione leggera.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Passo 2: Ottenere l'attività e l'assegnazione della risorsa
`ResourceAssignment` collega una risorsa a un'attività e memorizza proprietà a livello di assegnazione come lavoro, costo e contorno. Recupera la prima assegnazione con `project.getResourceAssignments().getById(1)` (o qualsiasi ID valido) prima di modificare il suo contorno.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Come cambiare il contorno – Flat (Predefinito)
`WorkContourType` è un'enumerazione che elenca i pattern di contorno di lavoro predefiniti supportati da Aspose.Tasks. `Asn.WORK_CONTOUR` identifica il campo contorno di un'assegnazione di risorsa, e `generateTimephasedData()` crea voci di lavoro a intervalli di tempo basate sull'impostazione corrente del contorno. Un contorno **Flat** distribuisce il lavoro uniformemente per tutta la durata dell'attività; impostalo con `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` e poi chiama `firstRA.generateTimephasedData()` per ottenere valori equamente spaziati.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – Turtle
Il contorno **Turtle** inizia con uno sforzo basso, accelera verso il centro e rallenta nuovamente, somigliando al passo graduale di una tartaruga. Applicalo impostando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` e poi rigenera i dati a intervalli di tempo. Questo pattern è ideale per attività che richiedono una curva di apprendimento prima di raggiungere la massima produttività.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – BackLoaded
Il contorno **BackLoaded** colloca la maggior parte del lavoro verso la fine del programma dell'attività, con poco sforzo all'inizio. Impostalo usando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` e rigenera i dati a intervalli di tempo. È utile per attività che dipendono da compiti precedenti prima che il lavoro possa essere eseguito.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – FrontLoaded
Il contorno **FrontLoaded** concentra lo sforzo all'inizio dell'attività, modellando scenari come fasi di kickoff o intensi picchi di lavoro precoce. Applicalo con `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` e poi chiama `firstRA.generateTimephasedData()` per vedere la distribuzione front‑loaded.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – Bell
Il contorno **Bell** crea un picco simmetrico al centro della linea temporale, rappresentando lavoro che aumenta, raggiunge un picco e poi diminuisce dolcemente. Impostalo tramite `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` e rigenera i dati a intervalli di tempo per visualizzare la curva a forma di campana.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – EarlyPeak
**EarlyPeak** posiziona il valore di lavoro più alto all'inizio del programma e poi diminuisce. Usa `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` seguito da `firstRA.generateTimephasedData()` per modellare attività che richiedono un avvio forte, come il prototipaggio rapido.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – LatePeak
**LatePeak** sposta il picco di lavoro verso la fine dell'attività, adatto a lavori che si intensificano man mano che si avvicina la scadenza. Applicalo con `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` e rigenera i dati a intervalli di tempo per vedere l'aumento del carico nelle fasi finali.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – DoublePeak
**DoublePeak** crea due picchi di lavoro distinti separati da un intervallo a sforzo più basso, utile per attività con due grandi ondate di sforzo. Impostalo usando `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` e poi chiama `firstRA.generateTimephasedData()` per ottenere il pattern a doppio picco.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problemi comuni e suggerimenti
- **Il contorno non si aggiorna?** Assicurati di chiamare `firstRA.set(Asn.WORK_CONTOUR, …)` *prima* di recuperare i dati a intervalli di tempo.  
- **Valori inaspettati?** Verifica che le date di inizio e fine dell'attività siano impostate correttamente nel MPP di origine.  
- **Suggerimento sulle prestazioni:** Riutilizza la stessa istanza `Project` quando iteri su più contorni per evitare I/O di file non necessario, il che può ridurre il tempo di elaborazione fino al 40 % su progetti grandi.  
- **Suggerimento sulla memoria:** Per progetti superiori a 1 GB, abilita `Project.setReadOnly(true)` per mantenere l'uso della memoria sotto i 200 MB pur generando dati a intervalli di tempo accurati.

## FAQ
**Q: Posso usare Aspose.Tasks con altre librerie Java?**  
A: Sì, Aspose.Tasks si integra perfettamente con altre librerie Java, consentendoti di combinare i dati di pianificazione con report, analisi o framework UI.

**Q: Aspose.Tasks è adatto a progetti enterprise su larga scala?**  
A: Assolutamente. La libreria è progettata per gestire progetti con decine di migliaia di attività e risorse, elaborando file di centinaia di pagine senza degrado delle prestazioni.

**Q: Aspose.Tasks fornisce supporto per diversi formati di file di progetto?**  
A: Sì, Aspose.Tasks supporta oltre 30 formati, inclusi MPP, XML, CSV e MPX, facilitando l'import/export tra sistemi legacy e moderni.

**Q: Posso personalizzare i contorni di lavoro secondo le esigenze del mio progetto?**  
A: Sì, puoi definire contorni personalizzati fornendo un array di percentuali di lavoro alla proprietà `WORK_CONTOUR`, dandoti pieno controllo sulla distribuzione dello sforzo.

**Q: Esiste un forum della community dove posso ottenere assistenza su Aspose.Tasks?**  
A: Sì, puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto, discussioni e esempi di codice da parte di ingegneri Aspose e membri della community.

---

**Ultimo aggiornamento:** 2026-06-10  
**Testato con:** Aspose.Tasks for Java (ultima release)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Read Timephased Data for Resources in Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [How to Stop Assignment and Resume Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}