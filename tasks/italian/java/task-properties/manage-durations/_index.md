---
date: 2026-02-20
description: Scopri come aggiungere un'attività a un progetto e gestire le durate
  con Aspose.Tasks per Java. Impara come impostare la durata e come convertirla facilmente.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aggiungi attività al progetto e gestisci le durate con Aspose.Tasks
url: /it/java/task-properties/manage-durations/
weight: 20
---

 produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un'attività al progetto e gestire le durate con Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come aggiungere un'attività a un progetto** e controllarne la durata usando Aspose.Tasks per Java. Che tu stia creando un nuovo strumento di pianificazione dei progetti o estendendo una soluzione esistente, padroneggiare la gestione della durata delle attività è essenziale per una programmazione e una reportistica accurate.

## Risposte rapide
- **Che cosa significa “add task to project”?** Crea un nuovo oggetto Task sotto la radice del progetto o sotto un task riepilogativo specifico.  
- **Quale classe rappresenta una durata?** `com.aspose.tasks.Duration`.  
- **Come impostare la durata?** Usa `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Posso convertire una durata in un'altra unità?** Sì, chiama `duration.convert(TimeUnitType.Hour)` o qualsiasi altro `TimeUnitType`.  
- **Ho bisogno di una licenza per la produzione?** È necessaria una licenza valida di Aspose.Tasks per l'uso commerciale.

## Che cos'è “add task to project”?
Aggiungere un'attività a un progetto significa creare un oggetto `Task` e collegarlo alla gerarchia delle attività del progetto. Questa operazione è il primo passo prima di poter definire lavoro, risorse o durata per quell'attività.

## Perché gestire le durate delle attività?
Durate accurate guidano tempistiche realistiche, allocazione delle risorse e analisi del percorso critico. Con Aspose.Tasks puoi impostare, leggere, convertire e regolare le durate programmaticamente, dandoti il pieno controllo sui calendari di progetto.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Java Development Kit (JDK): Assicurati di avere Java installato sulla tua macchina. Puoi scaricarlo [qui](https://www.oracle.com/java/technologies/javase-downloads.html).
- Libreria Aspose.Tasks: Scarica e includi la libreria Aspose.Tasks nel tuo progetto. Puoi trovare la libreria [qui](https://releases.aspose.com/tasks/java/).

## Importare i pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per lavorare con Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Passo 1: Configura il tuo progetto
```java
// Create a new project
Project project = new Project();
```

## Passo 2: Aggiungi una nuova attività (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Come impostare la durata
Ora che l'attività esiste, puoi definirne la lunghezza. Per impostazione predefinita, le durate sono espresse in giorni.

## Passo 3: Ottieni e converti la durata dell'attività
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Come convertire la durata
Il metodo `convert` ti consente di tradurre una `Duration` da un `TimeUnitType` a un altro (ad esempio, giorni → ore, settimane → giorni).

## Passo 4: Aggiorna la durata dell'attività a 1 settimana
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Passo 5: Riduci la durata dell'attività
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Seguendo questi passaggi, hai **aggiunto con successo un'attività a un progetto** e gestito la sua durata usando Aspose.Tasks per Java.

## Problemi comuni e consigli
- **Problema:** Dimenticare di convertire la durata prima di eseguire operazioni aritmetiche può portare a risultati errati. Verifica sempre l'unità con `duration.getTimeUnit()`.
- **Consiglio:** Usa `project.getDuration(value, TimeUnitType)` per creare durate nell'unità desiderata invece di convertirle in seguito.
- **Problema:** Impostare una durata negativa genererà un'eccezione. Assicurati di convalidare i valori di input.

## Conclusione
In questa guida abbiamo trattato come **aggiungere un'attività a un progetto**, leggere la sua durata predefinita, **impostare la durata** e **convertire la durata** in diverse unità di tempo. Ora puoi integrare queste tecniche in applicazioni di pianificazione più ampie per una gestione precisa dei progetti.

## FAQ
### Aspose.Tasks è compatibile con tutte le versioni di Java?
Aspose.Tasks è compatibile con Java 6 e versioni successive.

### Posso usare Aspose.Tasks per progetti commerciali?
Sì, puoi usare Aspose.Tasks sia per progetti personali che commerciali. Visita [qui](https://purchase.aspose.com/buy) per i dettagli sulla licenza.

### Dove posso trovare supporto e risorse aggiuntive?
Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto della community e discussioni.

### Come posso ottenere una licenza temporanea per scopi di test?
Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/) per test e valutazione.

### È disponibile una prova gratuita per Aspose.Tasks?
Sì, puoi accedere alla prova gratuita [qui](https://releases.aspose.com/) per esplorare Aspose.Tasks prima di acquistare.

## Domande frequenti

**Q: Come modifico la durata di un'attività dopo averla impostata?**  
A: Recupera la durata corrente con `task.get(Tsk.DURATION)`, modificala (ad es., `add`, `subtract` o `convert`), e poi impostala nuovamente usando `task.set(Tsk.DURATION, newDuration)`.

**Q: Posso impostare una durata in minuti?**  
A: Sì, usa `TimeUnitType.Minute` quando chiami `project.getDuration(value, TimeUnitType.Minute)`.

**Q: La modifica della durata aggiorna automaticamente le date di inizio e fine dell'attività?**  
A: Solo se la modalità di pianificazione del progetto è impostata su automatico. Altrimenti, potresti dover ricalcolare il calendario con `project.calculateCriticalPath()`.

**Q: È possibile recuperare la durata come numero grezzo?**  
A: Chiama `duration.getTimeSpan()` per ottenere il valore numerico nell'unità di tempo corrente.

**Q: Cosa succede se sottraggo più della durata corrente?**  
A: L'API lancerà un `ArgumentOutOfRangeException`. Convalida sempre che la durata risultante rimanga positiva.

---

**Ultimo aggiornamento:** 2026-02-20  
**Testato con:** Aspose.Tasks for Java (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}