---
date: 2026-01-25
description: Scopri come aggiungere un attributo alle attività usando Aspose.Tasks
  per Java, personalizzando i file Microsoft Project con attributi estesi per un migliore
  controllo del progetto.
linktitle: Add Extended Attributes to Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come aggiungere un attributo – Aggiungere attributi estesi alle attività in
  Aspose.Tasks
url: /it/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un attributo – Aggiungere attributi estesi alle attività in Aspose.Tasks

## Introduzione
Migliorare le tue capacità di gestione dei progetti è fondamentale per un monitoraggio efficiente delle attività e una gestione ottimale delle risorse. In questo tutorial, **imparerai come aggiungere un attributo** alle attività con Aspose.Tasks per Java, offrendoti la flessibilità di personalizzare i file Microsoft Project in base alle esigenze specifiche della tua organizzazione. Ti guideremo attraverso l'intero processo passo dopo passo, dalla configurazione dell'ambiente al salvataggio del file di progetto aggiornato.

## Risposte rapide
- **Qual è lo scopo principale?** Aggiungere attributi personalizzati (estesi) alle attività in un file Microsoft Project.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso aggiungere valori di ricerca?** Sì – è possibile creare attributi di tipo testo o durata con elenchi di ricerca predefiniti.  
- **Quali formati di file sono supportati per il salvataggio?** MPP, XML e altri formati supportati da Aspose.Tasks.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Tasks per Java installata. Puoi scaricarla dal [sito web](https://releases.aspose.com/tasks/java/).  
- Un ambiente di sviluppo integrato (IDE) Java installato sul tuo sistema.

## Importare i pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per accedere alle funzionalità di Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```

Ora, analizziamo ogni esempio in più passaggi:

## Come aggiungere un attributo a un'attività (Esempio di testo semplice)
### 1. Impostare la directory del documento
Per prima cosa, definisci la cartella che contiene il tuo file di progetto sorgente:
```java
String dataDir = "Your Document Directory";
```

### 2. Caricare il progetto
Crea un'istanza `Project` che punti a un file `.mpp` esistente:
```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. Definire un attributo esteso di testo semplice
Crea una definizione di attributo di tipo **Text1** – questo conterrà il nome della città per ogni attività:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 4. Aggiungere la definizione al progetto
Registra la nuova definizione nella collezione di attributi estesi del progetto:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 5. Creare una nuova attività
Aggiungi un'attività figlia sotto l'attività radice:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 6. Istanziare l'attributo esteso
Genera un'istanza reale dell'attributo dalla definizione creata in precedenza:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 7. Assegnare un valore
Imposta il valore concreto (ad es., la città “London”) per l'attributo esteso di questa attività:
```java
taskExtendedAttributeText1.setTextValue("London");
```

### 8. Collegare l'attributo all'attività
Aggiungi l'attributo popolato alla collezione dell'attività:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

### 9. Salvare il progetto aggiornato
Infine, persisti le modifiche in un nuovo file così da poter verificare il risultato in Microsoft Project:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Aggiungere un attributo di testo con opzione di ricerca
Per creare un attributo di testo che offra un elenco predefinito di valori (lookup), ripeti i passaggi sopra, ma sostituisci `ExtendedAttributeTask.Text1` con `ExtendedAttributeTask.Text2` e popola la tabella di lookup usando `taskExtendedAttributeText2Definition.getLookupValues().add(...)`. Questo consente agli utenti di scegliere da un set fisso di opzioni durante la modifica dell'attività.

## Aggiungere un attributo di durata con opzione di ricerca
Analogamente, per un attributo basato su durata, utilizza `CustomFieldType.Duration` e `ExtendedAttributeTask.Duration2`. Popola i valori di lookup con intervalli di tempo specifici (ad es., “1 day”, “2 weeks”) per standardizzare le voci di durata in tutto il progetto.

## Perché utilizzare gli attributi estesi?
- **Flessibilità:** Memorizzare qualsiasi dato personalizzato non coperto dai campi predefiniti di Project.  
- **Standardizzazione:** Le tabelle di ricerca garantiscono inserimenti di dati coerenti.  
- **Reporting:** I campi personalizzati possono essere inclusi nei report e nei filtri, fornendo approfondimenti più dettagliati.

## Problemi comuni e risoluzione
- **Percorso non valido:** Assicurati che `dataDir` termini con un separatore di file (`/` o `\\`) appropriato per il tuo OS.  
- **Eccezioni di licenza:** Senza una licenza valida, la libreria funziona in modalità di valutazione e può aggiungere filigrane.  
- **Lookup non visualizzato:** Dopo aver definito i valori di ricerca, aggiungi sempre la definizione al progetto prima di creare gli attributi delle attività.

## Domande frequenti
### Q: Posso usare Aspose.Tasks per Java con altre librerie Java?
A: Sì, Aspose.Tasks per Java può essere integrato senza problemi nei tuoi progetti Java e funziona bene con altre librerie Java.

### Q: Aspose.Tasks per Java è adatto per applicazioni di gestione progetti su larga scala?
A: Assolutamente, Aspose.Tasks per Java è progettato per gestire progetti di varie dimensioni, comprese le applicazioni su larga scala.

### Q: Ci sono considerazioni di licenza per l'uso di Aspose.Tasks per Java in un progetto commerciale?
A: Sì, assicurati di consultare le informazioni sulla licenza fornite sul [sito web di Aspose.Tasks](https://purchase.aspose.com/buy).

### Q: Come posso ottenere supporto o assistenza per Aspose.Tasks per Java?
A: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto della community e discussioni.

### Q: Posso provare Aspose.Tasks per Java prima di acquistarlo?
A: Sì, puoi accedere a una versione di prova gratuita [qui](https://releases.aspose.com/).

**Domande aggiuntive**

**Q: Posso aggiungere più attributi estesi a una singola attività?**  
A: Sì, crea semplicemente ulteriori istanze `ExtendedAttribute` e aggiungile alla collezione `ExtendedAttributes` dell'attività.

**Q: I valori di lookup supportano la localizzazione?**  
A: I valori di lookup sono memorizzati come stringhe semplici, quindi puoi fornire testo localizzato per ogni voce secondo necessità.

## Conclusione
Seguendo questa guida passo dopo passo, **hai imparato come aggiungere un attributo** alle attività nei file Microsoft Project usando Aspose.Tasks per Java. Questa potente personalizzazione ti consente di catturare dati specifici del progetto, migliorare il reporting e mantenere la coerenza nei programmi della tua organizzazione.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}