---
date: 2026-02-18
description: Scopri come salvare un progetto come PDF e leggere il database di Microsoft
  Project con Aspose.Tasks per Java, oltre a connettersi a Project Server, convertire
  il progetto in HTML ed esportare il progetto in XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salva il progetto come PDF e leggi il DB del progetto con Aspose.Tasks per
  Java
url: /it/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva il progetto come PDF e leggi il database di Microsoft Project con Aspose.Tasks per Java

## Introduzione
In questo tutorial scoprirai come **leggere il database di Microsoft Project** direttamente da un Microsoft Project Server e poi **salvare il progetto come PDF** utilizzando l'API Aspose.Tasks per Java. Che tu debba generare report, migrare dati o integrare le informazioni di progetto nelle tue applicazioni, questa guida ti accompagna passo dopo passo — dall'impostazione della connessione al database all'esportazione del progetto in PDF, XML o HTML. Alla fine avrai una soluzione solida, pronta per la produzione, che funziona senza installare Microsoft Project sulla macchina host.

## Risposte rapide
- **Cosa fa Aspose.Tasks?** Fornisce un'API pure‑Java per leggere, scrivere e manipolare file e database di Microsoft Project.  
- **È necessario avere Microsoft Project installato?** No, Aspose.Tasks funziona in modo indipendente da Microsoft Project.  
- **Quale tipo di database è supportato?** Microsoft SQL Server (il backend di Project Server).  
- **Posso esportare in altri formati?** Sì, oltre al PDF è possibile salvare in XML, HTML, CSV e altro.  
- **Quali sono i prerequisiti principali?** JDK, libreria Aspose.Tasks per Java, driver JDBC per SQL Server e credenziali per **connettersi a Project Server**.

## Cos'è “leggere il database di Microsoft Project”?
Leggere un database di Microsoft Project significa connettersi al repository SQL Server di Project Server, estrarre i dati di progetto memorizzati e caricarli in un oggetto `Project` che Aspose.Tasks può manipolare. Questo approccio è ideale per report automatizzati, migrazione dati o analisi personalizzate.

## Perché usare Aspose.Tasks per Java?
- **Nessuna dipendenza da Microsoft Project** – esegui su qualsiasi server o ambiente CI.  
- **Modello oggetto ricco** – accedi programmaticamente a attività, risorse, assegnazioni, calendari e campi personalizzati.  
- **Molteplici opzioni di esportazione** – PDF, XML, HTML, PNG, ecc., con una singola chiamata API.  
- **Alte prestazioni** – ottimizzato per progetti aziendali di grandi dimensioni.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. Un ambiente di sviluppo Java funzionante (JDK 8 o superiore).  
2. La libreria Aspose.Tasks per Java aggiunta al classpath del tuo progetto.  
3. Credenziali di accesso per il database SQL di Project Server (nome server, porta, nome database, username, password) **per connettersi a Project Server**.  
4. Il driver Microsoft JDBC per SQL Server (ad es., `sqljdbc4.jar`).  

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
Stabilire una connessione affidabile è la base per leggere i dati di progetto. Verifica che l'istanza di SQL Server sia raggiungibile dal tuo host Java e che l'account di login abbia permessi **SELECT** sullo schema di Project Server.

## Passo 1: Configura la connessione al database
Crea un'istanza di `MspDbSettings` che contiene la stringa di connessione JDBC. Sostituisci i valori segnaposto con i dettagli reali del tuo server.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Suggerimento:** Conserva la stringa di connessione in un file di configurazione sicuro o in una variabile d'ambiente anziché codificarla direttamente nel codice.

## Passo 2: Aggiungi il driver JDBC
Carica il driver JDBC di Microsoft SQL Server a runtime così che la JVM possa comunicare con il database.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Attenzione:** Assicurati che la versione del driver corrisponda alla versione del tuo SQL Server. Un driver incompatibile può provocare errori di connessione.

## Passo 3: Leggi i dati del progetto
Istanzia un oggetto `Project` passando l'istanza `MspDbSettings`. Aspose.Tasks recupererà automaticamente i dati del progetto dal database.

```java
Project project = new Project(settings);
```

A questo punto puoi esplorare l'oggetto `project` — elencare attività, risorse o modificare i campi secondo necessità.

## Passo 4: Salva il progetto come PDF
Esporta il progetto caricato nel formato desiderato. L'esempio seguente salva il progetto come **PDF**, ideale per report stampabili. Puoi anche **esportare il progetto in XML** o **convertire il progetto in HTML** modificando l'enumerazione `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Se preferisci XML, sostituisci semplicemente `SaveFileFormat.Pdf` con `SaveFileFormat.Xml`. Per l'output HTML, usa `SaveFileFormat.Html`.

## Problemi comuni e soluzioni
| Problema | Causa tipica | Soluzione |
|----------|--------------|-----------|
| **Timeout di connessione** | Nome server/porta errati o firewall che blocca | Verifica l'indirizzo del server, apri la porta 1433 e testa la connettività con un semplice programma JDBC. |
| **Errore di autenticazione** | Username/password non validi o SQL Server non configurato per l'autenticazione SQL | Usa un login SQL valido o abilita l'autenticazione mista sul server. |
| **Driver non trovato** | Jar JDBC non presente nel classpath | Assicurati che `addJDBCDriver` punti al file `.jar` corretto e che il percorso utilizzi doppi backslash (`\\`). |
| **Progetto vuoto dopo il caricamento** | Permessi insufficienti per leggere le tabelle di Project Server | Concedi al login i diritti SELECT sullo schema del database di Project Server. |

## Domande frequenti

**D: Aspose.Tasks può leggere dati di progetto da altri database oltre a Microsoft Project?**  
R: Sì, Aspose.Tasks supporta la lettura di dati di progetto da varie fonti, inclusi file XML, Primavera e database di Microsoft Project.

**D: Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?**  
R: Sì, Aspose.Tasks è progettato per funzionare con più versioni di Microsoft Project, garantendo un'integrazione senza interruzioni.

**D: Posso manipolare i dati del progetto prima di salvarli?**  
R: Assolutamente sì, Aspose.Tasks offre un'API completa per aggiungere attività, aggiornare risorse e impostare proprietà del progetto prima dell'esportazione.

**D: Aspose.Tasks supporta più formati di output?**  
R: Sì, è possibile salvare i progetti come PDF, XML, HTML, CSV, PNG, JPEG e molto altro.

**D: Dove posso trovare ulteriore supporto o assistenza per Aspose.Tasks?**  
R: Per ulteriore aiuto, visita il forum di Aspose.Tasks o consulta la documentazione disponibile sul sito [here](https://forum.aspose.com/c/tasks/15).

## Conclusione
Seguendo questa guida passo‑passo, ora sai come **leggere il database di Microsoft Project**, **salvare il progetto come PDF** e esportare in altri formati usando Aspose.Tasks per Java. Questo approccio elimina la dipendenza da Microsoft Project, semplifica la generazione automatica di report e apre la porta a potenti integrazioni personalizzate.

---

**Ultimo aggiornamento:** 2026-02-18  
**Testato con:** Aspose.Tasks per Java 24.5 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}