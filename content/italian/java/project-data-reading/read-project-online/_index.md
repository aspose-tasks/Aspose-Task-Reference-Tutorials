---
title: Lettura semplice dei dati online di MS Project con Aspose.Tasks
linktitle: Lettura dei dati online del progetto in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come leggere facilmente i dati di Microsoft Project Online utilizzando Aspose.Tasks per Java. Migliora le tue capacità di gestione dei progetti.
type: docs
weight: 13
url: /it/java/project-data-reading/read-project-online/
---
## introduzione
Nell'ambito della gestione dei progetti, la gestione efficiente dei dati di Microsoft Project Online è fondamentale per semplificare le operazioni. Aspose.Tasks per Java fornisce una soluzione solida per leggere tali dati senza sforzo. Questo tutorial approfondisce l'utilizzo di Aspose.Tasks per accedere e manipolare i dati di MS Project Online senza problemi.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere quanto segue:
1. Java Development Kit (JDK): installa JDK per compilare ed eseguire programmi Java.
2.  Aspose.Tasks per Java Library: scarica e includi la libreria Aspose.Tasks nel tuo progetto Java. Puoi acquisirlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Account Microsoft Project Online: ottieni credenziali valide per accedere ai dati di MS Project Online.
4. Indirizzo del dominio SharePoint: l'indirizzo del dominio SharePoint in cui risiedono i dati di MS Project Online.
5. Nome utente e password: credenziali per autenticare l'accesso a MS Project Online.
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti Aspose.Tasks necessari per un'integrazione perfetta:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Passaggio 1: impostare l'indirizzo del dominio, il nome utente e la password di SharePoint
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Sostituire`"https://contoso.sharepoint.com"` con il tuo indirizzo di dominio SharePoint,`"admin@contoso.onmicrosoft.com"` con il tuo nome utente e`"MyPassword"` con la tua password.
## Passaggio 2: autenticarsi con le credenziali di Project Server
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Creare`ProjectServerCredentials` oggetto con l'indirizzo del dominio, il nome utente e la password di SharePoint. Quindi inizializzare`ProjectServerManager` con queste credenziali.
## Passaggio 3: recuperare l'elenco dei progetti e visualizzare le informazioni
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Scorrere l'elenco dei progetti ottenuto da`reader.getProjectList()` e visualizzare i dettagli del progetto come nome, data di creazione e data dell'ultimo salvataggio.
## Passaggio 4: caricare i singoli progetti e il conteggio delle risorse di output
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Per ogni progetto, caricalo utilizzando`reader.getProject(p.getId())` e visualizza il nome del progetto insieme al conteggio delle risorse associate.

## Conclusione
Aspose.Tasks per Java semplifica il processo di lettura dei dati di MS Project Online, offrendo agli sviluppatori un potente set di strumenti per semplificare le attività di gestione dei progetti. Seguendo questo tutorial, puoi integrare in modo efficiente Aspose.Tasks nelle tue applicazioni Java per accedere e manipolare facilmente i dati del progetto.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per Java per modificare i dati di MS Project Online?
R: Sì, Aspose.Tasks offre funzionalità estese non solo per leggere ma anche per modificare i dati di MS Project Online a livello di codice.
### D: Aspose.Tasks supporta altri formati di file di gestione dei progetti?
R: Assolutamente, Aspose.Tasks supporta vari formati di file tra cui MPP, XML e altri, garantendo la compatibilità con diversi sistemi di gestione dei progetti.
### D: È disponibile una prova gratuita per Aspose.Tasks per Java?
 R: Sì, puoi usufruire di una prova gratuita da[Qui](https://releases.aspose.com/) per esplorare le caratteristiche e le funzionalità di Aspose.Tasks.
### D: Dove posso trovare la documentazione completa per Aspose.Tasks per Java?
 R: Puoi fare riferimento alla documentazione dettagliata[Qui](https://reference.aspose.com/tasks/java/)per una guida completa sull'utilizzo di Aspose.Tasks nei tuoi progetti Java.
### D: Quali opzioni di supporto sono disponibili per Aspose.Tasks per Java?
 R: Se riscontri problemi o hai domande, puoi chiedere assistenza al forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).