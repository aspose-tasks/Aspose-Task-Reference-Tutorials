---
date: 2025-12-20
description: Scopri come recuperare i codici di outline di MS Project in modo programmatico
  usando Aspose.Tasks per Java. Migliora le tue capacità di gestione del progetto.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Recupera i codici di struttura di MS Project in Aspose.Tasks
url: /it/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperare i codici di outline di MS Project in Aspose.Tasks

## Introduzione
In questo tutorial, scoprirai **come recuperare i codici di outline di MS Project** usando Aspose.Tasks per Java. I codici di outline in MS Project offrono un modo potente per categorizzare attività, risorse e assegnazioni, e accedervi programmaticamente ti consente di creare report personalizzati, automazione o soluzioni di integrazione. Ti guideremo attraverso un esempio completo, passo‑per‑passo, che potrai copiare nel tuo progetto.

## Risposte rapide
- **Cosa fa il codice?** Carica un file Project e stampa ogni definizione di codice di outline, le sue maschere e i suoi valori.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (qualsiasi versione recente).  
- **È necessaria una licenza?** Una versione di prova funziona per lo sviluppo; è richiesta una licenza completa per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.  
- **Posso modificare i codici dopo averli recuperati?** Sì – la stessa API consente di aggiungere, modificare o eliminare i codici di outline.

## Cosa sono i codici di outline di MS Project?
I codici di outline sono campi personalizzati che consentono ai project manager di raggruppare e filtrare le attività oltre la gerarchia predefinita. Possono essere valori numerici semplici, stringhe o persino codici personalizzati a livello aziendale definiti a livello di organizzazione. Leggendo questi codici, è possibile alimentare dashboard, esportare dati o applicare automaticamente convenzioni di denominazione.

## Perché recuperare i codici di outline di MS Project con Aspose.Tasks?
- **Automazione:** Genera report o attiva flussi di lavoro senza esportazioni manuali.  
- **Integrazione:** Sincronizza i codici di outline con ERP, PPM o strumenti BI.  
- **Personalizzazione:** Applica regole di business basate sui valori dei codici (ad es., allocazione dei costi).  
- **Cross‑platform:** Funziona su Windows, Linux e macOS, indipendente dall’interfaccia di Microsoft Project.

## Prerequisiti
Prima di iniziare, assicurati di aver configurato i seguenti prerequisiti:

### 1. Ambiente di sviluppo Java
Assicurati di avere il Java Development Kit (JDK) installato sul tuo sistema. Puoi scaricare e installare il JDK dal sito web di Oracle.

### 2. Libreria Aspose.Tasks
Scarica e includi la libreria Aspose.Tasks nel tuo progetto Java. Puoi scaricare la libreria dalla [Pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).

## Importare i pacchetti
Per prima cosa, importa i pacchetti necessari da Aspose.Tasks nel tuo codice Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Ora analizziamo il codice di esempio fornito in più passaggi:

## Passo 1: Caricare il progetto
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
In questo passaggio, carichiamo il file Microsoft Project in un oggetto `Project` utilizzando il nome file fornito.

## Passo 2: Recuperare i codici di outline
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Iteriamo attraverso ogni definizione di codice di outline nel progetto.

## Passo 3: Accedere alle proprietà del codice di outline
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Recuperiamo e stampiamo varie proprietà della definizione del codice di outline, come Alias, ID campo e Nome campo.

## Passo 4: Verificare il codice personalizzato aziendale
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Verifichiamo se il codice di outline è un codice personalizzato aziendale e stampiamo il risultato di conseguenza.

## Passo 5: Visualizzare le maschere dei codici di outline
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iteriamo attraverso ogni maschera associata al codice di outline e stampiamo il livello e il valore della maschera.

## Passo 6: Visualizzare i valori dei codici di outline
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Iteriamo attraverso ogni valore del codice di outline e stampiamo la descrizione, l'ID valore, il valore e il tipo.

## Problemi comuni e soluzioni
| Problema | Motivo | Correzione |
|----------|--------|------------|
| **Nessun output** | Percorso del file di progetto errato | Verifica che `projectName` punti a un file `.mpp` valido. |
| **Valori null** | Codice di outline non definito nel file | Assicurati che il file Project contenga effettivamente codici di outline (controlla nell'interfaccia di MS Project). |
| **LicenseException** | Uso della versione di prova senza attivazione corretta | Applica una licenza temporanea o completa tramite `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Domande frequenti

**D: Posso usare Aspose.Tasks per Java per modificare i codici di outline in un file Project?**  
R: Sì, Aspose.Tasks per Java fornisce API per modificare i codici di outline programmaticamente. Puoi aggiungere, modificare o eliminare le definizioni usando lo stesso oggetto `Project`.

**D: È disponibile una versione di prova di Aspose.Tasks per Java?**  
R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java dalla [pagina web di Aspose.Tasks](https://releases.aspose.com/).

**D: Come posso ottenere supporto tecnico per Aspose.Tasks per Java?**  
R: Puoi ottenere supporto tecnico visitando il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) e pubblicando le tue domande lì.

**D: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?**  
R: Sì, puoi acquistare una licenza temporanea per Aspose.Tasks per Java dalla [pagina di acquisto](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare la documentazione completa per Aspose.Tasks per Java?**  
R: Puoi consultare la [documentazione](https://reference.aspose.com/tasks/java/) per informazioni dettagliate sull'uso di Aspose.Tasks per Java.

## Conclusione
In questo tutorial, abbiamo imparato come recuperare **i codici di outline di MS Project** usando Aspose.Tasks per Java. Seguendo i passaggi forniti, potrai accedere e manipolare efficacemente i codici di outline nelle tue applicazioni Java, abilitando capacità avanzate di gestione dei progetti come report personalizzati, automazione e integrazione con altri sistemi aziendali.

---

**Ultimo aggiornamento:** 2025-12-20  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}