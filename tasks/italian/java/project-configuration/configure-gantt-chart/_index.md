---
title: Configurare la visualizzazione del diagramma di Gantt nei progetti Aspose.Tasks
linktitle: Configurare la visualizzazione del diagramma di Gantt nei progetti Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come configurare la visualizzazione del diagramma di Gantt MS Project in Aspose.Tasks utilizzando Java. Personalizza i progetti e visualizzali nel diagramma di Gantt passo dopo passo.
type: docs
weight: 10
url: /it/java/project-configuration/configure-gantt-chart/
---
## introduzione
In questo tutorial imparerai come configurare la visualizzazione del grafico di Gantt MS Project nei progetti Aspose.Tasks utilizzando Java. Aspose.Tasks è una potente API Java che ti consente di lavorare con i file di Microsoft Project a livello di codice. Seguendo questi passaggi, sarai in grado di personalizzare la visualizzazione del diagramma di Gantt in base ai requisiti del tuo progetto.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema.
2.  Libreria Aspose.Tasks: scarica e installa la libreria Aspose.Tasks. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Ambiente di sviluppo integrato (IDE): scegli un IDE a tua scelta. Questo tutorial utilizza IntelliJ IDEA, ma puoi utilizzare qualsiasi IDE con cui ti trovi a tuo agio.
## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari per lavorare con Aspose.Tasks nel tuo progetto Java. Aggiungi le seguenti istruzioni di importazione al tuo file Java:
```java
import com.aspose.tasks.*;
```
Ora, analizziamo il processo di configurazione della visualizzazione del diagramma di progetto Gantt MS in istruzioni dettagliate:
## Passaggio 1: impostare la directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso della directory dei dati del progetto.
## Passaggio 2: caricare il file di progetto
```java
Project project = new Project(dataDir + "project.mpp");
```
Carica il file del tuo progetto (`project.mpp` in questo esempio) utilizzando il file`Project` classe da Aspose.Tasks.
## Passaggio 3: aggiungi una nuova attività
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Crea una nuova attività nel tuo progetto utilizzando il file`Task` class e aggiungerla ai figli dell'attività root.
## Passaggio 4: definire l'attributo personalizzato
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Definire un nuovo attributo personalizzato utilizzando il file`ExtendedAttributeDefinition`class e aggiungerlo agli attributi estesi del progetto.
## Passaggio 5: aggiungi un attributo personalizzato all'attività
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Aggiungi l'attributo personalizzato all'attività creata utilizzando il file`createExtendedAttribute` metodo.
## Passaggio 6: personalizzare la tabella
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
Personalizza la tabella aggiungendo il campo degli attributi di testo con larghezza, titolo e allineamento specificati.
## Passaggio 7: salva il progetto
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Salvare il progetto con la vista diagramma di progetto Gantt MS configurata. Il file risultante può essere aperto in Microsoft Project 2010.
## Conclusione
Congratulazioni! Hai configurato correttamente la visualizzazione del grafico di Gantt MS Project nei progetti Aspose.Tasks utilizzando Java. Ora puoi personalizzare gli attributi del progetto e visualizzarli nel diagramma di Gantt in base alle esigenze del tuo progetto.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks con altri linguaggi di programmazione?
R: Sì, Aspose.Tasks è disponibile per più linguaggi di programmazione tra cui .NET, Java e C++.
### D: È disponibile una prova gratuita per Aspose.Tasks?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Dove posso trovare supporto per Aspose.Tasks?
R: Puoi trovare supporto e porre domande su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### D: Come posso acquistare una licenza per Aspose.Tasks?
 R: Puoi acquistare una licenza da[Qui](https://purchase.aspose.com/buy).
### D: Ho bisogno di una licenza temporanea a scopo di test?
 R: Sì, puoi ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).