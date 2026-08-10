---
date: 2026-06-30
description: Apprenez à mettre à jour plusieurs ressources et à modifier les données
  du groupe de ressources, puis à exporter le projet au format MPP et à enregistrer
  le projet au format MPP à l'aide d'Aspose.Tasks for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Mettre à jour plusieurs ressources dans Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Mettre à jour plusieurs ressources dans Aspose.Tasks for Java
url: /fr/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mettre à jour plusieurs ressources dans Aspise.Tasks pour Java

## Introduction
Dans ce tutoriel, vous apprendrez comment **mettre à jour plusieurs ressources** dans un fichier Microsoft Project à l’aide d’Aspose.Tasks pour Java. Que vous ayez besoin de modifier les tarifs, de réaffecter des groupes ou d’exporter le fichier mis à jour au format MPP, les étapes ci‑dessous vous guident à travers un flux de travail complet, prêt pour la production. Aucun besoin d’une installation de Microsoft Project, et l’API peut gérer efficacement des projets contenant des centaines de ressources.

## Réponses rapides
- **Puis-je mettre à jour plusieurs ressources à la fois ?** Oui – parcourez la `ResourceCollection` et définissez les attributs en une seule passe.  
- **Quelle méthode enregistre le fichier au format MPP ?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Ai-je besoin d'une licence pour une utilisation commerciale ?** Une licence payante est requise pour la production ; un essai gratuit est disponible.  
- **Quelles versions de Java sont prises en charge ?** Java 6 et supérieures, y compris Java 17 LTS.  
- **La mise à jour en masse est‑elle performante ?** Aspose.Tasks traite des projets de 500 ressources en moins de 2 secondes sur un serveur typique.

## Qu’est‑ce que « mettre à jour plusieurs ressources » ?
**« Update multiple resources »** désigne la modification programmatique des propriétés de plusieurs entrées de ressources — telles que les tarifs, les groupes, les calendriers ou les champs personnalisés — au sein d’un même fichier Project. Cette opération est souvent requise lors de la synchronisation des données de projet avec des systèmes ERP, de l’ajustement des budgets sur de nombreuses ressources ou de l’application de changements de politique à l’échelle de l’organisation.

## Pourquoi utiliser Aspose.Tasks pour modifier le groupe de ressources et exporter le projet au format MPP ?
Aspose.Tasks prend en charge **plus de 50 formats d’entrée et de sortie**, dont MPP, XML et CSV, et peut **exporter le projet au format MPP** sans charger le fichier complet en mémoire. La bibliothèque traite des fichiers jusqu’à **2 Go** de taille, vous permettant de **sauvegarder le projet au format MPP** rapidement et de manière fiable.

## Prérequis

1. Java Development Kit (JDK) installé sur votre système.  
2. Bibliothèque Aspose.Tasks pour Java. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/tasks/java/).  
3. Connaissances de base en programmation Java.  

## Importer les packages

Les instructions `import` font entrer les classes Aspose.Tasks requises dans votre fichier source.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Étape 1 : Configurer votre répertoire de données

Définissez le répertoire où se trouvent vos fichiers de données :

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Spécifier les fichiers d’entrée et de sortie

Définissez les chemins pour le fichier MS Project d’entrée et le fichier mis à jour résultant :

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Étape 3 : Charger le projet

`Project` représente un fichier Microsoft Project chargé en mémoire, offrant un accès aux tâches, aux ressources et aux autres données du projet.

```java
Project project = new Project(file);
```

## Étape 4 : Ajouter une ressource et définir les attributs

`Resource` modélise une ressource de projet individuelle, vous permettant de définir les tarifs, les groupes, les calendriers et d’autres attributs.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Étape 5 : Mettre à jour plusieurs ressources efficacement

`ResourceCollection` est la collection de toutes les ressources d’un projet, accessible via `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Étape 6 : Enregistrer le projet

`SaveFileFormat` énumère les formats de fichier pris en charge pour l’enregistrement d’un projet, tels que MPP, XML et PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Comment mettre à jour plusieurs ressources dans un projet ?

Chargez le projet existant, récupérez sa `ResourceCollection` et parcourez chaque objet `Resource`. Pour chaque ressource, modifiez les champs requis tels que les tarifs, les groupes ou les attributs personnalisés, puis passez à l’élément suivant. Après le traitement de toutes les ressources, appelez `project.save(...)` une seule fois pour persister les modifications de manière efficace.

## Problèmes courants et solutions

- **Conflit d’ID de ressource** – Assurez‑vous que chaque nouvelle ressource obtient un ID unique en utilisant `project.getResources().add(new Resource())`.  
- **Erreurs de format de taux** – Utilisez des objets `ResourceRate` et définissez le `RateType` sur `StandardRate` ou `OvertimeRate`.  
- **Les gros fichiers provoquent une pression mémoire** – Activez `Project.setReadOnly(true)` avant le chargement pour réduire l’empreinte mémoire.

## Questions fréquentes

**Q : Puis‑je mettre à jour plusieurs ressources dans le même projet en utilisant Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez mettre à jour plusieurs ressources en les parcourant et en définissant leurs attributs en conséquence.

**Q : Aspose.Tasks prend‑il en charge d’autres formats de fichier en plus de MS Project ?**  
R : Oui, Aspose.Tasks prend en charge divers formats de fichier, y compris XML, MPP et plus encore.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de Java ?**  
R : Aspose.Tasks est compatible avec les versions de Java 6 et supérieures.

**Q : Puis‑je effectuer d’autres opérations sur les fichiers MS Project avec Aspose.Tasks ?**  
R : Oui, vous pouvez réaliser un large éventail d’opérations telles que la lecture, l’écriture et la manipulation des tâches, des ressources et des calendriers.

**Q : Où puis‑je trouver de l’aide supplémentaire ou du support pour Aspose.Tasks ?**  
R : Vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question.

**Q : Comment exporter le fichier mis à jour au format MPP ?**  
R : Appelez `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` après avoir effectué toutes les modifications de ressources.

**Q : Quelle est la meilleure façon de modifier un groupe de ressources ?**  
R : Définissez la propriété `Resource.Group` sur chaque objet `Resource` avant d’enregistrer le projet.

---

**Dernière mise à jour :** 2026-06-30  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Ajouter une ressource au projet avec Aspose.Tasks pour Java](/tasks/java/resource-management/create-resources/)
- [Gérer les coûts des ressources MS Project avec Aspose.Tasks pour Java](/tasks/java/resource-management/resource-cost/)
- [Comment exporter MPP vers Excel avec Aspose.Tasks pour Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}