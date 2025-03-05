---
title: Convertir MS Project en SVG en Java
linktitle: Enregistrer au format SVG dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment enregistrer des fichiers Microsoft Project au format SVG en Java à l'aide de la bibliothèque Aspose.Tasks. Guide étape par étape avec des exemples de code.
type: docs
weight: 18
url: /fr/java/project-file-operations/save-as-svg/
---
## Introduction
Aspose.Tasks for Java est une bibliothèque puissante permettant de travailler avec des fichiers de gestion de projet, permettant aux développeurs de manipuler les données du projet, d'effectuer diverses opérations et de générer des rapports efficacement. Dans ce didacticiel, nous allons explorer comment enregistrer un projet au format SVG à l'aide d'Aspose.Tasks pour Java. SVG (Scalable Vector Graphics) est un format largement utilisé pour afficher des graphiques vectoriels sur le Web, offrant une évolutivité et un rendu de haute qualité.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
### Environnement de développement Java
Assurez-vous que le kit de développement Java (JDK) est installé sur votre système. Vous pouvez télécharger et installer JDK à partir du site Web d'Oracle.
### Aspose.Tasks pour la bibliothèque Java
 Téléchargez et installez la bibliothèque Aspose.Tasks pour Java à partir du site Web. Vous pouvez trouver le lien de téléchargement dans la documentation fournie[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre programme Java pour utiliser les fonctionnalités Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Décomposons maintenant l'exemple fourni en plusieurs étapes :
## Étape 2 : Définir le répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"`avec le chemin d’accès au répertoire où se trouve votre fichier projet.
## Étape 3 : Charger le fichier de projet
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Cette étape charge le fichier projet nommé « HomeMovePlan.mpp » à partir du répertoire de données spécifié.
## Étape 4 : Enregistrer au format SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Cette étape enregistre le projet chargé au format SVG avec le nom « project5.svg » dans le répertoire de données spécifié.

## Conclusion
Dans ce didacticiel, nous avons appris à enregistrer un projet au format SVG à l'aide d'Aspose.Tasks pour Java. En suivant les étapes fournies, vous pouvez convertir efficacement les fichiers de projet au format SVG, permettant une intégration transparente avec des applications Web ou des outils de visualisation.
## FAQ
### Aspose.Tasks for Java est-il compatible avec toutes les versions des fichiers Microsoft Project ?
Oui, Aspose.Tasks for Java prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP, MPT et XML.
### Puis-je personnaliser l’apparence de la sortie SVG ?
Oui, vous pouvez personnaliser l'apparence de la sortie SVG en ajustant des paramètres tels que les polices, les couleurs et les configurations de mise en page.
### Aspose.Tasks for Java nécessite-t-il une licence pour un usage commercial ?
 Oui, une licence valide est requise pour une utilisation commerciale d'Aspose.Tasks pour Java. Vous pouvez obtenir une licence sur le site Web[ici](https://purchase.aspose.com/temporary-license/).
### Puis-je essayer Aspose.Tasks pour Java avant d’acheter ?
 Oui, vous pouvez demander un essai gratuit d'Aspose.Tasks pour Java sur le site Web.[ici](https://purchase.aspose.com/buy) pour évaluer ses caractéristiques et ses capacités.
### Où puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
 Vous pouvez obtenir de l'aide pour Aspose.Tasks pour Java en visitant le forum[ici](https://forum.aspose.com/c/tasks/15), où vous pouvez poser des questions et interagir avec la communauté.