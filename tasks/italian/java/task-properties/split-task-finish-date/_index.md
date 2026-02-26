---
date: 2026-02-26
description: Scopri come suddividere le date di fine attività e gestire le tempistiche
  del progetto usando Aspose.Tasks per Java. Questa guida mostra come suddividere
  le attività in modo efficiente.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gestire le tempistiche del progetto – Data di fine attività divisa in Aspose.Tasks
url: /it/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Data di fine attività divisa in Aspose.Tasks

## Introduzione
Gestire efficacemente **le tempistiche del progetto** è una pietra miliare per una consegna di successo. Quando la durata di un'attività cambia, la sua data di fine deve essere ricalcolata per mantenere il programma accurato. In questo tutorial ti mostreremo **come dividere le date di fine attività** con Aspose.Tasks per Java, fornendoti un controllo preciso sulla tempistica del tuo progetto.

## Risposte rapide
- **Che cosa ottieni dividendo la data di fine di un'attività?** Consente di calcolare la data di fine per qualsiasi durata, aiutandoti a regolare i programmi al volo.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (scaricabile dal sito ufficiale).  
- **Ho bisogno di una licenza per lo sviluppo?** Una licenza temporanea è sufficiente per i test; è necessaria una licenza completa per la produzione.  
- **Posso usarlo con qualsiasi calendario di progetto?** Sì, l'API utilizza il calendario del progetto per rispettare i giorni lavorativi e le festività.  
- **Quante righe di codice sono necessarie?** Meno di dieci righe per ottenere la data di fine per qualsiasi durata.

## Cos'è “gestire le tempistiche del progetto” nel contesto di Aspose.Tasks?
Gestire le tempistiche del progetto significa mantenere le date di inizio e fine di ogni attività sincronizzate con il programma complessivo, tenendo conto di calendari, risorse e dipendenze delle attività. Calcoli accurati della data di fine sono essenziali per proiezioni realistiche e per la fiducia degli stakeholder.

## Perché dividere la data di fine di un'attività?
- **Flessibilità:** Vedi rapidamente come diverse assegnazioni di ore di lavoro influenzano la consegna.  
- **Valutazione del rischio:** Valuta scenari “what‑if” senza modificare il piano originale.  
- **Pianificazione delle risorse:** Allinea le durate delle attività con la capacità del team e le restrizioni del calendario.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Tasks per Java installata. Puoi scaricarla [qui](https://releases.aspose.com/tasks/java/).  
- Un ambiente di sviluppo Java configurato.

## Importare i pacchetti
Inizia includendo i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.*;
```

## Passo 1: Trovare un'attività da dividere
Individua l'attività che desideri dividere all'interno del progetto:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Passo 2: Trovare il calendario del progetto
Recupera il calendario del progetto per calcoli accurati delle date:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Passo 3: Calcolare la data di fine dell'attività con durate diverse
Ora, calcola la data di fine dell'attività per varie durate.

### Passo 3.1: Durata di 8 ore
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*Ripeti il codice sopra per durate diverse, regolando le ore di conseguenza, per vedere come ogni modifica influisce sulla data di fine.*

## Problemi comuni e soluzioni
- **Riferimento al calendario errato:** Assicurati di recuperare il calendario del progetto (`project.get(Prj.CALENDAR)`) anziché crearne uno nuovo.  
- **UID attività errato:** L'UID deve corrispondere a un'attività esistente; altrimenti `getByUid` restituisce `null` e genera una `NullPointerException`.  
- **Mismatching dei fusi orari:** L'API utilizza il fuso orario del calendario; verifica il fuso predefinito del tuo sistema se i risultati sembrano errati.

## Conclusione
Padroneggiare l'arte di **gestire le tempistiche del progetto** dividendo le date di fine delle attività è fondamentale per una gestione efficace del progetto. Aspose.Tasks per Java semplifica questo processo, consentendoti di ottimizzare i tuoi programmi senza sforzo.

## FAQ
### Q1: Come posso scaricare Aspose.Tasks per Java?
A1: Puoi scaricarlo [qui](https://releases.aspose.com/tasks/java/).

### Q2: Dove posso trovare la documentazione per Aspose.Tasks?
A2: Consulta la documentazione [qui](https://reference.aspose.com/tasks/java/).

### Q3: Come posso ottenere una licenza temporanea per Aspose.Tasks?
A3: Ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Q4: Dove posso richiedere supporto per Aspose.Tasks?
A4: Visita il forum di supporto [qui](https://forum.aspose.com/c/tasks/15).

### Q5: Posso acquistare Aspose.Tasks?
A5: Sì, puoi acquistarlo [qui](https://purchase.aspose.com/buy).

## Domande frequenti aggiuntive

**Q: Posso usare questa tecnica con un calendario personalizzato?**  
A: Assolutamente. Basta sostituire `project.get(Prj.CALENDAR)` con la tua istanza personalizzata di `Calendar`.

**Q: Il metodo considera i giorni non lavorativi?**  
A: Sì, le definizioni di orario lavorativo del calendario vengono applicate al calcolo della data di fine.

**Q: Esiste un modo per recuperare la data di fine per ore frazionarie (es. 3,5 ore)?**  
A: Passa un valore `double` come `3.5d` a `getTaskFinishDateFromDuration`; l'API gestisce durate frazionarie.

**Q: Come formatto la data di output?**  
A: Usa `java.time.format.DateTimeFormatter` sull'oggetto `Date` restituito per visualizzarlo nel formato desiderato.

---

**Ultimo aggiornamento:** 2026-02-26  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}