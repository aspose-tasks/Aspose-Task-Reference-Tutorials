---
title: Lettura dei dati del progetto dal database MS Project in Aspose.Tasks
linktitle: Lettura dei dati del progetto dal database di Microsoft Project in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come leggere i dati del progetto dal database di Microsoft Project utilizzando Aspose.Tasks per Java. Guida passo passo con esempi di codice.
type: docs
weight: 12
url: /it/java/project-data-reading/read-project-database/
---
## introduzione
In questo tutorial esploreremo come leggere i dati del progetto da un database di Microsoft Project utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente API Java che consente agli sviluppatori di manipolare i documenti di Microsoft Project senza la necessità di installare Microsoft Project. Seguendo i passaggi descritti in questa guida, imparerai come estrarre in modo efficiente i dati di progetto da un database e salvarli nel formato desiderato.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza base della programmazione Java.
2. Java Development Kit (JDK) installato sul tuo sistema.
3. Aspose.Tasks per la libreria Java scaricata e configurata nel tuo progetto.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## Passaggio 1: configurare la connessione al database
Innanzitutto è necessario configurare la connessione al database di Microsoft Project. Ciò include la specifica dell'URL del database, del nome del server, del numero di porta, del nome del database, del nome utente e della password.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Passaggio 2: aggiungi il driver JDBC
Successivamente, devi aggiungere il driver JDBC al tuo progetto. Questo driver facilita la comunicazione tra le applicazioni Java e il database Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Passaggio 3: leggere i dati del progetto
 Ora crea un file`Project` oggetto e caricare i dati del progetto dal database utilizzando le impostazioni definite in precedenza.
```java
Project project = new Project(settings);
```
## Passaggio 4: salvare i dati del progetto
Infine, salva i dati del progetto nel formato desiderato. In questo esempio, lo salviamo come file XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Congratulazioni! Hai letto con successo i dati del progetto da un database di Microsoft Project utilizzando Aspose.Tasks per Java.

## Conclusione
In questo tutorial, abbiamo trattato il processo di lettura dei dati di progetto da un database di Microsoft Project utilizzando Aspose.Tasks per Java. Seguendo i passaggi descritti, puoi estrarre facilmente le informazioni sul progetto e manipolarle in base alle tue esigenze. Aspose.Tasks semplifica la gestione dei documenti di Microsoft Project, consentendo un'efficiente estrazione e manipolazione dei dati.
## Domande frequenti
### D: Aspose.Tasks può essere utilizzato per leggere i dati del progetto da altri database oltre a Microsoft Project?
R: Sì, Aspose.Tasks supporta la lettura dei dati del progetto da varie fonti, inclusi file XML, Primavera e database Microsoft Project.
### D: Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?
R: Sì, Aspose.Tasks è progettato per funzionare con diverse versioni di Microsoft Project, garantendo compatibilità e integrazione perfetta.
### D: Posso manipolare i dati del progetto prima di salvarlo?
R: Assolutamente, Aspose.Tasks fornisce un'ampia gamma di funzionalità per la manipolazione dei dati del progetto, come l'aggiunta di attività, l'aggiornamento delle risorse e l'impostazione delle proprietà del progetto.
### D: Aspose.Tasks supporta più formati di output?
R: Sì, Aspose.Tasks supporta vari formati di output, inclusi XML, PDF, HTML e formati di immagine come PNG e JPEG.
### D: Dove posso trovare ulteriore supporto o assistenza con Aspose.Tasks?
 R: Per ulteriore supporto o assistenza, è possibile visitare il forum Aspose.Tasks o esplorare la documentazione disponibile sul sito Web[Qui](https://forum.aspose.com/c/tasks/15).