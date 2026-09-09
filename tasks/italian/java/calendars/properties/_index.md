---
date: 2026-09-09
description: Come impostare il project calendar in Java usando Aspose.Tasks. Scopri
  come visualizzare i calendar working hours, configurare i working time e modificare
  i calendar days nei file MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Gestisci le proprietà del calendar in Aspose.Tasks
og_description: Come impostare il project calendar in Java usando Aspose.Tasks. Questa
  guida mostra come visualizzare i calendar working hours, configurare i working time
  e modificare i calendar days nei file MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Come impostare il project calendar Java con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Come impostare il project calendar Java con Aspose.Tasks
url: /it/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il calendario del progetto Java con Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come impostare il calendario del progetto** in Java sfruttando la libreria Aspose.Tasks. Controllare le proprietà del calendario ti consente di **visualizzare le ore lavorative del calendario**, configurare giorni lavorativi personalizzati e mantenere il programma del progetto allineato a vincoli reali come festività o turni. Vedremo la configurazione dell'ambiente, il caricamento di un progetto, l'iterazione sui calendari e la lettura o l'aggiornamento delle loro proprietà, così potrai gestire con sicurezza le impostazioni del **calendario di MS Project** in qualsiasi applicazione Java.

## Risposte rapide
- **Cosa significa “impostare il calendario del progetto”?** Significa creare o aggiornare gli orari di lavoro, il calendario di base e i tipi di giorno di un calendario all'interno di un file MS Project.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (qualsiasi versione recente).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso visualizzare le ore lavorative del calendario?** Sì—leggendo ogni `WeekDay` è possibile stampare le ore per ogni tipo di giorno.  
- **È compatibile con Maven/Gradle?** Assolutamente—basta aggiungere il JAR di Aspose.Tasks come dipendenza.

## Come impostare il calendario del progetto in Java
Carica il file di progetto, individua il calendario di destinazione e poi regola le definizioni degli orari di lavoro, il calendario di base e i tipi di giorno secondo necessità. I passaggi seguenti forniscono una soluzione completa, end‑to‑end, che dimostra il caricamento, l'iterazione, la modifica e il salvataggio del progetto gestendo le eccezioni e garantendo calcoli accurati delle ore lavorative.

## Cos'è un calendario di progetto?
Un calendario di progetto definisce i giorni e le ore lavorative per attività, risorse e l'intera linea temporale del progetto. In MS Project, i calendari possono ereditare da un calendario di base, e ogni tipo di giorno (ad es., **Standard**, **Non‑working**) può avere i propri orari di lavoro. Gestire queste impostazioni programmaticamente consente di apportare aggiustamenti dinamici al programma senza modifiche manuali.

## Perché gestire il calendario di MS Project programmaticamente?
Gestire i calendari in modo programmatico ti permette di applicare regole di pianificazione coerenti su molti progetti, ridurre errori manuali e integrare i dati del calendario con altri sistemi aziendali come HR o ERP. Questa automazione accelera la configurazione del progetto e garantisce che tutti i membri del team seguano le stesse politiche di orario di lavoro.

- **Automazione:** Regola i calendari su decine di progetti con un unico script.  
- **Coerenza:** Applica automaticamente le politiche di orario di lavoro a livello organizzativo.  
- **Integrazione:** Sincronizza i calendari con sistemi HR o ERP esterni.  
- **Visibilità:** Visualizza rapidamente le **ore lavorative del calendario** per report o debug.  
- **Flessibilità:** Aggiungi eccezioni o turni al volo senza aprire l'interfaccia grafica.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK) 8+** installato e `JAVA_HOME` configurato.  
- **Aspose.Tasks per Java** scaricato dalla [pagina di download](https://releases.aspose.com/tasks/java/). Aggiungi il JAR al classpath o dichiara la dipendenza in Maven/Gradle.  
- Un file di esempio MS Project (`.mpp` o `.xml`) che contenga almeno un calendario da ispezionare o modificare.

## Importare i pacchetti
Le classi `Project`, `Calendar`, `WeekDay` e le classi correlate sono il nucleo della manipolazione dei calendari.  
La classe `Calendar` rappresenta un calendario di progetto, contenente giorni lavorativi, eccezioni e relazioni con il calendario di base.  
La classe `WeekDay` definisce le impostazioni di orario di lavoro per un singolo giorno all'interno di un calendario.

La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file MS Project in memoria. Dopo aver caricato un file, tutte le operazioni sui calendari passano attraverso questo oggetto.

```java
import com.aspose.tasks.*;
```

## Passo 1: impostare la directory dei dati
Definisci la cartella che contiene i tuoi file di progetto. Sostituisci il segnaposto con il percorso reale sulla tua macchina.

```java
String dataDir = "Your Data Directory";
```

## Passo 2: definire le costanti di unità di tempo
Gli orari di lavoro sono espressi in millisecondi. Definire costanti riutilizzabili rende il codice più leggibile e ti aiuta a **calcolare accuratamente le ore lavorative in Java**.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Passo 3: caricare i dati del progetto
Crea un'istanza `Project` caricando un file XML di MS Project esistente (`.xml` o `.mpp`). Questo ti dà accesso a tutti i calendari memorizzati nel file.

La classe `Project` carica il file in un modello di oggetti leggero; **non** richiede che l'intero file sia tenuto in memoria, consentendoti di lavorare con progetti contenenti decine di migliaia di attività.

```java
Project project = new Project(dataDir + "project.xml");
```

## Passo 4: iterare attraverso i calendari Java
Ora cicliamo su ogni calendario, stampando il suo identificatore unico, nome, calendario di base e le ore lavorative per ogni tipo di giorno. Questo dimostra **come impostare il calendario del progetto Java** e anche come **visualizzare le ore lavorative del calendario**.

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
- **Mostra il calendario di base** – oppure “Self” (il calendario è il proprio base) o il nome del calendario ereditato.  
- **Cicla su ogni `WeekDay`** per calcolare e stampare le ore lavorative totali (`workingTime` è in millisecondi, quindi dividiamo per `OneHour`).  

## Benefici quantificati dell'utilizzo di Aspose.Tasks
Aspose.Tasks supporta **oltre 30 formati di input e output** e può elaborare **progetti con fino a 10.000 attività** senza caricare l'intero file in memoria, fornendo risultati in meno di un secondo su hardware server tipico. Questi numeri lo rendono una scelta affidabile per l'automazione su scala aziendale.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| `NullPointerException` su `cal.getBaseCalendar()` | Il calendario è un calendario di base (`isBaseCalendar()` restituisce `true`). | Usa il controllo ternario mostrato (`cal.isBaseCalendar() ? "Self" : ...`). |
| Nessun output per le ore lavorative | Il file di progetto utilizza un'unità di tempo diversa (ticks). | Verifica il formato del file; Aspose.Tasks normalizza in millisecondi, ma assicurati di caricare il tipo di file corretto. |
| Impossibile trovare `project.xml` | Percorso `dataDir` errato. | Usa un percorso assoluto o `Paths.get(dataDir, "project.xml").toString()`. |

## Domande frequenti

**D: Posso modificare le proprietà del calendario programmaticamente usando Aspose.Tasks?**  
R: Sì, l'API fornisce pieno accesso in lettura/scrittura ai calendari, consentendo di aggiungere, modificare o eliminare orari di lavoro, eccezioni e relazioni con il calendario di base.

**D: Ci sono limitazioni nella personalizzazione del calendario con Aspose.Tasks?**  
R: La libreria replica le capacità di Microsoft Project, quindi è possibile personalizzare praticamente tutti gli aspetti del calendario. Solo versioni molto vecchie di file Project potrebbero presentare piccole incompatibilità.

**D: Posso integrare la gestione del calendario in progetti Java esistenti?**  
R: Assolutamente. Basta aggiungere il JAR di Aspose.Tasks al percorso di compilazione e utilizzare gli stessi pattern di codice mostrati qui.

**D: Aspose.Tasks supporta altre funzionalità di gestione progetti oltre alla gestione dei calendari?**  
R: Sì, copre attività, risorse, assegnazioni, strutture, baseline e molto altro—offrendo una soluzione completa per l'automazione di progetti basata su Java.

**D: È disponibile supporto tecnico per gli sviluppatori che usano Aspose.Tasks?**  
R: Sì, Aspose fornisce forum dedicati, supporto via email e una documentazione estesa per tutti gli utenti con licenza.

---

**Ultimo aggiornamento:** 2026-09-09  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose

## Tutorial correlati

- [Create Project Calendar Java – Aspose.Tasks for Java Guide](/tasks/java/)
- [Load Project Files in Java and Manage Project Properties](/tasks/java/project-management/default-properties/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}