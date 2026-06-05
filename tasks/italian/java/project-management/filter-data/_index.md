---
date: 2026-06-05
description: Scopri come filtrare i file MPP usando Aspose.Tasks per Java, personalizzare
  i criteri di filtro e filtrare le attività per data per ottimizzare la gestione
  dei progetti.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Come filtrare i file MPP usando Aspose.Tasks per Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come filtrare i file MPP usando Aspose.Tasks per Java
url: /it/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come filtrare i file MPP usando Aspose.Tasks per Java

## Introduzione
Se stai lavorando con file Microsoft Project (*.mpp*) in un'applicazione Java, spesso avrai bisogno di **filtrare i file MPP** per isolare le attività, le risorse o le assegnazioni più importanti. In questo tutorial vedremo **come filtrare i file mpp** programmaticamente con Aspose.Tasks per Java, ti mostreremo come **personalizzare i criteri di filtro** e dimostreremo uno scenario pratico di “filtrare le attività per data”. Alla fine avrai uno snippet pronto all'uso che potrai inserire in qualsiasi progetto Java.

## Risposte rapide
- **Che cosa significa “filter mpp”?** Significa estrarre un sottoinsieme di dati del progetto basato su condizioni definite.  
- **Quale libreria gestisce questo?** Aspose.Tasks per Java fornisce un'API completa per creare e applicare filtri.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso filtrare attività, risorse e assegnazioni?** Sì – ogni tipo di entità ha la propria collezione di filtri.  
- **È richiesto Java 8 o superiore?** Aspose.Tasks supporta Java 8 e versioni successive.

## Che cos'è “how to filter mpp” in Java?
`How to filter mpp` è il processo di utilizzo degli oggetti `Filter` di Aspose.Tasks per selezionare solo quegli elementi del progetto che soddisfano predicati specifici come data di inizio, costo o campi personalizzati. Carica un `Project`, recupera un `Filter` e l'API restituisce una collezione che corrisponde ai tuoi criteri, consentendo report mirati o integrazioni successive.

## Perché personalizzare i criteri di filtro?
I criteri di filtro personalizzati ti consentono di mirare a attività ad alto rischio, elementi in ritardo o risorse con budget superato, trasformando un file di progetto enorme in una vista concisa e azionabile. Aspose.Tasks supporta **50+ predefined filter types** e ti permette di creare filtri personalizzati illimitati, riducendo il tempo di setacciamento manuale dei dati fino al 70 %.

## Prerequisiti
1. **Java Development Kit (JDK)** – versione 8 o più recente.  
2. **Aspose.Tasks for Java** – scaricalo dalla [download page](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse o NetBeans funzioneranno bene.  

## Importare i pacchetti
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` e `Project` sono classi core utilizzate per definire e applicare filtri ai dati del progetto.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Guida passo‑passo

### Passo 1: Configurare il progetto
Per prima cosa, crea un'istanza `Project` che punti al file MPP che desideri analizzare, quindi caricala in memoria. Questo unico passaggio prepara l'intero modello di progetto per il filtraggio, la convalida e ulteriori manipolazioni, consentendoti di accedere a attività, risorse e assegnazioni tramite l'API.

### Come configuro il progetto per filtrare i file MPP?
La classe `Project` carica e rappresenta un file MPP in memoria. Crea un'istanza `Project` che punti al file MPP che desideri analizzare, quindi caricala in memoria. Questo unico passaggio prepara l'intero modello di progetto per il filtraggio, la convalida e ulteriori manipolazioni, consentendoti di accedere a attività, risorse e assegnazioni tramite l'API.

### Come posso recuperare e ispezionare un filtro?
Gli oggetti `Filter` racchiudono le definizioni di filtro utilizzate per selezionare gli elementi del progetto. Aspose.Tasks memorizza filtri predefiniti come “All Tasks” o “Critical Tasks”. Usa `project.getTaskFilters().getByName("My Filter")` o l'accesso basato su indice per ottenere un oggetto `Filter`, quindi esamina la sua collezione `FilterCriteria` per vedere ogni regola e l'operatore logico (AND/OR) che le combina, assicurandoti che il filtro soddisfi i tuoi requisiti.

### Come iterare attraverso le righe di criteri nidificate?
`FilterCriteriaGroup` rappresenta un gruppo di criteri di filtro combinati con un operatore logico. I filtri possono contenere gruppi di criteri, ciascuno con il proprio operatore. Scorri `filter.getCriteria().getRows()` e, per ogni riga che è un `FilterCriteriaGroup`, ricorri nelle sue righe figlie. Questo attraversamento ti consente di comprendere appieno la logica di filtro complessa, come “(Start < today AND Cost > 1000) OR Priority = High”, e di modificare i criteri secondo necessità.

### Come stampare le informazioni dei criteri per il debug?
Dopo aver attraversato l'albero dei criteri, stampa su console il nome del campo, l'operatore di test e il valore di ogni riga. Questo semplice dump ti aiuta a verificare che il filtro corrisponda alle regole di business previste prima di applicarlo a progetti di grandi dimensioni, e rende più facile individuare operatori o valori errati.

### Come creare un filtro nuovo di zecca programmaticamente?
Istanzia un `Filter` con `new Filter("My Filter")`, quindi aggiungilo alla collezione di filtri delle attività del progetto usando `project.getTaskFilters().add(filter)`. Successivamente, popola la sua collezione `FilterCriteria` con le righe desiderate, specificando i nomi dei campi, gli operatori di test e i valori per definire esattamente quali attività devono essere incluse quando il filtro viene applicato.

### Posso applicare un filtro alle risorse invece che alle attività?
La collezione `ResourceFilters` contiene le definizioni di filtro applicabili alle risorse. Sì – usa `project.getResourceFilters()` per lavorare con filtri specifici per le risorse nello stesso modo dei filtri per le attività. Dopo aver aggiunto o recuperato un filtro, configura il suo `FilterCriteria` proprio come faresti per le attività, quindi applicalo alla collezione di risorse per ottenere il set filtrato di risorse.

### È possibile combinare più filtri con logica OR?
Crea un `FilterCriteriaGroup` genitore con la sua `Operation` impostata a `OR`, quindi aggiungi oggetti `FilterCriteria` individuali come figli. Questo gruppo valuterà ogni criterio figlio e restituirà gli elementi che soddisfano almeno uno di essi, permettendoti di combinare diversi filtri semplici in una selezione più ampia.

### Aspose.Tasks supporta il filtraggio sui campi personalizzati?
`CustomField` enum fornisce gli identificatori per i campi personalizzati definiti in un progetto. Assolutamente. Riferisci i campi personalizzati tramite l'enum `CustomField`, e si comportano come qualsiasi campo incorporato nelle espressioni di filtro. Puoi includerli nelle righe `FilterCriteria`, usando gli stessi operatori e valori, consentendo query potenti sui dati definiti dall'utente insieme agli attributi standard del progetto.

### Qual è l'impatto sulle prestazioni del filtraggio su file MPP di grandi dimensioni?
Il filtraggio avviene interamente in memoria e tipicamente elabora un progetto di 1.000 attività in meno di 200 ms. Per file con migliaia di attività, considera di caricare solo le sezioni necessarie usando `ProjectReader` e applicare i filtri dopo il caricamento selettivo, il che mantiene basso l'uso della memoria e mantiene tempi di risposta rapidi anche su progetti molto grandi.

**Ultimo aggiornamento:** 2026-06-05  
**Testato con:** Aspose.Tasks for Java 24.10  
**Autore:** Aspose

## Tutorial correlati

- [Carica file MPP Java - Gestisci le proprietà del progetto con Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Lettura senza sforzo dei dati di MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Imposta la data di inizio del progetto in MS Project usando Aspose.Tasks per Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```