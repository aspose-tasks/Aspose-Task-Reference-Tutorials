---
date: 2026-01-10
description: Impara come leggere la scala delle tariffe e gestire le assegnazioni
  delle risorse in Aspose.Tasks per Java. Definisci la risorsa materiale, come impostare
  la scala e assegnare le risorse al compito.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come leggere la scala di tariffa e scrivere la scala di tariffa per le assegnazioni
  delle risorse in Aspose.Tasks
url: /it/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere e scrivere la scala delle tariffe per le assegnazioni di risorse in Aspose.Tasks

In questo tutorial scoprirai **come leggere la scala delle tariffe** e regolarla per le assegnazioni di risorse utilizzando Aspose.Tasks per Java. Che tu stia creando un programmatore, uno strumento di reporting, o semplicemente abbia bisogno di automatizzare gli aggiornamenti di progetto, padroneggiare la manipolazione della scala delle tariffe ti offre un controllo dettagliato su risorse materiali e di lavoro.

## Risposte rapide
- **Qual è la classe principale per la gestione delle tariffe?** `ResourceAssignment` con la proprietà `Asn.RATE_SCALE`.  
- **Quale enum definisce le opzioni di scala?** `RateScaleType` (Day, Week, Month, ecc.).  
- **È necessaria una licenza per eseguire l'esempio?** Una licenza di valutazione gratuita funziona per i test; è richiesta una licenza commerciale per la produzione.  
- **Posso modificare la scala dopo il salvataggio?** Sì – ricarica il progetto e modifica `Asn.RATE_SCALE` come mostrato.  
- **IDE supportati?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans) può compilare il codice.

## Cos'è la scala delle tariffe?
La scala delle tariffe determina l'unità di tempo (giorno, settimana, mese, ecc.) a cui viene applicata la tariffa di costo di una risorsa. Regolare la scala consente di modellare con precisione il consumo di materiale o lo sforzo lavorativo.

## Perché leggere e scrivere la scala delle tariffe?
Leggere la scala attuale ti aiuta a verificare i programmi esistenti, mentre scrivere una nuova scala ti consente di allineare le risorse alle politiche di fatturazione o consumo del progetto. Questo è particolarmente utile quando **definisci le risorse materiali** o quando devi **impostare la scala** per calendari di lavoro non standard.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. **Ambiente di sviluppo Java** – JDK 8 o superiore installato.  
2. **Libreria Aspose.Tasks per Java** – Scarica e installa la libreria da [qui](https://releases.aspose.com/tasks/java/).

## Importare i pacchetti
Per prima cosa, importa le classi necessarie di Aspose.Tasks.

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

## Passo 1: Configura il tuo progetto Java
Crea un progetto Maven o Gradle e aggiungi il JAR di Aspose.Tasks al classpath. Questo passaggio garantisce che il compilatore possa trovare le classi importate.

## Passo 2: Carica il file di progetto
Carica il file Microsoft Project esistente con cui desideri lavorare.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Passo 3: Aggiungi un'attività
Crea una nuova attività che in seguito riceverà le assegnazioni di risorse.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Passo 4: Definisci le risorse
Qui **definiamo una risorsa materiale** e una risorsa di lavoro regolare. Nota l'uso di `ResourceType.Material` per la risorsa di tipo materiale.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Passo 5: Assegna le risorse all'attività
Ora **assegniamo le risorse all'attività** e specifichiamo **come impostare la scala** usando `RateScaleType.Week`. Questo illustra sia la lettura che la scrittura della scala delle tariffe.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Passo 6: Salva il progetto
Salva le modifiche in un nuovo file in modo da poter verificare in seguito la scala delle tariffe memorizzata.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Passo 7: Recupera le assegnazioni di risorse
Ricarica il progetto salvato e **leggi la scala delle tariffe** per confermare che sia stata scritta correttamente.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Problemi comuni e suggerimenti
- **Discrepanza UID** – Quando recuperi le assegnazioni per UID, assicurati che i valori UID corrispondano a quelli assegnati durante la creazione.  
- **Tipo di risorsa errato** – Usare `ResourceType.Material` per una risorsa di lavoro farà sì che i calcoli delle tariffe si comportino in modo inatteso.  
- **Formato di salvataggio** – Salva sempre usando `SaveFileFormat.Mpp` (o un altro formato supportato) per preservare campi personalizzati come la scala delle tariffe.

## Conclusione
Gestire e ispezionare la scala delle tariffe per le assegnazioni di risorse in Aspose.Tasks per Java è semplice una volta conosciute le classi e le proprietà pertinenti. Seguendo questa guida potrai **leggere le informazioni sulla tariffa**, **definire oggetti di risorsa materiale**, **impostare la scala** e **assegnare risorse all'attività** con fiducia.

## Domande frequenti

**Q: Posso usare Aspose.Tasks per Java con qualsiasi IDE Java?**  
**A:** Sì, Aspose.Tasks per Java è compatibile con tutti i principali IDE Java, inclusi IntelliJ IDEA, Eclipse e NetBeans.

**Q: Aspose.Tasks supporta altri formati di file oltre a MPP?**  
**A:** Sì, Aspose.Tasks supporta vari formati di file, inclusi MPP, XML e HTML.

**Q: Aspose.Tasks è adatto per la gestione di progetti a livello enterprise?**  
**A:** Assolutamente, Aspose.Tasks offre funzionalità complete per gestire progetti di qualsiasi dimensione, rendendolo adatto alla gestione di progetti a livello enterprise.

**Q: Posso personalizzare ulteriormente le assegnazioni di risorse oltre la scala delle tariffe?**  
**A:** Sì, Aspose.Tasks fornisce ampie capacità per personalizzare le assegnazioni di risorse, inclusi costi, lavoro e aggiustamenti di durata.

**Q: Esiste un forum della community per il supporto di Aspose.Tasks?**  
**A:** Sì, puoi trovare supporto e interagire con altri utenti sul forum di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-01-10  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}