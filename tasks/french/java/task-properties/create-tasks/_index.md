---
date: 2026-09-25
description: Apprenez à créer un planning de projet en Java en utilisant Aspose.Tasks.
  Ce guide vous montre comment ajouter des tâches récapitulatives, gérer la hiérarchie
  du projet et définir le répertoire des documents efficacement.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Créer des tâches avec Aspose.Tasks
og_description: Apprenez à créer un planning de projet en Java en utilisant Aspose.Tasks.
  Suivez les instructions étape par étape pour ajouter des tâches récapitulatives,
  gérer la hiérarchie et définir le répertoire des documents.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Comment créer un planning de projet avec Aspose.Tasks pour Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Comment créer un planning de projet avec Aspose.Tasks pour Java
url: /fr/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un planning de projet avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous apprendrez à **créer un planning de projet** dans une application Java en utilisant Aspose.Tasks. Que vous construisiez une simple liste de tâches ou un planificateur d’entreprise complexe, les étapes ci‑dessous vous guideront pour ajouter des tâches récapitulatives, gérer la hiérarchie du projet et définir le répertoire du document — le tout avec des extraits de code clairs et exécutables. À la fin, vous disposerez d’un planning entièrement structuré, prêt à être manipulé ou exporté.

## Réponses rapides
- **Que gère Aspose.Tasks ?** Il gère les hiérarchies de tâches, les ressources, les calendriers et les formats de fichiers de projet (MS‑Project, Primavera, etc.).  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire gratuite fonctionne pour l’évaluation ; une licence complète est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 et les versions ultérieures sont entièrement prises en charge.  
- **Puis‑je ajouter des champs personnalisés aux tâches ?** Oui, vous pouvez étendre les tâches avec des champs définis par l’utilisateur via l’API.  
- **Existe‑t‑il une prise en charge intégrée des diagrammes de Gantt ?** Aspose.Tasks peut exporter en PDF/HTML incluant des visualisations de Gantt.

## Qu’est‑ce qu’un planning de projet dans Aspose.Tasks ?
Un planning de projet est l’ensemble complet des tâches, dépendances et échéances qui définissent comment le travail sera exécuté. Aspose.Tasks stocke ces informations dans un objet `Project` que vous pouvez lire, modifier et enregistrer dans divers formats. Il comprend les dates de début et de fin, les contraintes et les affectations de ressources, permettant une planification et un reporting complets.

## Pourquoi utiliser Aspose.Tasks pour la gestion de projet Java ?
Aspose.Tasks prend en charge **plus de 30 formats d’entrée et de sortie** et peut traiter des projets contenant **jusqu’à 10 000 tâches** sans charger le fichier complet en mémoire, offrant ainsi des performances élevées pour les scénarios de gestion de projet Java à grande échelle.

## Prérequis
Avant de commencer le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- **Kit de développement Java (JDK)** – JDK 8 ou version ultérieure installé sur votre machine.  
- **Bibliothèque Aspose.Tasks pour Java** – Téléchargez et installez la bibliothèque depuis [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Environnement de développement intégré (IDE)** – Utilisez Eclipse, IntelliJ IDEA ou tout IDE compatible Java que vous préférez.

## Importer les packages
`Project`, `Task` et les classes associées se trouvent dans l’espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier Java :

La classe `Project` représente un planning de projet complet et fournit des méthodes pour manipuler les tâches et les ressources.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

La classe `Project` est le point d’entrée pour toutes les opérations sur un fichier de projet.

## Comment créer un planning de projet avec Aspose.Tasks ?

Chargez une nouvelle instance `Project`, définissez le répertoire du document et commencez à ajouter des tâches. Ce paragraphe explicatif décrit le flux principal : vous créez un `Project`, configurez son `RootFolder` (le répertoire du document), puis ajoutez une tâche récapitulative suivie de sous‑tâches. Toutes les modifications restent en mémoire jusqu’à ce que vous appeliez `save` pour persister le planning dans un fichier.

### Étape 1 : définir le répertoire du document
Définissez l’endroit où le fichier de projet résultant sera écrit. Définir le répertoire dès le départ garantit que toutes les opérations d’enregistrement ultérieures utilisent un chemin cohérent.

La propriété `RootFolder` spécifie le dossier de base où les fichiers de projet sont lus ou écrits.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Étape 2 : créer un nouveau projet
Instanciez un nouvel objet `Project` qui contiendra votre planning. Vous pouvez éventuellement fournir le chemin d’un fichier existant pour charger un planning à modifier.

Le constructeur `Project` crée un planning vide prêt à recevoir des tâches.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Étape 3 : ajouter une tâche récapitulative
Une tâche récapitulative regroupe des sous‑tâches liées et apparaît comme un nœud réductible dans les diagrammes de Gantt. Utilisez la classe `Task` et définissez `IsSummary` à `true`.

La méthode `addTask` crée une nouvelle tâche sous un parent spécifié et renvoie son ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Étape 4 : ajouter une sous‑tâche
Les sous‑tâches héritent des dates de début/fin de leur tâche récapitulative parent, sauf si vous les remplacez. Ajouter une sous‑tâche est aussi simple que d’appeler de nouveau `addTask` en précisant l’ID du parent.

Appeler `addTask` avec un ID de parent ajoute une sous‑tâche sous cette tâche récapitulative.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Continuez à ajouter autant de tâches et de sous‑tâches que nécessaire pour votre projet. Chaque étape contribue à construire une hiérarchie de projet structurée qui peut être exportée vers MS‑Project, PDF ou d’autres formats pris en charge.

## Problèmes courants et solutions
- **Problème :** « Répertoire du document introuvable. »  
  **Solution :** Vérifiez que le chemin que vous attribuez à `RootFolder` existe sur le système de fichiers et que votre processus Java dispose des droits d’écriture.
- **Problème :** Les sous‑tâches n’apparaissent pas sous la tâche récapitulative.  
  **Solution :** Assurez‑vous de fournir le bon ID de tâche parent lors de l’appel à `addTask`. L’API exige l’ID du parent comme deuxième argument.
- **Problème :** Les projets volumineux provoquent une OutOfMemoryError.  
  **Solution :** Aspose.Tasks traite les tâches en mode flux ; augmentez la taille du tas JVM (`-Xmx2g`) ou divisez le planning en plusieurs fichiers.

## Questions fréquentes
**Q : Aspose.Tasks convient‑il aux projets de petite envergure ?**  
R : Absolument. La bibliothèque passe d’une simple liste de tâches à des plannings d’entreprise avec des milliers de tâches.

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks pour Java ?**  
R : Consultez la documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Visitez la [temporary license request page](https://purchase.aspose.com/temporary-license/) pour obtenir une licence limitée dans le temps, utilisable pour le développement et les tests.

**Q : Puis‑je personnaliser les attributs des tâches avec Aspose.Tasks ?**  
R : Oui, vous pouvez étendre les tâches avec des champs personnalisés, affecter des ressources et modifier les calendriers programmaticalement.

**Q : Existe‑t‑il une communauté de support pour les utilisateurs d’Aspose.Tasks ?**  
R : Absolument ! Rejoignez la communauté Aspose.Tasks sur [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-09-25  
**Testé avec :** Aspose.Tasks 24.12 for Java  
**Auteur :** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Tutoriels associés

- [Définir la date de début du projet dans MS Project avec Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)
- [Créer des dépendances de tâches de gestion de projet dans Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Comment ajouter une ressource au projet et créer des affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}