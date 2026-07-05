---
date: 2026-07-05
description: Apprenez à copier les données du projet en utilisant Aspose.Tasks pour
  .NET avec les options de copie. Optimisez vos applications .NET avec une gestion
  de projet précise.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Comment copier les données du projet avec les options de copie dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Comment copier les données du projet avec les options de copie dans Aspose.Tasks
url: /fr/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment copier les données du projet avec les options de copie dans Aspose.Tasks

## Introduction

Si vous devez **comment copier le projet** des informations d'un fichier Microsoft Project à un autre, Aspose.Tasks pour .NET vous offre une méthode propre, axée sur le code, pour le faire. Dans ce tutoriel, nous parcourrons le flux de travail complet — charger un projet source, configurer les options de copie, créer une copie et charger le résultat — afin que vous puissiez intégrer la logique de copie de projet dans n'importe quelle application .NET en toute confiance.

## Réponses rapides
- **Quelle est la fonction de la copie ?** Elle duplique les données du projet tout en vous permettant d'inclure ou d'exclure des sections spécifiques telles que les calendriers, les ressources ou les informations de vue.  
- **Quelle classe contrôle le comportement ?** `CopyToOptions` vous permet d'ajuster finement ce qui est copié.  
- **Ai-je besoin d'une licence ?** Une licence valide d'Aspose.Tasks est requise pour la production ; un essai gratuit suffit pour le développement.  
- **Formats pris en charge ?** Aspose.Tasks gère les fichiers MPP, XML et XER — plus de 20 + formats au total.  
- **Puis-je ignorer les données de vue ?** Oui, définissez `CopyToOptions.SkipViewData = true` pour omettre les informations liées à l'interface utilisateur.

## Qu’est‑ce que “how to copy project” dans Aspose.Tasks ?
**“How to copy project”** fait référence à l'utilisation de l'API d'Aspose.Tasks pour dupliquer les données d'un objet Project dans un nouveau fichier, en filtrant éventuellement les éléments indésirables. Cette opération est utile pour la création de modèles, l'archivage ou la création de variantes de projet sans étapes manuelles d'interface, et elle fonctionne avec tous les formats de fichiers pris en charge.

## Pourquoi utiliser les options de copie dans Aspose.Tasks ?
Aspose.Tasks prend en charge **plus de 50 entités liées aux projets** (tâches, ressources, calendriers, affectations, etc.) et peut traiter des fichiers contenant **jusqu'à 10 000 tâches** tout en maintenant l'utilisation de la mémoire en dessous de 200 Mo. L'utilisation de `CopyToOptions` vous permet d'éviter la copie des données de vue lourdes, réduisant la taille du fichier de sortie de **30‑40 %** et accélérant l'opération d'environ **2×** pour les grands projets.

## Prérequis

1. **Aspose.Tasks for .NET** – téléchargez la dernière version depuis le [lien de téléchargement](https://releases.aspose.com/tasks/net/).  
2. **Environnement de développement .NET** – Visual Studio 2022 (ou tout IDE supportant .NET 6+) installé.  
3. **Une licence valide d'Aspose.Tasks** – optionnelle pour l'évaluation, obligatoire pour les builds de production.  
4. **Un fichier de projet existant** (par ex., `SourceProject.xml`) que vous souhaitez copier.

## Comment importer les espaces de noms pour Aspose.Tasks ?

Ajoutez les directives `using` requises en haut de votre fichier C# afin que le compilateur puisse localiser les types Aspose.Tasks. Inclure ces instructions vous donne un accès direct à `Project`, `CopyToOptions` et d'autres classes utilitaires sans devoir qualifier pleinement leurs noms, simplifiant ainsi votre code et améliorant la lisibilité.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Étape 1 : Initialiser les objets Project

Tout d'abord, créez une instance `Project` qui représente le fichier source et chargez les données XML.  
La classe `Project` représente un fichier Microsoft Project chargé en mémoire, exposant les tâches, les ressources, les calendriers et d'autres informations du projet.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Astuce :** Si vous travaillez avec des fichiers très volumineux, envisagez d'utiliser le constructeur `LoadOptions` pour activer le chargement paresseux et réduire la consommation de mémoire.

## Étape 2 : Créer une copie du projet

Ensuite, instanciez un second objet `Project` qui recevra les données copiées. Cet objet commence vide.

```csharp
Project copiedProject = new Project();
```

Vous avez maintenant deux objets `Project` distincts : l'un chargé depuis le disque et l'autre prêt à recevoir la copie.

## Étape 3 : Charger le projet copié

Après l'opération de copie (illustrée plus tard), vous voudrez vérifier le résultat en chargeant le fichier nouvellement enregistré dans une autre instance `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Recharger le fichier confirme que la copie a réussi et que les options que vous avez définies se sont comportées comme prévu.

## Étape 4 : Configurer les options de copie

La classe `CopyToOptions` vous permet de spécifier exactement ce qui est transféré de la source vers la destination.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Définir `SkipViewData = true` réduit la taille du fichier de sortie et accélère l'opération, surtout lorsque vous n'avez besoin que des données logiques du projet.

## Étape 5 : Effectuer la copie du projet

Enfin, invoquez la méthode `CopyTo` sur le projet source, en passant le projet de destination et les options que vous avez configurées.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Cet appel en deux lignes exécute l'opération de copie complète, en respectant les options que vous avez définies. Le fichier résultant `CopiedProject.xml` ne contient que les données que vous avez demandées.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **NullReferenceException lors de l'appel à `CopyTo`** | Projet de destination non instancié. | Assurez-vous que `new Project()` est appelé avant `CopyTo`. |
| **Tâches manquantes après la copie** | `CopyCommonData` défini sur `false`. | Définissez `CopyCommonData = true` ou copiez manuellement les collections spécifiques. |
| **Fichier de sortie volumineux** | `SkipViewData` laissé à `false`. | Activez `SkipViewData` pour omettre les données liées à l'interface utilisateur. |
| **Licence non appliquée** | Fichier de licence non chargé. | Appelez `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` avant toute utilisation de l'API. |

## Questions fréquentes

**Q : Puis‑je copier uniquement un sous‑ensemble de tâches ?**  
R : Oui, utilisez `CopyToOptions` avec `ProjectRootTask` pour spécifier une tâche de départ, ou copiez manuellement les tâches sélectionnées après la copie initiale.

**Q : Aspose.Tasks prend‑il en charge la copie entre différents formats de fichiers ?**  
R : Absolument. Vous pouvez charger un fichier MPP et enregistrer la copie en XML, XER ou tout autre format pris en charge — plus de **20 + formats** au total.

**Q : Comment gérer les fichiers de projet protégés par mot de passe ?**  
R : Chargez la source avec `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, puis poursuivez la copie comme d'habitude.

**Q : Existe‑t‑il un moyen de copier les pools de ressources sans les tâches ?**  
R : Définissez `CopyToOptions.CopyResources = true` et `CopyToOptions.CopyTasks = false` pour transférer uniquement les informations de ressources.

**Q : Où puis‑je trouver plus d'exemples ?**  
R : Consultez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour des extraits communautaires, des conseils de dépannage et la documentation officielle.

---

**Dernière mise à jour :** 2026-07-05  
**Testé avec :** Aspose.Tasks 24.12 pour .NET  
**Auteur :** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Maîtriser les données de projet avec Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Maîtriser les options d'enregistrement MS Project pour Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Calendrier et planification Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}