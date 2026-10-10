---
date: 2026-10-10
description: Scopri come aggiungere attributi estesi in Aspose.Tasks, utilizzare le
  funzioni di valutazione e generare report di progetto con questa libreria Java per
  la gestione dei progetti.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Supporta le funzioni di valutazione nelle formule di Aspose.Tasks
og_description: Scopri come aggiungere attributi estesi in Aspose.Tasks, utilizzare
  le funzioni di valutazione e generare report di progetto con questa libreria Java
  per la gestione dei progetti.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Come aggiungere attributi estesi nelle formule di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Come aggiungere attributi estesi nelle formule di Aspose.Tasks
url: /it/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere attributi estesi nelle formule di Aspose.Tasks

## Introduzione
Aspose.Tasks for Java è una **libreria Java per la gestione dei progetti** che consente di generare report di progetto creando un oggetto `Project` in Java e valutando le funzioni di Microsoft Project direttamente nel tuo codice. Incorporando queste formule, puoi eseguire calcoli sofisticati, generare report personalizzati e automatizzare l'analisi del progetto senza lasciare l'ambiente di sviluppo. In questo tutorial vedremo come creare un oggetto progetto, aggiungere un attributo esteso e utilizzare le funzioni di valutazione per **aggiungere dati di campo personalizzato al task**.

## Risposte rapide
- **Cosa significa “create project object java”?** Crea un'istanza `Project` in memoria che puoi manipolare programmaticamente.  
- **Quale libreria è necessaria?** Aspose.Tasks for Java (scarica dal sito ufficiale).  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa di Aspose.Tasks per l'uso in produzione; è disponibile una versione di prova gratuita.  
- **Posso usare campi personalizzati?** Sì – puoi **aggiungere attributi estesi** ai task e trattarli come campi personalizzati.  
- **È compatibile con tutti i formati di file Project?** Aspose.Tasks supporta 3 formati principali (MPP, MPT, XML) e oltre 50 formati aggiuntivi di input/output.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Ambiente di sviluppo Java** – JDK 8+ e un IDE come IntelliJ IDEA o Eclipse.  
2. **Libreria Aspose.Tasks per Java** – Scarica e includi la libreria dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Aggiungi lo spazio dei nomi Aspose.Tasks alla tua classe Java in modo da poter lavorare con progetti, task e attributi estesi:

```java
import com.aspose.tasks.*;
```

## Genera report di progetto – create project object java
La classe `Project` rappresenta un file Microsoft Project in memoria, esponendo task, risorse e dati personalizzati. Istanziare questa classe ti fornisce un contenitore per tutti gli elementi del progetto che definirai.

```java
Project project = new Project();
```

La riga sopra **crea project object java** che parte vuota e pronta per la personalizzazione.

## Come aggiungere attributi estesi
La classe `ExtendedAttributeDefinition` definisce un campo personalizzato che può essere associato ai task. Per aggiungere un attributo esteso, crea un'istanza di questa classe con tipo `Number`, assegnale un alias come “Sine”, aggiungila alla collezione `ExtendedAttributes` del progetto e poi collegala a ciascun task che richiede il campo personalizzato.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Qui **aggiungiamo un attributo esteso** di tipo `Number` chiamato “Sine” e lo associamo ai task.

## Aggiungi l'attributo esteso al progetto
Registra la definizione dell'attributo nel progetto affinché ogni task possa fare riferimento ad esso.

```java
project.getExtendedAttributes().add(attr);
```

## Crea un nuovo task
`Task` rappresenta un elemento di lavoro nel progetto e può contenere campi personalizzati.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Aggiungi campo personalizzato al task nel progetto
Collega l'attributo esteso definito in precedenza al task appena creato, assegnando al task un campo personalizzato “Sine” che puoi utilizzare in formule o calcoli.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Ora il task contiene un campo personalizzato “Sine” che puoi utilizzare in formule o calcoli. Questo è anche il modo in cui **aggiungi dati di campo personalizzato al task** programmaticamente.

## Perché usare le funzioni di valutazione?
Le funzioni di valutazione ti consentono di incorporare formule native di Microsoft Project (ad es., `Sin([Start])`) direttamente in Aspose.Tasks, abilitando calcoli in tempo reale senza elaborazione esterna. Questo mantiene tutta la logica del progetto in un unico luogo, riduce gli errori di sincronizzazione dei dati e accelera la generazione dei report. Aspose.Tasks supporta la valutazione di oltre 100 funzioni di MS Project, fornendo un motore di calcolo completo all'interno di Java.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **La formula restituisce `NaN`** | Verifica che il tipo del campo personalizzato corrisponda al tipo numerico previsto. |
| **Attributo esteso non visibile** | Assicurati che la definizione dell'attributo sia aggiunta al progetto **prima** di creare i task. |
| **Eccezione di licenza** | Installa una licenza temporanea o completa di **Aspose.Tasks**; la modalità di prova potrebbe limitare alcune funzionalità. |
| **Licenza temporanea mancante** | Ottieni una **licenza temporanea Aspose** dal sito web di Aspose. |

## Domande frequenti

**D: Aspose.Tasks per Java può gestire formule MS Project complesse?**  
R: Sì, Aspose.Tasks per Java supporta la valutazione di un'ampia gamma di funzioni MS Project, consentendo calcoli complessi all'interno delle applicazioni Java.

**D: Aspose.Tasks per Java è compatibile con diverse versioni dei file Microsoft Project?**  
R: Sì, Aspose.Tasks per Java supporta varie versioni dei file Microsoft Project, inclusi i formati MPP, MPT e XML.

**D: Posso provare Aspose.Tasks per Java prima di acquistarlo?**  
R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java dal sito web [pagina di acquisto di Aspose.Tasks per Java](https://purchase.aspose.com/buy).

**D: Come posso ottenere supporto per Aspose.Tasks per Java?**  
R: Puoi ottenere supporto dal forum della community di Aspose.Tasks [forum della community di Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**D: È disponibile una licenza temporanea per Aspose.Tasks per Java?**  
R: Sì, puoi ottenere una licenza temporanea per scopi di test dal sito web di Aspose [pagina della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/).

## Conclusione
Seguendo questi passaggi hai imparato come **creare un oggetto progetto**, **aggiungere un attributo esteso** e sfruttare le funzioni di valutazione per **generare automaticamente un report di progetto**. Ora puoi estendere questa base per costruire analisi di progetto più approfondite, dashboard personalizzate o strumenti di pianificazione automatizzata—tutto alimentato da Aspose.Tasks per Java.

---

**Last Updated:** 2026-10-10  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose

## Tutorial correlati

- [Colonne personalizzate e attributi estesi nella gestione progetti Java](/tasks/java/project-management/extended-attributes/)
- [Leggi attributi estesi dei task con Aspose.Tasks per Java](/tasks/java/task-properties/extended-task-attributes/)
- [Come usare Aspose.Tasks per Java – Aggiungere attributi estesi alle assegnazioni delle risorse](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}