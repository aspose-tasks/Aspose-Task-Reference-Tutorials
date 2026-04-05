---
date: 2026-02-26
description: Scopri come riprendere e interrompere un'attività in Aspose.Tasks per
  Java, includendo il filtraggio delle attività per data per un controllo preciso
  del progetto.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come riprendere l'attività e fermare l'attività in Aspose.Tasks
url: /it/java/task-properties/stop-resume-task/
weight: 30
---

.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come riprendere un'attività e fermare un'attività in Aspose.Tasks

## Introduzione
Se stai costruendo una soluzione di project management basata su Java, spesso avrai bisogno di **mettere in pausa** un'attività temporaneamente e poi **riprenderla** in seguito. Aspose.Tasks per Java semplifica questo compito grazie alle proprietà integrate per fermare e riprendere le attività. In questo tutorial scoprirai **come riprendere un'attività** e **come fermare un'attività** programmaticamente, e vedrai anche come **filtrare le attività per data** in modo da lavorare solo con gli elementi pertinenti del tuo calendario.

## Risposte rapide
- **Cosa significa “stop” per un'attività?** Imposta una data di stop, sospendendo il lavoro dopo quel punto.  
- **Come posso riprendere un'attività fermata?** Assegnando una data di resume successiva alla data di stop.  
- **Posso limitare l'operazione a un intervallo di date?** Sì – usa una data minima per filtrare le attività.  
- **Quale versione della libreria è necessaria?** Qualsiasi versione recente di Aspose.Tasks per Java (l'API rimane stabile).  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza per la produzione.

## Che cosa è “come riprendere un'attività” in Aspose.Tasks?
Riprendere un'attività significa semplicemente fornire una data **RESUME** su un oggetto `Task`. Quando il motore del progetto elabora il calendario, il lavoro continuerà da quella data in poi. È particolarmente utile per gestire interruzioni come l'indisponibilità di risorse o dipendenze esterne.

## Perché usare la funzionalità stop/resume?
- **Controllo sui tempi:** Metti in pausa il lavoro senza eliminare l'attività.  
- **Reportistica accurata:** Mostra date di inizio/fine realistiche nei diagrammi di Gantt.  
- **Automazione semplice:** Combina con filtri di data per aggiornare molte attività contemporaneamente.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Una solida conoscenza dei fondamenti di Java.  
- JDK installato sulla tua macchina.  
- La libreria Aspose.Tasks per Java aggiunta al tuo progetto (scaricala da [qui](https://releases.aspose.com/tasks/java/)).  

## Importare i pacchetti
Per prima cosa, porta le classi necessarie nello scope in modo da poter lavorare con progetti e attività.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Passo 1: Inizializzare il progetto e il raccoglitore
Crea un'istanza `Project` che punti al tuo file MPP e configura un `ChildTasksCollector` per raccogliere ogni attività nella gerarchia.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Passo 2: Definire una data minima per il filtraggio
Se desideri lavorare solo con le attività che hanno date di stop o resume significative, definisci una **data minima**. Questo è il fulcro della tecnica *filtrare le attività per data*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Passo 3: Iterare, verificare e visualizzare i valori Stop/Resume
Ora cicla tra le attività raccolte, applica la logica **come fermare un'attività** e stampa le date. Il codice dimostra anche **come riprendere un'attività** leggendo la proprietà `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Consiglio professionale:** Sostituisci le chiamate a `System.out.println` con la tua logica (ad esempio, aggiornare le date, scrivere su un file di log o modificare gli oggetti attività) per *fermare* o *riprendere* effettivamente le attività secondo necessità.

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| `NullPointerException` su `tsk.get(Tsk.STOP)` | L'attività non ha una data di stop impostata. | Verifica `null` prima di chiamare `.before(minDate)`. |
| Le date appaiono come `NA` anche dopo l'impostazione | La data minima è troppo recente. | Usa una `minDate` più antica o rimuovi il filtro. |
| Le modifiche non sono riflesse nel MPP salvato | Il progetto non è stato salvato dopo le modifiche. | Chiama `project.save("output.mpp");` dopo aver aggiornato le attività. |

## Domande frequenti

### Aspose.Tasks per Java è adatto a progetti su larga scala?
Assolutamente sì! Aspose.Tasks per Java è progettato per gestire progetti di varie dimensioni, garantendo efficienza e affidabilità.

### Posso personalizzare la data di stop e resume delle attività?
Sì, l'esempio fornito consente flessibilità nell'impostare la data minima in base ai requisiti del tuo progetto.

### Dove posso trovare supporto aggiuntivo per Aspose.Tasks per Java?
Visita il [Forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto della community e discussioni.

### È disponibile una prova gratuita per Aspose.Tasks per Java?
Sì, puoi accedere alla [prova gratuita](https://releases.aspose.com/) per esplorare le funzionalità prima di acquistare.

### Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?
Puoi acquisire una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/) per scopi di test.

**Domande e risposte aggiuntive**

**D: Come imposto effettivamente una nuova data di stop per un'attività?**  
R: Usa `tsk.set(Tsk.STOP, new Date(...));` e poi salva il progetto.

**D: Posso filtrare le attività per un intervallo specifico invece di una sola data minima?**  
R: Sì—confronta sia `before` che `after` con le tue date di inizio e fine.

**D: L'API ricalcola automaticamente il calendario dopo aver modificato le date di stop/resume?**  
R: Dopo aver modificato le date, chiama `project.calculateCriticalPath();` per aggiornare il calendario.

## Conclusione
In questa guida abbiamo coperto **come riprendere un'attività** e **come fermare un'attività** usando Aspose.Tasks per Java, insieme a un metodo pratico per **filtrare le attività per data**. Integrando questi snippet nella tua applicazione, otterrai un controllo granulare sui tempi del progetto e potrai automatizzare le regolazioni del calendario con sicurezza.

---

**Ultimo aggiornamento:** 2026-02-26  
**Testato con:** Aspose.Tasks per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}