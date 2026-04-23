---
date: 2026-02-07
description: Impara come impostare il calendario del progetto in Java e gestire le
  proprietà del calendario di MS Project usando Aspose.Tasks. Guida passo‑passo per
  visualizzare le ore lavorative del calendario e personalizzare i programmi.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come impostare il calendario del progetto in Java con Aspose.Tasks
url: /it/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il calendario del progetto Java con Aspose.Tasks

## Introduzione
In questo tutorial scoprirai **how to set project calendar java** programmaticamente usando la libreria Aspose.Tasks per Java. Controllare le proprietà del calendario ti consente di **display calendar working hours**, definire giorni lavorativi personalizzati e allineare la pianificazione del tuo progetto con vincoli del mondo reale. Ti guideremo passo dopo passo—dalla configurazione dell'ambiente all'iterazione sui calendari e alla lettura delle loro proprietà—così potrai gestire con sicurezza le impostazioni di **manage ms project calendar** nelle tue applicazioni.

## Risposte rapide
- **What does “set project calendar” mean?** Significa creare o aggiornare gli orari di lavoro di un calendario, il calendario di base e i tipi di giorno all'interno di un file MS Project.  
- **Which library is required?** Aspose.Tasks for Java (qualsiasi versione recente).  
- **Do I need a license?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Can I display calendar working hours?** Sì—leggendo ogni `WeekDay` puoi stampare le ore per ogni tipo di giorno.  
- **Is this compatible with Maven/Gradle?** Assolutamente—basta aggiungere il JAR di Aspose.Tasks come dipendenza.

## Come impostare il calendario del progetto Java
Questa sezione risponde direttamente alla parola chiave principale. Copriremo i passaggi esatti per **set project calendar java**, modificare i giorni lavorativi del calendario e calcolare le ore lavorative in stile Java.

## Che cos'è un calendario di progetto?
Un calendario di progetto definisce i giorni e le ore lavorative per attività, risorse e l'intera linea temporale del progetto. In MS Project, i calendari possono ereditare da un calendario di base, e ogni tipo di giorno (ad esempio **Standard**, **Non‑working**) può avere il proprio orario di lavoro. Gestire queste impostazioni programmaticamente consente di adeguare dinamicamente la pianificazione senza interventi manuali.

## Perché gestire il calendario di MS Project programmaticamente?
- **Automazione:** Regola i calendari in molti progetti con un unico script.  
- **Coerenza:** Applica politiche di orario di lavoro a livello organizzativo.  
- **Integrazione:** Sincronizza i calendari con sistemi esterni (HR, ERP).  
- **Visibilità:** Visualizza rapidamente **display calendar working hours** per report o debug.  
- **Flessibilità:** Puoi **modify calendar working days** o aggiungere eccezioni al volo.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK) 8+** installato e `JAVA_HOME` configurato.  
- **Aspose.Tasks for Java** scaricato dalla [download page](https://releases.aspose.com/tasks/java/). Aggiungi il JAR al classpath del tuo progetto o alle dipendenze Maven/Gradle.  

## Importa pacchetti
Per prima cosa, importa le classi principali di Aspose.Tasks che utilizzeremo durante il tutorial:

```java
import com.aspose.tasks.*;
```

## Passo 1: Configura la directory dei dati
Definisci la cartella che contiene i tuoi file di progetto. Sostituisci il segnaposto con il percorso reale sul tuo computer.

```java
String dataDir = "Your Data Directory";
```

## Passo 2: Definisci le unità di tempo
Gli orari di lavoro sono espressi in millisecondi. Definire costanti riutilizzabili rende il codice più leggibile e ti aiuta a **calculate working hours java** con precisione.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Passo 3: Carica i dati del progetto
Crea un'istanza `Project` caricando un file XML di MS Project esistente (`.xml` o `.mpp`). Questo ti dà accesso a tutti i calendari presenti nel file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Itera attraverso i calendari Java
Ora cicliamo tutti i calendari, stampando il loro identificatore unico, nome, calendario di base e le ore lavorative per ogni tipo di giorno. Questo dimostra **how to set project calendar java** e anche come **display calendar working hours**.

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
- **Mostra il calendario di base** – “Self” (il calendario è il proprio base) o il nome del calendario ereditato.  
- **Scorre ogni `WeekDay`** per calcolare e visualizzare le ore lavorative totali (`workingTime` è in millisecondi, quindi dividiamo per `OneHour`).  

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| `NullPointerException` su `cal.getBaseCalendar()` | Il calendario è un calendario di base (`isBaseCalendar()` restituisce `true`). | Usa il controllo ternario mostrato (`cal.isBaseCalendar() ? "Self" : ...`). |
| Nessuna stampa delle ore lavorative | Il file di progetto utilizza un'unità di tempo diversa (ticks). | Verifica il formato del file; Aspose.Tasks normalizza in millisecondi, ma assicurati di caricare il tipo di file corretto. |
| Impossibile trovare `project.xml` | Percorso `dataDir` errato. | Usa un percorso assoluto o `Paths.get(dataDir, "project.xml").toString()`. |

## Domande frequenti

**D: Posso modificare le proprietà del calendario programmaticamente usando Aspose.Tasks?**  
R: Sì, l'API fornisce pieno accesso in lettura/scrittura ai calendari, consentendoti di aggiungere, modificare o eliminare orari di lavoro, eccezioni e relazioni di calendario di base.

**D: Ci sono limitazioni nella personalizzazione del calendario con Aspose.Tasks?**  
R: La libreria replica le funzionalità di Microsoft Project, quindi puoi personalizzare praticamente tutti gli aspetti del calendario. Solo versioni molto vecchie dei file Project potrebbero presentare piccole incompatibilità.

**D: Posso integrare la gestione del calendario in progetti Java esistenti?**  
R: Assolutamente. Basta aggiungere il JAR di Aspose.Tasks al percorso di compilazione e utilizzare gli stessi pattern di codice mostrati qui.

**D: Aspose.Tasks supporta altre funzionalità di gestione progetti oltre alla gestione dei calendari?**  
R: Sì, copre attività, risorse, assegnazioni, strutture, baseline e molto altro—offrendo una soluzione completa per l'automazione di progetti basata su Java.

**D: È disponibile supporto tecnico per gli sviluppatori che usano Aspose.Tasks?**  
R: Sì, Aspose offre forum dedicati, supporto via email e documentazione estesa per tutti gli utenti con licenza.

**Ultimo aggiornamento:** 2026-02-07  
**Testato con:** Aspose.Tasks for Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}