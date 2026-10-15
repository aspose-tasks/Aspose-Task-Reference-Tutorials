---
date: 2026-10-15
description: Apprenez comment ajouter une custom property et gérer les custom project
  properties dans Aspose.Tasks pour .NET, améliorant le contrôle des métadonnées de
  votre projet.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Gestion de la collection de Custom Project Property dans Aspose.Tasks
og_description: Ajoutez une custom property à vos fichiers de projet avec Aspose.Tasks
  pour .NET. Ce guide vous montre comment gérer les custom properties, les lire, et
  ajouter des valeurs booléennes ou de chaîne efficacement.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Ajoutez une custom property en utilisant l'Aspose.Tasks .NET API pour les
  projets
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Comment ajouter une custom property dans Aspose.Tasks pour .NET
url: /fr/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une propriété personnalisée dans Aspose.Tasks pour .NET

## Introduction

Add custom property support lets you store project‑specific metadata that the built‑in fields don’t cover. In this tutorial you’ll learn how to **add custom property**, read it back, and manage the entire custom property collection using Aspose.Tasks for .NET. By the end you’ll be able to tailor project files with Boolean, DateTime, Double, and String values that fit your business rules.

## Réponses rapides
- **Puis‑je ajouter une propriété personnalisée booléenne ?** Yes – use `CustomPropertyType.Boolean`.
- **Combien de types de propriétés personnalisées sont pris en charge ?** Four: Boolean, DateTime, Double, String.
- **La collection de propriétés personnalisées est‑elle en lecture seule ?** It can be read‑only if the project is loaded from a read‑only source.
- **Ai‑je besoin d’une licence pour utiliser cette fonctionnalité ?** A temporary license works for evaluation; a full license is required for production.
- **Quelles versions de .NET sont compatibles ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est‑ce qu'une propriété personnalisée ?

A custom property is a user‑defined metadata field that you attach to a Project object. It lets you store extra information such as “Risk Level”, “Customer ID”, or any Boolean flag that isn’t covered by the standard MS‑Project fields.

## Pourquoi ajouter une propriété personnalisée dans Aspose.Tasks ?

Aspose.Tasks supports **50+ input and output formats** and can handle projects with **up to 10,000 tasks** without loading the entire file into memory. Adding custom properties lets you embed business‑critical data directly in the project file, eliminating the need for external databases and ensuring the data travels with the project.

## Prérequis

- Visual Studio (toute version récente) installé sur votre poste de travail.  
- Aspose.Tasks for .NET – téléchargez‑le depuis le [download link](https://releases.aspose.com/tasks/net/).  
- Familiarité de base avec la syntaxe C# et la structure d’un projet .NET.

## Importer les espaces de noms

The following namespaces give you access to the core project model and the custom property APIs.

```csharp
using Aspose.Tasks;
using System;


```

## Comment ajouter une propriété personnalisée dans Aspose.Tasks ?

To add a custom property, first load the project, then create a `CustomProperty` object, set its name, type, and value, and finally add it to the project's `CustomProperties` collection. This operation embeds the metadata directly into the project file, and the changes are saved when you call `project.Save(...)`.  

`CustomProperty` represents a single user‑defined field attached to a project.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Étape 1 : initialiser le projet

`Project` is the primary class representing a project file in Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Étape 2 : vérifier la disponibilité de la collection de propriétés personnalisées

`CustomProperties` is the collection that holds all custom property objects for a project.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Étape 3 : ajouter des propriétés personnalisées

`Add` method inserts a new custom property into the project's collection.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Étape 4 : accéder aux propriétés personnalisées

`CustomProperties` collection implements IEnumerable, allowing iteration over each `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Étape 5 : récupérer la valeur d'une propriété personnalisée

`Get` method returns the value of a custom property by its name.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Étape 6 : parcourir les noms des propriétés personnalisées

`Names` property provides a list of all custom property names in the collection.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Étape 7 : supprimer ou vider les propriétés personnalisées

`Remove` method deletes a specific property, while `Clear` empties the entire collection.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Problèmes courants et dépannage

- **Collection en lecture seule** – If `project.CustomProperties.IsReadOnly` returns `true`, ensure the source file isn’t opened with exclusive read access or copy it to a writable location before editing.  
- **Incompatibilité de type** – Assigning a value that doesn’t match the declared `CustomPropertyType` throws an `ArgumentException`. Always set the `Value` after defining the correct `Type`.  
- **Enregistrement des modifications** – After adding or removing properties, call `project.Save("output.mpp")` to persist the modifications; otherwise changes remain in memory only.

## Questions fréquemment posées

**Q : Puis‑je ajouter des propriétés personnalisées de n’importe quel type de données à mon projet avec Aspose.Tasks pour .NET ?**  
R : Yes, you can add custom properties supporting Boolean, DateTime, Double, and String types.

**Q : Est‑il possible de parcourir les noms des propriétés personnalisées dans Aspose.Tasks pour .NET ?**  
R : Absolutely, you can iterate over custom property names using the `Names` property.

**Q : Comment puis‑je supprimer une propriété personnalisée spécifique de mon projet ?**  
R : You can remove a custom property by its name using the `Remove` method.

**Q : Aspose.Tasks pour .NET propose‑t‑il un support pour les licences temporaires ?**  
R : Yes, you can obtain a temporary license from the Aspose website for evaluation purposes.

**Q : Où puis‑je trouver de l’assistance ou de l’aide supplémentaire concernant Aspose.Tasks pour .NET ?**  
R : You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any queries or assistance.

---

**Dernière mise à jour :** 2026-10-15  
**Testé avec :** Aspose.Tasks 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment lire les propriétés de projet intégrées avec Aspose.Tasks pour .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Gérer la collection d'attributs MS Project dans Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Types de champs personnalisés Aspose.Tasks – Calendrier et planification](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}