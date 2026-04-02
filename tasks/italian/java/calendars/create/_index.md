---
date: 2026-01-31
description: Impara come creare il calendario del progetto, aggiungere il calendario
  delle festività ed esportare l'XML del progetto usando Aspose.Tasks per Java.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come creare un calendario di progetto con Aspose.Tasks per Java
url: /it/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un calendario di progetto con Aspose.Tasks per Java

## Introduzione
Nei moderni flussi di lavoro di gestione dei progetti, la possibilità di **creare un calendario di progetto** programmaticamente può far risparmiare ore di modifica manuale. Aspose.Tasks per Java offre agli sviluppatori un'API pulita e type‑safe per manipolare i file Microsoft Project senza mai aprire il client desktop. In questo tutorial imparerai **come aggiungere un calendario**, **come creare un calendario MS Project** e **esportare il progetto XML** — il tutto con poche righe di codice Java.

## Risposte rapide
- **C generare una nuova definizione di orario di lavoroQuale libreria gestisce questo?**  
  Aspose.Tasks per Java fornisce la classe `Calendar` e il contenitore `Project` per gestire i calendari.  
- **Ho bisogno di una licenza?**  
  Una licenza di valutazione temporanea funziona per i test; è necessaria una licenzaPosso esportare il file come XML?**are il progetto come file XML.  
- **Quali sono i prerequisiti?**  
  Java JDK 8+ e il JAR di Aspose.Tasks per Java nel calendario di progetto”?
Creare un calendario di progetto definisce i giorni lavorativinaliere per un progetto. Una volta che il calendario è associato a task, risorse o all'intero progetto, tutti i calcoli di pianificazione rispettano il tempo di lavoro definito.

## Perché utilizzare Aspose.Tasks per Java per creare un calendario di progetto?
- **Controllo totale** – Automatizza la creazione di massa di calendari su molti progetti senza un'interfaccia utente.  
- **Compatibilità cross‑versione** – Funziona con file Project 2007, 2010, 2013, 201 installazione di Microsoft Project** – Esegui su qualsiasi server o pipeline CI.  
- **Flessibilità di esportazione** – Salva come XML, MPP o altri formati supportati.  

## Prerequisiti
- **Java Development Kit (JDK) 8 o superiore** installato e configurato.  
- **Libreria Aspose.Tasks per Java** – scarica dal [sito ufficiale](https://releases.aspose.com/tasks/java/) e aggiungi il JAR al classpath del tuo progetto.  
- Un IDE o uno strumento di build (Maven/Gradle) a tua scelta.

## Guida passo‑passo

### Passo 1: Importa il pacchetto Aspose.Tasks richiesto
Per prima cosa, porta le classi di.

```java
import com.aspose.tasks.*;
```

### Passo 2: Imposta il
Definisci dove verrà scritto il file di progetto generato. Sostituisci il segnaposto con un percorso assoluto o relativo sulla tua macchina.

```java
String dataDir = "Your Data Directory";
```

### Passo 3: Crea una nuova istanza di Project
Istanzia un oggetto `Project` – rappresenta un file Microsoft Project vuoto che puoi popolare.

```java
Project prj = new Project();
```

### Passo 4: Definisci i calendari da aggiungere
Usa il metodo `Calendars.add(String name)` per creare nuove voci di calendario. In questo esempio aggiungiamo tre calendari, ma puoi aggiungerne quanti ne servono e configurare i loro orari di lavoro in seguito.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Suggerimento professionale:** Dopo aver aggiunto un calendario, puoi personalizzare i suoi giorni lavorativi con `cal1.getWeekDays().add(...)` e impostare le ore di lavoro giornaliere usando `cal1.getBaseCalendar().setWorkingTime(...)`.

### Passo 5: Salva il progetto (esporta il progetto XML)
Persisti il progetto, inclusi i calendari appena aggiunti, in un file XML. Questo formato è facile da ispezionare e compatibile con molti strumenti.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Passo 6: Visualizza un messaggio di completamento
Fai sapere all'utente che l'operazione è terminata con successo.

```java
System.out.println("Process completed Successfully");
```

Seguendo questi sei passaggi concisi, hai **creato con successo un calendario di progetto**, lo hai aggiunto a un file Microsoft Project e **esportato il progetto come XML**.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`NullPointerException` on `prj.getCalendars()`** | L'oggetto Project non è stato inizializzato correttamente. | Assicurati che `new Project()` sia chiamato prima di accedere ai calendDir` punta a una cartella inesistente. | Crea prima la directory o usa un percorso assoluto. |
| **Calendar name appears as “no info”** | Sono stati usati nomi segnaposto nel campione. | Sostituiscili con nomi significativi che riflettano il programma ( be opened in MS Project** | Uso di una versione obsoleta di Aspose.Tasks. | Aggiorna all'ultima versione di Aspose.Tasks per Java. |

## Domande frequenti

**D: Aspose.Tasks può gestire calendari complessi con più eccezioni?**  
R: Sì — dopo aver aggiunto un calendario puoi definire eccezioni, ore lavorative e giorni non lavorativi usando le classi `WeekDay` e `Exception`.

**D: È possibile assegnare il nuovo calendario a task specific task tramite `prj.getRootTask().getChildren().add("Task Name")` e imposta `task.set(Tsk.CALENDAR, cal3);`.

**D: La libreria supporta il salvataggio in altri formati come MPP?**  
R: Sì. Sostituisci `SaveFileFormat.Xml` con `SaveFileFormat.Mpp` o `SaveFileFormat.P6` secondo necessità.

**D: Ho bisogno di una licenza per le build di sviluppo?**  
R: Una licenza di valutazione temporanea è sufficiente per i test; è necessaria una licenza completa per le distribuzioni in produzione: Il forum della community di Aspose.Tasks è una risorsa eccellente: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusione
Utilizzando Aspose.Tasks per Java, puoi programmare la **creazione di un calendario di progetto**, personalizzare le regole di pianificazione e **esportare il progetto XML** con poche righe di codice. Questa automazione riduce lo sforzo manuale, elimina gli errori umani e consente l'elaborazione batch di grandi portafogli di progetti.

---

**Ultimo aggiornamento:** 2026-01-31  
**Testato con:** Aspose.Tasks for Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}