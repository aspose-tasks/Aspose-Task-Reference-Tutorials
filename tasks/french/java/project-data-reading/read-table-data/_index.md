---
title: Lire les données de la table à partir du fichier dans Aspose.Tasks
linktitle: Lire les données de la table à partir du fichier dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Libérez la puissance d’Aspose.Tasks pour Java. Apprenez à extraire des données de table à partir de fichiers dans ce didacticiel complet.
type: docs
weight: 17
url: /fr/java/project-data-reading/read-table-data/
---
## Introduction
Dans ce didacticiel, nous allons explorer comment lire les données d'une table à partir d'un fichier à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de travailler avec des documents Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger et l'installer à partir du site Web d'Oracle.
2.  Fichier JAR Aspose.Tasks for Java : téléchargez la bibliothèque Aspose.Tasks for Java à partir du[lien de téléchargement](https://releases.aspose.com/tasks/java/) et incluez-le dans votre projet Java.

## Importer des packages
Importez les packages nécessaires pour travailler avec Aspose.Tasks dans votre projet Java :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## Étape 1 : configurer le répertoire de données
Définissez le chemin d'accès au répertoire où se trouve votre fichier Projet :
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin réel vers votre répertoire de données.
## Étape 2 : charger le fichier de projet
Chargez le fichier projet à l'aide d'Aspose.Tasks :
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Assurez-vous de remplacer`"Project2003.mpp"` avec le nom de votre fichier projet.
## Étape 3 : Récupérer les informations sur la table
Récupérez la table du projet et parcourez ses champs :
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Cet extrait de code récupère des informations sur les champs du tableau telles que la largeur, le titre et l'alignement.

## Conclusion
Dans ce didacticiel, nous avons appris à lire les données d'une table à partir d'un fichier à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez extraire et manipuler efficacement les données des documents Microsoft Project dans vos applications Java.
## FAQ
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?
R : Aspose.Tasks prend en charge différentes versions de Microsoft Project, notamment Project 2003, 2007, 2010, 2013 et 2016.
### Q : Puis-je modifier les données du tableau et les enregistrer à nouveau dans le fichier projet ?
R : Oui, vous pouvez utiliser Aspose.Tasks pour modifier les données de la table par programme et enregistrer les modifications dans le fichier projet d'origine.
### Q : Aspose.Tasks nécessite-t-il une licence distincte pour une utilisation commerciale ?
 R : Oui, vous devez acheter une licence pour Aspose.Tasks si vous avez l'intention de l'utiliser dans un environnement commercial. Vous pouvez obtenir une licence auprès du[page d'achat](https://purchase.aspose.com/buy).
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks à partir du[page des versions](https://releases.aspose.com/).
### Q : Où puis-je trouver de l'aide et du support pour Aspose.Tasks ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)pour l’aide et le soutien de la communauté et de l’équipe Aspose.