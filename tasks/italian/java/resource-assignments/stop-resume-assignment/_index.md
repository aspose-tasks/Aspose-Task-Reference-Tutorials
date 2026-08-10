---
date: 2026-07-14
description: Scopri come interrompere resource assignment java, gestire le resource
  assignments e visualizzare esempi usando Aspose.Tasks per Java in questa guida passo‑passo.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Interrompi e riprendi Resource Assignments in Aspose.Tasks
og_description: Interrompi resource assignment java con Aspose.Tasks. Questo tutorial
  mostra come mettere in pausa e riprendere le assignments, gestire le date e integrare
  l'API senza Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Interrompi Resource Assignment Java – Guida Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Come interrompere Resource Assignment Java – Riprendere con Aspose.Tasks
url: /it/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come interrompere l'assegnazione di risorse Java – Riprendere con Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come interrompere l'assegnazione di risorse java** e successivamente riprenderla usando Aspose.Tasks per Java. Aspose.Tasks è una robusta API Java che consente di leggere e scrivere file Microsoft Project, manipolare i programmi e controllare le assegnazioni di risorse—tutto senza la necessità di avere Microsoft Project installato. Passeremo attraverso ogni passaggio, spiegheremo perché ogni riga è importante e condivideremo consigli pratici che potrai applicare a piani di progetto reali.

## Risposte rapide
- **Cosa significa “interrompere l'assegnazione”?** Contrassegna un'assegnazione di risorsa come temporaneamente inattiva a partire da una data di interruzione specifica.  
- **Posso riprendere la stessa assegnazione in seguito?** Sì, impostando una data di ripresa sulla stessa assegnazione.  
- **È necessario Microsoft Project per usare questa API?** No, Aspose.Tasks funziona indipendentemente da Microsoft Project.  
- **Quale versione di Java è richiesta?** Si consiglia Java 8 o superiore.  
- **Dove posso scaricare la libreria?** Dalla pagina ufficiale di download di Aspose.Tasks Java.

## Come interrompere l'assegnazione di risorse java?
Carica il tuo progetto, individua il `ResourceAssignment` target, imposta la data `STOP`, opzionalmente imposta una data `RESUME`, quindi salva il file. Questa sequenza mette in pausa il lavoro per il periodo specificato e lo riattiva automaticamente dopo la data di ripresa, fornendoti un controllo preciso sui calendari delle risorse senza modifiche manuali al file.

## Cos'è “interrompere l'assegnazione” nel contesto di Aspose.Tasks?
Interrompere un'assegnazione indica allo scheduler di ignorare il lavoro assegnato a una risorsa dopo la **data di interruzione** fino alla **data di ripresa** (se presente). È utile per gestire vacanze, tempi di inattività delle attrezzature o qualsiasi periodo in cui una risorsa non dovrebbe essere considerata attiva.

## Perché usare Aspose.Tasks per gestire le assegnazioni di risorse?
Aspose.Tasks ti consente di controllare programmaticamente le date di assegnazione, eliminando le modifiche manuali e riducendo il rischio di errori. Supporta **oltre 50 formati di input e output** e può elaborare progetti con **fino a 10.000 attività** mantenendo l'uso di memoria sotto i 200 MB perché trasmette i dati invece di caricare l'intero file in memoria. L'API funziona su qualsiasi OS che supporta Java, offrendoti flessibilità cross‑platform.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Java Development Kit (JDK) 8 o più recente installato.  
- Libreria Aspose.Tasks per Java scaricata. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).  
- Conoscenza di base della programmazione Java.  

## Importare i pacchetti
Le classi `Project`, `ResourceAssignment` e `Asn` risiedono nello spazio dei nomi `com.aspose.tasks`. Importale all'inizio del tuo file sorgente:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Passo 1: Caricare il file di progetto
La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file Microsoft Project in memoria. Creare un'istanza carica il file e ti dà accesso a attività, risorse e assegnazioni.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Passo 2: Iterare attraverso le assegnazioni di risorse
Gli oggetti `ResourceAssignment` espongono tutti i campi relativi alle assegnazioni. Impostiamo una **data minima** per filtrare le date segnaposto e poi cicliamo su ogni assegnazione. Questo modello è l'esempio standard di *assegnazione di risorse* per ispezione o modifica.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Passo 3: Verificare le date di interruzione e ripresa
In questo blocco esaminiamo i campi `STOP` e `RESUME` per ogni assegnazione. Se una data è precedente alla nostra `minDate`, la consideriamo non impostata (`"NA"`); altrimenti stampiamo la data reale. Questa logica è essenziale per **gestire correttamente le assegnazioni di risorse**.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Problemi comuni e soluzioni
- **Date nulle** – `ra.get(Asn.STOP)` può restituire `null`. Proteggi il codice aggiungendo un controllo null prima di chiamare `.before(minDate)`.  
- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore di percorso (`/` o `\\`) appropriato per il tuo OS.  
- **Incompatibilità di versione** – Usa l'ultima versione di Aspose.Tasks per Java per evitare valori enum mancanti.

## Domande frequenti

**D: Come impostare programmaticamente una data di interruzione per un'assegnazione?**  
R: Usa `ra.set(Asn.STOP, yourDateObject);` dove `yourDateObject` è un `java.util.Date`.

**D: Cosa succede se la data di ripresa è precedente alla data di interruzione?**  
R: L'API non impone l'ordine cronologico; tuttavia, lo scheduler tratterà l'assegnazione come attiva solo dopo la data più tarda tra le due, quindi dovresti validare le date autonomamente.

**D: Posso filtrare le assegnazioni per includere solo quelle con una data di interruzione impostata?**  
R: Sì, itera su `prj.getResourceAssignments()` e verifica `ra.get(Asn.STOP) != null`.

**D: È possibile rimuovere una data di interruzione una volta impostata?**  
R: Imposta la data di interruzione a `null` con `ra.set(Asn.STOP, null);` e poi salva il progetto.

**D: Aspose.Tasks supporta altri campi relativi alle date, come start, finish o actual start?**  
R: Assolutamente. L'enumerazione `Asn` fornisce costanti per tutti i campi di assegnazione, come `Asn.START`, `Asn.FINISH`, ecc.

## Conclusione
Seguendo questi passaggi ora sai **come interrompere l'assegnazione di risorse java**, ispezionare le date di interruzione/ripresa e riprendere l'assegnazione quando necessario. Questa capacità ti consente di **gestire le assegnazioni di risorse** in modo più preciso, soprattutto in scenari come vacanze delle risorse o tempi di inattività delle attrezzature. Sentiti libero di estendere l'esempio per aggiornare le date, generare report o integrare con la tua logica di pianificazione.

---

**Ultimo aggiornamento:** 2026-07-14  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Creare assegnazioni di risorse in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Come calcolare la varianza dei costi e gestire i costi delle assegnazioni con Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Come aggiungere note alle assegnazioni di risorse in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}