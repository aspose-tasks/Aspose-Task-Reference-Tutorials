---
date: 2026-03-19
description: Apprenez à définir la ligne de base du projet et à gérer efficacement
  les lignes de base des affectations avec Aspose.Tasks pour .NET, garantissant un
  suivi précis de l’avancement du projet.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Définir la ligne de base du projet – Gestion de la ligne de base des affectations
  dans Aspose.Tasks
url: /fr/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la ligne de base du projet – Gestion de la ligne de base des affectations dans Aspose.Tasks

## Introduction

Lors de la gestion de projets, **définir une ligne de base du projet** est essentiel pour mesurer l’avancement réel par rapport au plan initial. Aspose.Tasks pour .NET vous permet non seulement de **définir une ligne de base du projet**, mais aussi de contrôler entièrement les lignes de base des affectations, offrant ainsi un suivi précis des performances. Dans ce tutoriel, nous parcourrons l’ensemble du processus — chargement d’un projet, définition d’une ligne de base, lecture des données de ligne de base des affectations et comparaison des lignes de base — pour que vous puissiez surveiller vos projets en toute confiance.

## Réponses rapides
- **Que signifie « définir une ligne de base du projet » ?** Cela enregistre les données de planning et de coût originales pour les comparer ultérieurement aux performances réelles.  
- **Quelle méthode d’API définit une ligne de base ?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Les lignes de base des affectations nécessitent-elles un appel séparé ?** Non, elles sont stockées automatiquement lorsque vous définissez une ligne de base du projet.  
- **Quels formats sont pris en charge ?** MPP, XML, MPX et bien d’autres via Aspose.Tasks.  
- **Une licence est‑elle requise pour la production ?** Oui, une licence commerciale est nécessaire pour une utilisation hors période d’essai.

## Prérequis

Avant de commencer, assurez‑vous de disposer de :

- Connaissances de base en programmation C#.  
- Visual Studio (toute version récente).  
- Bibliothèque Aspose.Tasks pour .NET ajoutée à votre projet. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/net/).  
- Accès à un fichier de projet au format MPP (par ex., `AssignmentBaseline2007.mpp`).

## Importer les espaces de noms

Ajoutez les espaces de noms requis en haut de votre fichier C# afin que le compilateur sache où trouver les classes Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Étape 1 : Charger le projet et définir la ligne de base du projet

Chargez d’abord le fichier MPP existant, puis appelez `SetBaseline` pour **définir la ligne de base du projet** pour l’ensemble du projet.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Étape 2 : Lire les informations de ligne de base des affectations

Une fois la ligne de base définie, chaque affectation de ressource possède ses propres enregistrements de ligne de base. La boucle ci‑dessous extrait et affiche ces détails, incluant les dates de début/fin, le coût, le travail et les éventuelles données temporelles.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Étape 3 : Comparer les lignes de base des affectations

Vous pouvez comparer les lignes de base de différentes affectations à l’aide des opérateurs d’égalité et de comparaison intégrés. Cela est pratique pour détecter les décalages de planning ou les dépassements de coûts entre les tâches.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Les données de ligne de base sont vides** | Le fichier projet a été ouvert en mode lecture‑seule ou la ligne de base n’a jamais été définie. | Appelez `project.SetBaseline(BaselineType.Baseline)` avant de lire les lignes de base des affectations. |
| **`NullReferenceException` sur `TimephasedData`** | Toutes les lignes de base ne contiennent pas d’entrées temporelles. | Vérifiez toujours que `baseline.TimephasedData != null` (comme montré dans le code). |
| **Récupération d’UID incorrecte** | Les valeurs UID diffèrent selon les versions de fichier. | Utilisez `ResourceAssignments.GetByUid` avec le bon UID ou parcourez les affectations pour trouver celle dont vous avez besoin. |

## Questions fréquentes

**Q : Aspose.Tasks peut‑il gérer plusieurs lignes de base pour une même affectation ?**  
R : Oui, Aspose.Tasks prend en charge plusieurs lignes de base pour chaque affectation, permettant un suivi complet de l’avancement du projet dans le temps.

**Q : Aspose.Tasks est‑il compatible avec d’autres formats de fichiers de projet que le MPP ?**  
R : Oui, Aspose.Tasks supporte une large gamme de formats de fichiers de projet, incluant XML, MPX et MPP, assurant ainsi la compatibilité avec divers outils de gestion de projet.

**Q : Puis‑je modifier les informations de ligne de base de façon programmatique avec Aspose.Tasks ?**  
R : Absolument, Aspose.Tasks fournit des API étendues pour modifier dynamiquement les informations de ligne de base selon les exigences du projet, offrant flexibilité et contrôle sur les processus de gestion.

**Q : Aspose.Tasks propose‑t‑il de la documentation et des ressources d’assistance pour les développeurs ?**  
R : Oui, les développeurs peuvent accéder à une documentation complète, des tutoriels et des forums sur le site web d’Aspose.Tasks, facilitant l’intégration et le dépannage.

**Q : Existe‑t‑il une version d’essai d’Aspose.Tasks pour .NET ?**  
R : Oui, les développeurs peuvent obtenir une version d’essai gratuite d’Aspose.Tasks pour .NET [ici](https://releases.aspose.com/), leur permettant d’évaluer les fonctionnalités avant de prendre une décision d’achat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-19  
**Testé avec :** Aspose.Tasks 24.12 for .NET  
**Auteur :** Aspose