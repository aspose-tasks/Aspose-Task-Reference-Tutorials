---
date: 2026-10-15
description: Scopri come creare un'attività, impostare la directory dei dati, personalizzare
  i campi della tabella e salvare il progetto come MPP con Aspose.Tasks for Java.
  Guida passo‑passo per gli sviluppatori Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Come creare un'attività e impostare la directory dei dati usando Aspose.Tasks
  for Java
og_description: Come creare un'attività, personalizzare i campi della tabella e salvare
  il progetto come MPP usando Aspose.Tasks for Java. Segui questa guida dettagliata
  per una rapida implementazione.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Come creare un'attività e impostare la directory dei dati in Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Come creare un'attività e impostare la directory dei dati usando Aspose.Tasks
  for Java
url: /it/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare attività e impostare la directory dei dati usando Aspose.Tasks per Java

## Introduzione
In questo tutorial scoprirai **come creare attività** programmaticamente, configurare la **directory dei dati** e **salvare il progetto come MPP** oltre a **personalizzare i campi della tabella** in una visualizzazione di diagramma di Gantt. Aspose.Tasks per Java è un'API potente che supporta oltre 30 formati di input e output e può elaborare progetti con fino a 10 000 attività senza caricare l'intero file in memoria. Alla fine della guida sarai in grado di automatizzare la creazione del progetto, arricchire le attività con attributi personalizzati e produrre un file MPP pronto per l'apertura in Microsoft Project.

## Risposte rapide
- **Qual è il primo passo?** Imposta il percorso della directory dei dati dove risiedono i file del tuo progetto.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (scaricabile dal sito ufficiale).  
- **Posso aggiungere attributi personalizzati?** Sì – puoi definire attributi estesi e mostrarli nel diagramma di Gantt.  
- **Ho bisogno di una licenza per i test?** È disponibile una licenza temporanea per scopi di valutazione.  
- **Quale IDE è consigliato?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans) funzionerà.

## Cos'è “impostare la directory dei dati” e perché è importante?
Impostare la directory dei dati indica ad Aspose.Tasks dove leggere e scrivere i file di progetto. Senza un percorso corretto l'API non può individuare i tuoi file `.mpp`, generando errori `FileNotFoundException`. Definire questa directory all'inizio del codice rende il flusso di lavoro ripetibile e isola le preoccupazioni del file‑system dalla logica di business.

## Perché personalizzare i campi della tabella in un diagramma di Gantt?
I campi della tabella personalizzati ti consentono di mostrare informazioni aggiuntive — come attributi personalizzati, dati delle risorse o note specifiche del progetto — direttamente nella visualizzazione Gantt. Questo riduce la necessità di report separati e fornisce agli stakeholder un'unica visuale ricca di dati che può migliorare la velocità di decisione fino al 30 %.

## Come creare una nuova attività?
Crei una nuova attività (task) istanziando un oggetto `Task` e aggiungendolo alla raccolta dei task radice del progetto. Questo approccio ti consente di generare automaticamente grandi pianificazioni, recuperare dati dei task da sistemi esterni o applicare aggiornamenti massivi senza modifiche manuali.

## Prerequisiti
1. **Java Development Kit (JDK)** – versione 8 o successiva.  
2. **Aspose.Tasks per Java** – scaricalo dalla **pagina di rilascio di Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java che preferisci.  

## Importare i pacchetti
Lo spazio dei nomi `com.aspose.tasks` contiene tutte le classi necessarie per la manipolazione dei progetti. Importandolo ottieni l'accesso a `Project`, `Task`, `ExtendedAttributeDefinition` e altri tipi fondamentali.

```java
import com.aspose.tasks.*;
```

## Dipendenza Maven (opzionale)
Se gestisci il tuo progetto con Maven, aggiungi la dipendenza Aspose.Tasks a `pom.xml`. Questo garantisce che la libreria venga risolta automaticamente durante la compilazione.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Guida passo‑passo

### Passo 1: impostare la directory dei dati
Definisci la cartella che contiene i file del tuo progetto. La variabile `dataDir` contiene il percorso assoluto ed è riutilizzata in tutto il tutorial.

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso completo della cartella in cui si trova `project.mpp`, ad esempio `C:/Projects/MyGantt`.

### Passo 2: caricare il file di progetto
`Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta in memoria un singolo file Microsoft Project. Caricare un file esistente ti dà accesso ai suoi task, risorse e tabelle.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Passo 3: aggiungere una nuova attività
`Task` rappresenta un'attività individuale nella pianificazione. Aggiungere un task alla raccolta dei task radice lo inserisce al livello superiore della gerarchia del progetto.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Passo 4: definire un attributo personalizzato
`ExtendedAttributeDefinition` ti consente di creare un campo personalizzato riutilizzabile che può essere associato a qualsiasi task, risorsa o assegnazione.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Passo 5: aggiungere l'attributo personalizzato al task
`ExtendedAttribute` è l'istanza concreta di un attributo personalizzato che assegni a un task specifico.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Passo 6: personalizzare la tabella – aggiungere l'attributo personalizzato come colonna
`TableField` descrive una colonna in una tabella del diagramma di Gantt. Aggiungendo un `TableField` che fa riferimento all'attributo personalizzato, rendi l'attributo visibile nella visualizzazione del diagramma.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Passo 7: salvare il progetto
Chiamando `project.save` si salvano tutte le modifiche in un nuovo file. La costante `SaveFileFormat.MPP` indica ad Aspose.Tasks di scrivere il file nel formato binario nativo di Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|----------|
| **FileNotFoundException** durante il caricamento del progetto | Il percorso **set data directory** è errato o manca una barra finale. | Verifica che `dataDir` punti alla cartella esatta e includi il separatore di file corretto (`/` o `\\`). |
| Attributo personalizzato non visibile nella visualizzazione Gantt | Il campo della tabella è stato aggiunto all'indice sbagliato o la larghezza della colonna è troppo piccola. | Assicurati che `table.getTableFields().add(3, attrField);` utilizzi un indice valido e regola `setWidth` secondo necessità. |
| LicenseException durante il salvataggio | Nessuna licenza valida è stata applicata per l'uso in produzione. | Applica una licenza temporanea o permanente prima di chiamare `project.save()`. |

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks è disponibile per .NET, Java e C++.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Sì, puoi scaricare una versione di prova gratuita dalla **pagina di download della prova gratuita di Aspose.Tasks**.

**D: Dove posso trovare supporto per Aspose.Tasks?**  
R: Puoi trovare supporto e porre domande sul [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**D: Come posso acquistare una licenza per Aspose.Tasks?**  
R: Puoi acquistare una licenza dalla **pagina di acquisto di Aspose.Tasks**.

**D: Ho bisogno di una licenza temporanea per scopi di test?**  
R: Sì, puoi ottenere una licenza temporanea dalla **pagina di richiesta della licenza temporanea**.

## Conclusione
Ora sai **come creare attività**, impostare la directory dei dati, definire e allegare un attributo personalizzato, e **salvare il progetto come MPP** mentre **personalizzi i campi della tabella** nella visualizzazione di un diagramma di Gantt usando Aspose.Tasks per Java. Queste funzionalità ti offrono un controllo programmatico completo sui dati del progetto, consentendo la generazione automatica di pianificazioni e report visivi più ricchi per i tuoi stakeholder.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose

## Tutorial correlati

- [Come creare un file di progetto vuoto in Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Come creare un file MPP – Creare e salvare un progetto vuoto in formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Come creare un progetto aspose.tasks – Impostare nuovi attributi del task](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}