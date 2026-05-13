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

## Introduzione
In questo tutorial, **scoprirai come interrompere un'assegnazione** e successivamente riprenderla utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente API Java che ti consente di leggere i formati di file di progetto Java, manipolare i dati di Microsoft Project e gestire le assegnazioni delle risorse senza avere Microsoft Project installato. Ti guideremo passo passo, spiegheremo perché ogni riga è importante e ti forniremo consigli pratici da applicare a progetti reali.

## Risposte rapide
- **Cosa significa “interrompere l'assegnazione”?** Segna un'assegnazione di risorsa come temporaneamente inattiva a partire da una data di interruzione specifica.
- **Posso riprendere la stessa assegnazione in seguito?** Sì, impostando una data di ripresa sulla stessa assegnazione.
- **È necessario Microsoft Project per usare questa API?** No, Aspose.Tasks funziona indipendentemente da Microsoft Project.
- **Quale versione di Java è richiesta?** Si consiglia Java8 o superiore.
- **Dove posso scaricare la libreria?** Dalla pagina ufficiale di download di Aspose.Tasks per Java.

## Cos'è "come interrompere l'assegnazione" nel contesto di Aspose.Tasks?
Fermare un'assegnazione indica allo scheduler di ignorare il lavoro assegnato a una risorsa dopo la **data di interruzione** fino alla **data di ripresa** (se presente). Questo è utile per gestire le vacanze, i tempi di inattività delle attrezzature o qualsiasi periodo in cui una risorsa non dovrebbe essere considerata attiva.

## Perché utilizzare Aspose.Tasks per gestire le assegnazioni delle risorse?
- **Nessuna necessità di Microsoft Project** – lavora direttamente con file .mpp.
- **Controllo completo sulle date** – puoi verificare programmaticamente la data di interruzione, la data di ripresa e modificarle.
- **Cross‑platform** – esegui su qualsiasi sistema operativo che supporti Java.
- **API ricca** – fornisce un *esempio di assegnazione delle risorse* che puoi estendere per report personalizzati.

## Prerequisiti
- Java Development Kit (JDK) installato sul tuo sistema.
- Libreria Aspose.Tasks per Java scaricata. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).
- Conoscenza di base della programmazione Java.

## Importa pacchetti
Prima, importiamo i pacchetti necessari nel nostro progetto Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Fase 1: Caricare il file di progetto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Qui **leggiamo il file di progetto Java** (`.mpp`) e creiamo un oggetto `Project` che ci dà accesso a tutti i dati del progetto, incluse le assegnazioni delle risorse.

## Fase 2: Iterare sulle assegnazioni delle risorse
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Impostiamo una **data minima** per filtrare le date segnaposto e poi iteriamo su ogni assegnazione. Questo è il tipico modello di *esempio di assegnazione delle risorse* usato quando è necessario ispezionare o modificare le assegnazioni.

## Fase 3: Verificare le date di interruzione e ripresa
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

## Problemi e soluzioni comuni
- **Data nulla** – `ra.get(Asn.STOP)` può restituire `null`. Proteggi il codice aggiungendo un controllo null prima di chiamare `.before(minDate)`.
- **Percorso file errato** – Assicurati che `dataDir` termini con un separatore di percorso (`/` o `\\`) appropriato per il tuo sistema operativo.
- **Mancata corrispondenza della versione** – Usa l'ultima versione di Aspose.Tasks per Java per evitare valori enum mancanti.

## Domande frequenti

**D: Come faccio a impostare a livello di codice una data di fine per un compito?**
R: Utilizza `ra.set(Asn.STOP, yourDateObject);` dove `yourDateObject` è un `java.util.Date`.

**D: Cosa succede se la data di ripresa è precedente alla data di fine?**
R: L'API non impone l'ordine cronologico; Tuttavia, lo scheduler considererà l'assegnazione attiva solo dopo la data più recente tra le due, quindi è necessario verificare manualmente le date.

**D: Posso filtrare le assegnazioni per visualizzare solo quelle con una data di fine impostata?**
R: Sì, scorri `prj.getResourceAssignments()` e verifica che `ra.get(Asn.STOP) != null`.

**D: È possibile rimuovere una data di fine una volta impostata?**
R: Imposta la data di fine su `null` con `ra.set(Asn.STOP, null);` e poi salva il progetto.

**D: Aspose.Tasks supporta altri campi relativi alle date, come inizio, fine o data di inizio effettiva?**
R: Assolutamente sì. L'enumerazione "Asn" fornisce costanti per tutti i campi di assegnazione, come "Asn.START", "Asn.FINISH", ecc.

## Conclusione
Seguendo questi passaggi ora sai **come interrompere l'assegnazione**, ispezionare le date di interruzione/ripresa e riprendere l'assegnazione quando necessario. Questa capacità ti consente di **gestire le assegnazioni delle risorse** nel modo più preciso, soprattutto in scenari come vacanze delle risorse o tempi di inattività delle attrezzature. Sentiti libero di estendere l'esempio per aggiornare le date, generare report o integrare la logica con il tuo sistema di pianificazione.

---

**Ultimo aggiornamento:** 2026-01-10
**Testato con:** Aspose.Tasks per Java 24.12
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}