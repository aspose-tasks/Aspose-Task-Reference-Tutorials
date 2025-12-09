---
date: 2025-12-04
description: Impara come impostare il calendario del progetto e gestire le proprietà
  del calendario di MS Project in Java usando Aspose.Tasks. Guida passo‑passo per
  visualizzare le ore lavorative del calendario e personalizzare i programmi.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come impostare il calendario del progetto con Aspose.Tasks per Java
url: /it/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il calendario del progetto con Aspose.Tasks per Java

## Introduzione
In questo tutorial scoprirai **come impostare il calendario del progetto** in modo programmatico utilizzando la libreria Aspose.Tasks per Java. Controllare le proprietà del calendario ti consente di **visualizzare le ore lavorative del calendario**, definire giorni lavorativi personalizzati e allineare la pianificazione del progetto a vincoli del mondo reale. Ti guideremo passo dopo passo—dalla configurazione dell'ambiente all'iterazione sui calendari e alla lettura delle loro proprietà—così potrai gestire con sicurezza i calendari di MS Project nelle tue applicazioni.

## Risposte rapide
- **Cosa significa “impostare il calendario del progetto”?** Significa creare o aggiornare gli orari di lavoro, il calendario di base e i tipi di giorno di un calendario all'interno di un file MS Project.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (qualsiasi versione recente).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso visualizzare le ore lavorative del calendario?** Sì—leggendo ogni `WeekDay` è possibile stampare le ore per ogni tipo di giorno.  
- **È compatibile con Maven/Gradle?** Assolutamente—aggiungi il JAR di Aspose.Tasks come dipendenza.

## Cos'è un calendario di progetto?
Un calendario di progetto definisce i giorni e le ore lavorative per attività, risorse e la linea temporale complessiva del progetto. In MS Project, i calendari possono ereditare da un calendario di base, e ogni tipo di giorno (ad es. **Standard**, **Non‑working**) può avere il proprio orario di lavoro. Gestire queste impostazioni programmaticamente consente di apportare aggiustamenti dinamici al programma senza interventi manuali.

## Perché gestire il calendario di MS Project programmaticamente?
- **Automazione:** Regola i calendari su molti progetti con un unico script.  
- **Coerenza:** Applica politiche di orario di lavoro a livello organizzativo.  
- **Integrazione:** Sincronizza i calendari con sistemi esterni (HR, ERP).  
- **Visibilità:** Visualizza rapidamente **le ore lavorative del calendario** per report o debug.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK) 8+** installato e `JAVA_HOME` configurato.  
- **Aspose.Tasks per Java** scaricato dalla [pagina di download](https://releases.aspose.com/tasks/java/). Aggiungi il JAR al classpath del tuo progetto o alle dipendenze Maven/Gradle.  

## Importare i pacchetti
Per prima cosa, importa le classi principali di Aspose.Tasks che utilizzeremo durante il tutorial:

```java
import com.aspose.tasks.*;
```

## Passo 1: Configurare la directory dei dati
Definisci la cartella che contiene i file del tuo progetto. Sostituisci il segnaposto con il percorso reale sulla tua macchina.

```java
String dataDir = "Your Data Directory";
```

## Passo 2: Definire le unità di tempo
Gli orari di lavoro sono espressi in millisecondi. Definire costanti riutilizzabili rende il codice più leggibile.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Passo 3: Caricare i dati del progetto
Crea un'istanza `Project` caricando un file XML di MS Project esistente (`.xml` o `.mpp`). Questo ti dà accesso a tutti i calendari memorizzati nel file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Passo 4: Iterare sui calendari e visualizzare le ore lavorative
Ora cicliamo su ogni calendario, stampiamo il suo identificatore unico, nome, calendario di base e le ore lavorative per ogni tipo di giorno. Questo dimostra **come impostare il calendario del progetto** e anche **come visualizzare le ore lavorative del calendario**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Cosa fa questo codice
- **Filtra i calendari senza nome** (alcuni calendari interni possono avere un nome `null`).  
- **Stampa UID e nome** – utile per identificare il calendario in seguito.  
- **Mostra il calendario di base** – “Self” (il calendario è il proprio base) oppure il nome del calendario ereditato.  
- **Scorre ogni `WeekDay`** per calcolare e stampare le ore lavorative totali (`workingTime` è in millisecondi, quindi lo dividiamo per `OneHour`).  

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| `NullPointerException` su `cal.getBaseCalendar()` | Il calendario è un calendario di base (`isBaseCalendar()` restituisce `true`). | Usa il controllo ternario mostrato (`cal.isBaseCalendar() ? "Self" : ...`). |
| Nessuna uscita per le ore lavorative | Il file di progetto utilizza un'unità di tempo diversa (ticks). | Verifica il formato del file; Aspose.Tasks normalizza in millisecondi, ma assicurati di caricare il tipo di file corretto. |
| Impossibile trovare `project.xml` | Percorso `dataDir` errato. | Usa un percorso assoluto o `Paths.get(dataDir, "project.xml").toString()`. |

## Domande frequenti

**D: Posso modificare le proprietà del calendario programmaticamente usando Aspose.Tasks?**  
R: Sì, l'API fornisce pieno accesso in lettura/scrittura ai calendari, consentendo di aggiungere, modificare o eliminare orari di lavoro, eccezioni e relazioni di calendario di base.

**D: Ci sono limitazioni nella personalizzazione del calendario con Aspose.Tasks?**  
R: La libreria rispecchia le capacità di Microsoft Project, quindi è possibile personalizzare praticamente tutti gli aspetti del calendario. Solo versioni molto vecchie dei file Project potrebbero presentare piccole incompatibilità.

**D: Posso integrare la gestione del calendario in progetti Java esistenti?**  
R: Assolutamente. Basta aggiungere il JAR di Aspose.Tasks al percorso di compilazione e utilizzare gli stessi pattern di codice mostrati qui.

**D: Aspose.Tasks supporta altre funzionalità di gestione progetti oltre alla gestione del calendario?**  
R: Sì, copre attività, risorse, assegnazioni, strutture, baseline e molto altro—offrendo una soluzione completa per l'automazione di progetti basata su Java.

**D: È disponibile supporto tecnico per gli sviluppatori che usano Aspose.Tasks?**  
R: Sì, Aspose fornisce forum dedicati, supporto via email e una documentazione estesa per tutti gli utenti con licenza.

## Conclusione
Seguendo questa guida ora sai **come impostare il calendario del progetto**, leggere e **visualizzare le ore lavorative del calendario**, e integrare queste funzionalità in qualsiasi applicazione Java usando Aspose.Tasks. Questo ti permette di automatizzare le modifiche di programmazione, applicare politiche di lavoro coerenti e creare soluzioni di gestione progetti più ricche.

---

**Ultimo aggiornamento:** 2025-12-04  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}