---
date: 2026-01-18
description: Scopri come impostare la tariffa standard e altre proprietà delle risorse
  in MS Project usando Aspose.Tasks per Java, inclusa la modalità per aggiungere risorse
  a MS Project e gestirle in modo efficiente.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come impostare la tariffa standard per le risorse in Aspose.Tasks
url: /it/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta Tariffa Standard per le Risorse in Aspose.Tasks

## Introduzione
Se stai sviluppando applicazioni Java che devono interagire con file Microsoft Project, **impostare la tariffa standard** per una risorsa è una delle attività più comuni. In questo tutorial imparerai come **impostare la tariffa standard** e altre proprietà delle risorse utilizzando Aspose.Tasks per Java. Alla fine della guida sarai in grado di creare un oggetto progetto, aggiungere una risorsa a un file MS Project e gestire le risorse di MS Project con sicurezza.

## Risposte Rapide
- **Qual è la classe principale per lavorare con un file Project?** `Project`
- **Quale metodo aggiunge una nuova risorsa?** `project.getResources().add()`
- **Come si imposta la tariffa standard?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza valida di Aspose.Tasks.
- **Quale versione di Java è supportata?** Java 8+ (si consiglia l'ultima JDK).

## Che cosa significa “impostare tariffa standard”?
L'operazione *imposta tariffa standard* assegna un costo orario predefinito a una risorsa. I project manager usano questo valore per calcolare i costi del lavoro, generare report sui costi e prevedere i budget.

## Perché impostare le tariffe con Aspose.Tasks?
- **Nessuna installazione di Microsoft Project necessaria** – manipola i file direttamente da Java.
- **Fedele al 100 %** – tutti i campi delle risorse, inclusi straordinari e tariffe di costo, vengono preservati.
- **Cross‑platform** – funziona su Windows, Linux e macOS.
- **Adatto all'automazione** – ideale per l'elaborazione batch o l'integrazione con pipeline CI.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### Configurazione dell'Ambiente di Sviluppo Java
1. Installa JDK: assicurati di avere il Java Development Kit (JDK) installato sul tuo sistema. Puoi scaricarlo dal [sito Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Configurazione IDE: scegli un Integrated Development Environment (IDE) come IntelliJ IDEA, Eclipse o NetBeans e configuralo sulla tua macchina.

### Installazione di Aspose.Tasks per Java
1. Scarica Aspose.Tasks per Java: vai alla [pagina di download](https://releases.aspose.com/tasks/java/) e procurati l'ultima versione di Aspose.Tasks per Java.
2. Integra con il Progetto: incorpora la libreria Aspose.Tasks per Java nel tuo progetto Java aggiungendola come dipendenza.

## Importare i Pacchetti
Per iniziare, devi importare i pacchetti necessari da Aspose.Tasks per Java nel tuo progetto. Questo passaggio garantisce l'accesso alle funzionalità richieste.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Passo 1: Creare un Oggetto Project
Creare un **oggetto project** è il primo passo per qualsiasi manipolazione di MS Project. Rappresenta l'intero file di progetto in memoria.

```java
Project project = new Project();
```

## Passo 2: Aggiungere una Risorsa (add resource ms project)
Ora **aggiungeremo una risorsa MS Project** usando la collezione Resources. Il nome della risorsa può essere qualsiasi cosa abbia senso per il tuo programma.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Passo 3: Impostare le Proprietà della Risorsa (how to set rates)
Qui **impostiamo la tariffa standard** e dimostriamo anche come impostare una tariffa per gli straordinari. Queste tariffe sono memorizzate come valori `BigDecimal` per preservare la precisione.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Problemi Comuni e Soluzioni
| Problema | Perché si Verifica | Soluzione |
|----------|--------------------|-----------|
| `NullPointerException` durante la chiamata a `set` | La risorsa non è stata aggiunta correttamente. | Assicurati che `project.getResources().add()` restituisca un `Resource` non nullo. |
| Le tariffe appaiono come 0 nel file salvato | Uso di `int` anziché `BigDecimal`. | Usa sempre `BigDecimal.valueOf()` per i valori monetari. |
| Licenza non trovata | Il file di licenza non è stato caricato prima di creare `Project`. | Carica la licenza (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) all'inizio del programma. |

## Conclusione
Seguendo questi passaggi hai imparato come **creare un oggetto project**, **aggiungere una risorsa MS Project** e **impostare la tariffa standard** insieme ad altre proprietà della risorsa. Questo ti consente di automatizzare i calcoli dei costi, generare report personalizzati e gestire completamente le risorse di MS Project da Java.

## FAQ
### Aspose.Tasks per Java può gestire file MS Project complessi?
Sì, Aspose.Tasks per Java è in grado di gestire un'ampia gamma di formati di file MS Project, inclusi quelli complessi con gerarchie di attività estese.

### È disponibile una versione di prova gratuita di Aspose.Tasks per Java?
Sì, puoi accedere a una prova gratuita di Aspose.Tasks per Java da [qui](https://releases.aspose.com/).

### Dove posso trovare supporto per Aspose.Tasks per Java?
Puoi richiedere assistenza e partecipare a discussioni relative a Aspose.Tasks per Java sul [forum di supporto](https://forum.aspose.com/c/tasks/15).

### Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?
Puoi ottenere una licenza temporanea dalla [pagina delle licenze temporanee](https://purchase.aspose.com/temporary-license/) per scopi di valutazione.

### Dove posso acquistare una versione con licenza di Aspose.Tasks per Java?
Puoi acquistare una versione con licenza di Aspose.Tasks per Java dalla [pagina di acquisto](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo Aggiornamento:** 2026-01-18  
**Testato Con:** Aspose.Tasks per Java 24.12 (ultima al momento della stesura)  
**Autore:** Aspose