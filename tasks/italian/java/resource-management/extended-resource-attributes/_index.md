---
date: 2026-06-10
description: Scopri come creare un extended attribute in Java, caricare un file Microsoft
  Project, impostare valori numerici e salvare il progetto come XML utilizzando Aspose.Tasks
  per Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Gestire gli Extended Resource Attributes in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come creare un extended attribute in Java con Aspose.Tasks
url: /it/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un attributo esteso in Java con Aspose.Tasks

## Introduzione
In questa guida pratica **creerai un attributo esteso in Java** per un file Microsoft Project utilizzando Aspose.Tasks. Ti guideremo attraverso il caricamento di un progetto esistente, la definizione di un nuovo attributo numerico, l'assegnazione di un valore a una risorsa e, infine, la persistenza delle modifiche in un file XML. Alla fine avrai uno schema di codice riutilizzabile che potrà essere inserito in qualsiasi soluzione di gestione progetti basata su Java.

## Risposte rapide
- **Cos'è un attributo esteso?**  
  Un campo definito dall'utente (ad es., Età, Livello di competenza) che memorizza dati aggiuntivi per risorse o attività.  
- **Quale API lo crea?**  
  Aspose.Tasks for Java fornisce la classe `ExtendedAttributeDefinition` per definire e gestire attributi personalizzati.  
- **Ho bisogno di una licenza?**  
  Una licenza di valutazione temporanea è sufficiente per lo sviluppo; è necessaria una licenza completa per le distribuzioni in produzione.  
- **Posso memorizzare numeri?**  
  Sì – usa `setNumericValue(BigDecimal)` per assegnare valori decimali precisi.  
- **Come persisto le modifiche?**  
  Chiama `project.save("output.xml", SaveFileFormat.Xml)` per scrivere il progetto aggiornato in formato XML.

## Che cos'è un attributo personalizzato?
Un **attributo personalizzato** (noto anche come attributo esteso) è una colonna aggiuntiva che puoi inserire in risorse o attività in Microsoft Project. Ti consente di catturare dati non coperti dai campi predefiniti, come l'età dei dipendenti, il livello di certificazione o qualsiasi metrica specifica per il tuo business.

## Perché creare un attributo esteso in Java?
Creare un attributo esteso in Java ti permette di arricchire programmaticamente i dati di progetto, garantendo coerenza tra i file e abilitando report automatizzati. Definendo l'attributo una sola volta, puoi applicarlo a qualsiasi numero di risorse o attività senza inserimenti manuali, risparmiando tempo e riducendo gli errori.

- **Adatta i dati alla tua organizzazione** – memorizza qualsiasi metrica importante per te senza soluzioni manuali in Excel.  
- **Abilita report più completi** – interroga il campo personalizzato in seguito per dashboard o analisi.  
- **Mantieni la coerenza** – applica programmaticamente la stessa definizione a decine di progetti, eliminando gli errori umani.  
- **Testato per le prestazioni** – Aspose.Tasks elabora progetti con fino a 10.000 attività e 5.000 risorse senza caricare l'intero file in memoria, secondo i benchmark del prodotto.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit** – JDK 8 o versioni successive installate.  
2. **Aspose.Tasks for Java** – scarica l'ultima versione da [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA o qualsiasi ambiente di sviluppo compatibile con Java.  

## Come creare un attributo esteso in Java?
Carica il tuo progetto, definisci l'attributo, collegalo a una risorsa e salva il file – tutto in pochi passaggi semplici. Le sezioni seguenti suddividono ogni passaggio in una spiegazione concisa seguita dal segnaposto dove inserire il tuo codice reale.

### Guida passo‑passo

#### Importa i pacchetti
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` e le classi correlate risiedono nello spazio dei nomi `com.aspose.tasks`. Importale all'inizio del tuo file Java.

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

#### Passo 1: Definisci la directory dei dati
`Paths` è una classe di utilità che fornisce metodi per ottenere un percorso di file system in modo indipendente dalla piattaforma.

```java
String dataDir = "Your Data Directory";
```

#### Passo 2: Carica il file Microsoft Project
`Project` rappresenta un file Microsoft Project in memoria, consentendo l'accesso in lettura e scrittura al suo contenuto.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Passo 3: Definisci l'attributo personalizzato
`ExtendedAttributeDefinition` definisce lo schema di un nuovo campo personalizzato che può essere collegato a risorse o attività.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Passo 4: Imposta valore numerico in Java
`ExtendedAttributeResource` contiene il valore di un attributo personalizzato per una specifica istanza di risorsa.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Passo 5: Aggiungi risorsa e collega l'attributo personalizzato
`Resource` modella una risorsa di progetto come una persona, attrezzatura o materiale.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Passo 6: Salva il progetto come XML
`SaveFileFormat` enumera i formati di output supportati per il salvataggio di un progetto, incluso XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Passo 7: Visualizza risultato
`System.out.println` stampa una riga di testo sulla console standard.

```java
System.out.println("Process completed Successfully");
```

## Problemi comuni e consigli
- **Conflitti di ID attributo:** chiama sempre `project.getExtendedAttributes().getById(id)` prima di creare una nuova definizione per evitare identificatori duplicati.  
- **Gestione della precisione:** preferisci `BigDecimal` rispetto a `float`/`double` per valori numerici esatti; ciò evita errori di arrotondamento nei report.  
- **Affidabilità del percorso file:** usa `Paths.get(...).toAbsolutePath()` o configura la directory di lavoro del tuo IDE per eliminare `FileNotFoundException`.  

## Domande frequenti

**Q: Posso creare attributi personalizzati sia per le attività che per le risorse?**  
A: Sì – usa `ExtendedAttributeTask` invece di `ExtendedAttributeResource` quando definisci lo schema dell'attributo.

**Q: È possibile aggiungere più attributi personalizzati contemporaneamente?**  
A: Assolutamente. Crea oggetti `ExtendedAttributeDefinition` separati per ciascun attributo e collegali alle risorse o attività desiderate.

**Q: In quali formati posso salvare il progetto?**  
A: Aspose.Tasks supporta XML, MPP, PDF, HTML e oltre 30 formati aggiuntivi. In questo esempio abbiamo usato `SaveFileFormat.Xml`.

**Q: Ho bisogno di una licenza per le build di sviluppo?**  
A: Una licenza di valutazione temporanea è sufficiente per i test. Per qualsiasi distribuzione in produzione, è necessaria una licenza commerciale completa.

**Q: Come leggo in seguito i valori degli attributi personalizzati?**  
A: Chiama `resource.getExtendedAttributes()` e itera sulla collezione; recupera il valore memorizzato con `getNumericValue()` o `getTextValue()`.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutorial correlati

- [Come creare risorse – Gestione risorse con Aspose.Tasks per Java](/tasks/java/resource-management/)
- [Crea campo personalizzato Aspose - Gestisci attributi estesi](/tasks/java/project-management/extended-attributes/)
- [Come creare progetto – Imposta nuovi attributi attività con Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}