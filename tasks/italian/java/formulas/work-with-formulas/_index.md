---
date: 2026-10-05
description: Scopri come creare un progetto di test e calcolare i giorni tra le date
  usando Aspose.Tasks per Java, aggiungere un campo personalizzato e manipolare i
  file MPP in modo efficiente.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Lavorare con le formule in Aspose.Tasks
og_description: Crea progetto di test e calcola i giorni tra le date usando Aspose.Tasks
  per Java. Questa guida mostra come aggiungere un campo personalizzato, impostare
  le scadenze delle attività e salvare il progetto come file MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Crea progetto di test e calcola i giorni tra le date
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Crea progetto di test e calcola i giorni tra le date
url: /it/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un progetto di test e calcola i giorni tra le date

In questo tutorial **creerai un progetto di test** e **calcolerai i giorni tra le date** aggiungendo un campo personalizzato, definendo un attributo esteso e applicando una formula di Microsoft Project tramite la libreria Aspose.Tasks per Java. Che tu abbia bisogno di generare programmi, calcolare scadenze o automatizzare i report, Aspose.Tasks ti consente di manipolare i dati di Project in modo programmatico senza installazione desktop, supportando oltre 50 formati di input e output e gestendo file di centinaia di pagine in modalità a basso consumo di memoria.

## Risposte rapide
- **Di cosa tratta il tutorial?** Mostra come creare un progetto di test, definire un attributo esteso, impostare una scadenza per un'attività e utilizzare una formula per calcolare i giorni tra le date.  
- **Quale libreria è necessaria?** Aspose.Tasks for Java (latest version).  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per l'uso in produzione.  
- **Quale IDE posso usare?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, VS Code) che supporti JDK 8+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per copiare il codice ed eseguirlo.

## Cos'è “calculate days between dates” in Aspose.Tasks?
In Aspose.Tasks, una formula è una stringa che può fare riferimento ai campi delle attività e eseguire calcoli. `[Deadline] - [Finish]` è la sintassi della formula che Aspose.Tasks utilizza per restituire la differenza numerica in giorni tra due campi data. Il risultato è memorizzato come valore numerico che rappresenta giorni interi, che puoi visualizzare in un campo personalizzato o utilizzare in ulteriori calcoli.

## Perché usare Aspose.Tasks per calcolare i giorni tra le date?
Aspose.Tasks offre **copertura completa dell'API** per ogni proprietà di Project, Task e Resource, funziona su Windows, Linux e macOS, e **non richiede Microsoft Project o Office** installati. Il motore può elaborare progetti con **oltre 500 attività** in meno di un secondo su hardware server tipico, rendendolo ideale per pipeline CI, contenitori Docker e elaborazione batch ad alto volume.

## Come impostare la scadenza per un'attività
java.util.Calendar è una classe Java che rappresenta un momento specifico nel tempo. Imposti una scadenza assegnando un valore `java.util.Calendar` al campo `Tsk.DEADLINE` di un'attività. Dopo aver creato l'istanza Calendar, imposta anno, mese e giorno alla scadenza desiderata, quindi chiama `task.set(Tsk.DEADLINE, calendar);`. La scadenza viene memorizzata nel file di progetto e può essere usata in formule come `[Deadline] - [Finish]`.

## Come definire un attributo esteso
Un attributo esteso è un campo personalizzato che memorizza il risultato della tua formula. Lo crei una volta, gli assegni un alias descrittivo e colleghi l'espressione `[Deadline] - [Finish]` in modo che ogni attività possa calcolare automaticamente l'intervallo. Crealo istanziando `ExtendedAttribute`, impostando il suo Alias, assegnando la formula e aggiungendolo alla collezione del progetto.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- **Java Development Kit (JDK) 8+** – scaricalo dal sito Oracle o adotta OpenJDK.  
- **Aspose.Tasks for Java** – ottieni l'ultimo JAR dalla [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) e aggiungilo al classpath del tuo progetto o alle dipendenze Maven/Gradle.

## Importa i pacchetti
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guida passo‑passo

### Passo 1: Crea un progetto di test con un campo personalizzato
Iniziamo **creando un progetto di test** e aggiungendo un campo personalizzato che in seguito conterrà il risultato della nostra formula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Suggerimento:* `CreateTestProjectWithCustomField()` è un metodo di supporto che crea un programma minimale e registra un attributo esteso pronto per l'assegnazione della formula.

### Passo 2: Definisci un attributo esteso (aggiungi campo personalizzato)
Successivamente, **definiamo un attributo esteso** – fondamentalmente il campo personalizzato – e gli assegniamo un alias descrittivo. Qui è dove inseriamo la logica per **aggiungere il campo personalizzato**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** rende il campo leggibile in Project.  
- **Formula** calcola il numero di giorni tra la data *Finish* di un'attività e la sua *Deadline* – il fulcro di *calculate days between dates*.

### Passo 3: Imposta la scadenza per un'attività (aggiungi attività di scadenza e imposta la scadenza dell'attività)
Ora **aggiungiamo i dati dell'attività di scadenza** impostando la proprietà *Deadline* su un'attività specifica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- L'istanza `Calendar` definisce il momento esatto della scadenza.  
- `set(Tsk.DEADLINE, …)` **imposta la scadenza dell'attività** per l'attività selezionata.

### Passo 4: Salva il progetto (manipola il file Microsoft Project)
Infine, **manipoliamo Microsoft Project** salvando le modifiche in un file MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Puoi aprire `SaveFile.mpp` in Microsoft Project per vedere il campo personalizzato, il risultato della formula e la scadenza riflessi nel programma.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Formula not evaluating** | Assicurati che la stringa `Formula` dell'attributo utilizzi i nomi di campo corretti (es., `[Deadline]`, `[Finish]`). |
| **Task not found** | Verifica che l'ID attività (`1` nell'esempio) esista; usa `project.getRootTask().getChildren().size()` per il debug. |
| **License exception** | Applica una licenza valida di Aspose.Tasks prima di chiamare qualsiasi metodo API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks fornisce API per .NET, Java e altre piattaforme, consentendoti di manipolare i file Microsoft Project nel linguaggio che preferisci.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Assolutamente. Scarica una versione di prova completamente funzionante dalla [Aspose.Tasks download page](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?**  
R: La documentazione ufficiale è disponibile su [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**D: Come posso ottenere supporto per Aspose.Tasks?**  
R: Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per porre domande e condividere esperienze con la community.

**D: È necessaria una licenza temporanea per la valutazione?**  
R: È disponibile una licenza temporanea per test a breve termine; puoi richiederla dalla [pagina di richiesta licenza temporanea](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-10-05  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose

## Tutorial correlati

- [Come creare un file MPP – Creare e salvare un progetto vuoto in formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Imposta la data di inizio del progetto in MS Project usando Aspose.Tasks per Java](/tasks/java/project-properties/write-project-info/)
- [Come creare un attributo esteso in Java con Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}