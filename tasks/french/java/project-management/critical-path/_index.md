---
title: Calculer le chemin critique du projet MS dans Aspose.Tasks
linktitle: Calculer le chemin critique dans les projets Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment calculer le chemin critique dans MS Project à l'aide d'Aspose.Tasks pour Java. Celui-ci fournit des conseils étape par étape pour une gestion de projet efficace.
weight: 10
url: /fr/java/project-management/critical-path/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calculer le chemin critique du projet MS dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de calcul du chemin critique dans MS Project à l'aide d'Aspose.Tasks pour Java. Le chemin critique est essentiel pour la gestion de projet car il permet d'identifier la séquence de tâches qui doivent être terminées à temps pour garantir que le calendrier global du projet ne soit pas retardé.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre classe Java :
```java
import com.aspose.tasks.*;
```
## Étape 1 : configurer le répertoire de données
Définissez le chemin d'accès à votre répertoire de données où se trouve votre fichier MS Project.
```java
String dataDir = "Your Data Directory";
```
## Étape 2 : Charger le fichier MS Project
Chargez le fichier MS Project à l'aide de la bibliothèque Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Étape 3 : Définir le mode de calcul
Définissez le mode de calcul sur automatique pour permettre le calcul du chemin critique.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## Étape 4 : Ajouter des tâches
Ajoutez des tâches à votre projet. Dans cet exemple, nous ajoutons trois sous-tâches.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## Étape 5 : Créer des liens de tâches
Créez des liens de tâches pour définir les dépendances entre les tâches.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## Étape 6 : Afficher le chemin critique
Récupérer et afficher le chemin critique du projet.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## Étape 7 : Afficher le résultat
Afficher un message indiquant la réussite du processus.
```java
System.out.println("Process completed Successfully");
```

## Conclusion
Le calcul du chemin critique dans MS Project à l'aide d'Aspose.Tasks pour Java est crucial pour une gestion de projet efficace. En suivant les étapes décrites dans ce didacticiel, vous pouvez identifier avec précision la séquence de tâches critiques pour le calendrier de votre projet.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour Java avec n’importe quelle version des fichiers MS Project ?
R : Oui, Aspose.Tasks for Java prend en charge différentes versions de fichiers MS Project, y compris les fichiers .mpp de MS Project 2003 à MS Project 2019.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de l'assistance pour Aspose.Tasks pour Java ?
 R : Vous pouvez trouver de l'aide sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez acheter une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Q : Comment puis-je acheter Aspose.Tasks pour Java ?
 R : Vous pouvez acheter Aspose.Tasks pour Java sur le site Web.[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
