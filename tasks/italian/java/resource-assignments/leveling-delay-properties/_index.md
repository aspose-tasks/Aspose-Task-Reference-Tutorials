---
date: 2026-01-07
description: Scopri come aggiungere una risorsa al progetto e gestire le proprietà
  di ritardo di livellamento per le assegnazioni di risorse utilizzando Aspose.Tasks
  per Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come aggiungere una risorsa al progetto e gestire le proprietà di ritardo di
  livellamento in Aspose.Tasks
url: /it/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere una risorsa al progetto e gestire le proprietà di ritardo di livellamento in Aspose.Tasks

## Introduzione
In questo tutorial, imparerai **come aggiungere una risorsa al progetto** gestendo anche le proprietà di ritardo di livellamento per le assegnazioni delle risorse con Aspose.Tasks per Java. Che tu stia costruendo un motore di pianificazione o automatizzando gli aggiornamenti del progetto, padroneggiare questi passaggi ti permette di mantenere i dati del progetto accurati senza la necessità di avere Microsoft Project installato.

## Risposte rapide
- **Che cosa significa “add resource to project”?** Crea una nuova voce di risorsa che può essere assegnata alle attività.  
- **Posso impostare un ritardo di livellamento dopo l'assegnazione?** Sì, usando i campi `Asn.DELAY` o `Asn.LEVELING_DELAY`.  
- **È necessaria una licenza per eseguire questo codice?** Una versione di prova gratuita funziona per lo sviluppo; è richiesta una licenza a pagamento per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o successive.  
- **È compatibile con tutti i formati di file MS Project?** Aspose.Tasks supporta .MPP, .XML, .XER e altri.

## Cos'è “add resource to project” in Aspose.Tasks?
Aggiungere una risorsa a un progetto significa creare un oggetto `Resource` all'interno del modello `Project`. Questo oggetto può poi essere collegato alle attività tramite `ResourceAssignment`, consentendo di tenere traccia del lavoro, dei costi e delle impostazioni di livellamento.

## Perché gestire le proprietà di ritardo di livellamento?
Il ritardo di livellamento aiuta il pianificatore a distribuire il lavoro quando le risorse sono sovraccaricate. Impostando un ritardo, si indica al motore di posticipare l'inizio di un'assegnazione, evitando conflitti e mantenendo il progetto realistico.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. **Java Development Kit (JDK):** Assicurati di avere Java JDK installato sul tuo sistema. Puoi scaricarlo e installarlo dal [sito web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. **Libreria Aspose.Tasks per Java:** Scarica la libreria Aspose.Tasks per Java dalla [pagina di download](https://releases.aspose.com/tasks/java/).

## Importa i pacchetti
Prima, importa i pacchetti necessari nel tuo progetto Java per utilizzare le funzionalità di Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Passo 1: Crea un oggetto Project
Istanzia un oggetto `Project`, che servirà da contenitore per tutte le attività, risorse e assegnazioni:
```java
Project prj = new Project();
```

## Passo 2: Crea un'attività
Aggiungi un'attività al progetto. Questo dimostra **come aggiungere un'attività** programmaticamente:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Passo 3: Imposta la data di inizio e la durata dell'attività
Definisci quando l'attività inizia e quanto durerà:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Passo 4: Aggiungi una risorsa
Ora **addiamo una risorsa al progetto** creando una nuova voce `Resource`:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Passo 5: Crea un'assegnazione di risorsa
Collega l'attività e la risorsa appena aggiunta:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Passo 6: Imposta il ritardo di livellamento
Configura il ritardo di livellamento per l'assegnazione. Impostarlo a zero significa nessun ritardo aggiuntivo, ma puoi regolare il valore secondo necessità:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Passo 7: Visualizza i risultati
Stampa le proprietà importanti per verificare che tutto sia stato impostato correttamente:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Problemi comuni e consigli
- **Problema:** Dimenticare di impostare la data di inizio dell'attività può far sì che l'assegnazione utilizzi la data di inizio del progetto per impostazione predefinita.  
- **Consiglio:** Usa `prj.getDuration(value, TimeUnitType.Day)` per controllare la granularità del ritardo.  
- **Consiglio:** Dopo aver aggiunto più risorse, chiama `prj.updateResourceAssignments()` per far ricalcolare al pianificatore il livellamento.

## Conclusione
Seguendo questi passaggi, ora sai **come aggiungere una risorsa al progetto**, assegnarla a un'attività e gestire le proprietà di ritardo di livellamento usando Aspose.Tasks per Java. Questa conoscenza ti consente di costruire soluzioni robuste di automazione dei progetti che rimangono sincronizzate con le reali limitazioni delle risorse.

## FAQ's
### Q: Posso usare Aspose.Tasks con altre librerie Java?
A: Sì, Aspose.Tasks può essere integrato con altre librerie Java per migliorare le capacità di gestione dei progetti.

### Q: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
A: Sì, Aspose.Tasks supporta varie versioni dei file Microsoft Project, garantendo la compatibilità in diversi ambienti.

### Q: Dove posso trovare supporto aggiuntivo per Aspose.Tasks?
A: Puoi trovare supporto e risorse sul [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q: Posso provare Aspose.Tasks prima di acquistarlo?
A: Sì, puoi ottenere una versione di prova gratuita di Aspose.Tasks dalla [pagina dei rilasci](https://releases.aspose.com/).

### Q: Come posso ottenere una licenza temporanea per Aspose.Tasks?
A: Puoi richiedere una licenza temporanea dalla [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/) per scopi di valutazione.

## Domande frequenti aggiuntive

**Q: Cosa succede se imposto un ritardo di livellamento diverso da zero?**  
A: Il pianificatore posticiperà l'inizio dell'assegnazione della durata specificata, aiutando a risolvere le sovrallocazioni.

**Q: Posso recuperare il ritardo di livellamento dopo aver salvato il progetto?**  
A: Sì, puoi riaprire il file del progetto e leggere la proprietà `Asn.DELAY` dall'assegnazione.

**Q: Esiste un modo per applicare il ritardo di livellamento a tutte le assegnazioni contemporaneamente?**  
A: Puoi iterare su `prj.getResourceAssignments()` e impostare il ritardo per ogni assegnazione in un ciclo.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}