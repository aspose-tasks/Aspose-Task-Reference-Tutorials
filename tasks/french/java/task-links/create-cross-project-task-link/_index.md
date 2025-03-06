---
title: Créer un lien de tâche inter-projet dans Aspose.Tasks
linktitle: Créer un lien de tâche inter-projet dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Améliorez la collaboration sur les projets avec Aspose.Tasks pour Java. Apprenez à créer des liens de tâches inter-projets étape par étape. Boostez votre efficacité dès maintenant !
weight: 10
url: /fr/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un lien de tâche inter-projet dans Aspose.Tasks

## Introduction
Dans le monde dynamique de la gestion de projet, l’efficacité et la collaboration sont primordiales. Aspose.Tasks for Java fournit une solution robuste pour améliorer vos capacités de gestion de projet. Dans ce didacticiel, nous approfondirons le processus de création de liens de tâches entre projets à l'aide d'Aspose.Tasks pour Java. Ce guide étape par étape vous dotera des compétences nécessaires pour relier de manière transparente les tâches de différents projets, favorisant ainsi une meilleure coordination et des flux de travail rationalisés.
## Conditions préalables
Avant de commencer ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une connaissance pratique de la programmation Java.
-  Aspose.Tasks pour Java installé. Vous pouvez le télécharger depuis le[Aspose.Tasks pour la page de version Java](https://releases.aspose.com/tasks/java/).
- Une compréhension de base de la gestion de projet et des dépendances des tâches.
## Importer des packages
Pour lancer le processus, importons les packages nécessaires dans votre environnement Java. Cela garantit que vous avez accès aux fonctionnalités Aspose.Tasks pour Java. Utilisez l'extrait de code suivant :
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Maintenant, décomposons le code ci-dessus en étapes compréhensibles :
## Étape 1 : Configurez votre environnement
Avant de plonger dans le code, assurez-vous que Java est installé et que la bibliothèque Aspose.Tasks for Java est correctement ajoutée à votre projet.
## Étape 2 : Créer une instance de projet
Initialisez un nouveau projet à l'aide de la bibliothèque Aspose.Tasks :
```java
Project project = new Project();
```
## Étape 3 : Ajouter une tâche récapitulative
Créez une tâche récapitulative pour organiser et gérer les tâches liées :
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Étape 4 : Ajouter une tâche externe
Afin de créer un lien vers une tâche d'un autre projet, ajoutez une tâche externe à la tâche récapitulative :
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Étape 5 : Ajouter une tâche locale
Ajoutez une tâche locale à la tâche récapitulative. Ce sera la tâche liée à la tâche externe :
```java
Task t = summary.getChildren().add("Task");
```
## Étape 6 : Créer un lien de tâche
Etablir le lien de tâche entre la tâche externe et la tâche locale :
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Étape 7 : Afficher les résultats
Enfin, affichez le résultat de la conversion :
```java
System.out.println("Process completed Successfully");
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment créer des liens de tâches entre projets à l'aide d'Aspose.Tasks pour Java. Cette fonctionnalité améliore la collaboration et la coordination dans la gestion de projet, garantissant une intégration transparente entre les tâches de différents projets.
## FAQ
### Puis-je lier des tâches de plusieurs projets externes dans la même tâche récapitulative ?
Oui, vous pouvez lier des tâches de différents projets externes au sein d'une même tâche récapitulative, en suivant un processus similaire.
### Que se passe-t-il si la tâche externe du projet lié est modifiée ?
Toute modification apportée à la tâche externe sera reflétée dans la tâche liée dans votre projet actuel.
### Est-il possible de créer des liens entre des tâches dans différents formats de fichiers ?
Oui, Aspose.Tasks for Java prend en charge la liaison de tâches entre des projets dans différents formats de fichiers.
### Puis-je dissocier les tâches une fois qu'elles sont liées entre les projets ?
Oui, vous pouvez dissocier les tâches en supprimant le lien de tâche à l'aide des méthodes Aspose.Tasks appropriées.
### Existe-t-il des limites au nombre de tâches pouvant être liées entre les projets ?
Le nombre de tâches pouvant être liées est soumis aux capacités et aux limitations de votre licence Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
