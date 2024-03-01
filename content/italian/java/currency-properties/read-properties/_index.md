---
title: Leggere le proprietà della valuta nei progetti Aspose.Tasks
linktitle: Leggere le proprietà della valuta nei progetti Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come estrarre informazioni sulla valuta dai file MS Project utilizzando Aspose.Tasks per Java. Guida passo passo fornita.
type: docs
weight: 10
url: /it/java/currency-properties/read-properties/
---
## introduzione
In questo tutorial impareremo come utilizzare Aspose.Tasks per Java per leggere le proprietà della valuta dai file di Microsoft Project. Aspose.Tasks è una potente API Java che consente agli sviluppatori di manipolare i documenti di Microsoft Project senza richiedere l'installazione di Microsoft Project. Seguendo i passaggi descritti di seguito, sarai in grado di estrarre informazioni relative alla valuta senza sforzo.
## Prerequisiti
Prima di procedere con questo tutorial, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Tasks per Java JAR: scarica la libreria Aspose.Tasks per Java da[Qui](https://releases.aspose.com/tasks/java/) e includilo nel tuo progetto Java.
## Importa pacchetti
Inizia importando i pacchetti necessari nella tua classe Java:
```java
import com.aspose.tasks.*;
```
## Passaggio 1: imposta la directory del progetto
Innanzitutto, configura la directory del progetto in cui si trova il file Microsoft Project. È possibile definire questo percorso di directory come segue:
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso effettivo della directory del progetto.
## Passaggio 2: crea un'istanza del lettore del progetto
 Istanziare a`Project` oggetto fornendo il percorso del file Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Assicurarsi di sostituire`"project.mpp"` con il nome del file MS Project.
## Passaggio 3: Visualizza le proprietà della valuta
Recupera e visualizza le proprietà della valuta dal file di progetto:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Questo segmento di codice recupera informazioni come codice valuta, cifre, simboli e posizione dei simboli dal file MS Project e li stampa sulla console.
## Passaggio 4: completamento del processo
Infine, stampa un messaggio che indica il completamento positivo del processo:
```java
System.out.println("Process completed Successfully");
```
## Conclusione
In questo tutorial, abbiamo esplorato come leggere le proprietà della valuta dai file di Microsoft Project utilizzando Aspose.Tasks per Java. Seguendo i passaggi descritti, puoi estrarre facilmente informazioni relative alla valuta dai file di progetto in modo programmatico, consentendo un'integrazione perfetta nelle tue applicazioni Java.
## Domande frequenti
### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?
R: Aspose.Tasks supporta varie versioni di Microsoft Project, inclusi i file MPP generati da MS Project 2003-2021.
### D: Posso modificare le proprietà della valuta utilizzando Aspose.Tasks?
R: Sì, Aspose.Tasks consente di leggere e modificare le proprietà della valuta nei file MS Project a livello di codice.
### D: Aspose.Tasks è adatto per l'uso commerciale?
 R: Sì, Aspose.Tasks è una libreria commerciale progettata per uso professionale. È possibile acquistare una licenza[Qui](https://purchase.aspose.com/buy).
### D: Aspose.Tasks offre una prova gratuita?
 R: Sì, puoi usufruire di una prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### D: Dove posso cercare aiuto o supporto per Aspose.Tasks?
 R: È possibile visitare il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.