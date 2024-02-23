---
title: Maîtriser la collecte de données chronologiques dans Aspose.Tasks
linktitle: Collecte de données chronologiques dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explorez la collecte de données chronologique dans Aspose.Tasks pour .NET. Guide étape par étape, FAQ et bien plus encore. Améliorez vos capacités de gestion de projet dès aujourd'hui !
type: docs
weight: 15
url: /fr/net/text-view-configuration/timephased-data-collection/
---
## Introduction
Cherchez-vous à exploiter la puissance des données chronologiques dans vos applications .NET à l’aide d’Aspose.Tasks ? Cherchez pas plus loin! Ce guide complet vous guidera tout au long du processus de collecte de données chronologiques avec Aspose.Tasks pour .NET, garantissant que vous tirez le meilleur parti de cette puissante bibliothèque.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.Tasks pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir de[Documentation Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. Environnement de développement .NET : assurez-vous d'avoir configuré un environnement de développement .NET fonctionnel.
3. Votre répertoire de documents : remplacez l'espace réservé "Votre répertoire de documents" dans les extraits de code par le chemin d'accès à votre répertoire de documents.
## Importer des espaces de noms
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour exploiter les fonctionnalités d'Aspose.Tasks :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Créer un projet et des ressources
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Ajouter des tâches au projet
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Définir les propriétés de la tâche...
var task2 = project.RootTask.Children.Add("Task 2");
// Définir les propriétés de la tâche 2...
```
## 3. Attribuer des ressources aux tâches
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Définir les propriétés de l'affectation...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Définir les propriétés de l'affectation2...
```
## 4. Travailler avec des données chronologiques
```csharp
// Définir le contour de travail profilé
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Vérifiez si la collecte de données chronologiques est en lecture seule
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Effacer les données chronologiques générées
assignment.TimephasedData.Clear();
// Créer et ajouter des données chronologiques
var td = new TimephasedData
{
    // Définir les propriétés des données chronologiques...
};
assignment.TimephasedData.Add(td);
// Ajouter une liste de données chronologiques
var list = new List<TimephasedData>();
// Ajoutez d'autres éléments de données chronologiques à la liste...
assignment.TimephasedData.AddRange(list);
// Filtrer les données chronologiques par type et plage de dates
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Imprimer les données chronologiques filtrées...
```
## 5. Manipuler les données chronologiques
```csharp
//Ajoutez un mauvais élément de données chronologiques, puis supprimez-le
var td4 = new TimephasedData
{
    // Définir de mauvaises propriétés de données chronologiques...
};
assignment.TimephasedData.Add(td4);
// Supprimer le mauvais élément de données chronologiques
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Itérer sur tous les éléments chronologiques
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Imprimer les détails chronologiques de l'élément...
}
```
## 6. Copier les données chronologiques vers une autre affectation
```csharp
// Copier les données chronologiques vers une autre affectation
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Convertir la collection en une liste simple
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Supprimer les éléments de données chronologiques un par un
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Conclusion
En conclusion, ce didacticiel a fourni une présentation détaillée de la collecte de données chronologiques à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez intégrer de manière transparente cette fonctionnalité dans vos projets, permettant un suivi efficace du temps et une gestion des ressources.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Tasks pour .NET avec d’autres outils de gestion de projet ?
Oui, Aspose.Tasks for .NET est conçu pour fonctionner avec les outils de gestion de projet populaires et prend en charge divers formats de fichiers.
### Y a-t-il une limite au nombre de ressources et de tâches que je peux gérer avec Aspose.Tasks ?
Aspose.Tasks gère des projets de différentes tailles et il n'y a pas de limite stricte sur le nombre de ressources et de tâches.
### Comment puis-je obtenir de l'aide pour tout problème ou requête lié à Aspose.Tasks for .NET ?
 Pour obtenir de l'aide, visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour entrer en contact avec la communauté et obtenir de l'aide.
### Puis-je essayer Aspose.Tasks pour .NET avant de l’acheter ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.Tasks pour .NET en accédant au[essai gratuit](https://releases.aspose.com/).
### Où puis-je acheter une licence pour Aspose.Tasks pour .NET ?
 Vous pouvez acheter une licence pour Aspose.Tasks pour .NET[ici](https://purchase.aspose.com/buy).