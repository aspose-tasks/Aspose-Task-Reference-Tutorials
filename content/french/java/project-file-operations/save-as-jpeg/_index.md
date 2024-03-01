---
title: Convertir MS Project en JPEG dans Aspose.Tasks
linktitle: Enregistrer le projet au format JPEG dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment convertir facilement des fichiers Microsoft Project en images JPEG à l'aide d'Aspose.Tasks pour Java. Boostez votre productivité.
type: docs
weight: 20
url: /fr/java/project-file-operations/save-as-jpeg/
---
## Introduction
Dans ce didacticiel, nous allons explorer comment enregistrer un fichier Microsoft Project en tant qu'image JPEG à l'aide d'Aspose.Tasks pour Java. Cela peut être particulièrement utile pour partager des visualisations de projet ou intégrer des données de projet dans des rapports ou des présentations.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version à partir du[Site Web Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks pour Java : téléchargez et configurez Aspose.Tasks pour Java en suivant les instructions fournies dans le[Documentation](https://reference.aspose.com/tasks/java/).

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre fichier Java :
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Étape 1 : Définir le répertoire de données
Définissez le chemin d'accès à votre répertoire de données où se trouve votre fichier MS Project.
```java
String dataDir = "Your Data Directory";
```
## Étape 2 : Charger le fichier MS Project
Chargez le fichier MS Project à l'aide d'Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Étape 3 : configurer la qualité JPEG (facultatif)
 Si vous souhaitez ajuster la qualité JPEG, vous pouvez la définir à l'aide du`ImageSaveOptions` classe. La qualité varie de 0 à 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Réglez la qualité JPEG sur 50
```
## Étape 4 : Enregistrer le projet au format JPEG
Enregistrez le fichier MS Project en tant qu'image JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Conclusion
Dans ce didacticiel, nous avons appris à enregistrer un fichier Microsoft Project en tant qu'image JPEG à l'aide d'Aspose.Tasks pour Java. Cette fonctionnalité permet un partage et une intégration faciles des données du projet dans divers documents et présentations.
## FAQ
### Q : Puis-je ajuster la qualité de l’image JPEG ?
 R : Oui, vous pouvez régler la qualité à l'aide du`setJpegQuality()` méthode, avec une plage de 0 à 100.
### Q : Que se passe-t-il si je ne spécifie pas la qualité JPEG ?
R : Si vous ne spécifiez pas la qualité, la qualité par défaut sera utilisée.
### Q : L'utilisation d'Aspose.Tasks pour Java est-elle gratuite ?
 R : Aspose.Tasks for Java est une bibliothèque commerciale, mais vous pouvez explorer ses fonctionnalités avec un essai gratuit. Visiter le[page d'essai gratuit](https://releases.aspose.com/) pour plus d'informations.
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
R : Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks ?
 R : Oui, vous pouvez acheter une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).