---
date: 2026-01-13
description: Scopri come creare un attributo personalizzato, caricare un file Microsoft
  Project, impostare un valore numerico in Java e salvare il progetto come XML con
  Aspose.Tasks per Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come creare un attributo personalizzato in MS Project usando Aspose.Tasks
url: /it/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un attributo personalizzato in MS Project con Aspose.Tasks

## Introduzione
In questo tutorial, **scoprirai come creare un attributo personalizzato** per le risorse in un file Microsoft Project usando Aspose.Tasks per Java. Vedremo come caricare un file Microsoft Project, definire un nuovo attributo numerico, assegnare un valore e infine salvare il progetto in formato XML. Alla fine, avrai un esempio pratico e chiaro da adattare alle tue soluzioni di gestione progetti.

## Risposte rapide
- **Cosa significa “attributo personalizzato”?**  
  Un campo definito dall'utente che memorizza informazioni aggiuntive (ad es., Età, Livello di competenza) per una risorsa o un'attività.  
- **Quale libreria gestisce questo?**  
  Aspose.Tasks per Java fornisce un'API fluida per creare e gestire attributi personalizzati.  
- **È necessaria una licenza?**  
  Una licenza temporanea gratuita è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Posso impostare valori numerici?**  
  Sì – usa `setNumericValue` con un `BigDecimal` (ad es., `30.5345`).  
- **Come viene salvato il progetto?**  
  Il file modificato può essere salvato come XML usando `SaveFileFormat.Xml`.

## Che cos'è un attributo personalizzato?
Un **attributo personalizzato** (chiamato anche attributo esteso) è una colonna aggiuntiva che puoi inserire nelle risorse o nelle attività di Microsoft Project. Consente di acquisire dati non coperti dai campi predefiniti, come l'età dei dipendenti, il livello di certificazione o qualsiasi metrica specifica per il tuo business.

## Perché creare un attributo personalizzato in MS Project?
- **Adattare i dati del progetto** alle esigenze della tua organizzazione.  
- **Abilitare report avanzati** memorizzando valori che potranno essere interrogati in seguito.  
- **Mantenere la coerenza** tra più progetti applicando programmaticamente la stessa definizione di attributo.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Ambiente di sviluppo Java** – JDK 8 o superiore installato.  
2. **Aspose.Tasks per Java** – Scarica l'ultima versione da [qui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA o qualsiasi IDE compatibile con Java.  

## Guida passo‑passo

### Importare i pacchetti
Per prima cosa, importa le classi di Aspose.Tasks necessarie. Esse forniscono le funzionalità di base per gestire progetti, risorse e attributi estesi.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Passo 1: Definire la directory dei dati
Imposta la cartella in cui si trova il file di progetto di origine e dove verrà scritto l'output.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: Caricare il file Microsoft Project
Crea un'istanza di `Project` caricando il file esistente. Questo è il **passo di caricamento del file Microsoft Project** che ti dà pieno accesso al suo contenuto.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Passo 3: Definire l'attributo personalizzato
Definiremo un nuovo attributo numerico chiamato **Age**. L'API verifica se la definizione esiste già; in caso contrario, ne crea una.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Passo 4: Impostare il valore numerico in Java
Crea un'istanza dell'attributo per una risorsa specifica e assegna un valore numerico usando `setNumericValue`. Questo dimostra **set numeric value java** in azione.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Passo 5: Aggiungere la risorsa e collegare l'attributo personalizzato
Aggiungi una nuova risorsa denominata **R1** e collega l'attributo personalizzato creato in precedenza.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Passo 6: Salvare il progetto come XML
Infine, persisti le modifiche salvando il progetto. Questo è il **passo di salvataggio del progetto come xml**, che produce una rappresentazione XML pulita del file aggiornato.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Passo 7: Visualizzare il risultato
Stampa una conferma amichevole così sai che il processo è terminato senza errori.

```java
System.out.println("Process completed Successfully");
```

Seguendo questi passaggi, hai **creato con successo un attributo personalizzato**, caricato un file Microsoft Project, impostato un valore numerico usando Java e salvato il progetto come XML.

## Problemi comuni e consigli
- **Conflitti di ID attributo:** Controlla sempre `getById` prima di creare una nuova definizione per evitare ID duplicati.  
- **Gestione della precisione:** `BigDecimal` preserva la precisione decimale; evita di usare `float` o `double` per valori esatti.  
- **Percorsi dei file:** Usa percorsi assoluti o configura la directory di lavoro del tuo IDE per prevenire `FileNotFoundException`.  

## Domande frequenti

**D: Posso creare attributi personalizzati anche per le attività, oltre che per le risorse?**  
R: Sì – usa `ExtendedAttributeTask` invece di `ExtendedAttributeResource` quando definisci l'attributo.

**D: È possibile aggiungere più attributi personalizzati contemporaneamente?**  
R: Assolutamente. Crea oggetti `ExtendedAttributeDefinition` separati per ciascun attributo e collegali alle risorse o alle attività desiderate.

**D: In quali formati posso salvare il progetto?**  
R: Aspose.Tasks supporta XML, MPP e diversi altri formati come PDF e HTML. In questo esempio abbiamo usato `SaveFileFormat.Xml`.

**D: È necessaria una licenza Aspose.Tasks per le build di sviluppo?**  
R: Una licenza temporanea è sufficiente per la valutazione. Per le distribuzioni in produzione è richiesta una licenza completa.

**D: Come leggere in seguito i valori degli attributi personalizzati?**  
R: Usa `resource.getExtendedAttributes()` per iterare sugli attributi collegati e recuperare i valori con `getNumericValue()` o `getTextValue()`.

## Conclusione
Creare un **attributo personalizzato** in Microsoft Project con Aspose.Tasks per Java è semplice una volta compreso il flusso di lavoro: carica il progetto, definisci l'attributo, imposta il valore, collegalo a una risorsa e salva il file. Questo approccio ti consente di estendere programmaticamente i modelli di dati del progetto, abilitando report più ricchi e un'integrazione più stretta con i processi aziendali.

---

**Ultimo aggiornamento:** 2026-01-13  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}