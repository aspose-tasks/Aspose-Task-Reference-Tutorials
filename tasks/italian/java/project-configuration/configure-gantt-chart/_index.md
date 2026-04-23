---
date: 2026-02-13
description: Scopri come creare una nuova attività, impostare la directory dei dati
  e salvare il progetto come MPP in Aspose.Tasks Java. Questa guida passo passo copre
  anche la personalizzazione dei campi della tabella.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come creare una nuova attività e impostare la directory dei dati Aspose.Tasks
url: /it/java/project-configuration/configure-gantt-chart/
weight: 10
---

 unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare una nuova attività e impostare la directory dei dati Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come impostare la directory dei dati**, come **creare una nuova attività** e come **salvare il progetto come MPP** configurando la visualizzazione del diagramma di Gantt di MS Project in progetti Aspose.Tasks usando Java. Aspose.Tasks è una robusta API Java che consente di manipolare i file Microsoft Project in modo programmatico. Alla fine di questa guida sarai in grado di **personalizzare i campi della tabella**, regolare la directory dei dati e visualizzare il tuo progetto esattamente come desideri.

## Risposte rapide
- **Qual è il primo passo?** Imposta il percorso della directory dei dati dove risiedono i file del tuo progetto.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (scaricabile dal sito ufficiale).  
- **Posso aggiungere attributi personalizzati?** Sì – puoi definire attributi estesi e mostrarli nel diagramma di Gantt.  
- **Ho bisogno di una licenza per i test?** È disponibile una licenza temporanea per scopi di valutazione.  
- **Quale IDE funziona meglio?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans) funzionerà.

## Che cosa significa “impostare la directory dei dati” e perché è importante?
Impostare la directory dei dati indica ad Aspose.Tasks dove leggere e scrivere i file di progetto. Senza un percorso corretto l'API non può trovare i file `.mpp`, generando errori FileNotFound. Definire questa directory all'inizio del codice rende il resto del flusso di lavoro pulito e ripetibile.

## Perché personalizzare i campi della tabella in un diagramma di Gantt?
I campi della tabella personalizzati consentono di mostrare informazioni aggiuntive — come attributi personalizzati, dati delle risorse o note specifiche del progetto — direttamente nella visualizzazione Gantt. Questo rende il diagramma più informativo per gli stakeholder e riduce la necessità di passare tra più report.

## Come creare una nuova attività?
Creare una nuova attività (task) è una delle operazioni fondamentali quando si costruisce o si aggiorna un programma di progetto. Aggiungendo attività programmaticamente è possibile automatizzare la generazione di piani complessi, integrare dati da altri sistemi o applicare modifiche in blocco senza interventi manuali.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – qualsiasi versione recente (8+).  
2. **Libreria Aspose.Tasks** – scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, o qualsiasi editor compatibile con Java che preferisci.

## Importa i pacchetti
Per prima cosa, importa lo spazio dei nomi Aspose.Tasks così da poter lavorare con le sue classi:

```java
import com.aspose.tasks.*;
```

## Guida passo‑passo

### Passo 1: Configura la directory dei dati
Definisci la cartella che contiene i tuoi file di progetto. Questo è il passo di **impostare la directory dei dati** su cui si concentra il tutorial.

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso assoluto della cartella in cui è memorizzato `project.mpp`.

### Passo 2: Carica il file di progetto
Crea un'istanza `Project` caricando un file Microsoft Project esistente.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Passo 3: Aggiungi una nuova attività
Inserisci un nuovo task (attività) nella radice del progetto. Questo dimostra **come creare una nuova attività** programmaticamente.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Passo 4: Definisci un attributo personalizzato
Crea una definizione di attributo personalizzato che potrai successivamente associare ai task.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Passo 5: Aggiungi l'attributo personalizzato al task
Assegna l'attributo appena definito al task che hai creato.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Passo 6: Personalizza la tabella – **personalizzare i campi della tabella**
Aggiungi l'attributo personalizzato come colonna nella tabella del diagramma di Gantt, specificando larghezza, titolo e allineamento.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Passo 7: Salva il progetto
Persisti le modifiche in un nuovo file che può essere aperto in Microsoft Project. Questo passo **salva il progetto come MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **FileNotFoundException** durante il caricamento del progetto | Il percorso della **directory dei dati** è errato o manca la barra finale. | Verifica che `dataDir` punti alla cartella esatta e includi il separatore di file corretto (`/` o `\\`). |
| Attributo personalizzato non visibile nella vista Gantt | Il campo della tabella è stato aggiunto all'indice sbagliato o la larghezza della colonna è troppo piccola. | Assicurati che `table.getTableFields().add(3, attrField);` utilizzi un indice valido e regola `setWidth` secondo necessità. |
| LicenseException durante il salvataggio | Nessuna licenza valida è stata applicata per l'uso in produzione. | Applica una licenza temporanea o permanente prima di chiamare `project.save()`. |

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks è disponibile per più linguaggi, inclusi .NET, Java e C++.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Sì, puoi scaricare una prova gratuita da [here](https://releases.aspose.com/).

**D: Dove posso trovare supporto per Aspose.Tasks?**  
R: Puoi trovare supporto e porre domande sul [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**D: Come posso acquistare una licenza per Aspose.Tasks?**  
R: Puoi acquistare una licenza da [here](https://purchase.aspose.com/buy).

**D: È necessaria una licenza temporanea per scopi di test?**  
R: Sì, puoi ottenere una licenza temporanea da [here](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora sai **come impostare la directory dei dati**, **creare una nuova attività**, definire e associare un attributo personalizzato, e **salvare il progetto come MPP** mentre **personalizzi i campi della tabella** in una visualizzazione Gantt usando Aspose.Tasks per Java. Questi passaggi ti danno il pieno controllo su come i dati del progetto vengono visualizzati, rendendo i tuoi diagrammi di Gantt più informativi e su misura per le esigenze dei tuoi stakeholder.

---

**Ultimo aggiornamento:** 2026-02-13  
**Testato con:** Aspose.Tasks Java 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}