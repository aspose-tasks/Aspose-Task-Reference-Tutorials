---
title: Aggiungi attributi estesi alle attività in Aspose.Tasks
linktitle: Aggiungi attributi estesi alle attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora la potenza di Aspose.Tasks Java nella personalizzazione dei file Microsoft Project con attributi estesi. Migliora le tue capacità di gestione dei progetti senza sforzo.
weight: 11
url: /it/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi attributi estesi alle attività in Aspose.Tasks

## introduzione
Migliorare le capacità di gestione dei progetti è fondamentale per un monitoraggio efficiente delle attività e una gestione delle risorse. Aspose.Tasks per Java fornisce una potente soluzione agli sviluppatori Java per manipolare i file di Microsoft Project senza problemi. In questo tutorial esploreremo come aggiungere attributi estesi alle attività utilizzando Aspose.Tasks per Java, consentendoti di personalizzare e organizzare i dati del tuo progetto in base ai tuoi requisiti specifici.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
-  Aspose.Tasks per la libreria Java installata. Puoi scaricarlo da[sito web](https://releases.aspose.com/tasks/java/).
- Un ambiente di sviluppo integrato Java (IDE) installato sul tuo sistema.
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per accedere alle funzionalità Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Ora suddividiamo ciascun esempio in più passaggi:
## 1. Aggiunta di attributi di testo semplice
1. Imposta il percorso della directory del documento:
```java
String dataDir = "Your Document Directory";
```
2. Crea un nuovo progetto:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Crea una definizione di attributo esteso di tipo Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Aggiungi la definizione alla raccolta di attributi estesi del progetto:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Aggiungi un'attività al progetto:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Creare un attributo esteso dalla definizione dell'attributo:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Assegna un valore all'attributo esteso generato:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Aggiungi l'attributo esteso all'attività:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Salva il progetto:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Aggiunta di attributi di testo con l'opzione di ricerca
Segui gli stessi passaggi di cui sopra, sostituendo Testo1 con Testo2 e personalizzando i valori di ricerca.
## 3. Aggiunta dell'attributo Durata con l'opzione di ricerca
Segui gli stessi passaggi di cui sopra, sostituendo Testo1 con Durata2 e personalizzando i valori di ricerca.
## Conclusione
Seguendo questa guida passo passo, hai imparato come sfruttare Aspose.Tasks per Java per aggiungere attributi estesi alle attività nei file Microsoft Project. Questa personalizzazione ti consente di personalizzare il tuo approccio alla gestione del progetto, migliorando flessibilità ed efficienza.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per Java con altre librerie Java?
R: Sì, Aspose.Tasks per Java può essere perfettamente integrato nei tuoi progetti Java e funziona bene con altre librerie Java.
### D: Aspose.Tasks per Java è adatto per applicazioni di gestione di progetti su larga scala?
R: Assolutamente, Aspose.Tasks per Java è progettato per gestire progetti di varie dimensioni, comprese applicazioni su larga scala.
### D: Esistono considerazioni sulla licenza per l'utilizzo di Aspose.Tasks per Java in un progetto commerciale?
 R: Sì, assicurati di rivedere le informazioni sulla licenza fornite nel file[Sito web Aspose.Tasks](https://purchase.aspose.com/buy).
### D: Come posso ottenere supporto o assistenza con Aspose.Tasks per Java?
 R: Visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto e le discussioni della comunità.
### D: Posso provare Aspose.Tasks per Java prima dell'acquisto?
 R: Sì, puoi accedere a una versione di prova gratuita[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
