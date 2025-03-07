---
title: Maîtriser les temps de travail dans Aspose.Tasks
linktitle: Collection des temps de travail dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez la puissance d'Aspose.Tasks pour .NET pour gérer efficacement les délais de projet. Personnalisez les calendriers, définissez les horaires de travail et rationalisez vos projets en toute simplicité.
weight: 14
url: /fr/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les temps de travail dans Aspose.Tasks

## Introduction
Cherchez-vous à maîtriser l’art de gérer les temps de travail dans Aspose.Tasks pour .NET ? Cherchez pas plus loin! Dans ce guide étape par étape, nous aborderons les subtilités de la collecte du temps de travail à l'aide d'Aspose.Tasks, vous permettant de gérer efficacement les calendriers personnalisés et de rationaliser les délais de votre projet.
## Conditions préalables
Avant de nous lancer dans cette aventure, assurez-vous d’avoir les conditions préalables suivantes en place :
-  Bibliothèque Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[Page de version d'Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Environnement de travail : configurez un environnement de développement approprié, de préférence en utilisant un IDE compatible .NET.
## Importer des espaces de noms
Dans votre projet, importez les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Tasks :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Maintenant, décomposons le didacticiel en plusieurs étapes, garantissant une expérience d'apprentissage fluide.
## Étape 1 : Créer un calendrier personnalisé
Commencez par créer un nouveau projet et ajoutez-y un calendrier personnalisé :
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Étape 2 : Définir les jours ouvrables
Configurez les jours ouvrables par défaut du lundi au vendredi :
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Étape 3 : Configurer les horaires de travail du samedi
Précisez les horaires de travail pour le samedi :
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Étape 4 : Imprimer les périodes de travail du samedi
Imprimez les horaires de travail configurés pour le samedi :
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Étape 5 : Configurer les horaires de travail du dimanche
Définir les horaires de travail pour le dimanche :
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Étape 6 : Imprimer les périodes de travail du dimanche
Imprimez les horaires de travail configurés pour le dimanche :
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Étape 7 : Ajouter des jours personnalisés au calendrier
Inclure le samedi et le dimanche configurés dans le calendrier :
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Étape 8 : Parcourir les temps de travail
Parcourez les horaires de travail et affichez-les pour chaque jour dans le calendrier :
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Maintenant que vous avez parcouru les étapes avec succès, vous êtes en mesure d’exploiter la puissance d’Aspose.Tasks pour .NET pour gérer efficacement les temps de travail.
## Conclusion
Maîtriser la collecte des temps de travail dans Aspose.Tasks vous permet de personnaliser les calendriers de projet, garantissant une planification précise et une utilisation efficace des ressources. Plongez dans vos projets en toute confiance, armé des connaissances acquises grâce à ce guide complet.
## Questions fréquemment posées
### Aspose.Tasks est-il adapté à la gestion de projets à grande échelle ?
Oui, Aspose.Tasks est conçu pour gérer des projets de différentes tailles, offrant des fonctionnalités robustes pour une gestion de projet efficace.
### Puis-je intégrer Aspose.Tasks à d’autres bibliothèques .NET ?
Certainement! Aspose.Tasks s'intègre de manière transparente à d'autres bibliothèques .NET, améliorant sa polyvalence et sa compatibilité.
### À quelle fréquence Aspose.Tasks est-il mis à jour ?
 Aspose.Tasks est régulièrement mis à jour pour intégrer de nouvelles fonctionnalités, améliorations et améliorations de compatibilité. Vérifier la[page de sortie](https://releases.aspose.com/tasks/net/) pour les dernières mises à jour.
### Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 Oui, vous pouvez explorer Aspose.Tasks avec un essai gratuit en visitant[ce lien](https://releases.aspose.com/).
### Où puis-je demander de l’aide pour Aspose.Tasks ?
 Pour toute question ou assistance, visitez le[Forum d'assistance Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
