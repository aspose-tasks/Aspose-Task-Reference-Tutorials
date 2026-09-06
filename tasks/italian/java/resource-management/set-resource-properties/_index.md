---
date: 2026-08-24
description: Scopri come aggiungere una risorsa MS Project, impostare la tariffa standard
  e altre proprietà della risorsa in MS Project usando Aspose.Tasks per Java e gestire
  le risorse in modo efficiente.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Imposta le proprietà della risorsa in Aspose.Tasks
og_description: Aggiungi una risorsa MS Project e imposta la tariffa standard usando
  Aspose.Tasks per Java. Scopri i prerequisiti, il codice passo‑passo e la risoluzione
  dei problemi in questa guida concisa.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Aggiungi una risorsa MS Project e imposta la tariffa con Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Come aggiungere una risorsa MS Project con Aspose.Tasks
url: /it/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi resource ms project e imposta la tariffa in Aspose.Tasks

## Introduzione
Se stai sviluppando applicazioni Java che devono leggere o scrivere file Microsoft Project, **add resource ms project** e configurare la sua tariffa standard è un compito di routine ma essenziale. In questa guida vedrai come creare un oggetto `Project`, aggiungere una risorsa e impostare sia le tariffe standard che quelle di straordinario usando Aspose.Tasks per Java. Alla fine potrai automatizzare i calcoli dei costi e mantenere i piani di progetto aggiornati senza necessità di installare Microsoft Project.

## Risposte rapide
- **Quale classe rappresenta un file Project?** `Project`
- **Quale chiamata aggiunge una nuova risorsa?** `project.getResources().add()`
- **Come impostare la tariffa standard?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **È necessaria una licenza per l'uso in produzione?** Sì, devi caricare una licenza valida di Aspose.Tasks.
- **Quali versioni di Java sono supportate?** Java 8 e successive (Java 17+ consigliato).

## Che cos'è “set standard rate”?
L'operazione *set standard rate* assegna un costo orario predefinito a una risorsa. Questa tariffa è utilizzata dai project manager per calcolare le spese di manodopera, generare report sui costi e prevedere i budget, garantendo che i calcoli dei costi riflettano il prezzo previsto del lavoro svolto da ciascuna risorsa durante l'intero ciclo di vita del progetto.

## Perché impostare le tariffe con Aspose.Tasks?
Aspose.Tasks può elaborare **oltre 50 formati di input e output**, inclusi file MPP, MPX, XML e Primavera, e gestisce progetti di centinaia di pagine senza caricare l'intero file in memoria. Ciò consente elaborazioni batch ad alta velocità su server Windows, Linux o macOS, riducendo lo sforzo manuale fino al 90 % negli scenari tipici di automazione.

## Prerequisiti
Prima di iniziare, assicurati che i seguenti elementi siano pronti:

### Configurazione dell'ambiente di sviluppo Java
1. Installa JDK 8 o versioni successive. Puoi scaricarlo dal [sito Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Scegli un IDE come IntelliJ IDEA, Eclipse o NetBeans e configuralo per lo sviluppo Java.

### Installazione di Aspose.Tasks per Java
1. Scarica l'ultimo pacchetto Aspose.Tasks per Java dalla [pagina di download](https://releases.aspose.com/tasks/java/).  
2. Aggiungi i file JAR al classpath del tuo progetto o dichiara la dipendenza Maven/Gradle come mostrato nella documentazione del prodotto.

## Importa pacchetti
Importa le classi principali di Aspose.Tasks di cui avrai bisogno. Questo passaggio ti dà accesso ai tipi `Project`, `Resource` e `Rsc` utilizzati in seguito.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Passo 1: crea un oggetto progetto
La classe `Project` è l'oggetto di livello superiore che rappresenta un intero file MS Project in memoria. Istanziandola si crea un progetto vuoto che puoi popolare con attività, risorse e altri dati.

```java
Project project = new Project();
```

## Passo 2: aggiungi una risorsa (add resource ms project)
La classe `Resource` modella una singola risorsa di progetto, come una persona, un'attrezzatura o un materiale. Aggiungere una risorsa tramite `project.getResources().add()` restituisce un'istanza `Resource` non nulla pronta per la configurazione delle proprietà.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Passo 3: imposta le proprietà della risorsa (how to set rates)
L'enumerazione `Rsc` contiene costanti per i campi della risorsa come `STANDARD_RATE` e `OVERTIME_RATE`.  
Imposti le tariffe standard e di straordinario chiamando `set` sull'oggetto `Resource` con i valori enum `Rsc` appropriati. Le tariffe sono memorizzate come `BigDecimal` per preservare la precisione monetaria.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| `NullPointerException` durante la chiamata a `set` | La risorsa non è stata aggiunta correttamente. | Assicurati che `project.getResources().add()` restituisca una `Resource` non nulla. |
| Le tariffe appaiono come 0 nel file salvato | Uso di `int` invece di `BigDecimal`. | Usa sempre `BigDecimal.valueOf()` per i valori monetari. |
| Licenza non trovata | Il file di licenza non è stato caricato prima di creare `Project`. | Carica la licenza (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) all'avvio del programma. |

## Conclusione
Ora sai come **add resource ms project**, creare un oggetto `Project` e **impostare le tariffe standard e di straordinario** usando Aspose.Tasks per Java. Questa capacità ti consente di automatizzare i calcoli dei costi, generare report personalizzati e gestire completamente le risorse di MS Project da qualsiasi applicazione Java.

## Domande frequenti
**Q: Aspose.Tasks per Java può gestire file MS Project complessi?**  
A: Sì, supporta tutti i principali formati Project, inclusi file di grandi dimensioni con migliaia di attività e risorse, preservando ogni campo senza perdita di dati.

**Q: È disponibile una versione di prova gratuita?**  
A: Sì, puoi accedere a una prova gratuita di Aspose.Tasks per Java dalla [pagina di prova gratuita di Aspose.Tasks](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
A: Puoi richiedere assistenza sul [forum di supporto](https://forum.aspose.com/c/tasks/15).

**Q: Come posso ottenere una licenza temporanea per la valutazione?**  
A: Una licenza temporanea è disponibile nella [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso acquistare una versione con licenza?**  
A: Acquista una licenza completa dalla [pagina di acquisto](https://purchase.aspose.com/buy).

**Ultimo aggiornamento:** 2026-08-24  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose

## Tutorial correlati

- [Come creare risorse – Gestione delle risorse con Aspose.Tasks per Java](/tasks/java/resource-management/)
- [Aggiungi risorsa al progetto con Aspose.Tasks per Java](/tasks/java/resource-management/create-resources/)
- [Come aggiungere risorsa al progetto e gestire le proprietà di ritardo di livellamento in Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}