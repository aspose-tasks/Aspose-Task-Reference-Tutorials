---
title: Lire les données de définition de groupe dans Aspose.Tasks
linktitle: Lire les données de définition de groupe dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment lire les données de définition de groupe à partir de fichiers Microsoft Project à l'aide d'Aspose.Tasks pour Java. Suivez notre tutoriel étape par étape.
weight: 10
url: /fr/java/project-data-reading/read-group-definition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les données de définition de groupe dans Aspose.Tasks

## Introduction
Aspose.Tasks for Java est une bibliothèque puissante qui permet aux développeurs de manipuler facilement les fichiers Microsoft Project. Dans ce didacticiel, nous allons parcourir étape par étape le processus de lecture des données de définition de groupe à partir d'un fichier de projet à l'aide d'Aspose.Tasks pour Java.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez et installez la bibliothèque Aspose.Tasks pour Java à partir de[ici](https://releases.aspose.com/tasks/java/).
3. Environnement de développement intégré (IDE) : choisissez votre IDE préféré tel que IntelliJ IDEA ou Eclipse.

## Importer des packages
Tout d’abord, importons les packages nécessaires pour commencer à travailler avec Aspose.Tasks for Java.
```java
import com.aspose.tasks.*;
```
## Étape 1 : Configurez votre répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin d'accès au répertoire contenant votre fichier projet.
## Étape 2 : charger le fichier de projet
```java
Project project = new Project(dataDir + "project.mpp");
```
 Chargez votre fichier de projet à l'aide du`Project` constructeur de classe, en passant le chemin d'accès à votre fichier projet.
## Étape 3 : Récupérer le nombre de groupes de tâches
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 Récupérez le nombre de groupes de tâches dans le projet à l'aide de l'outil`getTaskGroups()` méthode.
## Étape 4 : Récupérer les informations du groupe de tâches
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
Récupérez des informations sur un groupe de tâches spécifique, telles que son nom et le nombre de critères de groupe.
## Étape 5 : Récupérer les informations sur les critères du groupe
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
Récupérez des informations sur les critères de groupe, tels que le champ, le groupe activé, la couleur de la cellule et le modèle.
## Étape 6 : Vérifier le groupe parent
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
Vérifiez si le groupe parent est égal au groupe de tâches.
## Étape 7 : Récupérer les informations sur la police du critère
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
Récupérez les informations de police pour le critère, telles que la famille de polices, la taille, le style et l'ordre de tri.

## Conclusion
Dans ce didacticiel, nous avons appris à lire les données de définition de groupe à partir d'un fichier Microsoft Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez extraire et utiliser efficacement les informations sur les groupes de tâches dans vos applications Java.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour Java pour modifier des fichiers de projet ?
R : Oui, Aspose.Tasks pour Java fournit des fonctionnalités étendues pour lire et modifier les fichiers Microsoft Project par programme.
### Q : Aspose.Tasks pour Java est-il compatible avec toutes les versions des fichiers Microsoft Project ?
R : Aspose.Tasks for Java prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP et XML.
### Q : Comment puis-je gérer les erreurs lorsque je travaille avec Aspose.Tasks pour Java ?
R : Vous pouvez implémenter des mécanismes de gestion des erreurs à l’aide de blocs try-catch pour gérer correctement les exceptions pouvant survenir lors de la manipulation de fichiers.
### Q : Aspose.Tasks for Java prend-il en charge l'exportation des données de projet vers d'autres formats ?
R : Oui, Aspose.Tasks for Java vous permet d'exporter des données de projet vers des formats tels que PDF, XLSX et CSV.
### Q : Où puis-je trouver des ressources supplémentaires et une assistance pour Aspose.Tasks pour Java ?
 R : Vous pouvez visiter le[Documentation Aspose.Tasks pour Java](https://reference.aspose.com/tasks/java/) pour des guides complets et reportez-vous au[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
