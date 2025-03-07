---
title: Maîtriser le nombre d'échelles de temps MS Project dans Aspose.Tasks
linktitle: Définir le nombre d'échelles de temps dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment gérer efficacement le nombre d'échelles de temps dans MS Project à l'aide d'Aspose.Tasks pour Java. Optimisez la visualisation et la gestion des projets sans effort.
weight: 22
url: /fr/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser le nombre d'échelles de temps MS Project dans Aspose.Tasks

## Introduction
La gestion du nombre d'échelles de temps dans MS Project peut affecter considérablement la visualisation et la gestion du projet. Avec Aspose.Tasks for Java, une API puissante pour gérer les tâches de gestion de projet par programmation, vous pouvez manipuler efficacement le décompte de l'échelle de temps pour adapter les vues de projet à vos besoins spécifiques.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir mis en place les éléments suivants :
1. Environnement de développement Java : assurez-vous que le kit de développement Java (JDK) est installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez et installez la bibliothèque Aspose.Tasks pour Java. Vous pouvez l'obtenir de[ici](https://releases.aspose.com/tasks/java/).
3. Connaissance de base de la programmation Java : une connaissance du langage de programmation Java sera bénéfique.

## Importer des packages
Importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Étape 1 : Définir le répertoire de données
Définissez le chemin d'accès au répertoire de données où vos fichiers de projet seront stockés :
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin d'accès à votre répertoire de données.
## Étape 2 : Créer une instance de projet
 Instancier un nouveau`Project` objet:
```java
Project project = new Project();
```
Cela crée un nouvel objet de projet.
## Étape 3 : Configurer la vue Diagramme de Gantt
 Créer un`GanttChartView` objet pour configurer la vue du diagramme de Gantt :
```java
GanttChartView view = new GanttChartView();
```
## Étape 4 : Définir le nombre d'échelles de temps pour le niveau inférieur
Définissez le nombre et la visibilité des ticks pour le niveau inférieur de l'échelle de temps :
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Ceci spécifie le nombre d'intervalles et s'il faut afficher les graduations pour le niveau inférieur.
## Étape 5 : Définir le nombre d'échelles de temps pour le niveau intermédiaire
De même, configurez le niveau d'échelle de temps intermédiaire :
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Étape 6 : Ajouter une vue au projet
Ajoutez la vue configurée au projet :
```java
project.getViews().add(view);
```
Cela ajoute la vue personnalisée au projet.
## Étape 7 : Ajouter des données de test au projet
Ajoutez quelques données de test au projet pour démonstration :
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Cela crée deux tâches avec des durées spécifiées.
## Étape 8 : Enregistrer le projet au format PDF
Enregistrez le projet sous forme de fichier PDF :
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Cela enregistre le projet avec les configurations appliquées dans un fichier PDF.

## Conclusion
La gestion efficace du nombre d'échelles de temps dans MS Project à l'aide d'Aspose.Tasks pour Java vous permet de personnaliser les vues du projet pour une meilleure visualisation et gestion.
## FAQ
### Q : Aspose.Tasks pour Java peut-il gérer des fichiers de projet à grande échelle ?
R : Oui, Aspose.Tasks for Java est capable de gérer efficacement des fichiers de projet à grande échelle.
### Q : Aspose.Tasks pour Java est-il compatible avec différents IDE Java ?
R : Oui, Aspose.Tasks pour Java fonctionne de manière transparente avec les environnements de développement intégrés (IDE) Java populaires tels qu'Eclipse et IntelliJ IDEA.
### Q : Puis-je personnaliser l'apparence des diagrammes de Gantt à l'aide d'Aspose.Tasks pour Java ?
R : Absolument, Aspose.Tasks pour Java offre des fonctionnalités étendues pour personnaliser l'apparence des diagrammes de Gantt en fonction de vos besoins.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez obtenir une version d'essai gratuite auprès de[ici](https://releases.aspose.com/).
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
 R : Vous pouvez trouver de l'aide et de l'assistance sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
