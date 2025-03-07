---
title: Écrire des données de ressources mises à jour dans Aspose.Tasks
linktitle: Écrire des données de ressources mises à jour dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment mettre à jour sans effort les données de ressources dans les fichiers MS Project à l'aide d'Aspose.Tasks pour Java.
weight: 21
url: /fr/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Écrire des données de ressources mises à jour dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous vous guiderons dans la mise à jour des données de ressources Microsoft Project à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante API Java qui vous permet de manipuler les fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project sur votre système.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Kit de développement Java (JDK) installé sur votre système.
2.  Aspose.Tasks pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
3. Connaissance de base de la programmation Java.

## Importer des packages

Tout d’abord, vous devez importer les packages nécessaires pour travailler avec Aspose.Tasks dans votre code Java. Ajoutez les instructions d'importation suivantes à votre fichier Java :

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Étape 1 : Configurez votre répertoire de données

Définissez le répertoire où se trouvent vos fichiers de données :

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Spécifier les fichiers d'entrée et de sortie

Définissez les chemins du fichier MS Project d'entrée et du fichier mis à jour résultant :

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Fichier de test avec un rsc à mettre à jour
String resultFile = dataDir + "OutputMPP.mpp"; // Fichier pour écrire le projet de test
```

## Étape 3 : Charger le projet

 Chargez le fichier MS Project dans un`Project` objet:

```java
Project project = new Project(file);
```

## Étape 4 : Ajouter une ressource et définir les attributs

Ajoutez une nouvelle ressource au projet et définissez ses attributs tels que le taux standard, le taux d'heures supplémentaires et le groupe :

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Étape 5 : Enregistrez le projet

Enregistrez le projet mis à jour avec les données de ressources modifiées :

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion

Dans ce didacticiel, nous avons montré comment mettre à jour les données des ressources MS Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez manipuler efficacement les informations sur les ressources dans vos fichiers MS Project par programme.

## FAQ

### Q1 : Puis-je mettre à jour plusieurs ressources dans le même projet à l’aide d’Aspose.Tasks pour Java ?

A1 : Oui, vous pouvez mettre à jour plusieurs ressources en les parcourant et en définissant leurs attributs en conséquence.

### Q2 : Aspose.Tasks prend-il en charge d'autres formats de fichiers que MS Project ?

A2 : Oui, Aspose.Tasks prend en charge divers formats de fichiers, notamment XML, MPP, etc.

### Q3 : Aspose.Tasks est-il compatible avec différentes versions de Java ?

A3 : Aspose.Tasks est compatible avec les versions Java 6 et supérieures.

### Q4 : Puis-je effectuer d’autres opérations sur les fichiers MS Project avec Aspose.Tasks ?

A4 : Oui, vous pouvez effectuer un large éventail d'opérations telles que lire, écrire et manipuler des tâches, des ressources et des calendriers.

### Q5 : Où puis-je trouver une aide ou un support supplémentaire pour Aspose.Tasks ?

 A5 : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute aide ou question.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
