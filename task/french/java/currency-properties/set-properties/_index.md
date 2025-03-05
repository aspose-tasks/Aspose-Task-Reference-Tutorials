---
title: Définir les propriétés de devise dans les projets Aspose.Tasks
linktitle: Définir les propriétés de devise dans les projets Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment définir les propriétés monétaires dans les projets Aspose.Tasks à l'aide de Java. Manipulez les fichiers Microsoft Project sans effort.
type: docs
weight: 11
url: /fr/java/currency-properties/set-properties/
---
## Introduction
Dans ce didacticiel, nous verrons comment définir les propriétés de devise dans les projets Aspose.Tasks à l'aide de Java. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Bibliothèque Aspose.Tasks for Java : téléchargez et installez la bibliothèque Aspose.Tasks for Java à partir du[lien de téléchargement](https://releases.aspose.com/tasks/java/).
3. Environnement de développement intégré (IDE) : choisissez votre IDE préféré tel qu'Eclipse ou IntelliJ IDEA.
## Importer des packages
Tout d’abord, importons les packages nécessaires pour travailler avec Aspose.Tasks en Java.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## Étape 1 : Définir le répertoire de données
Définissez le répertoire de données où se trouvent vos fichiers de projet.
```java
String dataDir = "Your Data Directory";
```
## Étape 2 : Créer une instance de projet
Créez une nouvelle instance de projet à l'aide d'Aspose.Tasks.
```java
Project project = new Project();
```
## Étape 3 : Définir les propriétés de la devise
Maintenant, définissons les propriétés monétaires du projet.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## Étape 4 : Enregistrez le projet
Enregistrez le projet avec les propriétés de devise mises à jour.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## Étape 5 : Afficher le message de fin
Afficher un message indiquant la réussite du processus.
```java
System.out.println("Process completed Successfully");
```
Toutes nos félicitations! Vous avez défini avec succès les propriétés monétaires dans un projet Aspose.Tasks à l'aide de Java.
## Conclusion
Dans ce didacticiel, nous avons appris à utiliser Aspose.Tasks pour Java pour définir les propriétés monétaires dans les fichiers de projet. Avec Aspose.Tasks, les développeurs peuvent manipuler efficacement les données du projet, ce qui en fait un outil précieux pour les applications de gestion de projet.
## FAQ
### Puis-je définir plusieurs devises dans un seul projet à l'aide d'Aspose.Tasks ?
Oui, Aspose.Tasks vous permet de gérer plusieurs devises dans un seul fichier de projet.
### Aspose.Tasks est-il compatible avec différentes versions des fichiers Microsoft Project ?
Oui, Aspose.Tasks prend en charge différentes versions de fichiers Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.
### Aspose.Tasks prend-il en charge les formats de devises personnalisés ?
Absolument, Aspose.Tasks offre une flexibilité dans la définition de formats de devises personnalisés pour répondre aux exigences spécifiques du projet.
### Puis-je intégrer Aspose.Tasks à d’autres bibliothèques ou frameworks Java ?
Oui, Aspose.Tasks peut être intégré de manière transparente à d’autres bibliothèques et frameworks Java, améliorant ainsi sa fonctionnalité et sa polyvalence.
### Où puis-je trouver une assistance ou une assistance supplémentaire pour Aspose.Tasks ?
 Pour une assistance supplémentaire, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), où vous pouvez trouver des ressources utiles et interagir avec la communauté.