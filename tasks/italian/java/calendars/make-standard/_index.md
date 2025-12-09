---
date: 2025-12-03
description: Scopri come creare un calendario in Java usando Aspose.Tasks. Questa
  guida passo‑passo ti mostra come creare un calendario standard di MS Project, aggiungere
  un calendario standard e utilizzare Aspose.Tasks in modo efficace.
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come creare un calendario – Creare un calendario standard in Aspose.Tasks
url: /it/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un calendario – Creare un calendario standard in Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come creare un calendario** oggetti per i file Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Ti guideremo nella creazione di un calendario standard di MS Project, nella sua impostazione come calendario predefinito (standard) e nel salvataggio del file di progetto. Alla fine della guida sarai in grado di integrare la creazione di calendari in qualsiasi soluzione di gestione progetti basata su Java.

## Risposte rapide
- **Cosa significa “calendario standard”?** È la definizione di orario di lavoro predefinita utilizzata dalle attività che non specificano un calendario personalizzato.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (la parte “come usare Aspose”).  
- **Ho bisogno di una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quale formato di file viene prodotto?** Un file Microsoft Project basato su XML (`.xml`).  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per un calendario di base.

## Cos'è un calendario standard in Microsoft Project?
Un **calendario standard** definisce i giorni e le ore di lavoro predefiniti per un progetto. Quando aggiungi un calendario standard, tutte le attività che non hanno un calendario specifico assegnato seguiranno il suo programma.

## Perché usare Aspose.Tasks per creare un calendario?
Aspose.Tasks fornisce un'API pure‑Java che consente di manipolare i file Project senza necessità di avere Microsoft Project installato. Questo lo rende ideale per l'automazione lato server, pipeline CI o qualsiasi applicazione Java che deve **creare oggetti calendario MS Project** programmaticamente.

## Prerequisiti
Prima di iniziare, assicurati che i seguenti elementi siano presenti:

### Installazione del Java Development Kit (JDK)
Installa l'ultima versione del JDK dal sito Oracle o da una distribuzione OpenJDK.

### Libreria Aspose.Tasks per Java
Scarica la libreria dalla [pagina di download](https://releases.aspose.com/tasks/java/). Aggiungi il JAR al classpath del tuo progetto.

## Importare i pacchetti
Per questo tutorial è necessario un solo import:

```java
import com.aspose.tasks.*;
```

## Guida passo‑passo

### Passo 1: Configurare la directory dei dati
Definisci dove verrà salvato il file di progetto generato.

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso assoluto sulla tua macchina (ad es., `C:/Projects/Output/`).

### Passo 2: Creare un'istanza di Project
Istanzia un nuovo oggetto Project vuoto che conterrà il calendario.

```java
Project project = new Project();
```

### Passo 3: Definire e impostare il calendario come standard
Aggiungi un nuovo calendario chiamato **“My Cal”** e promuovilo a calendario standard per il progetto.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Suggerimento:** Il metodo `makeStandardCalendar` segna automaticamente il calendario fornito come predefinito per il progetto, che è esattamente ciò di cui hai bisogno quando vuoi **aggiungere funzionalità di calendario standard**.

### Passo 4: Salvare il progetto
Salva il progetto (incluso il nuovo calendario) in un file XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Puoi cambiare il nome del file o il formato (`SaveFileFormat.Pp`) se preferisci una versione diversa di Project.

### Passo 5: Visualizzare il messaggio di completamento
Fornisci a te stesso un'indicazione visiva che il processo è terminato senza errori.

```java
System.out.println("Process completed Successfully");
```

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **File non trovato** | `dataDir` punta a una cartella inesistente | Crea la cartella o usa un percorso assoluto |
| **Eccezione di licenza** | Esecuzione senza una licenza Aspose.Tasks valida in produzione | Applica un file di licenza tramite `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Calendario vuoto** | Dimenticare di aggiungere le definizioni di orario di lavoro | Usa `cal1.getWeekDays().add(WeekDay.DayType.Monday)` ecc., se hai bisogno di ore personalizzate |

## Domande frequenti

**D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?**  
R: Sì, Aspose.Tasks supporta un'ampia gamma di versioni di Microsoft Project, dalla 2000 fino alle ultime release.

**D: Posso personalizzare ulteriormente le impostazioni del calendario?**  
R: Assolutamente! Puoi modificare i giorni lavorativi, aggiungere eccezioni e definire orari di lavoro specifici usando le classi `WeekDay` e `WorkingTime`.

**D: Aspose.Tasks è adatto per applicazioni a livello enterprise?**  
R: Certamente. La libreria è progettata per ambienti ad alte prestazioni e scalabili e offre supporto completo per file Project di grandi dimensioni.

**D: Aspose.Tasks offre supporto tecnico per gli sviluppatori?**  
R: Sì, Aspose fornisce forum dedicati, supporto basato su ticket e documentazione estesa per aiutarti a risolvere rapidamente eventuali problemi.

**D: Posso provare Aspose.Tasks prima di acquistare?**  
R: Sì, puoi provare una versione di prova gratuita disponibile sul [sito web](https://purchase.aspose.com/buy), che ti permette di valutare tutte le funzionalità prima di impegnarti.

## Conclusione
Ora sai **come creare un calendario** oggetti in Aspose.Tasks per Java, impostarli come calendario standard e salvare il file Project risultante. Questa funzionalità ti consente di automatizzare la pianificazione dei progetti, garantire orari di lavoro coerenti e integrare i dati di Microsoft Project direttamente nelle tue applicazioni Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2025-12-03  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

---