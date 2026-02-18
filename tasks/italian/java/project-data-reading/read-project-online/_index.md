---
date: 2026-02-18
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
Nel campo della gestione dei progetti, gestire i dati di Microsoft Project Online in modo efficiente è fondamentale per operazioni semplificate. **aspose tasks java** fornisce un'API robusta e facile da usare che consente di leggere i dati di Project Online senza doversi occupare di chiamate HTTP a basso livello. In questo tutorial vedremo come recuperare un elenco di progetti, **elencare i progetti SharePoint**, e **ottenere il conteggio delle risorse** da ciascun progetto—tutto con poche righe di codice Java.

## Risposte rapide
- **Cosa fa aspose tasks java?** Legge e manipola i file Microsoft Project e i dati di Project Online in modo programmatico.  
- **Ho bisogno di una licenza per provarlo?** È disponibile una prova gratuita; è necessaria una licenza per l'uso in produzione.  
- **Quali credenziali sono richieste?** Dominio SharePoint, nome utente e password (o token Azure AD).  
- **Posso elencare i progetti SharePoint?** Sì – usa `ProjectServerManager.getProjectList()` per recuperarli.  
- **Come ottengo il conteggio delle risorse?** Carica ogni oggetto `Project` e chiama `project.getResources().size()`.

## Cos'è aspose tasks java?
**aspose tasks java** è una libreria orientata agli sviluppatori che astrae le complessità dei formati di file di Microsoft Project e della Project Server REST API. Consente di leggere, creare e modificare i dati di progetto direttamente da applicazioni Java, rendendo l'integrazione con i sistemi aziendali esistenti semplice.

## Perché usare aspose tasks java per leggere MS Project Online?
- **Nessuna gestione manuale di HTTP** – la libreria si occupa dell'autenticazione e delle chiamate REST.  
- **Forte tipizzazione** – lavora con `Project`, `ProjectInfo` e altri POJO invece di JSON grezzo.  
- **Cross‑platform** – funziona su qualsiasi ambiente compatibile con JVM.  
- **Set di funzionalità ricco** – oltre alla lettura, è possibile aggiornare attività, risorse e linee temporali.  
- **Utilizza internamente la Project Server REST API**, così ottieni uno strato di comunicazione stabile e supportato.

## Prerequisiti
1. **Java Development Kit (JDK)** – JDK 8 o superiore installato.  
2. **Aspose.Tasks for Java library** – scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – con permessi per leggere i progetti.  
4. **SharePoint domain address** – dove risiede la tua istanza di Project Online.  
5. **Username and password** – o credenziali Azure AD appropriate per l'autenticazione.

## Importazione dei pacchetti
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

## Passo 2: Autenticarsi con le credenziali di Project Server
Crea un oggetto `ProjectServerCredentials` e inizializza un `ProjectServerManager`. Questo manager gestirà tutte le chiamate successive a Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Passo 3: Recuperare l'elenco dei progetti e visualizzare le informazioni
Usa il manager per **recuperare l'elenco dei progetti** (cioè, elencare i progetti SharePoint) e stampare dettagli di base come nome, data di creazione e data dell'ultimo salvataggio.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Passo 4: Caricare i singoli progetti e visualizzare il conteggio delle risorse
Per ogni progetto restituito nel passo precedente, carica l'oggetto `Project` completo—questa chiamata **carica i dati del progetto** per l'ID specifico—e visualizza il **conteggio delle risorse**.

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
| **`reader.getProjectList()` returns empty** | L'account non ha accesso a nessun progetto. | Verifica i permessi su Project Online o utilizza un account amministratore. |
| **Large projects cause OutOfMemoryError** | Caricare molti progetti contemporaneamente consuma memoria. | Carica i progetti uno alla volta e rilascia i riferimenti dopo l'uso. |

## Domande frequenti
**Q:** Posso usare aspose tasks java per modificare i dati di MS Project Online?  
**A:** Sì, Aspose.Tasks offre ampie capacità sia per la lettura **che** per la modifica dei dati di Project Online in modo programmatico.

**Q:** Aspose.Tasks supporta altri formati di file di gestione progetti?  
**A:** Assolutamente. Supporta MPP, XML, Primavera e molti altri, garantendo la compatibilità attraverso diversi ecosistemi di progetto.

**Q:** È disponibile una prova gratuita per Aspose.Tasks per Java?  
**A:** Sì, puoi usufruire di una prova gratuita da [here](https://releases.aspose.com/) per esplorare le funzionalità di Aspose.Tasks.

**Q:** Dove posso trovare la documentazione completa per Aspose.Tasks per Java?  
**A:** Puoi consultare la documentazione dettagliata [here](https://reference.aspose.com/tasks/java/) per una guida completa sull'utilizzo di Aspose.Tasks nei tuoi progetti Java.

**Q:** Quali opzioni di supporto sono disponibili per Aspose.Tasks per Java?  
**A:** Se incontri problemi o hai domande, puoi richiedere assistenza sul forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-02-18  
**Testato con:** Aspose.Tasks for Java 24.11 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}