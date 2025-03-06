---
title: Enregistrer au format CSV, texte et modèle dans Aspose.Tasks
linktitle: Enregistrer au format CSV, texte et modèle dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment enregistrer des fichiers Microsoft Project aux formats CSV, Texte et Modèle à l'aide d'Aspose.Tasks pour Java.
type: docs
weight: 16
url: /fr/java/project-file-operations/save-csv-text-template/
---
## Introduction
Dans ce didacticiel, nous verrons comment enregistrer des fichiers de projet dans différents formats tels que CSV, texte et modèle à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de travailler avec des fichiers Microsoft Project sans avoir besoin d'installer Microsoft Project.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java téléchargée et configurée dans votre projet Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
3. Connaissance de base du langage de programmation Java.

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre fichier Java :
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Enregistrer le projet au format CSV
Décomposons les étapes pour enregistrer un projet au format CSV :
### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Étape 2 : Enregistrer au format CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Enregistrer le projet sous forme de texte
Voici comment enregistrer un projet sous forme de texte :
### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Étape 2 : Enregistrer sous forme de texte
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Enregistrer le projet comme modèle
L'enregistrement d'un projet en tant que modèle implique les étapes suivantes :
### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Étape 2 : Définir les options du modèle
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Étape 3 : Enregistrer en tant que modèle
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Conclusion
Dans ce didacticiel, nous avons appris à enregistrer des fichiers Microsoft Project au format CSV, texte et modèle à l'aide d'Aspose.Tasks pour Java. Avec ces étapes simples, vous pouvez gérer efficacement vos fichiers de projet dans différents formats, améliorant ainsi votre productivité en tant que développeur Java.
## FAQ
### Q : Aspose.Tasks pour Java peut-il gérer des fichiers de projet complexes ?
R : Absolument ! Aspose.Tasks for Java peut gérer facilement des projets de complexité variable, offrant une prise en charge complète des formats de fichiers Microsoft Project.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour Java à partir de[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de l'assistance pour Aspose.Tasks pour Java ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question concernant Aspose.Tasks pour Java.
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez acheter une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/), vous permettant d'évaluer tout le potentiel de la bibliothèque.
### Q : Aspose.Tasks pour Java est-il compatible avec différents systèmes d'exploitation ?
: Oui, Aspose.Tasks for Java est compatible avec divers systèmes d'exploitation, notamment Windows, macOS et Linux.