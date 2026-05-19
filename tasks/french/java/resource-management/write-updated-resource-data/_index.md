---
date: 2026-01-15
description: Apprenez à ajouter une ressource au projet, à mettre à jour les données
  de la ressource et à enregistrer le projet au format MPP à l'aide d'Aspose.Tasks
  pour Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Ajouter une ressource au projet en utilisant Aspose.Tasks pour Java
url: /fr/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ressource à un projet avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel pratique, vous découvrirez **comment ajouter une ressource à un projet** de façon programmatique avec l'API Aspose.Tasks Java. Nous parcourrons le chargement d'un fichier XML MS Project existant, l'insertion d'une nouvelle ressource, la mise à jour de ses propriétés, et enfin **l'enregistrement du projet au format MPP**. À la fin, vous disposerez d'un modèle clair et réutilisable que vous pourrez intégrer à tout outil de reporting ou d'automatisation basé sur Java.

## Quick Answers
- **Que signifie « ajouter une ressource à un projet » ?** Cela crée une nouvelle entrée de ressource (personnes, équipements, matériaux) dans un fichier Microsoft Project.  
- **Quelle bibliothèque gère cela ?** Aspose.Tasks for Java – aucune installation de Microsoft Project n'est requise.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je convertir XML en MPP ?** Oui – chargez le fichier XML et **enregistrez le projet au format MPP** avec `project.save(...)`.  
- **Quelle version de Java est requise ?** Java 6 ou supérieure (Java 8+ recommandé).

## What is “add resource to project”?
Ajouter une ressource à un projet signifie insérer une nouvelle ligne dans la table Ressources d'un fichier MS Project. Cette ligne stocke des détails tels que le nom, les taux de coût, le groupe et les champs personnalisés que les tâches peuvent ensuite référencer.

## Why use Aspose.Tasks for Java?
- **Aucune dépendance à Microsoft Project** – fonctionne sur n'importe quel OS ou serveur CI.  
- **Fidélité totale** – conserve toutes les fonctionnalités natives de Project lors de la conversion entre formats.  
- **API riche** – vous permet de lire, écrire et manipuler les tâches, ressources, calendriers, etc.

## Prerequisites
Avant de commencer, assurez-vous d'avoir :

1. Java Development Kit (JDK) 8 ou plus récent installé.  
2. Aspose.Tasks for Java library – téléchargez‑la depuis [here](https://releases.aspose.com/tasks/java/).  
3. Familiarité de base avec la syntaxe Java et la configuration de projet Maven/Gradle.

## Import Packages
Ajoutez les classes Aspose.Tasks requises à votre fichier source Java :

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Set Up Your Data Directory
Définissez où les fichiers XML source et les fichiers MPP résultants seront stockés :

```java
String dataDir = "Your Data Directory";
```

## Step 2: Specify Input and Output Files
Indiquez le fichier XML que vous souhaitez convertir (**convertir XML en MPP**) et le fichier MPP cible qui contiendra la nouvelle ressource :

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Step 3: Load the Project
Créez un objet `Project` à partir de la source XML :

```java
Project project = new Project(file);
```

## Step 4: Add a Resource and Set Attributes
C’est ici que nous **ajoutons une ressource au projet** et configurons ses taux et son groupe :

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Astuce :* Vous pouvez répéter l’appel `add` dans une boucle pour **mettre à jour plusieurs ressources** en une seule exécution.

## Step 5: Save the Project
Enfin, **enregistrez le projet au format MPP** pour persister les modifications :

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion
Vous venez d’apprendre **comment ajouter une ressource à un projet**, mettre à jour ses propriétés, et **enregistrer le projet au format MPP** avec Aspose.Tasks for Java. Cette approche est idéale pour les pipelines de reporting automatisés, les importations massives de ressources, ou tout scénario où vous devez manipuler des fichiers MS Project sans l’application de bureau.

## Frequently Asked Questions

**Q1 : Puis‑je mettre à jour plusieurs ressources dans le même projet avec Aspose.Tasks for Java ?**  
R : Oui, parcourez `project.getResources()` ou appelez `add` à plusieurs reprises, en définissant les champs de chaque ressource selon les besoins.

**Q2 : Aspose.Tasks prend‑il en charge d’autres formats de fichiers en plus de MS Project ?**  
R : Absolument – XML, MPP, MPX, Primavera, et bien d’autres sont tous supportés.

**Q3 : Aspose.Tasks est‑il compatible avec différentes versions de Java ?**  
R : La bibliothèque fonctionne avec Java 6 et supérieur ; Java 8+ est fortement recommandé pour de meilleures performances.

**Q4 : Puis‑je effectuer d’autres opérations sur les fichiers MS Project avec Aspose.Tasks ?**  
R : Oui, vous pouvez lire/écrire des tâches, calendriers, affectations, champs personnalisés, et même générer des rapports.

**Q5 : Où puis‑je trouver de l’aide ou du support supplémentaire pour Aspose.Tasks ?**  
R : Consultez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour l’assistance communautaire et le support officiel.

---

**Dernière mise à jour :** 2026-01-15  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}