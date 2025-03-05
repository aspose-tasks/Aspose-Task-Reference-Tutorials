---
title: Mettre à jour le fichier MPP dans Aspose.Tasks
linktitle: Mettre à jour le fichier MPP dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment mettre à jour les fichiers MPP de manière transparente à l'aide d'Aspose.Tasks pour Java. Suivez notre guide étape par étape pour une manipulation efficace des fichiers de projet.
type: docs
weight: 19
url: /fr/java/project-management/update-mpp/
---
## Introduction
Dans le domaine de la gestion de projet, le traitement et la mise à jour des dossiers de projet sont une tâche cruciale. Aspose.Tasks for Java fournit une solution puissante permettant aux développeurs Java de manipuler les fichiers Microsoft Project de manière transparente. Dans ce didacticiel, nous aborderons la mise à jour des fichiers MPP à l'aide d'Aspose.Tasks pour Java.
## Conditions préalables
Avant de plonger dans ce didacticiel, assurez-vous d'avoir les éléments suivants :
1. Environnement de développement Java : assurez-vous que Java est installé sur votre système.
2.  Aspose.Tasks for Java : téléchargez et installez Aspose.Tasks for Java à partir du[page de téléchargement](https://releases.aspose.com/tasks/java/).
3. Connaissance de base de Java : Une connaissance du langage de programmation Java est nécessaire pour suivre les exemples.

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre projet Java pour utiliser efficacement les fonctionnalités d'Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Cette ligne de code importe toutes les classes et méthodes essentielles de la bibliothèque Aspose.Tasks, vous permettant de travailler sans effort avec les fichiers Microsoft Project.

Maintenant, décomposons le processus de mise à jour d'un fichier MPP à l'aide d'Aspose.Tasks for Java en étapes gérables.
## Étape 2 : Définir le répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin réel où se trouve votre fichier MPP.
## Étape 3 : Lire le projet existant
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Ce code lit un fichier de projet MPP existant nommé`SampleMSP2010.mpp` à partir du répertoire de données spécifié.
## Étape 4 : Créer une nouvelle tâche
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Ici, nous ajoutons une nouvelle tâche nommée « Task1 » à la tâche racine du projet.
## Étape 5 : Définir les dates de début et de fin
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Ces lignes de code définissent la date de début et la date de fin de la tâche nouvellement créée.
## Étape 6 : Enregistrez le projet
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Enfin, cette étape enregistre le projet mis à jour avec la tâche nouvellement ajoutée dans un nouveau fichier MPP nommé`AfterLinking.mpp`.

## Conclusion
Dans ce didacticiel, nous avons exploré comment mettre à jour les fichiers MPP à l'aide d'Aspose.Tasks pour Java. En suivant le guide étape par étape, vous pouvez manipuler efficacement les fichiers Microsoft Project dans vos applications Java.
## FAQ
### Q : Aspose.Tasks pour Java peut-il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks for Java fournit des fonctionnalités robustes pour gérer efficacement les structures de projets complexes.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir du[site web](https://releases.aspose.com/).
### Q : Aspose.Tasks pour Java prend-il en charge différentes versions des fichiers Microsoft Project ?
R : Absolument, Aspose.Tasks for Java prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP, MPT et XML.
### Q : Puis-je obtenir des licences temporaires pour Aspose.Tasks pour Java ?
 R : Oui, des licences temporaires sont disponibles à des fins de test. Vous pouvez les obtenir auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je demander de l'aide ou de l'assistance concernant Aspose.Tasks pour Java ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute aide ou question.