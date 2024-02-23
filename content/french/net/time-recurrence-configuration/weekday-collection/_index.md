---
title: Maîtriser les jours de la semaine dans Aspose.Tasks
linktitle: Collection de jours de la semaine dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez la puissance d'Aspose.Tasks pour .NET pour gérer les jours de la semaine sans effort. Personnalisez les jours ouvrables, supprimez les week-ends et créez facilement des calendriers spécialisés.
type: docs
weight: 11
url: /fr/net/time-recurrence-configuration/weekday-collection/
---
## Introduction
Aspose.Tasks for .NET est une bibliothèque puissante qui facilite une manipulation efficace des données de gestion de projet. Dans ce didacticiel, nous explorerons la collection de jours de la semaine dans Aspose.Tasks, vous permettant de personnaliser les jours ouvrables, de supprimer les week-ends et de créer des calendriers spécialisés pour répondre aux exigences de votre projet. Que vous soyez un développeur chevronné ou un nouveau venu, ce guide étape par étape vous guidera tout au long du processus de travail avec les jours de la semaine dans Aspose.Tasks pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Installez la bibliothèque Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis le[Aspose.Tasks pour la page de téléchargement .NET](https://releases.aspose.com/tasks/net/).
- Familiarité avec le langage de programmation C#.
- Environnement de développement intégré (IDE) tel que Visual Studio.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet C# :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Étape 1 : Créer une instance de projet
Initialisez un nouveau projet Aspose.Tasks :
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Étape 2 : accéder au calendrier
Récupérez le calendrier du projet :
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Étape 3 : Personnaliser les jours de la semaine
Effacez les jours de la semaine existants et définissez les jours ouvrables par défaut :
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Ajoutez d'autres jours de la semaine de la même manière...
```
## Étape 4 : Ajouter des temps de travail
Ajoutez des horaires de travail pour des jours de semaine spécifiques :
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Étape 5 : Afficher les informations du calendrier
Afficher les détails du calendrier sur la console :
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Afficher chaque jour de la semaine et les horaires de travail...
```
## Étape 6 : Supprimer les week-ends
Supprimez le samedi et le dimanche des jours de la semaine :
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Étape 7 : Afficher les temps de travail mis à jour
Afficher les horaires de travail mis à jour après la suppression des week-ends :
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Afficher chaque jour de semaine et horaires de travail mis à jour...
```
## Étape 8 : Créer un calendrier de 24 heures
Créez un calendrier de 24 heures et copiez les jours de la semaine :
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Conclusion
Dans ce didacticiel, nous avons exploré les puissantes capacités d'Aspose.Tasks pour .NET dans la gestion des jours de la semaine dans les calendriers de projet. De la personnalisation des jours de travail à la création de calendriers spécialisés de 24 heures, Aspose.Tasks simplifie le processus, offrant flexibilité et contrôle dans la gestion de projet.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec d’autres langages de programmation ?
R : Aspose.Tasks prend principalement en charge les langages .NET, mais propose également des versions pour Java.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir du[Page des versions d'Aspose.Tasks](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour .NET ?
 R : Visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien de la communauté ou envisagez d’acheter un plan de soutien.
### Q : Où puis-je trouver une documentation complète pour Aspose.Tasks pour .NET ?
 R : Reportez-vous au[Aspose.Tasks pour la documentation .NET](https://reference.aspose.com/tasks/net/) pour des informations détaillées.
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Tasks pour .NET ?
 R : Vous pouvez acquérir une licence temporaire auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/).