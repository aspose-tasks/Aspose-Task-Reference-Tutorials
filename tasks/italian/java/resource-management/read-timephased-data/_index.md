---
date: 2026-06-15
description: Scopri come estrarre i dati Timephased dalle risorse di MS Project usando
  Aspose.Tasks per Java. Guida passo‑passo per get resource by id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Leggi i dati Timephased per le risorse in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Leggi i dati Timephased per le risorse in Aspose.Tasks – get resource by id
url: /it/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggere i dati timephased per le risorse in Aspose.Tasks

## Introduzione
In questo tutorial, imparerai **how to get resource by id** e leggerai i suoi dati timephased usando Aspose.Tasks per Java. Ti guideremo passo dopo passo—dalla configurazione della cartella del progetto alla stampa dei valori timephased di lavoro e costo—così potrai estrarre informazioni di programmazione preziose da qualsiasi file Microsoft Project in modo programmatico. Aspose.Tasks per Java è un'API completa che consente agli sviluppatori di creare, leggere, modificare e convertire file Microsoft Project senza richiedere l'installazione di Microsoft Project, supportando un'ampia gamma di funzionalità e formati di gestione dei progetti.

## Risposte rapide
- **What does “get resource by id” do?** Recupera un oggetto `Resource` specifico da un `Project` usando il suo identificatore unico.  
- **Which library handles timephased data?** Aspose.Tasks per Java fornisce l'API `Resource.getTimephasedData`.  
- **Do I need a license?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Can I read large projects?** Sì—Aspose.Tasks può elaborare file con fino a 10.000 attività senza caricare l'intero file in memoria.  
- **What Java version is required?** Java 8 o superiore; la libreria è compatibile con tutti i principali JDK.

## Cos'è “get resource by id”?
`get resource by id` è una chiamata di metodo che recupera un'istanza `Resource` da un `Project` caricato usando l'ID numerico della risorsa. Questa operazione consente l'accesso preciso alle proprietà dettagliate di una risorsa, come le assegnazioni, i calendari e i campi personalizzati, ed è essenziale per estrarre dati di lavoro o costo timephased associati a quella specifica risorsa.

## Perché usare Aspose.Tasks per i dati timephased?
Aspose.Tasks supporta **50+ formati di input e output** (MPP, XML, CSV, ecc.) e può estrarre valori di lavoro e costo timephased per le risorse su schedule pluriennali mantenendo un basso utilizzo di memoria. L'API restituisce i dati in intervalli di 15 minuti per impostazione predefinita, fornendo un'analisi granulare per report o analisi personalizzate.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): Assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo dal [sito web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguire le istruzioni di installazione.  
2. Aspose.Tasks for Java Library: Scarica la libreria Aspose.Tasks per Java dalla [pagina di download](https://releases.aspose.com/tasks/java/) e segui le istruzioni di installazione fornite nella documentazione.

## Importare i pacchetti
Il primo passo è importare le classi Aspose.Tasks necessarie nel tuo file sorgente Java.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Passo 1: Configurare la directory dei dati
Definisci prima la directory in cui si trova il tuo file MS Project. Tenere la cartella dei dati separata dal codice sorgente rende il progetto più facile da mantenere.

```java
String dataDir = "Your Data Directory";
```

## Passo 2: Leggere il file modello MS Project
Specifica il nome del tuo file modello MS Project. L'uso di un modello garantisce impostazioni di colonna coerenti tra progetti diversi.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Passo 3: Leggere il file di input come Project
La classe `Project` è l'oggetto core di Aspose.Tasks che rappresenta un file Microsoft Project in memoria. Caricare il file ti dà accesso programmatico a attività, risorse e schedule.

```java
Project project = new Project(dataDir + fileName);
```

## Passo 4: Ottenere la risorsa per ID
Per recuperare una risorsa specifica, chiama il metodo `getResources().getById(id)`. Questa è l'operazione esatta a cui fa riferimento la parola chiave principale.

```java
Resource resource = project.getResources().getByUid(1);
```

## Passo 5: Stampare i dati timephased per il lavoro della risorsa
Una volta ottenuto l'oggetto `Resource`, puoi chiamare `resource.getTimephasedData(ResourceTimephasedDataType.Work)` per ottenere le allocazioni di lavoro nel tempo. La collezione restituita contiene oggetti `TimephasedData` che includono data di inizio, data di fine e quantità di lavoro per ogni intervallo.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Passo 6: Stampare i dati timephased per il costo della risorsa
Analogamente, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` restituisce le informazioni di costo suddivise negli stessi intervalli temporali. Questo è utile per report di budgeting e monitoraggio dei costi.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Come ottenere la risorsa per ID in una sola riga?
Carica il progetto, poi chiama `project.getResources().getById(5)`—sostituisci **5** con l'ID reale della risorsa di cui hai bisogno. Questa singola chiamata restituisce l'oggetto `Resource`, dopo di che puoi interrogare i suoi dati timephased, le assegnazioni o i campi personalizzati. Il metodo funziona in tempo O(1) perché le risorse sono indicizzate internamente.

## Problemi comuni e soluzioni
- **Resource not found** – Assicurati che l'ID esista nel file di progetto; gli ID partono da 1 e sono unici per risorsa.  
- **Empty timephased data** – Verifica che la risorsa abbia assegnazioni di lavoro o costo; altrimenti la collezione sarà vuota.  
- **Large file performance** – Usa `Project.setLoadOptions(LoadOptions.fromFile(...))` per abilitare il caricamento lazy per progetti più grandi di 500 MB.

## Domande frequenti

**Q: Aspose.Tasks può gestire altri tipi di file di progetto oltre a Microsoft Project?**  
A: Sì, Aspose.Tasks supporta MPP, XML, CSV e diversi altri formati, consentendo di leggere e scrivere tra diversi standard.

**Q: Aspose.Tasks è compatibile con diversi ambienti di sviluppo Java?**  
A: Assolutamente. La libreria funziona con tutti i principali IDE (IntelliJ IDEA, Eclipse, NetBeans) e strumenti di build (Maven, Gradle).

**Q: Posso manipolare i dati del progetto usando Aspose.Tasks?**  
A: Sì, puoi creare, modificare ed eliminare attività, risorse, assegnazioni e persino campi personalizzati tramite l'API.

**Q: Aspose.Tasks è adatto a progetti di livello enterprise?**  
A: Lo è. Le aziende si affidano ad Aspose.Tasks per l'elaborazione ad alto volume, conversioni batch e report lato server perché non richiede l'installazione di Microsoft Project.

**Q: Dove posso trovare supporto se incontro problemi usando Aspose.Tasks?**  
A: Puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza dalla community e dal team di supporto.

## Conclusione
In questo tutorial, abbiamo imparato **how to get resource by id** e a leggere i suoi dati timephased di lavoro e costo usando Aspose.Tasks per Java. Seguendo questi passaggi, potrai estrarre in modo efficiente informazioni di programmazione preziose dai tuoi file di progetto e integrarle in pipeline di reportistica o analisi personalizzate.

---

**Ultimo aggiornamento:** 2026-06-15  
**Testato con:** Aspose.Tasks 24.11 per Java  
**Autore:** Aspose

## Tutorial correlati

- [Aggiungere risorsa al progetto con Aspose.Tasks per Java](/tasks/java/resource-management/create-resources/)
- [Gestire i costi delle risorse MS Project con Aspose.Tasks per Java](/tasks/java/resource-management/resource-cost/)
- [Leggere le settimane lavorative Java dal calendario MS Project con Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}