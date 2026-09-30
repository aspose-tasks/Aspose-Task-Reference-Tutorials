---
date: 2026-09-30
description: Scopri come creare un attributo esteso di attività utilizzando Aspose.Tasks
  per Java, la principale libreria Java di gestione progetti per aggiungere campi
  personalizzati alle attività.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Come creare un attributo esteso di attività con Aspose.Tasks Java
og_description: Scopri come creare un attributo esteso di attività utilizzando Aspose.Tasks
  per Java, la principale libreria Java di gestione progetti per aggiungere campi
  personalizzati alle attività.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Come creare un attributo esteso di attività con Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Come creare un attributo esteso di attività con Aspose.Tasks Java
url: /it/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un attributo esteso per attività con Aspose.Tasks Java

## Introduzione
In questo tutorial imparerai a **create task extended attribute** in un file Microsoft Project utilizzando Aspose.Tasks per Java. L'aggiunta di campi personalizzati consente di acquisire dati specifici del progetto non coperti dalle colonne predefinite, offrendo un controllo più dettagliato su report e pianificazione delle risorse. Alla fine della guida sarai in grado di aggiungere attributi di testo semplice, con ricerca e di durata a qualsiasi attività.

## Risposte rapide
- **Cosa significa “extended attribute”?** È un campo personalizzato che definisci e alleghi a attività, risorse o assegnazioni.  
- **Quale libreria aggiunge questa funzionalità?** Aspose.Tasks per Java, una libreria di gestione progetti Java.  
- **È necessaria una licenza per provarla?** Sì – è disponibile una prova gratuita di 30 giorni dal sito Aspose.  
- **Posso aggiungere valori di lookup?** Assolutamente; puoi fornire un elenco di valori consentiti per campi di testo o durata.  
- **L'API è compatibile con Java 8 e successive?** Sì, supporta Java 8+ e funziona su tutti i principali sistemi operativi.

## Che cos'è un attributo esteso per attività?
Un attributo esteso per attività è una colonna definita dall'utente che memorizza informazioni aggiuntive per ciascuna attività in un file Project. Si comporta come un campo predefinito ma può contenere qualsiasi tipo di dato necessario, come testo, numeri, date o durate.

## Perché usare Aspose.Tasks per Java?
Aspose.Tasks supporta **50+ formati di file** e può elaborare progetti con **10.000+ attività** senza richiedere l'installazione di Microsoft Project. La libreria funziona completamente offline, garantendo privacy dei dati e prestazioni deterministiche per soluzioni a livello enterprise.

## Prerequisiti
- Conoscenze di base della programmazione Java.  
- La libreria Aspose.Tasks per Java installata. Puoi scaricarla dal [website](https://releases.aspose.com/tasks/java/).  
- Un IDE Java (IntelliJ IDEA, Eclipse o VS Code) configurato sulla tua macchina.

## Importare i pacchetti
Le istruzioni `import` ti danno accesso alle classi core di cui avrai bisogno, come `Project`, `ExtendedAttributeDefinition` e `ExtendedAttribute`.  

`Project` rappresenta un file Microsoft Project e fornisce metodi per leggere, modificare e salvare il file.  
`ExtendedAttributeDefinition` definisce un campo personalizzato che può essere allegato a attività, risorse o assegnazioni.  
`ExtendedAttribute` è un'istanza di una definizione che contiene il valore reale per una specifica entità.

## Come aggiungere un attributo esteso di testo semplice a un'attività?
Per aggiungere un attributo esteso di testo semplice, prima carichi il progetto, poi crei una definizione di tipo Text, la aggiungi alla collezione del progetto, crei un'attività, istanzi l'attributo dalla definizione, imposti il suo valore di testo, lo alleghi all'attività e infine salvi il progetto.

### 1. Impostare il percorso della directory dei documenti
Specifica dove risiedono i tuoi file di origine e di output.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Creare un nuovo progetto
Instanzia un oggetto `Project`, opzionalmente caricando un file .mpp esistente.

```java
String dataDir = "Your Document Directory";
```

### 3. Creare una definizione di attributo esteso di tipo Text1
Definisci il campo personalizzato come una colonna di testo semplice denominata “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Aggiungere la definizione alla collezione di attributi estesi del progetto
Registra la nuova definizione affinché il progetto la riconosca.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Aggiungere un'attività al progetto
Crea un'attività che riceverà il campo personalizzato.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Creare un attributo esteso dalla definizione dell'attributo
Genera un'istanza che puoi collegare a un'attività specifica.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Assegnare un valore all'attributo esteso generato
Imposta il testo effettivo da memorizzare, ad esempio “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Aggiungere l'attributo esteso all'attività
Allega l'istanza dell'attributo alla collezione `ExtendedAttributes` dell'attività.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Salvare il progetto
Scrivi il progetto aggiornato su disco nel formato desiderato.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Come aggiungere un attributo di testo con opzione di lookup?
Quando aggiungi un attributo di testo con lookup, segui gli stessi passaggi di un attributo di testo semplice, ma prima di aggiungere la definizione popoli la sua collezione `LookupValues` con le stringhe consentite. Questi valori appaiono come un elenco a discesa in Microsoft Project, garantendo coerenza dei dati.

## Come aggiungere un attributo di durata con opzione di lookup?
Per aggiungere un attributo di durata con lookup, sostituisci il tipo `Text1` con `Duration2` durante la creazione della definizione, quindi riempi la collezione `LookupValues` con stringhe di durata come “1 day”, “2 days”, ecc. Dopo aver aggiunto la definizione al progetto, crea l'istanza dell'attributo, imposta un valore di durata, allegala a un'attività e salva il file.

## Problemi comuni e risoluzione
- **Lookup values not appearing** – Assicurati di aggiungere ogni voce di lookup alla collezione `LookupValues` *prima* di chiamare `project.getExtendedAttributes().add(definition)`.  
- **Attribute value not saved** – Verifica di aggiungere l'istanza `ExtendedAttribute` all'attività *dopo* aver impostato il valore.  
- **File size grows unexpectedly** – Quando lavori con progetti molto grandi, considera di chiamare `project.setSaveOptions(new ProjectSaveOptions())` per abilitare il salvataggio incrementale.

## Domande frequenti

**Q: Posso usare Aspose.Tasks per Java con altre librerie Java?**  
A: Sì, Aspose.Tasks per Java si integra senza problemi con qualsiasi ecosistema Java, inclusi Spring, Hibernate e Apache POI.

**Q: Aspose.Tasks per Java è adatto per applicazioni di gestione progetti su larga scala?**  
A: Assolutamente. La libreria è progettata per gestire progetti con migliaia di attività e supporta lo streaming per mantenere basso l'uso della memoria.

**Q: Ci sono considerazioni di licenza per l'uso di Aspose.Tasks per Java in un progetto commerciale?**  
A: Sì, è necessaria una licenza commerciale valida. Puoi consultare i dettagli sul [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: Come posso ottenere supporto o assistenza per Aspose.Tasks per Java?**  
A: Visita il [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) per aiuto della community, o apri un ticket di supporto tramite il tuo account Aspose.

**Q: Posso provare Aspose.Tasks per Java prima di acquistarlo?**  
A: Sì, puoi accedere a una versione di prova gratuita nella pagina del [Aspose.Tasks free trial](https://releases.aspose.com/).

---

**Last updated:** 2026-09-30  
**Tested with:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Tutorial correlati

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}