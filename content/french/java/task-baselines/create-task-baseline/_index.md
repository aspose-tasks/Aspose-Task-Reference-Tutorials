---
title: Créer une référence de tâches MS Project dans Aspose.Tasks
linktitle: Création d'une référence de tâches dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment créer une base de données de tâches Microsoft Project en Java à l'aide d'Aspose.Tasks, une bibliothèque puissante permettant de gérer les données de projet sans effort.
type: docs
weight: 11
url: /fr/java/task-baselines/create-task-baseline/
---
## Introduction
Dans ce didacticiel, nous aborderons le processus de création d'une base de tâches Microsoft Project à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de travailler avec des fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project. Avec Aspose.Tasks, vous pouvez manipuler sans effort les données du projet, y compris les tâches, les ressources et les calendriers, pour rationaliser les tâches de gestion de projet.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : Aspose.Tasks pour Java nécessite que JDK soit installé sur votre système. Vous pouvez télécharger et installer JDK à partir du site Web d'Oracle.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez la bibliothèque Aspose.Tasks pour Java à partir du[lien de téléchargement](https://releases.aspose.com/tasks/java/) fourni.

## Importer des packages
Pour commencer à travailler avec Aspose.Tasks dans votre projet Java, importez les packages nécessaires :
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Étape 1 : Créer un objet de projet
```java
Project project = new Project();
```
 Tout d'abord, créez un nouveau`Project` objet. Cet objet représente le fichier Microsoft Project avec lequel vous allez travailler.
## Étape 2 : ajouter une tâche au projet
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 En utilisant le`getRootTask()` méthode, accédez à la tâche racine du projet puis ajoutez-y une nouvelle tâche à l'aide du`add()` méthode. Donnez un nom à la tâche entre parenthèses.
## Étape 3 : Définir la référence pour les tâches spécifiées
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Pour définir une référence pour des tâches spécifiques, créez une liste de tâches (`myList` dans ce cas) et remplissez-le avec les tâches pour lesquelles vous souhaitez définir la référence. Ensuite, utilisez le`setBaseline()` méthode, spécifiant le type de ligne de base et la liste des tâches.
## Étape 4 : Définir la référence pour l'ensemble du projet
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternativement, vous pouvez définir une référence pour l'ensemble du projet en appelant simplement le`setBaseline()` méthode avec le type de ligne de base spécifié.

## Conclusion
Dans ce didacticiel, nous avons expliqué comment créer une référence de tâches Microsoft Project à l'aide d'Aspose.Tasks pour Java. En suivant les étapes décrites ci-dessus, vous pouvez gérer efficacement les données du projet et rationaliser facilement les tâches de gestion de projet.
## FAQ
### Puis-je utiliser Aspose.Tasks pour Java sans que Microsoft Project soit installé ?
Oui, Aspose.Tasks for Java vous permet de travailler avec des fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project sur votre système.
### Aspose.Tasks pour Java est-il compatible avec différentes versions de Microsoft Project ?
Oui, Aspose.Tasks for Java prend en charge différentes versions de Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.
### Puis-je manipuler les ressources du projet à l’aide d’Aspose.Tasks pour Java ?
Absolument, Aspose.Tasks for Java fournit des fonctionnalités robustes pour manipuler les ressources du projet, notamment l'ajout, la mise à jour et la suppression de ressources selon les besoins.
### Aspose.Tasks for Java prend-il en charge la définition des dépendances des tâches ?
Oui, vous pouvez définir facilement les dépendances des tâches à l'aide d'Aspose.Tasks for Java, vous permettant d'établir la séquence des tâches au sein de votre projet.
### Un support technique est-il disponible pour Aspose.Tasks pour Java ?
 Oui, vous pouvez accéder au support technique pour Aspose.Tasks for Java via le[forum d'entraide](https://forum.aspose.com/c/tasks/15), où vous pouvez poser des questions et demander de l'aide à la communauté et au personnel d'assistance d'Aspose.