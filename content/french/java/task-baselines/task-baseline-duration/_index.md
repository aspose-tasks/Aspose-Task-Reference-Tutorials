---
title: Gestion de la durée de référence des tâches dans Aspose.Tasks
linktitle: Gestion de la durée de référence des tâches dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment gérer efficacement les références de tâches dans MS Project à l'aide d'Aspose.Tasks pour Java. Ce didacticiel vous guide étape par étape tout au long du processus.
type: docs
weight: 12
url: /fr/java/task-baselines/task-baseline-duration/
---
## Introduction
La gestion des tâches de base dans MS Project est cruciale pour la planification et le suivi du projet. Dans ce didacticiel, nous verrons comment gérer efficacement les durées de référence des tâches à l'aide d'Aspose.Tasks pour Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Environnement de développement Java : assurez-vous que le kit de développement Java (JDK) est installé sur votre système.
2.  Bibliothèque Aspose.Tasks : téléchargez et installez la bibliothèque Aspose.Tasks pour Java à partir de[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, importez les packages nécessaires à votre projet Java :
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Étape 1 : Créer une instance de projet
Initialisez une nouvelle instance de projet à l'aide du code suivant :
```java
Project project = new Project();
```
## Étape 2 : Créer une référence de tâches
Créez une nouvelle tâche et définissez sa référence à l'aide du code suivant :
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Étape 3 : Afficher les informations de base sur la tâche
Récupérez et affichez les informations de base des tâches telles que la durée, la date de début, la date de fin, etc. :
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Étape 4 : Vérifier la référence intermédiaire et le coût fixe
Vérifiez si la référence est une référence intermédiaire et récupérez tous les coûts fixes qui y sont associés :
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Étape 5 : Imprimer les données chronologiques
Imprimer les données chronologiques associées à la référence de tâche :
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
En suivant ces étapes, vous pouvez gérer efficacement les durées de référence des tâches dans MS Project à l'aide d'Aspose.Tasks pour Java.

## Conclusion
La gestion des références de tâches est essentielle pour la gestion de projet, vous permettant de suivre les écarts par rapport au calendrier prévu. Avec Aspose.Tasks pour Java, ce processus devient rationalisé et efficace, permettant un meilleur contrôle et une meilleure livraison du projet.
## FAQ
### Qu’est-ce qu’une référence de tâches dans MS Project ?
Une référence de tâche dans MS Project est un instantané du calendrier initial prévu pour une tâche, y compris sa date de début, sa date de fin et sa durée.
### Pourquoi la gestion des références de tâches est-elle importante ?
La gestion des références de tâches permet de comparer le calendrier prévu avec l'avancement réel du projet, facilitant ainsi un meilleur suivi et une meilleure prise de décision.
### Puis-je modifier une référence de tâche une fois qu'elle est définie ?
Oui, vous pouvez modifier les références de tâches dans MS Project pour refléter les modifications apportées au plan de projet. Cependant, il est essentiel de documenter tout écart par rapport à la référence initiale.
### Aspose.Tasks prend-il en charge d'autres fonctionnalités de gestion de projet ?
Oui, Aspose.Tasks offre un large éventail de fonctionnalités pour la gestion de projet, notamment la planification des tâches, l'allocation des ressources et la génération de diagrammes de Gantt.
### Où puis-je trouver de l’assistance pour Aspose.Tasks ?
 Vous pouvez trouver une assistance pour Aspose.Tasks sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), où vous pouvez poser des questions et interagir avec d'autres utilisateurs.