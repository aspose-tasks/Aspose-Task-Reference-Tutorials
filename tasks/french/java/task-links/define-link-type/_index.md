---
date: 2026-08-29
description: Apprenez à définir les types de liaison et à gérer les dépendances de
  tâches avec Aspose.Tasks for Java dans un tutoriel pas à pas.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Comment définir les types de liaison dans Aspose.Tasks for Java
og_description: Apprenez à définir les types de liaison et à gérer les dépendances
  de tâches avec Aspose.Tasks for Java. Guide pas à pas pour les développeurs.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Comment définir les types de liaison dans Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Comment définir les types de liaison dans Aspose.Tasks for Java
url: /fr/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir les types de liens dans Aspose.Tasks pour Java

## Introduction
Si vous vous demandez **comment définir un lien** entre les tâches tout en *gérant les dépendances de tâches* dans un projet, vous êtes au bon endroit. Dans ce tutoriel, nous allons créer un nouveau projet, ajouter des tâches et définir le type de lien (Start‑to‑Start, Finish‑to‑Start, etc.) à l’aide d’Aspose.Tasks pour Java. À la fin, vous vous sentirez à l’aise pour personnaliser les relations entre les tâches afin de répondre aux besoins de planification du monde réel et vous verrez comment l’API gère des plans à grande échelle contenant jusqu’à 10 000 tâches.

## Réponses rapides
- **Quelle classe représente une dépendance ?** `TaskLink` est l’objet principal qui modélise un lien entre deux tâches.  
- **Quel enum définit le type de relation ?** `TaskLinkType` (par ex., `StartToStart`, `FinishToStart`).  
- **Puis-je lire les types de liens existants ?** Oui – parcourez `Project.getTaskLinks()` et appelez `getLinkType()`.  
- **Ai‑je besoin d’une licence pour ce code ?** Une licence temporaire suffit pour les tests ; une licence complète est requise pour la production.  
- **Est‑ce compatible avec Java 8+ ?** Absolument – Aspose.Tasks prend en charge Java 8 jusqu’à Java 21, couvrant 13 versions majeures.

## Qu'est-ce qu'un lien de tâche ?
Un **lien de tâche** modélise une dépendance entre deux tâches dans le planning d’un projet.  
Vous pouvez créer, modifier ou supprimer un `TaskLink` pour refléter les relations prédécesseur‑successeur, permettant au planificateur de calculer automatiquement les dates de début et de fin.

## Pourquoi utiliser les types de liens Aspose.Tasks ?
Aspose.Tasks prend en charge **plus de 30 formats d’entrée et de sortie** et peut traiter des projets contenant **jusqu’à 10 000 tâches** sans charger le fichier complet en mémoire. Cette capacité quantifiée garantit des performances rapides même pour des plans à l’échelle de l’entreprise, et la bibliothèque préserve toutes les fonctionnalités de Microsoft Project telles que les champs personnalisés et les affectations de ressources.

## Prérequis
- **Environnement de développement Java** – JDK 8 ou version ultérieure installé et configuré.  
- **Bibliothèque Aspose.Tasks** – Téléchargez le dernier JAR depuis le [lien de téléchargement](https://releases.aspose.com/tasks/java/).  
- **Répertoire de documents** – Créez un dossier sur votre machine où vous conserverez les fichiers d’exemple du projet.

## Importer les packages
Nous commençons par importer les classes essentielles d’Aspose.Tasks. Cela prépare l’IDE à reconnaître les appels d’API que nous utiliserons plus tard.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Comment définir les types de liens dans Aspose.Tasks pour Java ?
Chargez une nouvelle instance `Project`, ajoutez deux tâches, puis créez un `TaskLink` avec le `TaskLinkType` souhaité. Ce modèle en deux étapes vous permet de définir l’un des quatre types de dépendance standard en un seul appel. `Project` représente le fichier de projet complet et son planning. `Task` est un élément de travail individuel au sein du projet. `TaskLink` relie une tâche prédécesseur à une tâche successeur. `TaskLinkType` est une énumération qui spécifie la relation (Start‑to‑Start, Finish‑to‑Start, etc.).

### Étape 1 : définir un type de lien
`TaskLink` représente une dépendance entre deux tâches, tandis que `TaskLinkType` énumère les types de relation possibles tels que `StartToStart`. Dans cette étape, nous créons un nouveau projet, ajoutons deux tâches et les relions en utilisant la relation **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Astuce :** Vous pouvez remplacer `StartToStart` par `FinishToStart`, `StartToFinish` ou `FinishToFinish` selon la dépendance que vous devez **gérer les dépendances de tâches**.

### Étape 2 : obtenir un type de lien
`Project.getTaskLinks()` renvoie une collection de tous les objets `TaskLink` du planning. En parcourant cette collection, vous pouvez lire le `TaskLinkType` de chaque lien et vérifier que la relation correcte a été enregistrée.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

La console affichera des valeurs telles que `StartToStart`, `FinishToStart`, etc., confirmant le type de lien que vous avez défini précédemment.

## Problèmes courants et solutions
- **NullPointerException lors de l’ajout de liens** – Assurez‑vous que les tâches prédécesseur et successeur sont ajoutées au projet avant de créer un `TaskLink`.  
- **Type de lien incorrect après l’enregistrement** – Appelez toujours `project.save("output.mpp")` (ou un autre format pris en charge) après avoir défini le type de lien pour persister les modifications.  
- **Licence introuvable** – Placez votre fichier de licence Aspose.Tasks dans le classpath du projet et chargez‑le avec `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Questions fréquemment posées

**Q : Aspose.Tasks est‑il compatible avec différents environnements Java ?**  
R : Oui, Aspose.Tasks s’intègre aux kits de développement Java SE, Java EE et Android standard sans dépendances supplémentaires.

**Q : Puis‑je personnaliser les types de liens en fonction des exigences de mon projet ?**  
R : Absolument. L’enum `TaskLinkType` fournit les quatre types standards, et vous pouvez les combiner avec des valeurs de retard pour modéliser des plannings complexes.

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks pour Java ?**  
R : Consultez la [documentation Aspose.Tasks pour Java](https://reference.aspose.com/tasks/java/) pour des instructions approfondies, la référence API et des exemples de code.

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Visitez la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire à des fins de test.

**Q : Où puis‑je obtenir du support pour les questions liées à Aspose.Tasks ?**  
R : Rejoignez la communauté Aspose.Tasks sur le [forum de support](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide et des discussions.

**Q : Puis‑je modifier un type de lien après que le projet a été enregistré ?**  
R : Oui. Chargez le projet, récupérez le `TaskLink`, appelez `setLinkType()` avec la nouvelle valeur d’enum, puis enregistrez à nouveau le projet.

**Q : Aspose.Tasks prend‑il en charge la lecture des fichiers Microsoft Project (MPP) ?**  
R : Oui. Utilisez `new Project("file.mpp")` pour charger les fichiers MPP et travailler avec leurs liens de tâches comme dans l’exemple XML ci‑dessus.

**Dernière mise à jour :** 2026-08-29  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un lien de tâche inter‑projets dans Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Définir la date de début du projet et gérer les tâches parent et enfant dans Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Charger un fichier MPP Java – gérer les propriétés du projet avec Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}