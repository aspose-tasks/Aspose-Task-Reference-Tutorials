---
title: Rédiger le résumé du projet MPP dans Aspose.Tasks
linktitle: Rédiger le résumé du projet MPP dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à rédiger des résumés de projets MPP en Java à l'aide d'Aspose.Tasks. Définissez et récupérez les informations du projet sans effort.
type: docs
weight: 27
url: /fr/java/project-file-operations/write-mpp-project-summary/
---
## Introduction
Dans ce didacticiel, nous apprendrons comment utiliser Aspose.Tasks pour Java pour rédiger des résumés de projets MPP. Aspose.Tasks est une puissante bibliothèque Java permettant de travailler avec des fichiers Microsoft Project. En suivant les étapes décrites ci-dessous, vous pourrez définir et récupérer diverses informations récapitulatives sur un projet utilisant cette bibliothèque.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Tasks pour Java : téléchargez et installez la bibliothèque Aspose.Tasks pour Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
3. Environnement de développement intégré (IDE) : choisissez votre IDE préféré pour le développement Java, tel que IntelliJ IDEA, Eclipse ou NetBeans.

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre classe Java :
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Étape 1 : configurer le projet et définir les informations récapitulatives
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
//Initialisez un nouvel objet Projet avec le chemin d'accès à votre fichier projet
Project project = new Project(dataDir + "project.mpp");
// Définir des informations récapitulatives sur le projet
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Définir la date de création du projet
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Définir des mots-clés pour le projet
project.set(Prj.KEYWORDS, "MPP Aspose");
// Définir la date de la dernière impression du projet
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Étape 2 : Enregistrer les informations récapitulatives du projet
```java
// Enregistrez à nouveau le projet au format MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Afficher un message de réussite
System.out.println("Process completed Successfully");
```
## Étape 3 : Lire les informations récapitulatives du projet
```java
// Lecture des informations récapitulatives du projet
project = new Project(dataDir + "MppAspose.xml");
// Auteur de l'impression du projet
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Imprimer le dernier auteur du projet
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Imprimer le numéro de révision du projet
System.out.println("Revision: " + project.get(Prj.REVISION));
// Imprimer les mots-clés du projet
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Imprimer les commentaires du projet
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Imprimer la date de création du projet
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Imprimer (à nouveau) les mots-clés du projet
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Imprimer la date de la dernière impression du projet
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment rédiger des résumés de projets MPP à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez définir et récupérer efficacement diverses informations récapitulatives sur vos fichiers de projet. Aspose.Tasks simplifie le processus de travail avec les fichiers Microsoft Project dans les applications Java, offrant des fonctionnalités robustes et une facilité d'utilisation.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour Java avec d'autres bibliothèques Java ?
R : Oui, Aspose.Tasks for Java peut être intégré de manière transparente à d'autres bibliothèques Java pour améliorer vos capacités de gestion de projet.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Q : À quelle fréquence Aspose.Tasks pour Java est-il mis à jour ?
R : Aspose.Tasks for Java est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions de fichiers Java et Microsoft Project.
### Q : Puis-je personnaliser davantage les informations récapitulatives du projet ?
R : Absolument, Aspose.Tasks for Java propose de nombreuses options pour personnaliser les informations récapitulatives du projet en fonction de vos besoins spécifiques.
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
R : Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).