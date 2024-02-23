---
title: Maîtrisez la gestion des données chronologiques avec Aspose.Tasks pour .NET
linktitle: Gestion des données chronologiques dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explorez Aspose.Tasks pour .NET pour gérer sans effort les données chronologiques, améliorer la planification de projet et optimiser la gestion des ressources. #Aspose #Tâches #MS Project
type: docs
weight: 14
url: /fr/net/text-view-configuration/timephased-data/
---
## Introduction
Dans le monde de la gestion de projet, la gestion efficace des données chronologiques est cruciale pour l'allocation des ressources, l'estimation des coûts et la planification globale du projet. Aspose.Tasks for .NET fournit une solution puissante pour travailler de manière transparente avec des données chronologiques personnalisées. Ce tutoriel vous guidera dans le processus de gestion des données chronologiques à l'aide d'Aspose.Tasks, vous permettant d'optimiser la gestion des ressources dans vos projets.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une compréhension de base des concepts de gestion de projet.
-  Aspose.Tasks installé pour .NET. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
- Un éditeur de code, tel que Visual Studio, pour implémenter les exemples fournis.
## Importer des espaces de noms
Dans votre projet .NET, assurez-vous d'importer les espaces de noms nécessaires pour tirer parti des fonctionnalités d'Aspose.Tasks. Ajoutez les lignes suivantes au début de votre fichier de code :
```csharp
    using Aspose.Tasks;
    using System;
    
```
Maintenant, décomposons l'exemple fourni en plusieurs étapes pour vous guider dans la gestion des données chronologiques à l'aide d'Aspose.Tasks :
## Étape 1 : configurer le projet
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Ici, nous initialisons un nouveau projet et définissons son mode de calcul.
## Étape 2 : Définir les ressources et les tâches
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Créez des ressources de travail et de coûts, ainsi qu'une tâche, pour simuler une structure de projet.
## Étape 3 : attribuer des ressources à une tâche
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Affectez des ressources de travail et de coûts à la tâche.
## Étape 4 : Ajouter des données chronologiques personnalisées
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Étapes similaires pour costAssignment
costAssignment.TimephasedData.Clear();
```
Ajoutez des données chronologiques personnalisées pour les affectations de travail et de coûts.
## Étape 5 : Afficher les données chronologiques
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Afficher des informations pertinentes sur chaque saisie de données chronologique
    }
}
```
Enfin, affichez les données chronologiques pour chaque mission.
#
## Conclusion
La gestion efficace des données chronologiques dans Aspose.Tasks ouvre de nouvelles possibilités pour la planification détaillée des projets et la gestion des ressources. En suivant ce guide étape par étape, vous avez appris à manipuler des données chronologiques pour répondre aux besoins spécifiques de vos projets.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Tasks pour .NET avec d’autres outils de gestion de projet ?
Aspose.Tasks est principalement conçu pour le développement .NET. Cependant, ses fonctionnalités peuvent compléter divers outils de gestion de projet.
### Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?
 Oui, vous pouvez explorer un essai gratuit[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l’assistance pour Aspose.Tasks pour .NET ?
 visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)pour le soutien de la communauté.
### Qu'est-ce qu'un permis temporaire et comment puis-je l'obtenir ?
 En savoir plus sur les licences temporaires[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver la documentation d’Aspose.Tasks pour .NET ?
 Référez-vous au document complet[Documentation](https://reference.aspose.com/tasks/net/) pour des informations détaillées.