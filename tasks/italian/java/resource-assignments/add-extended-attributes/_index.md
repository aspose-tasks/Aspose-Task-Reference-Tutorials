---
date: 2026-01-05
description: Scopri come impostare la data di inizio del progetto e salvare il file
  XML di MS Project utilizzando Aspose.Tasks per Java. Guida passo‑passo per gli sviluppatori
  Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Imposta la data di inizio del progetto con Aspose.Tasks per Java
url: /it/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta la Data di Inizio del Progetto con Aspose.Tasks per Java

## Introduzione
In questo tutorial imparerai **come impostare la data di inizio del progetto** in un file Microsoft Project e poi **salvare il file MS Project XML** utilizzando la libreria Aspose.Tasks per Java. Che tu stia automatizzando una pipeline di reportistica o costruendo uno strumento personalizzato di gestione progetti, padroneggiare questa operazione ti farà risparmiare tempo ed eliminerà errori manuali.

## Risposte Rapide
- **Qual è il metodo principale per impostare una data di inizio?** Usa `project.set(Prj.START_DATE, …)`.
- **Quale formato devo utilizzare per esportare il file?** Salvalo come XML con `SaveFileFormat.Xml`.
- **È necessaria una licenza per questa operazione?** Una versione di prova funziona, ma una licenza completa rimuove le filigrane.
- **Posso modificare la data di inizio dopo aver creato i task?** Sì, aggiorna la proprietà del progetto prima di aggiungere i task.
- **È compatibile con tutte le versioni di MS Project?** Aspose.Tasks supporta XML, MPP e molto altro.

## Che cos’è “Imposta la Data di Inizio del Progetto”?
Impostare la data di inizio del progetto definisce il calendario di base da cui iniziano tutti i calcoli di pianificazione dei task. È il primo passo per costruire programmaticamente un calendario di progetto affidabile.

## Perché usare Aspose.Tasks per Java?
Aspose.Tasks for Java fornisce un'API pura Java che funziona su qualsiasi piattaforma senza richiedere l'installazione di Microsoft Project. Ti consente di creare, modificare ed esportare dati di progetto rapidamente, rendendola ideale per l'automazione lato server.

## Prerequisiti
1. **Java Development Kit (JDK)** – qualsiasi versione recente del JDK.  
2. **Aspose.Tasks for Java** – scaricalo da [qui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o il tuo IDE Java preferito.

## Importa i Pacchetti
Per prima cosa, importa le classi necessarie:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Passo 1: Configura la Directory dei Dati
Definisci dove verranno salvati i file generati.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: Crea un'Istanza di Project
Istanzia un nuovo progetto vuoto.

```java
Project project = new Project();
```

### Passo 3: Imposta le Proprietà delle Informazioni del Progetto
Qui **impostiamo la data di inizio del progetto** e le proprietà di pianificazione correlate.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Passo 4: Salva il MS Project XML
Esporta il progetto configurato in un file XML.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemi Comuni e Soluzioni
- **Formato data errato:** Assicurati di utilizzare `java.util.Calendar` e di chiamare `getTime()` prima di assegnare.  
- **File non salvato:** Verifica che `dataDir` punti a una cartella esistente e scrivibile.  
- **Avvisi di licenza:** Una versione di prova aggiunge filigrane; applica una licenza valida per rimuoverle.

## Domande Frequenti

### Q: Posso usare Aspose.Tasks per Java per leggere file MS Project?  
**A:** Sì, Aspose.Tasks for Java offre funzionalità robuste sia per la lettura che per la scrittura di file MS Project.

### Q: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?  
**A:** Assolutamente, Aspose.Tasks for Java supporta vari formati di MS Project, garantendo ampia compatibilità.

### Q: Ci sono limitazioni nella versione di prova di Aspose.Tasks per Java?  
**A:** La versione di prova ti permette di esplorare la libreria ma aggiunge filigrane ai file di output.

### Q: Come posso ottenere supporto per Aspose.Tasks per Java?  
**A:** Puoi richiedere assistenza sul forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

### Q: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?  
**A:** Sì, le licenze temporanee sono disponibili per utilizzi a breve termine. Ottienila da [qui](https://purchase.aspose.com/temporary-license/).

### Q: Il salvataggio come XML conserva i campi personalizzati?  
**A:** Sì, quando salvi usando `SaveFileFormat.Xml`, tutti gli attributi personalizzati e i campi estesi vengono mantenuti.

### Q: Posso modificare la data di inizio dopo aver aggiunto i task?  
**A:** Puoi aggiornare la data di inizio in qualsiasi momento prima del salvataggio; basta chiamare nuovamente `project.set(Prj.START_DATE, …)`.

---

**Ultimo aggiornamento:** 2026-01-05  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}