---
title: Échelle de taux de lecture et d’écriture pour les affectations de ressources dans Aspose.Tasks
linktitle: Échelle de taux de lecture et d’écriture pour les affectations de ressources dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à gérer efficacement l'échelle des taux d'affectation des ressources dans Aspose.Tasks pour Java avec ce didacticiel complet.
type: docs
weight: 20
url: /fr/java/resource-assignments/read-write-rate-scale/
---
## Introduction
Dans ce didacticiel, nous aborderons la gestion de l'échelle de taux d'affectation des ressources à l'aide d'Aspose.Tasks for Java, une bibliothèque robuste permettant de travailler par programmation avec les fichiers Microsoft Project. En suivant ces étapes, vous serez en mesure de manipuler efficacement les paramètres d'échelle de taux pour les affectations de ressources dans vos applications Java.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Environnement de développement Java : assurez-vous que le kit de développement Java (JDK) est installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez et installez la bibliothèque Aspose.Tasks pour Java à partir de[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
Tout d’abord, vous devez importer les packages nécessaires pour travailler avec les fonctionnalités Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Étape 1 : Configurez votre projet
Commencez par configurer votre projet Java et incluez la bibliothèque Aspose.Tasks dans vos dépendances.
## Étape 2 : charger le fichier de projet
Chargez le fichier projet avec lequel vous souhaitez travailler dans votre application Java.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Étape 3 : Ajouter une tâche
Ajoutez une nouvelle tâche à votre projet.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Étape 4 : Définir les ressources
Définir les ressources matérielles et immatérielles et préciser leurs types.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Étape 5 : attribuer des ressources à une tâche
Affectez les ressources précédemment définies à la tâche ainsi que leurs types d'échelle de taux.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Étape 6 : Enregistrez le projet
Enregistrez le projet avec les affectations de ressources modifiées.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Étape 7 : Récupérer les affectations de ressources
Rechargez le projet enregistré et récupérez les affectations de ressources pour vérifier les paramètres de l'échelle de tarifs.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Conclusion
La gestion de l'échelle des taux d'affectation des ressources dans Aspose.Tasks pour Java est cruciale pour une gestion de projet efficace. En suivant ce guide étape par étape, vous pouvez manipuler de manière transparente les paramètres d'échelle de taux pour les affectations de ressources dans vos applications Java.
## FAQ
### Q1 : Puis-je utiliser Aspose.Tasks pour Java avec n’importe quel IDE Java ?
R : Oui, Aspose.Tasks for Java est compatible avec tous les principaux IDE Java, notamment IntelliJ IDEA, Eclipse et NetBeans.
### Q2 : Aspose.Tasks prend-il en charge d'autres formats de fichiers que MPP ?
R : Oui, Aspose.Tasks prend en charge différents formats de fichiers, notamment MPP, XML et HTML.
### Q3 : Aspose.Tasks est-il adapté à la gestion de projet au niveau de l’entreprise ?
: Absolument, Aspose.Tasks offre des fonctionnalités complètes pour gérer des projets de toute envergure, ce qui le rend adapté à la gestion de projet au niveau de l'entreprise.
### Q4 : Puis-je personnaliser les affectations de ressources au-delà de l'échelle tarifaire ?
R : Oui, Aspose.Tasks offre des fonctionnalités étendues pour personnaliser les affectations de ressources, y compris les ajustements de coût, de travail et de durée.
### Q5 : Existe-t-il un forum communautaire pour le support d'Aspose.Tasks ?
 R : Oui, vous pouvez trouver de l'aide et interagir avec d'autres utilisateurs sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).