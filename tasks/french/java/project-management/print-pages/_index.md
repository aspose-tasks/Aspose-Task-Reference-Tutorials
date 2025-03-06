---
title: Imprimer des pages pour séparer l'image dans Aspose.Tasks
linktitle: Imprimer des pages pour séparer l'image dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment imprimer des pages pour séparer les images dans Aspose.Tasks pour Java. Améliorez la visualisation du projet avec ce guide étape par étape.
weight: 22
url: /fr/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imprimer des pages pour séparer l'image dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'impression de pages pour séparer les images à l'aide d'Aspose.Tasks pour Java. Cette fonctionnalité peut être particulièrement utile lorsque vous devez visualiser séparément les présentations de projets ou les tâches critiques.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger depuis[ici](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez et incluez la bibliothèque Aspose.Tasks pour Java dans votre projet. Vous pouvez l'obtenir de[ici](https://releases.aspose.com/tasks/java/).

## Importer des packages
Assurez-vous d'importer les packages nécessaires au début de votre fichier Java :
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Étape 1 : Charger les données du projet
Tout d'abord, chargez les données du projet à partir de votre fichier MPP :
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Étape 2 : définir les options d'enregistrement de l'image
Définissez les options d'enregistrement de l'image, notamment la date de début, la date de fin, les tâches critiques, la légende et le quadrillage :
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Étape 3 : Personnaliser le quadrillage
Personnalisez le quadrillage de l'image, en spécifiant le type, la couleur et le motif :
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Étape 4 : Enregistrer les images
Enregistrez la présentation du projet sous forme d'images, à la fois sous forme de fichier unique et de fichiers séparés :
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Conclusion
Dans ce didacticiel, nous avons montré comment imprimer des pages pour séparer les images à l'aide d'Aspose.Tasks pour Java. En suivant les étapes décrites ci-dessus, vous pouvez visualiser efficacement les dispositions du projet et les tâches critiques en fonction de vos besoins.
## FAQ
### Q : Puis-je personnaliser le format de l'image lors de l'enregistrement des mises en page du projet ?
 R : Oui, Aspose.Tasks for Java prend en charge différents formats d'image tels que PNG, JPEG, BMP, etc. Vous pouvez spécifier le format souhaité dans le champ`ImageSaveOptions` classe.
### Q : Aspose.Tasks pour Java est-il compatible avec différents environnements de développement Java ?
R : Oui, Aspose.Tasks for Java est compatible avec la plupart des environnements de développement Java, notamment Eclipse, IntelliJ IDEA et NetBeans.
### Q : Puis-je intégrer Aspose.Tasks pour Java dans mon projet Maven ou Gradle ?
 : Oui, vous pouvez facilement intégrer Aspose.Tasks for Java dans votre projet Maven ou Gradle en ajoutant la dépendance appropriée dans votre`pom.xml` ou`build.gradle` déposer.
### Q : Aspose.Tasks for Java prend-il en charge l'exportation des données de projet vers d'autres formats que les images ?
R : Oui, Aspose.Tasks for Java prend en charge l'exportation des données de projet vers divers formats tels que PDF, HTML, XLSX, etc., offrant ainsi une flexibilité dans la visualisation des données et la création de rapports.
### Q : Existe-t-il un support communautaire disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez trouver l'assistance de la communauté, poser des questions et interagir avec d'autres utilisateurs sur le site.[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
