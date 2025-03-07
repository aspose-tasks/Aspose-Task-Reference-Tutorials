---
title: Générer des données chronologiques dans Aspose.Tasks
linktitle: Générer des données chronologiques pour les affectations de ressources dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment générer des données chronologiques pour les affectations de ressources à l'aide d'Aspose.Tasks pour Java. Améliorez l’efficacité de la gestion de projet avec ce guide complet.
weight: 24
url: /fr/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer des données chronologiques dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous allons parcourir le processus de génération de données chronologiques pour les affectations de ressources à l'aide d'Aspose.Tasks pour Java. Les données chronologiques fournissent des informations précieuses sur la façon dont les ressources sont allouées au fil du temps au sein d'un projet, aidant ainsi les chefs de projet à prendre des décisions éclairées.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez télécharger et installer JDK à partir de[ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Bibliothèque Aspose.Tasks pour Java : vous devez disposer de la bibliothèque Aspose.Tasks pour Java. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, importons les packages nécessaires pour travailler avec Aspose.Tasks :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Étape 1 : Lire le fichier MPP source
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
// Lire le fichier MPP source
Project project = new Project(dataDir + "project.mpp");
```
## Étape 2 : Obtenir l'affectation des tâches et des ressources
```java
// Obtenez la première tâche du projet
Task task = project.getRootTask().getChildren().getById(1);
// Obtenez la première affectation de ressource du projet
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Étape 3 : générer des données chronologiques avec un contour plat
```java
// Le contour plat est le contour par défaut
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 4 : Changer le contour en Tortue
```java
// Changer le contour en Tortue
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 5 : Changer le contour en BackLoaded
```java
// Changer le contour en BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 6 : Changer le contour en FrontLoaded
```java
// Changer le contour en FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 7 : Remplacez Contour par Bell
```java
// Changer le contour en Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 8 : Changer le contour en EarlyPeak
```java
// Changer le contour en EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 9 : Changer le contour en LatePeak
```java
// Changer le contour en LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Étape 10 : Changer le contour en DoublePeak
```java
// Changer le contour en DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment générer des données chronologiques pour les affectations de ressources à l'aide d'Aspose.Tasks pour Java. Comprendre les différents contours de travail peut aider les chefs de projet à gérer efficacement l'allocation des ressources et la planification de leurs projets.
## FAQ
### Puis-je utiliser Aspose.Tasks avec d’autres bibliothèques Java ?
Oui, Aspose.Tasks peut être intégré à d'autres bibliothèques Java pour améliorer les capacités de gestion de projet.
### Aspose.Tasks est-il adapté aux projets d’entreprise à grande échelle ?
Absolument, Aspose.Tasks est conçu pour gérer des projets de toutes tailles, y compris des projets d'entreprise à grande échelle.
### Aspose.Tasks prend-il en charge différents formats de fichiers de projet ?
Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet, notamment MPP, XML et MPX.
### Puis-je personnaliser les contours de travail en fonction des exigences de mon projet ?
Oui, Aspose.Tasks permet aux utilisateurs de définir des contours de travail personnalisés en fonction des besoins spécifiques de leur projet.
### Existe-t-il un forum communautaire où je peux obtenir de l'aide avec Aspose.Tasks ?
 Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour du soutien et des discussions.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
