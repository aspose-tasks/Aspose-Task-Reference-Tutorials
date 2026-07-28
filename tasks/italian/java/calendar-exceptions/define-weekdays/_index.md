---
date: 2026-01-28
description: Scopri come creare un calendario di progetto con Aspose, definire i giorni
  della settimana per le eccezioni del calendario e gestire un programma di giorni
  non lavorativi usando Aspose.Tasks per Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Crea calendario progetto Aspose – Definisci i giorni della settimana per le
  eccezioni del calendario
url: /it/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Calendario di Progetto Aspose – Definisci i Giorni della Settimana per le Eccezioni del Calendario

### Introduzione
Quando devi **creare project calendar aspose**, devi essere in grado di modellare giorni lavorativi non standard come festività, turni speciali o chiusure temporanee. Aspose.Tasks per Java ti offre il pieno controllo sulle definizioni del calendario, consentendoti di aggiungere eccezioni che riflettono orari reali. In questo tutorial percorreremo passo passo le istruzioni per definire i giorni della settimana per le eccezioni del calendario, così le tempistiche del tuo progetto rimarranno accurate e affidabili. Alla fine vedrai anche come questo si inserisce in una più ampia strategia di **programmazione dei giorni non lavorativi** per qualsiasi progetto aziendale.

##Risposte Rapide
- **Cosa significa "crea calendario progetto aspose"?** 
Si riferisce all'uso di Aspose.Tasks per creare un oggetto calendario personalizzato che guida la pianificazione delle attività.
- **Ho bisogno di una licenza per eseguire il campione?** 
Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.
- **Quali IDE sono supportati?** 
IntelliJ IDEA, Eclipse, NetBeans o qualsiasi IDE che supporti Java8+.
- **Posso aggiungere più eccezioni allo stesso calendario?** 
Sì – è possibile aggiungere quanti oggetti `CalendarException` servono.
- **In quali formati di file posso salvare il progetto?** 
XML, MPP e diversi altri formati supportati da Aspose.Tasks.

## Che cos'è un Calendario di Progetto in Aspose.Tasks?
Un **project calendar** definisce i giorni e le ore lavorative per un progetto. Influenza le date di inizio/fine delle attività, l'allocazione delle risorse e i calcoli complessivi del programma. Personalizzando un calendario, garantisci che la pianificazione rispetti i vincoli reali come le festività aziendali o le politiche di lavoro nei fine settimana.

## Perché definire i giorni della settimana per le eccezioni del calendario?
- **Tempistiche accurate:** le attività non verranno programmate nei giorni contrassegnati come non lavorativi.
- **Pianificazione delle risorse:** le risorse vengono assegnate solo nei giorni lavorativi validi.
- **Conformità:** allinea i programmi di progetto alle politiche organizzative o alle festività legali.

## Programma dei Giorni Non Lavorativi con Eccezioni del Calendario
Quando gestisci un **programma dei giorni non lavorativi**, di solito disponi di un elenco master di festività, finestre di manutenzione o altri periodi di blackout. Aggiungere queste date come oggetti `CalendarException` garantisce che ogni calcolo — sia esso analisi del percorso critico o livellamento delle risorse — rispettivi automaticamente tali vincoli. Questo approccio elimina le regolazioni manuali delle date e riduce il rischio di deviazioni nella pianificazione.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 e successiva.
2. **Aspose.Tasks per Java** – scaricalo dalla pagina ufficiale di [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).
3. **Un IDE** – IntelliJ IDEA, Eclipse, NetBeans o qualsiasi editor compatibile con Java.

## Come creare il calendario del progetto aspose – Definisci i giorni della settimana per le eccezioni del calendario

### Guida Passo‑Passo

### Passaggio 1: Importa i pacchetti necessari
Abbiamo bisogno delle classi principali di Aspose.Tasks e di `GregorianCalendar` di Java per la gestione delle date.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Passaggio 2: Definisci la directory dei dati
Specifica dove verrà salvato il file di progetto generato.

```java
String dataDir = "Your Data Directory";
```

### Passaggio 3: Crea un'istanza del progetto
Istanzia un nuovo oggetto `Project` – è il contenitore di tutti i dati del progetto, inclusi i calendari.

```java
Project project = new Project();
```

### Passaggio 4: Definisci un calendario
Aggiungi un calendario personalizzato al progetto. Questo calendario conterrà le nostre eccezioni.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Passaggio 5: Definisci l'eccezione per i giorni feriali
Crea un `CalendarException` che contrassegna un intervallo di giorni (ad esempio l'ultima settimana di dicembre) come non lavorativo.  
L'esempio imposta l'eccezione dal **24 Dic 2009** al **31 Dic 2009**, disabilita il lavoro per quei giorni e tratta l'eccezione come di tipo giornaliero.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Passaggio 6: Salva il progetto
Salva il progetto, includendo il calendario personalizzato e la sua eccezione, in un file XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Date di eccezione non applicate** | Assicurati di impostare `setEnteredByOccurrences(false)` e i valori corretti di `FromDate/ToDate`. |
| **Il file salvato è vuoto** | Verifica che `dataDir` punti su una cartella scrivibile e che il nome del file termini con `.xml`. |
| **Calendario non riflesso nella pianificazione delle attività** | Assegnare il calendario ad attività o risorse utilizzando `task.setCalendar(cal)` o `resource.setCalendar(cal)`. |

##Domande Frequenti

**D: Posso definire più eccezioni per diversi giorni della settimana nello stesso calendario?**
R: Sì. Aggiungi ulteriori oggetti `CalendarException` a `cal.getExceptions()` per ogni periodo o regola distinta.

**D: Aspose.Tasks per Java è compatibile con diversi IDE Java?**
R: Assolutamente. La libreria funziona con IntelliJ IDEA, Eclipse, NetBeans e qualsiasi IDE che supporti progetti Java standard.

**D: Posso personalizzare tipi di eccezione diversi dalle eccezioni giornaliere?**
R: Sì. Usa `CalendarExceptionType.Weekly`, `Monthly` o `Yearly` per soddisfare le tue esigenze di pianificazione.

**D: Come posso gestire le eccezioni in modo dinamico in base ai requisiti del progetto?**
R: Costruisci gli oggetti eccezione programmaticamente — ad esempio, leggi le date delle festività da un database o file di configurazione e crea istanze `CalendarException` in un ciclo.

**D: È disponibile una versione di prova di Aspose.Tasks per Java?**
R: Sì, puoi scaricare una prova gratuita dalla [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusione
Seguendo questi passaggi ora sai come **creare calendario progetto aspose** e definire le eccezioni dei giorni della settimana che riflettono accuratamente festività o periodi speciali non lavorativi. Una corretta configurazione del calendario è essenziale per programmi realistici, allocazione delle risorse e successo complessivo del progetto. Esplora ulteriormente collegando il calendario personalizzato a attività o risorse e sperimentando altri tipi di eccezione per costruire un **programma dei giorni non lavorativi** completo per qualsiasi progetto.

---

**Ultimo aggiornamento:** 28-01-2026
**Testato con:** Aspose.Tasks per Java 24.11
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}