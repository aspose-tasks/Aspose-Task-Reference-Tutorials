---
date: 2025-12-15
description: Impara a leggere i dati di MS Project Online usando Aspose.Tasks per
  Java. Questa guida mostra come recuperare l'elenco dei progetti, elencare i progetti
  SharePoint e ottenere il conteggio delle risorse.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Lettura senza sforzo dei dati di MS Project Online'
url: /it/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Lettura senza sforzo dei dati di MS Project Online

## Introduzione
Nel campo della gestione dei progetti, gestire i dati di Microsoft Project Online in modo efficiente è fondamentale per operazioni semplificate. **aspose tasks java** fornisce un'API robusta e facile da usare che consente di leggere i dati di Project Online senza doversi occupare di chiamate HTTP a basso livello. In questo tutorial vedremo come recuperare un elenco di progetti, elencare i progetti SharePoint e ottenere il conteggio delle risorse per ciascun progetto—tutto con poche righe di codice Java.

## Risposte rapide
- **Cosa fa aspose tasks java?** Legge e manipola i file Microsoft Project e i dati di Project Online in modo programmatico.  
- **È necessaria una licenza per provarlo?** È disponibile una versione di prova gratuita; è richiesta una licenza per l'uso in produzione.  
- **Quali credenziali sono richieste?** Dominio SharePoint, nome utente e password (o token Azure AD).  
- **Posso elencare i progetti SharePoint?** Sì – usa `ProjectServerManager.getProjectList()` per recuperarli.  
- **Come ottengo il conteggio delle risorse?** Carica ogni oggetto `Project` e chiama `project.getResources().size()`.

## Cos'è aspose tasks java?
**aspose tasks java** è una libreria orientata agli sviluppatori che astrae le complessità dei formati di file di Microsoft Project e delle REST API di Project Server. Consente di leggere, creare e modificare i dati di progetto direttamente da applicazioni Java, rendendo l'integrazione con i sistemi aziendali esistenti semplice e diretta.

## Perché usare aspose tasks java per leggere MS Project Online?
- **Nessuna gestione manuale di HTTP** – la libreria si occupa dell'autenticazione e delle chiamate REST.  
- **Forte tipizzazione** – lavora con `Project`, `ProjectInfo` e altri POJO invece di JSON grezzo.  
- **Cross‑platform** – funziona su qualsiasi ambiente compatibile con JVM.  
- **Set di funzionalità ricco** – oltre alla lettura, è possibile aggiornare attività, risorse e timeline.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – JDK 8 o superiore installato.  
2. **Libreria Aspose.Tasks per Java** – scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. **Account Microsoft Project Online** – con permessi di lettura sui progetti.  
4. **Indirizzo del dominio SharePoint** – dove risiede la tua istanza di Project Online.  
5. **Nome utente e password** – o credenziali Azure AD appropriate per l'autenticazione.

## Importare i pacchetti
Per prima cosa, importa le classi essenziali di Aspose.Tasks che utilizzeremo durante il tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Passo 1: Impostare dominio SharePoint, nome utente e password
Definisci i dettagli di connessione per il tuo ambiente Project Online. Sostituisci i valori segnaposto con le tue credenziali.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Passo 2: Autenticarsi con le credenziali del Project Server
Crea un oggetto `ProjectServerCredentials` e inizializza un `ProjectServerManager`. Questo manager gestirà tutte le chiamate successive a Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Passo 3: Recuperare l'elenco dei progetti e visualizzare le informazioni
Usa il manager per **recuperare l'elenco dei progetti** (elenco dei progetti SharePoint) e stampa i dettagli di base come nome, data di creazione e data dell'ultimo salvataggio.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Passo 4: Caricare i singoli progetti e mostrare il conteggio delle risorse
Per ogni progetto restituito nel passo precedente, carica l'oggetto `Project` completo e visualizza il **conteggio delle risorse**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Autenticazione fallita** | Dominio, nome utente o password errati. | Verifica le credenziali e assicurati che l'account abbia i permessi di lettura su Project Online. |
| **SSLHandshakeException** | L'ambiente Java non dispone della versione TLS richiesta. | Aggiorna il JDK all'ultima versione o abilita TLS 1.2+. |
| **`reader.getProjectList()` restituisce vuoto** | L'account non ha accesso a progetti. | Controlla i permessi su Project Online o utilizza un account amministratore. |
| **Progetti di grandi dimensioni causano OutOfMemoryError** | Il caricamento simultaneo di molti progetti consuma memoria. | Carica i progetti uno alla volta e rilascia i riferimenti dopo l'uso. |

## Domande frequenti
### D: Posso usare aspose tasks java per modificare i dati di MS Project Online?
R: Sì, Aspose.Tasks offre ampie capacità sia per la lettura **che** per la modifica dei dati di Project Online in modo programmatico.

### D: Aspose.Tasks supporta altri formati di file per la gestione dei progetti?
R: Assolutamente. Supporta MPP, XML, Primavera e molti altri, garantendo compatibilità con diversi ecosistemi di progetto.

### D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?
R: Sì, puoi ottenere una prova gratuita da [here](https://releases.aspose.com/) per esplorare le funzionalità di Aspose.Tasks.

### D: Dove posso trovare la documentazione completa per Aspose.Tasks per Java?
R: Consulta la documentazione dettagliata [here](https://reference.aspose.com/tasks/java/) per una guida completa sull'utilizzo di Aspose.Tasks nei tuoi progetti Java.

### D: Quali opzioni di supporto sono disponibili per Aspose.Tasks per Java?
R: Se incontri problemi o hai domande, puoi chiedere assistenza nel forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2025-12-15  
**Testato con:** Aspose.Tasks per Java 24.11 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}