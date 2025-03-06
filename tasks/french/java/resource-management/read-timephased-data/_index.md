---
title: Lire les données chronologiques pour les ressources dans Aspose.Tasks
linktitle: Lire les données chronologiques pour les ressources dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment extraire des données chronologiques à partir de ressources MS Project à l'aide d'Aspose.Tasks pour Java. Tutoriel étape par étape.
type: docs
weight: 15
url: /fr/java/resource-management/read-timephased-data/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de lecture des données chronologiques pour les ressources MS Project à l'aide d'Aspose.Tasks pour Java. Cette bibliothèque fournit des fonctionnalités puissantes pour gérer les fichiers Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger depuis le[site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) et suivez les instructions d'installation.
2.  Bibliothèque Aspose.Tasks pour Java : téléchargez la bibliothèque Aspose.Tasks pour Java à partir du[page de téléchargement](https://releases.aspose.com/tasks/java/) et suivez les instructions d'installation fournies dans la documentation.

## Importer des packages
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Étape 1 : Configurer le répertoire de données
Tout d’abord, définissez le répertoire où se trouve votre fichier MS Project.
```java
String dataDir = "Your Data Directory";
```
## Étape 2 : Lire le fichier de modèle MS Project
Spécifiez le nom de votre fichier modèle MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Étape 3 : Lire le fichier d'entrée en tant que projet
Lisez le fichier d'entrée à l'aide d'Aspose.Tasks et chargez-le en tant qu'objet Project.
```java
Project project = new Project(dataDir + fileName);
```
## Étape 4 : Obtenir la ressource par ID
Récupérez la ressource souhaitée du projet par son identifiant unique (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Étape 5 : Imprimer les données chronologiques pour le travail sur les ressources
Imprimez les données chronologiques pour le travail des ressources.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Étape 6 : Imprimer les données chronologiques pour le coût des ressources
Imprimez les données chronologiques pour le coût des ressources.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à lire les données chronologiques des ressources MS Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez extraire efficacement des informations précieuses de vos fichiers de projet par programmation.
## FAQ
### Aspose.Tasks peut-il gérer d'autres types de fichiers de projet en dehors de Microsoft Project ?
Oui, Aspose.Tasks prend en charge différents formats de fichiers, notamment MPP, XML et CSV.
### Aspose.Tasks est-il compatible avec différents environnements de développement Java ?
Oui, Aspose.Tasks est compatible avec tous les principaux IDE et frameworks Java.
### Puis-je manipuler les données du projet à l’aide d’Aspose.Tasks ?
Absolument, Aspose.Tasks fournit des API complètes pour créer, modifier et analyser les données de projet.
### Aspose.Tasks est-il adapté aux projets au niveau de l’entreprise ?
Oui, Aspose.Tasks est largement utilisé dans les environnements d'entreprise en raison de sa fiabilité et de son évolutivité.
### Où puis-je trouver de l'aide si je rencontre des problèmes lors de l'utilisation d'Aspose.Tasks ?
 Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir l’aide de la communauté et de l’équipe de soutien.