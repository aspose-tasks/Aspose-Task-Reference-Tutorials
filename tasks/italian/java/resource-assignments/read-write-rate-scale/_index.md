---
date: 2026-06-10
description: Scopri come leggere rate e come scrivere rate scale per resource assignments
  utilizzando Aspose.Tasks per Java. Supporta risorse materiali, più formati e progetti
  di grandi dimensioni.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Leggi e scrivi Rate Scale per Resource Assignments in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come leggere Rate Scale e scrivere Rate Scale per Resource Assignments in Aspose.Tasks
url: /it/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere la scala delle tariffe e scrivere la scala delle tariffe per le assegnazioni di risorse in Aspose.Tasks

In questo tutorial scoprirai **come leggere le impostazioni della scala delle tariffe** e come regolarle per le assegnazioni di risorse usando Aspose.Tasks per Java. Che tu stia costruendo un pianificatore, uno strumento di reporting, o semplicemente abbia bisogno di automatizzare gli aggiornamenti di progetto, padroneggiare la manipolazione della scala delle tariffe ti dà un controllo dettagliato su risorse materiali e di lavoro.

## Risposte rapide
`ResourceAssignment` collega un'attività a una risorsa e contiene dati specifici dell'assegnazione.  
`Asn` contiene costanti per i campi dell'assegnazione, incluso `RATE_SCALE`.  
`RateScaleType` enum elenca le possibili unità di tempo per la scala delle tariffe.  

- **Qual è la classe principale per la gestione delle tariffe?** `ResourceAssignment` con la proprietà `Asn.RATE_SCALE`.  
- **Quale enum definisce le opzioni di scala?** `RateScaleType` (Day, Week, Month, ecc.).  
- **È necessaria una licenza per eseguire il campione?** Una licenza di valutazione gratuita funziona per i test; è richiesta una licenza commerciale per la produzione.  
- **Posso cambiare la scala dopo il salvataggio?** Sì – ricarica il progetto e modifica `Asn.RATE_SCALE` come mostrato.  
- **IDE supportati?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans) può compilare il codice.

## Come leggere la scala delle tariffe per le assegnazioni di risorse?

Carica il progetto, individua la `ResourceAssignment` desiderata e chiama `getRateScale()` – questo restituisce un valore `RateScaleType` che indica se la tariffa è applicata per giorno, settimana, mese o altra unità. La risposta è immediata e richiede solo due chiamate API, rendendola ideale per script di audit o visualizzazioni UI.

## Come scrivere la scala delle tariffe per le assegnazioni di risorse?

Crea o recupera un oggetto `ResourceAssignment`, imposta la sua proprietà `Asn.RATE_SCALE` al `RateScaleType` desiderato (ad esempio `RateScaleType.Week`), quindi salva il progetto. Questa singola modifica della proprietà aggiorna automaticamente i calcoli dei costi e persiste in tutti i formati di file supportati. Dopo aver impostato la scala, potresti dover anche regolare la tariffa standard o la tariffa per straordinario della risorsa per riflettere la nuova unità di tempo, garantendo che i calcoli dei costi rimangano accurati.

## Cos'è la scala delle tariffe?

La scala delle tariffe determina l'unità di tempo (giorno, settimana, mese, ecc.) a cui viene applicata la tariffa di costo di una risorsa. Modificare la scala consente di modellare con precisione il consumo di materiale o lo sforzo lavorativo. Per esempio, impostare la scala su Settimana significa che la tariffa di costo è interpretata come costo per settimana, e il costo totale per un'attività viene calcolato in base al numero di settimane in cui la risorsa è assegnata.

## Perché leggere e scrivere la scala delle tariffe?

Leggere la scala attuale ti aiuta a verificare i programmi esistenti, mentre scrivere una nuova scala ti consente di allineare le risorse alle politiche di fatturazione o consumo del progetto. Questo è particolarmente utile quando **si definiscono i costi delle risorse materiali** o quando è necessario **impostare la scala** per calendari di lavoro non standard.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. **Ambiente di sviluppo Java** – JDK 8 o superiore installato.  
2. **Libreria Aspose.Tasks per Java** – Scarica e installa la libreria da [qui](https://releases.aspose.com/tasks/java/).

## Importa i pacchetti
La classe `ResourceAssignment` rappresenta un collegamento tra un'attività e una risorsa, mentre `RateScaleType` enumera le possibili unità di tempo per una tariffa. Importa le classi necessarie di Aspose.Tasks prima di iniziare a programmare.  

`Project` è l'oggetto principale che carica e salva i file Microsoft Project.  
`Resource` definisce una risorsa di progetto come lavoro o materiale.  
`ResourceType` enum specifica se una risorsa è lavoro o materiale.  
`Task` rappresenta un elemento di lavoro nella pianificazione del progetto.  
`SaveFileFormat` enum definisce il formato di output per il salvataggio di un progetto.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Step 1: Configura il tuo progetto Java
Crea un progetto Maven o Gradle e aggiungi il JAR di Aspose.Tasks al tuo classpath. Questo passaggio assicura che il compilatore possa trovare le classi importate.

## Step 2: Carica il file di progetto
Carica il file Microsoft Project esistente con cui vuoi lavorare.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Step 3: Aggiungi un'attività
Crea una nuova attività che in seguito riceverà le assegnazioni di risorse.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Step 4: Definisci le risorse
Qui **definiamo una risorsa materiale** e una risorsa di lavoro regolare. Nota l'uso di `ResourceType.Material` per la risorsa di tipo materiale.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Step 5: Assegna le risorse all'attività
Ora **assegniamo le risorse all'attività** e specifichiamo **come impostare la scala** usando `RateScaleType.Week`. Questo illustra sia la lettura che la scrittura della scala delle tariffe.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Step 6: Salva il progetto
Persisti le modifiche in un nuovo file così potremo verificare in seguito la scala delle tariffe memorizzata.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Step 7: Recupera le assegnazioni di risorse
Ricarica il progetto salvato e **leggi la scala delle tariffe** per confermare che sia stata scritta correttamente.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Problemi comuni e consigli
- **Discrepanza UID** – Quando recuperi le assegnazioni per UID, assicurati che i valori UID corrispondano a quelli assegnati durante la creazione.  
- **Tipo di risorsa errato** – Usare `ResourceType.Material` per una risorsa di lavoro causerà calcoli di tariffa inaspettati.  
- **Formato di salvataggio** – Salva sempre usando `SaveFileFormat.Mpp` (o un altro formato supportato) per preservare campi personalizzati come la scala delle tariffe.  
- **Progetti di grandi dimensioni** – Aspose.Tasks può elaborare file con **500+ pagine** senza caricare l'intero documento in memoria, grazie alla sua architettura di streaming.

## Domande frequenti

**D: Posso usare Aspose.Tasks per Java con qualsiasi IDE Java?**  
R: Sì, Aspose.Tasks per Java è compatibile con tutti i principali IDE Java, inclusi IntelliJ IDEA, Eclipse e NetBeans.

**D: Aspose.Tasks supporta altri formati di file oltre a MPP?**  
R: Sì, Aspose.Tasks supporta vari formati di file, inclusi MPP, XML e HTML.

**D: Aspose.Tasks è adatto per la gestione di progetti a livello enterprise?**  
R: Assolutamente, Aspose.Tasks offre funzionalità complete per gestire progetti di qualsiasi scala, rendendolo adatto per la gestione di progetti a livello enterprise.

**D: Posso personalizzare ulteriormente le assegnazioni di risorse oltre la scala delle tariffe?**  
R: Sì, Aspose.Tasks fornisce ampie capacità per personalizzare le assegnazioni di risorse, inclusi costi, lavoro e aggiustamenti di durata.

**D: Esiste un forum della community per il supporto di Aspose.Tasks?**  
R: Sì, puoi trovare supporto e interagire con altri utenti sul forum di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-06-10  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose

## Tutorial correlati

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [How to Modify Assignments – Read Shared Resources with Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [How to Add Notes to Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}