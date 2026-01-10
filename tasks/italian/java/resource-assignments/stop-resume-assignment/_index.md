---
date: 2026-01-10
description: Scopri come interrompere l'assegnazione, gestire le assegnazioni delle
  risorse e visualizzare un esempio di assegnazione delle risorse in Aspose.Tasks
  per Java con questo tutorial passo passo.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come interrompere l'assegnazione e riprendere le assegnazioni delle risorse
  in Aspose.Tasks
url: /it/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come interrompere l'assegnazione e riprendere le assegnazioni delle risorse in Aspose.Tasks

## Introduction
In questo tutorial, **scoprirai come interrompere un'assegnazione** e successivamente riprenderla usando Aspose.Tasks per Java. Aspose.Tasks è una potente API Java che ti consente di leggere i formati di file di progetto Java, manipolare i dati di Microsoft Project e gestire le assegnazioni delle risorse senza avere Microsoft Project installato. Ti guideremo passo passo, spiegheremo perché ogni riga è importante e ti forniremo consigli pratici da applicare a progetti reali.

## Quick Answers
- **Cosa significa “interrompere l'assegnazione”?** Segna un'assegnazione di risorsa come temporaneamente inattiva a partire da una data di interruzione specifica.  
- **Posso riprendere la stessa assegnazione in seguito?** Sì, impostando una data di ripresa sulla stessa assegnazione.  
- **È necessario Microsoft Project per usare questa API?** No, Aspose.Tasks funziona indipendentemente da Microsoft Project.  
- **Quale versione di Java è richiesta?** Si consiglia Java 8 o superiore.  
- **Dove posso scaricare la libreria?** Dalla pagina ufficiale di download di Aspose.Tasks per Java.  

## What is “how to stop assignment” in the context of Aspose.Tasks?
Fermare un'assegnazione indica allo scheduler di ignorare il lavoro assegnato a una risorsa dopo la **data di interruzione** fino alla **data di ripresa** (se presente). Questo è utile per gestire vacanze, tempi di inattività delle attrezzature o qualsiasi periodo in cui una risorsa non dovrebbe essere considerata attiva.

## Why use Aspose.Tasks to manage resource assignments?
- **Nessuna necessità di Microsoft Project** – lavora direttamente con file .mpp.  
- **Controllo completo sulle date** – puoi verificare programmaticamente la data di interruzione, la data di ripresa e modificarle.  
- **Cross‑platform** – esegui su qualsiasi OS che supporta Java.  
- **API ricca** – fornisce un *esempio di assegnazione delle risorse* che puoi estendere per report personalizzati.  

## Prerequisites
- Java Development Kit (JDK) installato sul tuo sistema.  
- Libreria Aspose.Tasks per Java scaricata. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).  
- Conoscenza di base della programmazione Java.  

## Import Packages
Prima, importiamo i pacchetti necessari nel nostro progetto Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Step 1: Load the Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Qui **leggiamo il file di progetto Java** (`.mpp`) e creiamo un oggetto `Project` che ci dà accesso a tutti i dati del progetto, incluse le assegnazioni delle risorse.

## Step 2: Iterate Through Resource Assignments
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Impostiamo una **data minima** per filtrare le date segnaposto e poi iteriamo su ogni assegnazione. Questo è il tipico modello di *esempio di assegnazione delle risorse* usato quando è necessario ispezionare o modificare le assegnazioni.

## Step 3: Check Stop and Resume Dates
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

In questo blocco **verifichiamo la data di interruzione** e **la data di ripresa** per ogni assegnazione. Se la data è precedente al nostro `minDate`, la consideriamo non impostata (`"NA"`); altrimenti stampiamo la data reale. Questa logica è essenziale per **gestire correttamente le assegnazioni delle risorse**.

## Common Issues and Solutions
- **Date nulle** – `ra.get(Asn.STOP)` può restituire `null`. Proteggi il codice aggiungendo un controllo null prima di chiamare `.before(minDate)`.  
- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore di percorso (`/` o `\\`) appropriato per il tuo OS.  
- **Mancata corrispondenza di versione** – Usa l'ultima versione di Aspose.Tasks per Java per evitare valori enum mancanti.  

## FAQ's
### Can I use Aspose.Tasks without Microsoft Project installed?
Sì, Aspose.Tasks ti consente di lavorare con i file di Microsoft Project senza dover installare Microsoft Project sul tuo sistema.

### Where can I find more documentation?
Puoi trovare la documentazione dettagliata [qui](https://reference.aspose.com/tasks/java/).

### Is there a free trial available?
Sì, puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

### How can I get support if I encounter any issues?
Puoi ottenere supporto dalla community [qui](https://forum.aspose.com/c/tasks/15).

### Can I purchase a temporary license?
Sì, puoi acquistare una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: How do I programmatically set a stop date for an assignment?**  
A: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.  

**Q: What happens if the resume date is earlier than the stop date?**  
A: The API does not enforce chronological order; however, the scheduler will treat the assignment as active only after the later of the two dates, so you should validate dates yourself.  

**Q: Can I filter assignments to only those that have a stop date set?**  
A: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP) != null`.  

**Q: Is it possible to remove a stop date once set?**  
A: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save the project.  

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: Absolutely. The `Asn` enum provides constants for all assignment fields, such as `Asn.START`, `Asn.FINISH`, etc.  

## Conclusion
Seguendo questi passaggi ora sai **come interrompere l'assegnazione**, ispezionare le date di interruzione/ripresa e riprendere l'assegnazione quando necessario. Questa capacità ti consente di **gestire le assegnazioni delle risorse** in modo più preciso, soprattutto in scenari come vacanze delle risorse o tempi di inattività delle attrezzature. Sentiti libero di estendere l'esempio per aggiornare le date, generare report o integrare la logica con il tuo sistema di pianificazione.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}