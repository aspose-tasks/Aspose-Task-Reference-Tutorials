---
date: 2026-10-31
description: Scopri come salvare il progetto come PDF e leggere il database di Microsoft
  Project con Aspose.Tasks per Java, oltre a connettersi a Project Server, convertire
  il progetto in HTML e esportare il progetto in XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Lettura dei dati del progetto dal database di Microsoft Project in Aspose.Tasks
og_description: Salva il progetto come PDF e leggi il database di Microsoft Project
  usando Aspose.Tasks per Java. Scopri come connettersi a Project Server, esportare
  in HTML, XML e CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Salva il progetto come PDF e leggi il database di Microsoft Project con
  Aspose.Tasks per Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Salva il progetto come PDF e leggi il database di Microsoft Project con Aspose.Tasks
  per Java
url: /it/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva il progetto come PDF e leggi il database di Microsoft Project con Aspose.Tasks per Java

## Introduzione
In questo tutorial scoprirai come **leggere il database di Microsoft Project** direttamente da un Microsoft Project Server e poi **salvare il progetto come PDF** utilizzando l'API Aspose.Tasks per Java. Che tu abbia bisogno di generare report stampabili, migrare dati legacy o incorporare informazioni di progetto in un portale personalizzato, questa guida ti accompagna passo dopo passo—dalla configurazione della connessione JDBC all'esportazione del progetto in PDF, XML o HTML. Alla fine, avrai una soluzione pronta per la produzione che gira su qualsiasi server Java senza installare Microsoft Project.

## Risposte rapide
- **Cosa fa Aspose.Tasks?** Fornisce un'API pure‑Java per leggere, scrivere e manipolare file e database di Microsoft Project.  
- **È necessario avere Microsoft Project installato?** No, Aspose.Tasks funziona indipendentemente da Microsoft Project.  
- **Quale tipo di database è supportato?** Microsoft SQL Server, il backend di Project Server.  
- **Posso esportare in altri formati?** Sì—PDF, XML, HTML, CSV, PNG, JPEG e altro.  
- **Quali sono i prerequisiti principali?** JDK 8 o superiore, libreria Aspose.Tasks per Java, driver JDBC per SQL Server e credenziali valide per Project Server.

## Cos'è “leggere il database di Microsoft Project”?
Leggere un database di Microsoft Project significa connettersi al repository SQL Server di Project Server, estrarre i dati di progetto memorizzati e caricarli in un oggetto `Project` che Aspose.Tasks può manipolare. Questo approccio è ideale per report automatizzati, migrazioni di dati o analisi personalizzate.

## Perché usare Aspose.Tasks per Java?
Aspose.Tasks per Java ti consente di lavorare con i dati di Microsoft Project senza l'applicazione desktop, offrendo una soluzione pure‑Java che gira su qualsiasi piattaforma. Fornisce un modello di oggetti completo per attività, risorse, calendari e campi personalizzati, e può gestire progetti aziendali di grandi dimensioni in modo efficiente, rendendolo ideale per report automatizzati, migrazioni e scenari di integrazione.

- **Nessuna dipendenza da Microsoft Project** – esegui su qualsiasi server o ambiente CI.  
- **Modello di oggetti ricco** – accedi programmaticamente a attività, risorse, assegnazioni, calendari e campi personalizzati.  
- **Opzioni di esportazione multiple** – Aspose.Tasks supporta l'esportazione in **oltre 20 formati di file**, inclusi PDF, XML, HTML, CSV, PNG e JPEG, con una singola chiamata API.  
- **Alte prestazioni** – la libreria può elaborare progetti contenenti **fino a 10.000 attività** in meno di un minuto e trasmette i dati in streaming per evitare di caricare l'intero file in memoria.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. Un ambiente di sviluppo Java funzionante (JDK 8 o superiore).  
2. La libreria Aspose.Tasks per Java aggiunta al classpath del tuo progetto.  
3. Credenziali di accesso al database SQL di Project Server (nome server, porta, nome database, username, password) per connettersi a Project Server.  
4. Il driver JDBC Microsoft per SQL Server (ad es., `sqljdbc4.jar`).  

## Importa i pacchetti
Per prima cosa, importa le classi necessarie. L'elenco comprende le classi core di Aspose.Tasks e le utility standard di Java.

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

## Come connettersi a Project Server
Stabilire una connessione affidabile è la base per leggere i dati di progetto. Assicurati che l'istanza di SQL Server sia raggiungibile dal tuo host Java e che il login utilizzato abbia permessi **SELECT** sullo schema di Project Server. Verifica anche la latenza di rete e configura eventuali impostazioni SSL richieste per garantire una comunicazione sicura.

## Passo 1: configurare la connessione al database
La classe `MspDbSettings` incapsula i dettagli della connessione JDBC necessari per accedere a un database Microsoft Project Server. Crea un'istanza di `MspDbSettings` che contenga la stringa di connessione JDBC. Sostituisci i valori segnaposto con i dettagli reali del tuo server.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Suggerimento professionale:** Conserva la stringa di connessione in un file di configurazione sicuro o in una variabile d'ambiente anziché codificare le credenziali in chiaro.

## Passo 2: aggiungere il driver JDBC
Carica il driver JDBC di Microsoft SQL Server a runtime così la JVM può comunicare con il database.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Attenzione:** Assicurati che la versione del driver corrisponda alla tua versione di SQL Server. Un driver incompatibile può provocare **errori di connessione**.

## Passo 3: leggere i dati del progetto
La classe `Project` rappresenta un file Microsoft Project caricato in memoria, esponendo attività, risorse e assegnazioni. Istanzia un oggetto `Project` passando `MspDbSettings`. Aspose.Tasks recupererà automaticamente i dati del progetto dal database.

```java
Project project = new Project(settings);
```

A questo punto puoi esplorare l'oggetto `project`—elencare attività, risorse o modificare i campi secondo necessità.

## Passo 4: salvare il progetto come PDF
L'enumerazione `SaveFileFormat` definisce il formato di output per il metodo `Project.save`, come PDF, XML o HTML. Esporta il progetto caricato nel formato desiderato. L'esempio seguente salva il progetto come **PDF**, ideale per report stampabili. Puoi anche **esportare il progetto in XML** o **convertire il progetto in HTML** modificando l'enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Se preferisci XML, sostituisci semplicemente `SaveFileFormat.Pdf` con `SaveFileFormat.Xml`. Per l'output HTML, usa `SaveFileFormat.Html`.

## Problemi comuni & soluzioni
| Problema | Causa tipica | Soluzione |
|----------|--------------|-----------|
| **Timeout di connessione** | Server/porta errati o firewall che blocca | Verifica l'indirizzo del server, apri la porta 1433 e testa la connettività con un semplice programma di test JDBC. |
| **Errore di autenticazione** | Nome utente/password non validi o SQL Server non configurato per l'autenticazione SQL | Usa un login SQL valido o abilita l'autenticazione a modalità mista sul server. |
| **Driver non trovato** | Jar JDBC non presente nel classpath | Assicurati che `addJDBCDriver` punti al file `.jar` corretto e che il percorso utilizzi doppi backslash (`\\`). |
| **Progetto vuoto dopo il caricamento** | Permessi insufficienti per leggere le tabelle di Project Server | Concedi al login i diritti SELECT sullo schema del database di Project Server. |

## Domande frequenti

**D: Aspose.Tasks può essere usato per leggere dati di progetto da altri database oltre a Microsoft Project?**  
R: Sì, Aspose.Tasks supporta la lettura di dati di progetto da file XML, database Primavera e altri formati di progetto standard.

**D: Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?**  
R: Sì, la libreria funziona con Microsoft Project 2007 fino alle ultime versioni 2024, garantendo un'integrazione fluida tra le versioni.

**D: Posso manipolare i dati del progetto prima di salvarli?**  
R: Assolutamente sì, puoi aggiungere, aggiornare o eliminare attività, risorse e campi personalizzati usando la ricca API prima dell'esportazione.

**D: Aspose.Tasks supporta più formati di output?**  
R: Sì, puoi salvare i progetti come PDF, XML, HTML, CSV, PNG, JPEG e altro—oltre 20 formati in totale.

**D: Dove posso trovare ulteriore supporto o assistenza su Aspose.Tasks?**  
R: Per ulteriore aiuto, visita il forum Aspose.Tasks o consulta la documentazione disponibile sul sito web [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusione
Seguendo questa guida passo‑passo, ora sai come **leggere il database di Microsoft Project**, **salvare il progetto come PDF** e esportare in altri formati usando Aspose.Tasks per Java. Questo approccio elimina la dipendenza da Microsoft Project, semplifica la generazione di report automatizzati e apre la porta a potenti integrazioni personalizzate.

---

**Ultimo aggiornamento:** 2026-10-31  
**Testato con:** Aspose.Tasks per Java 24.5 (ultima versione al momento della stesura)  
**Autore:** Aspose

## Tutorial correlati

- [How to Save Project as PDF with Aspose.Tasks – Export Guide](/tasks/java/project-file-operations/save-as-pdf/)
- [Save Project as PDF – Render Task Sheet with Aspose.Tasks for Java](/tasks/java/task-properties/render-task-sheet/)
- [Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}