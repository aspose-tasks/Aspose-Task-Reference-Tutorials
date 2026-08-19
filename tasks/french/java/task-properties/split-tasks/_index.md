---
date: 2026-02-26
description: Apprenez à fractionner les tâches avec Aspose.Tasks pour Java – le guide
  définitif pour fractionner les tâches, définir le calendrier du projet et créer
  une affectation de ressources.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment fractionner les tâches dans Aspose.Tasks
url: /fr/java/task-properties/split-tasks/
weight: 29
---

Also preserve code block placeholders as they are.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment diviser les tâches dans Aspose.Tasks

## Introduction
Si vous recherchez **comment diviser les tâches** dans un projet basé sur Java, vous êtes au bon endroit. Aspose.Tasks for Java vous offre une méthode propre et programmatique pour découper une tâche de longue durée en parties plus petites et gérables, ce qui facilite le nivellement des ressources, des rapports précis et des délais de projet plus serrés. Dans ce tutoriel, nous parcourrons l’ensemble du processus — de la configuration du calendrier du projet à la création d’une affectation de ressource, puis enfin la division de la tâche en plusieurs segments.

## Quick Answers
- **Qu’est‑ce que la division de tâche ?** Diviser une tâche unique en plusieurs intervalles plus petits tout en conservant sa durée totale.  
- **Pourquoi diviser les tâches en Java ?** Cela permet une allocation précise des ressources et un meilleur suivi de l’avancement.  
- **Quelle bibliothèque aide ?** Aspose.Tasks for Java fournit des méthodes intégrées pour la division et le phasage temporel.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence est requise pour la production.  
- **Quelle version de Java est prise en charge ?** La bibliothèque fonctionne avec Java 8 et les versions ultérieures.

## Prerequisites
Avant de plonger dans le tutoriel, assurez‑vous que les prérequis suivants sont en place :
- JDK (Java Development Kit) installé sur votre machine.  
- Bibliothèque Aspose.Tasks for Java téléchargée et ajoutée à votre projet. Vous pouvez la télécharger depuis la [documentation Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## Import Packages
Commencez par importer les packages nécessaires dans votre projet Java :

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Step 1: Create a New Project
Créez un nouveau projet en utilisant la bibliothèque Aspose.Tasks :

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Step 2: Set Project Calendar
Définir le **calendrier du projet** précise les jours ouvrés, les jours fériés et la chronologie globale de votre planning. Cette étape est essentielle pour des calculs temporels précis.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Step 3: Add a Root Task
Chaque projet nécessite un conteneur racine. Ajouter une tâche racine vous donne un endroit où attacher toutes les tâches suivantes.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Step 4: Add a New Task to Split
Créez la tâche que vous souhaitez diviser. Ici nous définissons une durée de trois jours à titre d’exemple.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Step 5: Create a Resource Assignment
Une **affectation de ressource** lie une ressource (ou un espace réservé) à la tâche. Cela est requis avant de générer des données temporelles.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Step 6: Generate Timephased Data
Les données temporelles représentent comment le travail est réparti sur la durée de la tâche. Les générer prépare la tâche à la division.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Step 7: Split the Task
Nous **divisons maintenant la tâche en parties**. Dans cet exemple, nous scindons la tâche de trois jours en trois segments d’un jour chacun.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Why Split Tasks?
Diviser les tâches vous offre un contrôle plus fin sur :
- **Nivellement des ressources :** Affecter différentes ressources à chaque segment.  
- **Suivi de l’avancement :** Mettre à jour le statut par segment.  
- **Rapports :** Générer des diagrammes de Gantt et des rapports plus détaillés.

## Common Issues and Solutions
- **Données de calendrier manquantes :** Assurez‑vous d’appeler `timephasedDataFromTaskDuration` avant de diviser.  
- **Segments de durée zéro :** Vérifiez que chaque intervalle découpé a une durée non nulle ; sinon la bibliothèque l’ignorera.  
- **Exceptions de licence :** Exécuter sans licence valide peut ajouter un filigrane aux fichiers exportés.

## Frequently Asked Questions
### Puis‑je diviser les tâches avec des durées différentes ?
Oui, vous pouvez ajuster la durée de chaque partie selon les exigences de votre projet.

### Aspose.Tasks for Java est‑il compatible avec toutes les versions de Java ?
Aspose.Tasks for Java est conçu pour fonctionner sans problème avec Java 8 et les versions ultérieures, garantissant une large compatibilité.

### Puis‑je utiliser Aspose.Tasks for Java gratuitement ?
Aspose.Tasks for Java propose un essai gratuit, vous permettant d’explorer ses fonctionnalités avant d’effectuer un achat.

### Comment obtenir du support pour Aspose.Tasks for Java ?
Visitez le [forum de support Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide et rejoindre la communauté.

### Ai‑je besoin d’une licence temporaire pour Aspose.Tasks for Java ?
Vous pouvez obtenir une licence temporaire via [ce lien](https://purchase.aspose.com/temporary-license/) pour les tests et l’évaluation.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}