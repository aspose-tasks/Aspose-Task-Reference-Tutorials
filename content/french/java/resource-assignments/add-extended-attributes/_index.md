---
title: Maîtriser la manipulation de MS Project avec Aspose.Tasks pour Java
linktitle: Ajouter des attributs étendus aux affectations de ressources dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à écrire efficacement des informations MS Project à l'aide d'Aspose.Tasks pour Java. Guide étape par étape pour les développeurs Java.
type: docs
weight: 10
url: /fr/java/resource-assignments/add-extended-attributes/
---
## Introduction
Dans ce didacticiel, nous aborderons l'utilisation d'Aspose.Tasks pour Java, une puissante bibliothèque permettant de manipuler les fichiers Microsoft Project par programme. Nous allons nous concentrer sur une tâche fondamentale : écrire des informations MS Project à l'aide d'Aspose.Tasks. Que vous soyez un développeur chevronné ou que vous commenciez tout juste votre parcours dans la programmation Java, ce guide vous guidera pas à pas tout au long du processus.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez et installez la bibliothèque Aspose.Tasks pour Java. Vous pouvez l'obtenir auprès de[ici](https://releases.aspose.com/tasks/java/).
3. Environnement de développement intégré (IDE) : choisissez un IDE de votre préférence. Nous recommandons IntelliJ IDEA ou Eclipse.

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
#Décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : configurer le répertoire de données
Définissez le répertoire dans lequel les données de votre projet seront stockées.
```java
String dataDir = "Your Data Directory";
```
## Étape 2 : Créer une instance de projet
Initialisez une nouvelle instance de projet.
```java
Project project = new Project();
```
## Étape 3 : Définir les propriétés des informations sur le projet
Définissez les propriétés du projet telles que la date de début, la planification à partir du début et la date d'état.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## Étape 4 : Enregistrer le projet au format XML
Enregistrez le projet avec les informations mises à jour sous forme de fichier XML.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à écrire des informations MS Project à l'aide d'Aspose.Tasks pour Java. Grâce à ces nouvelles connaissances, vous pouvez automatiser diverses tâches liées aux fichiers Microsoft Project, améliorant ainsi votre productivité en tant que développeur Java.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour Java pour lire des fichiers MS Project ?
R : Oui, Aspose.Tasks pour Java fournit des fonctionnalités robustes pour la lecture et l'écriture de fichiers MS Project.
### Q : Aspose.Tasks pour Java est-il compatible avec différentes versions de MS Project ?
R : Absolument, Aspose.Tasks for Java prend en charge différentes versions de MS Project, garantissant ainsi la compatibilité entre différents formats de fichiers.
### Q : Existe-t-il des limitations à la version d'essai d'Aspose.Tasks pour Java ?
: Bien que la version d'essai vous permette d'explorer les capacités de la bibliothèque, elle présente certaines limitations telles que des filigranes sur les fichiers de sortie.
### Q : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour Java ?
 R : Vous pouvez demander de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks pour Java ?
 R : Oui, des licences temporaires sont disponibles pour une utilisation à court terme. Vous pouvez en obtenir un auprès de[ici](https://purchase.aspose.com/temporary-license/).