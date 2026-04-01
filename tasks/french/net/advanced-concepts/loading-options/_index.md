---
date: 2026-03-08
description: Apprenez à importer un fichier de projet avec Aspose.Tasks pour .NET,
  y compris comment spécifier l’encodage du fichier et charger efficacement un fichier
  Microsoft Project.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Importer le fichier de projet – Options de chargement dans Aspose.Tasks
url: /fr/net/advanced-concepts/loading-options/
weight: 16
---

 headings same.

We need to translate content, including bullet points, sentences. Keep code block placeholders as is.

Let's produce French translation.

Check for any RTL note: French is LTR, ignore.

Make sure to keep shortcodes at top and bottom unchanged.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Importation de fichier de projet – Options de chargement dans Aspose.Tasks

## Introduction

Aspose.Tasks for .NET facilite l'**importation de données de fichier de projet** depuis Microsoft Project, Primavera et d'autres formats. Que vous ayez besoin de lire un fichier protégé par mot de passe, de définir un encodage personnalisé ou de gérer les erreurs d'analyse, la bibliothèque vous offre un contrôle granulaire grâce aux options de chargement. Dans ce tutoriel, nous parcourrons les scénarios les plus courants afin que vous puissiez **charger en toute confiance des objets de fichier Microsoft Project** dans vos applications .NET.

## Réponses rapides
- **Quelle est la méthode principale pour importer un fichier de projet ?** Utilisez le constructeur `Project` avec une instance de `LoadOptions`.  
- **Puis‑je ouvrir des fichiers protégés par mot de passe ?** Oui — définissez la propriété `Password` sur `LoadOptions`.  
- **Comment spécifier l'encodage du fichier ?** Assignez un objet `Encoding` à `LoadOptions.Encoding`.  
- **La gestion des erreurs est‑elle personnalisable ?** Absolument — fournissez un délégué à `LoadOptions.ErrorHandler`.  
- **Ces options fonctionnent‑elles avec les fichiers Primavera ?** Oui, via `PrimaveraReadOptions` à l'intérieur de `LoadOptions`.

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

1. **Visual Studio** (ou tout autre IDE .NET de votre choix).  
2. **Aspose.Tasks for .NET** – téléchargez‑le depuis le [site web](https://releases.aspose.com/tasks/net/).  
3. Une compréhension de base de la syntaxe **C#** et de la structure d'un projet.

Maintenant que tout est prêt, importons les espaces de noms requis.

## Importation des espaces de noms

Dans votre projet C#, ajoutez les instructions `using` suivantes afin que les classes de l'API soient disponibles :

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Comment importer un fichier de projet avec des options de chargement

Vous trouverez ci‑dessous quatre exemples pratiques couvrant les scénarios de chargement les plus fréquents.

### Étape 1 : Charger un projet protégé par mot de passe

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Étape 2 : Charger un projet Primavera avec des options personnalisées

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Étape 3 : **Spécifier l'encodage du fichier** lors de l'importation d'un fichier XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Étape 4 : Charger un projet Primavera avec une gestion d'erreurs personnalisée

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

En suivant ces étapes, vous pouvez importer précisément les données du **fichier de projet**, adapter le processus de chargement à vos besoins et garder votre application robuste.

## Problèmes courants & conseils

- **Mot de passe incorrect** – la propriété `Password` lèvera une exception ; vérifiez les informations d'identification avant le chargement.  
- **Encodage non pris en charge** – assurez‑vous que la page de code que vous spécifiez existe sur la machine cible (`Encoding.GetEncoding(1251)` fonctionne pour le cyrillique).  
- **Options Primavera manquantes** – si vous devez préserver les UID des tâches, définissez `PreserveUids = true` ; sinon des ID dupliqués peuvent apparaître.  
- **Gestionnaire d'erreurs retournant null** – retourner `null` indique au parseur d'ignorer l'élément problématique ; personnalisez selon vos besoins.

## Foire aux questions

**Q : Aspose.Tasks for .NET est‑il compatible avec toutes les versions de Microsoft Project ?**  
R : Oui, il prend en charge un large éventail de versions de Microsoft Project, vous permettant de **charger des formats de fichier Microsoft Project** depuis les anciens fichiers MPP jusqu'aux formats les plus récents.

**Q : Puis‑je intégrer Aspose.Tasks for .NET avec d'autres bibliothèques tierces ?**  
R : Absolument. La bibliothèque fonctionne de façon transparente avec d'autres packages .NET, vous permettant de la combiner avec des frameworks de reporting, d'interface utilisateur ou d'accès aux données.

**Q : Aspose.Tasks for .NET fournit‑il de la documentation et des ressources d'assistance ?**  
R : Oui, vous pouvez consulter la documentation complète [documentation](https://reference.aspose.com/tasks/net/) et accéder au support via le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q : Existe‑t‑il des options de licence pour Aspose.Tasks for .NET ?**  
R : Oui, vous pouvez explorer différentes options de licence, y compris les essais gratuits et les licences temporaires, sur le [site web Aspose.Tasks](https://purchase.aspose.com/buy).

**Q : À quelle fréquence les mises à jour et nouvelles fonctionnalités sont‑elles publiées pour Aspose.Tasks for .NET ?**  
R : Aspose.Tasks reçoit des mises à jour régulières qui ajoutent des fonctionnalités, améliorent les performances et maintiennent la compatibilité avec les dernières versions de Microsoft Project.

---

**Dernière mise à jour :** 2026-03-08  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}