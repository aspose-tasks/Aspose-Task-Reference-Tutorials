---
date: 2026-05-20
description: Apprenez comment ajouter une ressource à un projet et créer des affectations
  de ressources en utilisant Aspose.Tasks pour Java, une bibliothèque de gestion de
  projet Java robuste.
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: Créer des affectations de ressources dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment ajouter une ressource à un projet et créer des affectations de ressources
  dans Aspose.Tasks
url: /fr/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ressource au projet – Créer des affectations de ressources dans Aspose.Tasks

## Introduction
Dans la gestion de projet moderne, **add resource to project** est la pierre angulaire d'une planification efficace et du contrôle des coûts. Aspose.Tasks for Java vous offre une méthode programmatique et haute performance pour gérer les ressources, les tâches et les affectations sans quitter votre IDE. Dans ce tutoriel, vous verrez exactement comment ajouter une ressource à un projet, l'attacher à une tâche et affiner les détails de l'affectation — le tout avec du code Java propre et prêt pour la production.

## Réponses rapides
- **Quelle est la première étape ?** Create a `Project` instance that represents your .mpp or .xml file.  
- **Comment ajouter une tâche ?** Use the root task’s `addChild` method and give the task a name.  
- **Comment puis‑je ajouter une ressource ?** Call `project.getResources().add` with a `Resource` object.  
- **Comment lier une ressource à une tâche ?** Use `project.getResourceAssignments().add(task, resource)`.  
- **Ai‑je besoin d'une licence ?** Yes – a valid Aspose.Tasks for Java license is required for production use.

## Qu’est‑ce que “add resource to project” ?
**Add resource to project** signifie créer un objet `Resource` dans le fichier de projet et le lier à une ou plusieurs tâches afin que le travail, le coût et les données du calendrier soient calculés automatiquement. Cette opération est l'épine dorsale de toute application basée sur un planning.

## Pourquoi choisir Aspose.Tasks for Java ?
Aspose.Tasks for Java prend en charge **plus de 30 formats d’entrée et de sortie** (y compris MPP, XML et CSV) et peut traiter des projets contenant **plus de 10 000 tâches** tout en maintenant l’utilisation de la mémoire en dessous de 200 Mo. La bibliothèque fonctionne sur Java 8‑17, ne nécessite aucune installation de Microsoft Project et fournit des API thread‑safe pour l’automatisation côté serveur.

## Prérequis
Avant de plonger dans la création d’affectations de ressources, assurez‑vous de disposer de ce qui suit :

### Environnement de développement Java
Assurez‑vous d’avoir le Java Development Kit (JDK) installé sur votre système. Vous pouvez télécharger et installer le JDK depuis [ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Bibliothèque Aspose.Tasks for Java
Téléchargez la bibliothèque Aspose.Tasks for Java depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/). Suivez les instructions d’installation pour configurer la bibliothèque dans votre projet Java.

## Comment ajouter une ressource au projet ?
Chargez votre projet, créez une tâche, ajoutez une ressource, puis liez‑les ensemble — le tout en quatre étapes concises. Les extraits de code ci‑dessous (espaces réservés) montrent les appels API exacts ; vous n’avez qu’à remplacer le texte de l’espace réservé par vos propres chemins de fichiers et noms.

### Étape 1 : Créer un objet Project
La classe `Project` est le conteneur de niveau supérieur qui représente un fichier de projet unique en mémoire.  
Instanciez un objet `Project`, qui représente le fichier de projet avec lequel vous travaillez :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### Étape 2 : Ajouter une tâche au projet
La classe `Task` modélise un élément de travail individuel au sein du planning.  
Ajoutez une tâche au projet en utilisant la méthode `addChild` de la tâche racine :
```java
Project project = new Project();
```

### Étape 3 : Ajouter une ressource au projet
La classe `Resource` définit une personne, un équipement ou un matériau pouvant être affecté à des tâches.  
Ajoutez une ressource au projet en utilisant la méthode `add` de la collection `Resources` :
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### Étape 4 : Créer une affectation de ressource
La classe `ResourceAssignment` lie une `Task` et une `Resource` et stocke les détails d’allocation tels que les heures de travail et le coût.  
Créez une affectation de ressource pour la tâche et la ressource en utilisant la méthode `add` de la collection `ResourceAssignments` :
```java
Resource rsc = project.getResources().add("Rsc");
```

## Problèmes courants et solutions
- **NullPointerException sur `addChild`** – Assurez‑vous d’appeler `project.getRootTask()` avant d’ajouter des enfants.  
- **Licence non trouvée** – Placez votre fichier `Aspose.Tasks.lic` dans le classpath ou définissez la licence programmatique avec `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Ralentissement sur projet volumineux** – Utilisez `project.setReadOnly(true)` lorsque vous avez seulement besoin de lire les données ; cela réduit la charge mémoire.

## Questions fréquentes

**Q : Puis‑je modifier les affectations de ressources après création ?**  
A : Oui, vous pouvez mettre à jour les propriétés d’affectation telles que `Work`, `Cost` et `Start` en utilisant les mutateurs fournis par la classe `ResourceAssignment`.

**Q : Aspose.Tasks for Java est‑il compatible avec différents formats de fichiers de projet ?**  
A : Absolument, Aspose.Tasks for Java prend en charge MPP, XML, CSV et de nombreux autres formats, permettant une importation et une exportation fluides.

**Q : Aspose.Tasks for Java nécessite‑t‑il une licence pour une utilisation commerciale ?**  
A : Oui, une licence commerciale valide est requise. Une licence d’évaluation gratuite est disponible à des fins de test.

**Q : Puis‑je utiliser Aspose.Tasks for Java dans mes applications web ?**  
A : Oui, la bibliothèque est entièrement thread‑safe et peut être intégrée aux services web basés sur des servlets ou Spring‑Boot.

**Q : Où puis‑je trouver un support supplémentaire pour Aspose.Tasks for Java ?**  
A : Vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir une assistance technique et participer aux discussions communautaires.

---

**Dernière mise à jour :** 2026-05-20  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment créer des ressources – Gestion des ressources avec Aspose.Tasks for Java](/tasks/java/resource-management/)
- [Comment ajouter des notes aux affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Comment ajouter une ressource au projet et gérer les propriétés de délai de nivellement dans Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}