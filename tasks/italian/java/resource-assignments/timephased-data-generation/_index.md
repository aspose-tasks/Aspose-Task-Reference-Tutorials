---
date: 2026-01-10
description: Scopri come modificare il contorno e generare dati temporizzati per le
  assegnazioni delle risorse usando Aspose.Tasks per Java, migliorando l'efficienza
  della gestione dei progetti.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come modificare il contorno in Aspose.Tasks per i dati temporizzati
url: /it/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come cambiare il contorno in Aspose.Tasks per dati a intervalli temporali

## Introduzione
In questo tutorial, scoprirai **come cambiare il contorno** per un'assegnazione di risorsa e generare dati a intervalli temporali usando Aspose.Tasks per Java. I dati a intervalli temporali mostrano la distribuzione del lavoro lungo la cronologia del progetto, consentendoti di perfezionare i piani, bilanciare i carichi di lavoro e prendere decisioni basate sui dati.

## Risposte rapide
- **Che cos'è un contorno?** Un contorno di lavoro definisce come lo sforzo è distribuito nella durata di un'attività (es. Flat, Turtle, Bell).  
- **Perché cambiare un contorno?** Per riflettere schemi di lavoro realistici come il caricamento anticipato o posticipato dello sforzo.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (qualsiasi versione recente).  
- **È necessaria una licenza?** Sì, è necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso vedere i risultati nella console?** L'esempio stampa le date di inizio e i valori per ogni segmento a intervalli temporali.

## Che cosa significa “come cambiare il contorno”?
Cambiare un contorno significa aggiornare la proprietà `WORK_CONTOUR` di un `ResourceAssignment`. Aspose.Tasks supporta diversi contorni predefiniti (Flat, Turtle, Bell, ecc.) che influenzano come il lavoro è assegnato nel tempo.

## Perché usare Aspose.Tasks per generare dati a intervalli temporali?
- **Reportistica accurata:** Esporta una distribuzione precisa del lavoro per gli strumenti di reporting.  
- **Pianificazione di scenari:** Prova diversi contorni senza modificare il programma originale.  
- **Automazione:** Integra nei pipeline CI per convalidare automaticamente lo stato del progetto.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): Assicurati di avere il JDK installato sul tuo sistema. Puoi scaricare e installare il JDK da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Libreria Aspose.Tasks per Java: È necessario avere la libreria Aspose.Tasks per Java. Puoi scaricarla dal [sito web](https://releases.aspose.com/tasks/java/).

## Importa i pacchetti
Prima, importiamo i pacchetti necessari per lavorare con Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Passo 1: Leggi il file MPP di origine
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Passo 2: Ottieni l'attività e l'assegnazione della risorsa
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Come cambiare il contorno – Flat (Predefinito)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Come cambiare il contorno – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Problemi comuni e suggerimenti
- **Il contorno non si aggiorna?** Assicurati di chiamare `firstRA.set(Asn.WORK_CONTOUR, …)` *prima* di recuperare i dati a intervalli temporali.
- **Valori inattesi?** Verifica che le date di inizio e fine dell'attività siano impostate correttamente nel MPP di origine.
- **Suggerimento di performance:** Riutilizza la stessa istanza `Project` quando iteri attraverso più contorni per evitare I/O di file non necessario.

## FAQ
### Posso usare Aspose.Tasks con altre librerie Java?
Sì, Aspose.Tasks può essere integrato con altre librerie Java per migliorare le capacità di gestione dei progetti.

### Aspose.Tasks è adatto per progetti aziendali su larga scala?
Assolutamente, Aspose.Tasks è progettato per gestire progetti di tutte le dimensioni, incluse iniziative aziendali su larga scala.

### Aspose.Tasks fornisce supporto per diversi formati di file di progetto?
Sì, Aspose.Tasks supporta una varietà di formati, come MPP, XML e MPX.

### Posso personalizzare i contorni di lavoro in base ai requisiti del mio progetto?
Sì, puoi definire contorni di lavoro personalizzati per soddisfare esigenze di pianificazione specifiche.

### Esiste un forum della community dove posso ottenere assistenza su Aspose.Tasks?
Sì, puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto e discussioni.

---

**Ultimo aggiornamento:** 2026-01-10  
**Testato con:** Aspose.Tasks per Java (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}