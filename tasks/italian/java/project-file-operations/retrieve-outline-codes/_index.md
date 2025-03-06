---
title: Recupera i codici di struttura di MS Project in Aspose.Tasks
linktitle: Recupera i codici di struttura in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come recuperare i codici di struttura di Microsoft Project a livello di codice utilizzando Aspose.Tasks per Java. Migliora le tue capacità di gestione dei progetti.
type: docs
weight: 15
url: /it/java/project-file-operations/retrieve-outline-codes/
---
## introduzione
In questo tutorial impareremo come recuperare i codici di struttura di Microsoft Project utilizzando Aspose.Tasks per Java. I codici di struttura in MS Project forniscono un modo strutturato per classificare e organizzare attività, risorse e incarichi di progetto. Aspose.Tasks è una potente libreria Java che consente agli sviluppatori di manipolare e gestire i file di Microsoft Project a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di aver configurato i seguenti prerequisiti:
### 1. Ambiente di sviluppo Java
Assicurati di avere Java Development Kit (JDK) installato sul tuo sistema. È possibile scaricare e installare JDK dal sito Web Oracle.
### 2. Libreria Aspose.Tasks
 Scarica e includi la libreria Aspose.Tasks nel tuo progetto Java. È possibile scaricare la libreria da[Aspose.Tasks per la pagina di download di Java](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Innanzitutto, importa i pacchetti necessari da Aspose.Tasks nel tuo codice Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Ora suddividiamo il codice di esempio fornito in più passaggi:
## Passaggio 1: caricare il progetto
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 In questo passaggio carichiamo il file Microsoft Project in un file`Project` oggetto utilizzando il nome file fornito.
## Passaggio 2: recuperare i codici di struttura
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Iteriamo attraverso ogni definizione di codice di struttura nel progetto.
## Passaggio 3: accedere alle proprietà del codice struttura
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Recuperiamo e stampiamo varie proprietà della definizione del codice di struttura come Alias, ID campo e Nome campo.
## Passaggio 4: controlla il codice personalizzato aziendale
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Controlliamo se il codice di struttura è un codice personalizzato aziendale e stampiamo il risultato di conseguenza.
## Passaggio 5: Visualizza le maschere del codice struttura
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iteriamo attraverso ciascuna maschera associata al codice di contorno e stampiamo il suo livello e il valore della maschera.
## Passaggio 6: visualizzare i valori del codice struttura
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Eseguiamo un'iterazione su ciascun valore del codice di struttura e ne stampiamo la descrizione, l'ID valore, il valore e il tipo.
## Conclusione
In questo tutorial, abbiamo imparato come recuperare i codici di struttura di MS Project utilizzando Aspose.Tasks per Java. Seguendo i passaggi forniti, puoi accedere e manipolare in modo efficace i codici di struttura nelle tue applicazioni Java, abilitando funzionalità avanzate di gestione dei progetti.
## Domande frequenti
### Q1: posso utilizzare Aspose.Tasks per Java per modificare i codici di struttura in un file di progetto?
R: Sì, Aspose.Tasks per Java fornisce API per modificare i codici di struttura nei file MS Project a livello di codice.
### Q2: È disponibile una versione di prova per Aspose.Tasks per Java?
 R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java da[Sito web Aspose.Tasks](https://releases.aspose.com/).
### Q3: Come posso ottenere supporto tecnico per Aspose.Tasks per Java?
 R: Puoi ottenere supporto tecnico visitando il sito[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) e pubblicando lì le tue domande.
### Q4: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
 R: Sì, puoi acquistare una licenza temporanea per Aspose.Tasks per Java da[pagina di acquisto](https://purchase.aspose.com/temporary-license/).
### Q5: Dove posso trovare la documentazione completa per Aspose.Tasks per Java?
 R: Puoi fare riferimento a[documentazione](https://reference.aspose.com/tasks/java/) per informazioni dettagliate sull'utilizzo di Aspose.Tasks per Java.