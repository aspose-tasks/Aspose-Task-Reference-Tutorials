---
date: 2026-07-19
description: Apprenez à ajouter des types de champs personnalisés dans Aspose.Tasks
  pour .NET avec du code étape par étape, les prérequis et les FAQ.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Types de champs personnalisés dans Aspose.Tasks
og_description: Apprenez à ajouter des types de champs personnalisés dans Aspose.Tasks
  pour .NET. Suivez ce guide étape par étape pour créer, définir et utiliser efficacement
  les attributs étendus.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Comment ajouter des types de champs personnalisés dans Aspose.Tasks pour
  .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Comment ajouter des types de champs personnalisés dans Aspose.Tasks pour .NET
url: /fr/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des types de champs personnalisés dans Aspose.Tasks

## Introduction

Dans ce tutoriel, vous découvrirez **comment ajouter un champ personnalisé** aux types d'un fichier Microsoft Project en utilisant Aspose.Tasks pour .NET. Les champs personnalisés vous permettent de stocker des informations supplémentaires—comme des scores de risque, des codes de département ou des notes personnalisées—directement sur les tâches, les ressources ou le projet lui‑même. Nous parcourrons l’ensemble du processus, de la configuration de l’environnement à la définition, l’ajout et la vérification d’un champ texte personnalisé.

## Réponses rapides
- **Qu'est‑ce qu'un champ personnalisé ?** Une colonne définie par l'utilisateur qui peut contenir du texte, des nombres, des dates ou des indicateurs sur les tâches/ressources.  
- **Quelle classe définit un champ personnalisé ?** `ExtendedAttributeDefinition`.  
- **Puis‑je ajouter un champ personnalisé à un projet existant ?** Oui—chargez le projet, créez la définition, puis ajoutez‑la à la collection.  
- **Ai‑je besoin d'une licence pour Aspose.Tasks ?** Une licence est requise pour la production ; un essai gratuit fonctionne pour l'évaluation.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est‑ce que « comment ajouter un champ personnalisé » dans Aspose.Tasks ?

**Comment ajouter un champ personnalisé** désigne le processus de création d'un `ExtendedAttributeDefinition` et de son rattachement à la collection `ExtendedAttributes` d'un projet. Cela vous permet de stocker des métadonnées supplémentaires qui ne font pas partie du schéma standard de Project. Il peut être utilisé pour les tâches, les ressources ou le projet lui‑même, vous permettant de capturer des informations telles que les niveaux de risque, les codes de département ou des notes personnalisées qui ne sont pas disponibles dans les champs par défaut.

## Pourquoi utiliser des champs personnalisés dans la gestion de projet ?

Aspose.Tasks prend en charge **plus de 50 types d'attributs étendus intégrés** et vous permet de définir **un nombre illimité de champs personnalisés** sans affecter significativement la taille du fichier. En utilisant des champs personnalisés, vous pouvez :  
Ces champs apparaissent comme des colonnes supplémentaires dans Microsoft Project et peuvent être référencés dans des formules, des rapports et des filtres. Ils sont stockés dans le fichier de projet et le suivent, garantissant que les outils en aval conservent les données personnalisées.

## Pré-requis

### 1. Visual Studio installé
Assurez‑vous que Visual Studio (2019 ou version ultérieure) est installé sur votre machine. Vous pouvez le télécharger depuis le site Web de Microsoft.

### 2. Aspose.Tasks pour .NET
Ajoutez le package NuGet Aspose.Tasks à votre projet. Téléchargez la dernière version depuis [here](https://releases.aspose.com/tasks/net/).

### 3. Connaissances de base en C#
Vous devez être à l'aise avec la syntaxe C#, les classes et la structure d'un projet .NET.

## Importer les espaces de noms

Le `Project`, `ExtendedAttributeDefinition` et les énumérations associées se trouvent dans l'espace de noms `Aspose.Tasks`. Importez‑le en haut de votre fichier :

L'espace de noms `Aspose.Tasks` fournit tous les types principaux pour la manipulation des fichiers Microsoft Project.

```csharp

```

## Comment ajouter un champ personnalisé à un projet ?

Chargez le projet existant, créez une définition de champ personnalisé et ajoutez‑la à la collection des attributs étendus du projet — le tout en trois étapes concises. Ce modèle fonctionne pour les tâches, les ressources et le projet lui‑même, et garantit que le champ personnalisé est conservé lors de l’enregistrement du fichier.

### Étape 1 : Créer l’objet Project
`Project` est l'objet de niveau supérieur d'Aspose.Tasks qui représente un fichier Project unique en mémoire. L'instancier charge le fichier et vous donne accès aux tâches, aux ressources et aux attributs étendus.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Étape 2 : Définir le champ personnalisé
`ExtendedAttributeDefinition` décrit une nouvelle colonne. Dans cet exemple, nous créons un champ personnalisé de type **Text** pour les tâches et lui attribuons l'alias « MyText ». La valeur d'énumération `ExtendedAttributeTask.Text1` indique à Aspose.Tasks où stocker la valeur.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Étape 3 : Ajouter la définition du champ personnalisé au projet
La collection `ExtendedAttributes` du projet contient toutes les définitions de champs personnalisés. Ajouter la définition la rend disponible pour chaque tâche du projet.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Problèmes courants et solutions
- **Le champ n'apparaît pas dans l'interface MS Project** – Assurez‑vous de définir la propriété `Alias` ; MS Project affiche l'alias comme en‑tête de colonne.  
- **L'enregistrement génère une exception** – Vérifiez que le fichier du projet n'est pas en lecture‑seule et que vous disposez d'une licence valide.  
- **Les valeurs du champ personnalisé sont perdues après rechargement** – Assurez‑vous d'appeler `project.Save("output.mpp")` après avoir attribué des valeurs aux tâches.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks avec d'autres frameworks .NET ?**  
R : Oui, Aspose.Tasks fonctionne avec .NET Framework, .NET Core et .NET 5/6/7.

**Q : Aspose.Tasks est‑il adapté aux applications de niveau entreprise ?**  
R : Absolument. Il prend en charge le traitement de projets contenant **jusqu'à 10 000 tâches** et peut s'exécuter dans des environnements serveur multithreads.

**Q : Aspose.Tasks prend‑il en charge plusieurs formats de fichiers de projet ?**  
R : Oui—Aspose.Tasks lit et écrit les formats MPP, XML, HTML et CSV, couvrant **toutes les principales versions de Microsoft Project**.

**Q : Puis‑je manipuler les données de ressources avec Aspose.Tasks ?**  
R : Oui, vous pouvez ajouter, mettre à jour et supprimer des ressources, ainsi qu'assigner des champs personnalisés à celles‑ci.

**Q : Existe‑t‑il un forum communautaire pour les utilisateurs d'Aspose.Tasks ?**  
R : Oui, vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour interagir avec d'autres utilisateurs et obtenir de l'aide de l'équipe Aspose.

---

**Dernière mise à jour :** 2026-07-19  
**Testé avec :** Aspose.Tasks 24.12 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Maîtriser les définitions d'attributs étendus MS Project dans Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipuler les attributs étendus MS Project avec Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Intégration du Field Helper MS Project dans Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}