---
title: Maîtriser les critères de filtrage MS Project avec Aspose.Tasks
linktitle: Critères de filtrage dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment implémenter des critères de filtrage dans MS Project à l'aide d'Aspose.Tasks pour .NET. Améliorez l’efficacité de la gestion de projet grâce à une analyse de données ciblée.
type: docs
weight: 18
url: /fr/net/tasks-project-management/filter-criteria/
---
## Introduction
Dans le domaine de la gestion de projet, Microsoft Project se présente comme un outil solide, offrant une multitude de fonctionnalités pour aider les planificateurs et les gestionnaires de projets. Parmi ses nombreuses fonctionnalités figure la possibilité de filtrer les données du projet, permettant aux utilisateurs de se concentrer sur des aspects spécifiques des tâches de leur projet. Cependant, maîtriser ces capacités de filtrage peut s’avérer une tâche ardue sans les conseils appropriés. Ce didacticiel vise à démystifier le processus en fournissant un guide étape par étape sur la mise en œuvre de filtres de critères dans MS Project à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1. Compréhension de base de C# : une familiarité avec le langage de programmation C# est nécessaire pour comprendre les concepts abordés dans ce didacticiel.
2.  Installation d'Aspose.Tasks pour .NET : assurez-vous que Aspose.Tasks pour .NET est installé dans votre environnement de développement. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
3. Fichier Microsoft Project : préparez un fichier Microsoft Project (par exemple, Project2003.mpp), que vous utiliserez pour implémenter les critères de filtre.

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.Tasks pour .NET. Suivez ces étapes:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Étape 1 : Charger le fichier de projet
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Explication : Cette ligne de code initialise une nouvelle instance du`Project` classe et charge le fichier Microsoft Project spécifié par son chemin.
## Étape 2 : Récupérer le filtre de tâches
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Explication : Ici, nous récupérons un filtre de tâches du projet. Ajustez l'index (`[1]`) selon vos besoins pour sélectionner le filtre souhaité.
## Étape 3 : Afficher les lignes de critères
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Explication : Cette section parcourt chaque ligne de critères du filtre et affiche son champ, son opération, son test et ses valeurs (le cas échéant).
## Étape 4 : Imprimer les critères de filtre
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Explication : Imprime le fonctionnement des critères de filtre.
## Étape 5 : Afficher les détails des critères
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Explication : Cette partie récupère et affiche des informations détaillées sur chaque ligne de critères, fournissant ainsi un aperçu de la configuration du filtre.

## Conclusion
La maîtrise des critères de filtrage dans MS Project à l'aide d'Aspose.Tasks pour .NET est une compétence précieuse qui peut améliorer considérablement l'efficacité de la gestion de projet. En suivant ce didacticiel, vous avez appris à manipuler les critères de filtre par programmation, vous permettant ainsi d'adapter les vues de projet à vos besoins spécifiques.
## FAQ
### Q : Puis-je appliquer plusieurs filtres simultanément dans MS Project ?
R : Oui, vous pouvez combiner plusieurs filtres pour affiner davantage les données de votre projet.
### Q : Aspose.Tasks prend-il en charge les anciennes versions des fichiers Microsoft Project ?
: Oui, Aspose.Tasks offre une compatibilité descendante, vous permettant de travailler avec différentes versions de fichiers Microsoft Project.
### Q : Aspose.Tasks est-il compatible avec d'autres frameworks .NET ?
R : Aspose.Tasks prend en charge .NET Framework, .NET Core et .NET Standard, garantissant ainsi une flexibilité dans différents environnements de développement.
### Q : Puis-je personnaliser les critères de filtrage en fonction de conditions dynamiques ?
R : Absolument, vous pouvez ajuster par programme les critères de filtre en fonction de paramètres dynamiques, permettant ainsi une analyse adaptative des données de projet.
### Q : Où puis-je demander de l'aide si je rencontre des problèmes avec Aspose.Tasks ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour demander le soutien de la communauté ou contacter directement le support Aspose.Tasks pour une assistance personnalisée.