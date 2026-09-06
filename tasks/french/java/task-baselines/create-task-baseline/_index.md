---
date: 2026-08-29
description: Apprenez comment ajouter une tâche à un projet en Java, créer un task
  list et définir une baseline sans Microsoft Project en utilisant Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Création d'une Task Baseline dans Aspose.Tasks
og_description: Apprenez comment ajouter une tâche à un projet en Java et définir
  une baseline en utilisant Aspose.Tasks. Ce guide montre step‑by‑step code sans nécessiter
  Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Comment ajouter une tâche à un projet en Java et définir une baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Comment ajouter une tâche à un projet en Java et définir une baseline
url: /fr/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une tâche à un projet en Java et définir une ligne de base

## Introduction
Dans ce tutoriel, vous allez **ajouter une tâche à un projet** de manière programmatique, générer une ligne de base de tâche Microsoft Project, et enregistrer le fichier — le tout sans jamais ouvrir Microsoft Project. Aspose.Tasks for Java vous fournit une API pure‑Java qui fonctionne sur n’importe quelle plateforme, ce qui la rend idéale pour les pipelines de construction automatisés, les services de reporting ou toute solution côté serveur nécessitant de manipuler des fichiers .mpp.

## Réponses rapides
- **Que fait Aspose.Tasks ?** Elle fournit une API Java pour créer, lire et modifier des fichiers Microsoft Project sans nécessiter Microsoft Project.  
- **Dois‑je installer Microsoft Project ?** Non, la bibliothèque fonctionne complètement de manière indépendante.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur.  
- **Puis‑je définir une ligne de base pour une tâche unique ?** Oui – appelez `setBaseline` sur une liste contenant uniquement les tâches souhaitées.  
- **Une licence est‑elle nécessaire en production ?** Oui, une licence commerciale supprime les limites d’évaluation et débloque toutes les fonctionnalités.

## Qu'est‑ce qu'une ligne de base de tâche ?
Une ligne de base de tâche capture la date de début prévue, la date de fin prévue et l'effort de travail initial d’une tâche au moment où le planning est enregistré pour la première fois. Cette capture sert de point de référence, permettant aux chefs de projet de comparer l’avancement réel et les coûts par rapport au plan initial, et de calculer les écarts pour l’analyse de performance.

## Pourquoi utiliser Aspose.Tasks pour ajouter une tâche à un projet en Java ?
Vous pouvez créer, modifier et définir des lignes de base de tâches sans aucune installation de bureau, ce qui permet des flux de travail entièrement automatisés. Aspose.Tasks prend en charge **plus de 50 formats d’entrée et de sortie** et peut gérer des projets avec **des centaines de tâches** tout en maintenant l’utilisation de la mémoire en dessous de 200 Mo, ce qui la rend idéale pour les services cloud et les pipelines CI/CD.

## Prérequis
1. **Java Development Kit (JDK)** – installez le JDK 8 ou une version plus récente.  
2. **Aspose.Tasks for Java** – téléchargez la bibliothèque depuis le [download link](https://releases.aspose.com/tasks/java/).  

## Importer les packages
Pour commencer à travailler avec Aspose.Tasks dans votre projet Java, importez les packages nécessaires :
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Étape 1 : créer un objet projet
La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier Microsoft Project en mémoire. L’instancier vous donne un projet vierge que vous pouvez remplir avec des tâches, des ressources et des calendriers.

```java
Project project = new Project();
```
Ici nous instancions un nouvel objet `Project` – il représente le fichier MS Project qui contiendra notre liste de tâches.

## Étape 2 : ajouter une tâche au projet
La classe `Task` représente un élément de travail individuel dans le planning d’un projet. Chaque `Task` peut avoir sa propre durée, date de début et affectations de ressources.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
En utilisant `getRootTask()` nous accédons à la racine de la hiérarchie du projet et **ajoutons une tâche à Microsoft Project**. La chaîne `"Task"` est le nom de la tâche ; vous pouvez la remplacer par n’importe quelle description dont vous avez besoin.

## Étape 3 : définir la ligne de base pour les tâches spécifiées
`BaselineType` est une énumération qui définit quel créneau de ligne de base (Baseline, Baseline1 … Baseline10) vous souhaitez écrire. En passant une liste de tâches, vous pouvez appliquer la ligne de base uniquement aux éléments sélectionnés.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Pour **définir une ligne de base sans MS Project**, créez une liste des tâches que vous voulez inclure dans la ligne de base (ici `myList`) et passez‑la à `setBaseline`. Remplissez `myList` avec les tâches que vous avez ajoutées si vous ne avez besoin que d’une ligne de base sélective.

## Étape 4 : définir la ligne de base pour l'ensemble du projet
`setBaseline` écrit les valeurs de ligne de base sélectionnées sur chaque tâche du projet.  
Si vous préférez appliquer la ligne de base à tout le projet en un seul appel, invoquez simplement `setBaseline` avec le `BaselineType` souhaité.

```java
project.setBaseline(BaselineType.Baseline);
```
Cet appel écrit les valeurs de ligne de base choisies pour **toutes les tâches** du projet, garantissant une capture complète du planning original.

## Comment ajouter une tâche à Microsoft Project avec Aspose.Tasks
`add()` crée une nouvelle tâche enfant sous la tâche parent spécifiée et renvoie l’objet `Task` nouvellement créé.  
Vous ajoutez une tâche en appelant `add()` sur un objet `Task` parent (généralement la tâche racine). La méthode renvoie une nouvelle instance `Task` que vous pouvez configurer davantage — durée, date de début, ressources ou champs personnalisés—avant d’enregistrer le fichier du projet.

## Comment définir une ligne de base sans MS Project
Aspose.Tasks permet la création de lignes de base entièrement via le code. Choisissez un `BaselineType` (par ex., `BaselineType.Baseline`) et invoquez `setBaseline`. Vous pouvez répéter l’opération avec `Baseline1`‑`Baseline10` pour conserver plusieurs révisions de lignes de base, le tout sans ouvrir Microsoft Project.

## Problèmes courants et solutions
- **La ligne de base n’apparaît pas :** Assurez‑vous d’appeler `project.save("output.mpp")` après avoir défini la ligne de base (étape d’enregistrement omise ici pour plus de concision).  
- **La liste des tâches apparaît vide :** Vérifiez que vous ajoutez les tâches au bon parent (`getRootTask()` ou une sous‑tâche).  
- **Erreurs de incompatibilité de version :** Utilisez le dernier JAR Aspose.Tasks pour garantir la compatibilité avec les formats .mpp plus récents.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks pour Java sans Microsoft Project installé ?**  
R : Oui, Aspose.Tasks fonctionne de manière indépendante et ne nécessite pas Microsoft Project sur la machine hôte.

**Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de Microsoft Project ?**  
R : Absolument. La bibliothèque prend en charge les fichiers Project de 2007 jusqu’aux dernières versions 2024.

**Q : Puis‑je manipuler les ressources du projet avec Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez ajouter, mettre à jour et supprimer des ressources programmatiquement, tout comme les tâches.

**Q : Aspose.Tasks pour Java prend‑il en charge la définition des dépendances de tâche ?**  
R : Oui, vous pouvez définir des relations prédécesseur‑successeur en utilisant la classe `TaskLink`.

**Q : Un support technique est‑il disponible pour Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez obtenir de l’aide via le [support forum](https://forum.aspose.com/c/tasks/15), où le personnel d’Aspose et la communauté répondent aux questions.

## Conclusion
En suivant ces étapes, vous avez appris comment **ajouter une tâche à un projet** en Java, créer une liste de tâches, et **définir une ligne de base sans MS Project** à l’aide d’Aspose.Tasks. Cette approche simplifie l’automatisation des projets, élimine le besoin d’installations de bureau Project, et vous donne un contrôle programmatique complet sur chaque aspect de votre planning.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriels associés

- [Comment créer un projet aspose.tasks – Définir les nouveaux attributs de tâche](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Comment définir la durée de la ligne de base dans Aspose.Tasks pour Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Créer des tâches Aspose Java – Propriétés de la tâche](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}