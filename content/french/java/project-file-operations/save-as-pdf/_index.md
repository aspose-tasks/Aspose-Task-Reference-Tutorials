---
title: Enregistrer au format PDF dans Aspose.Tasks
linktitle: Enregistrer au format PDF dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment convertir des fichiers de projet en PDF à l'aide d'Aspose.Tasks pour Java. Des étapes simples pour une conversion efficace.
type: docs
weight: 17
url: /fr/java/project-file-operations/save-as-pdf/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'enregistrement d'un projet au format PDF à l'aide d'Aspose.Tasks pour Java. Avec Aspose.Tasks, vous pouvez convertir efficacement vos fichiers de projet au format PDF, garantissant la compatibilité et la facilité de partage. Passons aux étapes :
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Tasks pour la bibliothèque Java : téléchargez et installez la bibliothèque Aspose.Tasks. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/tasks/java/).
3. Un fichier de projet : préparez un fichier de projet (par exemple, HomeMovePlan.mpp) que vous souhaitez convertir en PDF.

## Importer des packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Étape 1 : Lire le fichier de projet d'entrée
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Assurez-vous de remplacer`"Your Data Directory"` avec le chemin d'accès à votre répertoire de données contenant le fichier de projet.
## Étape 2 : Enregistrez le projet au format PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Cet extrait de code enregistre le projet sous forme de fichier PDF sous le nom « Project5.pdf ».
## Étape 3 : Ajuster le contenu à la taille de la cellule
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Ici, nous définissons les options d'enregistrement du PDF, notamment l'ajustement du contenu, l'échelle de temps et le format de présentation.
## Étape 4 : Masquer les légendes
```java
o.setLegendOnEachPage(false);
```
Cette étape masque les légendes sur chaque page du PDF.
## Étape 5 : Enregistrez le projet avec les options appliquées
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Enfin, ce code enregistre le projet avec les options appliquées dans un fichier PDF.

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser Aspose.Tasks for Java pour enregistrer un projet au format PDF. En suivant ces étapes simples, vous pouvez convertir efficacement vos fichiers de projet pour un partage et une distribution faciles.
## FAQ
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Java ?
R : Oui, Aspose.Tasks prend en charge les versions Java à partir du JDK 6 et supérieur.
### Q : Puis-je personnaliser l’apparence de la sortie PDF ?
R : Absolument ! Aspose.Tasks propose diverses options pour personnaliser la sortie PDF en fonction de vos besoins.
### Q : Aspose.Tasks prend-il en charge d'autres formats de fichiers pour la conversion ?
R : Oui, Aspose.Tasks prend en charge un large éventail de formats de fichiers, notamment MPP, XML, XLSX, etc.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks auprès de[ici](https://releases.aspose.com/).
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks ?
 R : Pour obtenir de l'aide et de l'aide, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).