---
date: 2025-12-02
description: Scopri come aggiungere un calendario al progetto, come creare un calendario
  di MS Project e salvare il progetto come XML utilizzando Aspose.Tasks per Java.
language: it
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aggiungi calendario al progetto con Aspose.Tasks per Java
url: /java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere calendario al progetto con Aspose.Tasks per Java

## Introduzione
Nei moderni flussi di lavoro di gestione dei progetti, la possibilità di **add calendar to project** programmaticamente può far risparmiare ore di modifica manuale. Aspose.Tasks per Java offre agli sviluppatori un'API pulita e type‑safe per manipolare i file Microsoft Project senza mai aprire il client desktop. In questo tutorial imparerai **how to add calendar**, **how to create MS Project calendar**, e **save project as XML**—tutto con poche righe di codice Java.

## Risposte rapide
- **Cosa significa “add calendar to project”?**  
  Significa inserire una nuova definizione di tempo di lavoro (calendario) in un file Microsoft Project tramite codice.  
- **Quale libreria gestisce questo?**  
  Aspose.Tasks per Java fornisce la classe `Calendar` e il contenitore `Project` per gestire i calendari.  
- **Ho bisogno di una licenza?**  
  Una licenza di valutazione temporanea funziona per i test; è necessaria una licenza completa per l'uso in produzione.  
- **Posso salvare il file come XML?**  
  Sì—usa `SaveFileFormat.Xml` per esportare il progetto come file XML.  
- **Quali sono i prerequisiti?**  
  Java JDK 8+ e il JAR di Aspose.Tasks per Java nel tuo classpath.

## Cos'è “add calendar to project”?
Aggiungere un calendario a un progetto crea un programma personalizzato che definisce i giorni lavorativi, le festività e le ore di lavoro giornaliere. Questo calendario può quindi essere assegnato a attività, risorse o all'intero progetto, garantendo che i calcoli come le date di inizio e le durate rispettino il tempo di lavoro definito.

## Perché usare Aspose.Tasks per Java per add calendar to project?
- **Controllo completo** – Nessuna interfaccia UI richiesta; automatizza la creazione di calendari in blocco su molti progetti.  
- **Compatibilità cross‑versione** – Funziona con file Project 2007, 2010, 2013, 2016 e versioni successive.  
- **Nessuna installazione di Microsoft Project** – Esegui su qualsiasi server o pipeline CI.  
- **Flessibilità di esportazione** – Salva come XML, MPP o altri formati supportati.

## Prerequisiti
- **Java Development Kit (JDK) 8 o più recente** installato e configurato.  
- **Aspose.Tasks for Java** library – download from the [official website](https://releases.aspose.com/tasks/java/) and add the JAR to your project’s classpath.  
- Un IDE o uno strumento di build (Maven/Gradle) a tua scelta.

## Guida passo‑a‑passo

### Passo 1: Importa il pacchetto Aspose.Tasks richiesto
Per prima cosa, porta le classi Aspose.Tasks nello scope in modo da poter lavorare con progetti e calendari.

```java
import com.aspose.tasks.*;
```

### Passo 2: Imposta il percorso della directory dei dati
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

### Passo 5: Salva il progetto (save project as XML)
Persisti il progetto, inclusi i calendari appena aggiunti, in un file XML. Questo formato è facile da ispezionare e compatibile con molti strumenti.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Passo 6: Visualizza un messaggio di completamento
Fai sapere all'utente che l'operazione è terminata con successo.

```java
System.out.println("Process completed Successfully");
```

Seguendo questi sei passaggi concisi, hai aggiunto con successo **added a calendar to a project** e salvato il risultato come file XML.

## Problemi comuni e soluzioni
| Problema | Motivo | Risoluzione |
|----------|--------|-------------|
| **`NullPointerException` on `prj.getCalendars()`** | Oggetto Project non inizializzato correttamente. | Assicurati che `new Project()` sia chiamato prima di accedere ai calendari. |
| **File not found when saving** | `dataDir` punta a una cartella inesistente. | Crea prima la directory o usa un percorso assoluto. |
| **Calendar name appears as “no info”** | Sono stati usati nomi segnaposto nel campione. | Sostituiscili con nomi significativi che riflettano il programma (ad es., “US Holiday Calendar”). |
| **Saved XML cannot be opened in MS Project** | Uso di una versione obsoleta di Aspose.Tasks. | Aggiorna all'ultima versione di Aspose.Tasks per Java. |

## Domande frequenti

**Q: Aspose.Tasks può gestire calendari complessi con più eccezioni?**  
A: Sì – dopo aver aggiunto un calendario puoi definire eccezioni, ore lavorative e giorni non lavorativi usando le classi `WeekDay` e `Exception`.

**Q: È possibile assegnare il nuovo calendario a task specifici?**  
A: Assolutamente. Recupera un task tramite `prj.getRootTask().getChildren().add("Task Name")` e imposta `task.set(Tsk.CALENDAR, cal3);`.

**Q: La libreria supporta il salvataggio in altri formati come MPP?**  
A: Sì. Sostituisci `SaveFileFormat.Xml` con `SaveFileFormat.Mpp` o `SaveFileFormat.P6` secondo necessità.

**Q: Ho bisogno di una licenza per le build di sviluppo?**  
A: Una licenza di valutazione temporanea è sufficiente per i test; è necessaria una licenza completa per le distribuzioni in produzione.

**Q: Dove posso ottenere aiuto se incontro problemi?**  
A: Il forum della community di Aspose.Tasks è una risorsa eccellente: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusione
Utilizzando Aspose.Tasks per Java, puoi programmaticamente **add calendar to project**, personalizzare le regole di pianificazione e **save project as XML** con poche righe di codice. Questa automazione riduce lo sforzo manuale, elimina gli errori umani e consente l'elaborazione batch di grandi portafogli di progetti.

---

**Ultimo aggiornamento:** 2025-12-02  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}