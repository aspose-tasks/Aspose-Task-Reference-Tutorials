---
title: Travailler avec le calendrier dans Aspose.Tasks
linktitle: Travailler avec le calendrier dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Gérez les calendriers des projets, calculez les durées et gérez facilement les exceptions à l'aide d'Aspose.Tasks pour .NET.
type: docs
weight: 10
url: /fr/net/calendar-scheduling/working-with-calendar/
---
## Introduction

Aspose.Tasks for .NET fournit des fonctionnalités puissantes pour travailler avec des calendriers, permettant aux développeurs de gérer efficacement les calendriers de projet et les allocations de ressources. Dans ce didacticiel, nous explorerons comment utiliser Aspose.Tasks pour interagir avec les calendriers, couvrant les opérations essentielles telles que la récupération des informations du calendrier, la définition des semaines de travail, le calcul des heures de travail, etc.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir configuré les conditions préalables suivantes :

- Compréhension de base du langage de programmation C#.
-  Installation d'Aspose.Tasks pour .NET. S'il n'est pas installé, téléchargez-le depuis[ici](https://releases.aspose.com/tasks/net/).
- Familiarité avec Visual Studio ou tout autre environnement de développement .NET préféré.

## Importer des espaces de noms

Avant de commencer à coder, assurez-vous d'importer les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Maintenant, décomposons chaque exemple en plusieurs étapes dans un format de guide étape par étape :

## Étape 1 : Récupérer les informations du calendrier

Pour récupérer les informations de calendrier d'un projet, procédez comme suit :

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Récupérer les informations des calendriers
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Explication:
- Chargez le fichier de projet.
- Parcourez chaque calendrier du projet.
- Imprimez l'UID et le nom de chaque calendrier.

## Étape 2 : Lire les informations sur les semaines de travail

Pour lire les informations sur les semaines de travail à partir d'un calendrier, procédez comme suit :

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par UID.
- Parcourez chaque semaine de travail dans le calendrier.
- Imprimez le nom, la date de début et la date de fin de chaque semaine de travail.
- Parcourez les jours et les horaires de travail de chaque semaine.

## Étape 3 : Lire les propriétés du calendrier

Pour lire les propriétés des calendriers de projet, procédez comme suit :

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Explication:
- Chargez le fichier de projet.
- Parcourez chaque calendrier du projet.
- Imprimez l'UID, le nom et s'il s'agit d'un calendrier de base.
- Imprimez les heures de travail pour chaque type de jour.

## Étape 4 : Calculer les heures de travail

Pour calculer les heures de travail pour une tâche, procédez comme suit :

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez des détails sur les tâches comme le calendrier, la date de début et la date de fin.
- Calculez les heures de travail en parcourant chaque jour et en vérifiant s'il s'agit d'un jour ouvrable.
- Résumez la durée totale en minutes.

## Étape 5 : Définir les jours de la semaine pour le calendrier

Pour définir les jours de la semaine pour un calendrier, procédez comme suit :

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Explication:
- Créez un nouveau projet et un nouveau calendrier.
- Ajoutez des jours ouvrables par défaut (du lundi au jeudi) et des horaires de travail personnalisés pour le vendredi.
- Définissez le samedi et le dimanche comme jours non ouvrés.

## Étape 6 : Écrire les données de calendrier mises à jour dans MPP

Pour écrire des données de calendrier mises à jour dans un fichier MPP, procédez comme suit :

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/).");
    }
}
```

Explication:
- Chargez le fichier projet et récupérez le calendrier standard.
- Modifiez les données du calendrier telles que les exceptions et les horaires de travail.
- Enregistrez le projet mis à jour avec les données de calendrier modifiées.

## Étape 7 : Calculer la date de fin de la tâche fractionnée

Pour calculer la date de fin d'une tâche fractionnée, procédez comme suit :

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Explication:
- Chargez le fichier projet et récupérez la tâche fractionnée.
- Obtenez le calendrier du projet.
- Calculez la date de fin en fonction d'une durée personnalisée.

## Étape 8 : Récupérer les exceptions du calendrier

Pour récupérer des informations sur les exceptions de calendrier, procédez comme suit :

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Explication:
- Chargez le fichier de projet.
- Parcourez chaque calendrier et ses exceptions.
- Imprimez les dates de début et de fin de chaque exception.

## Étape 9 : Obtenir le calendrier des ressources de base

Pour utiliser le calendrier de base du calendrier d'une ressource, procédez comme suit :

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Explication:
- Chargez le fichier de projet.
- Ajoutez une ressource et son calendrier.
- Imprimez le nom du calendrier de base pour toutes les ressources.

## Étape 10 : Supprimer le calendrier

Pour supprimer un calendrier d'un projet, procédez comme suit :

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par nom.
- Supprimez le calendrier.

## Étape 11 : Obtenir la date de fin par début et travail

Pour calculer une date de fin par date de début et travail, procédez comme suit :

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier standard.
- Définissez une date de début et une durée de travail.
- Calculez la date de fin en fonction de la date de début et du travail.

## Étape 12 : Commencez le jour ouvrable suivant

Pour démarrer le jour ouvrable suivant à l'aide d'un calendrier, procédez comme suit :

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par UID.
- Obtenez l’heure de début du jour ouvrable suivant.

## Étape 13 : Obtenir la fin de la journée de travail précédente

Pour obtenir la fin de la journée de travail précédente à l'aide d'un calendrier, procédez comme suit :

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par UID.
- Obtenez l’heure de fin de la journée ouvrable précédente.

## Étape 14 : obtenir la date de début, la fin et la durée

Pour obtenir une date de début par date de fin et durée, procédez comme suit :

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par UID.
- Calculez la date de début à partir de la date de fin et de la durée.

## Étape 15 : Obtenez les heures de travail

Pour obtenir les heures de travail pour une date spécifique, procédez comme suit :

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par UID.
- Obtenez les heures de travail pour la date spécifiée.

## Étape 16 : Obtenez les temps de travail

Pour obtenir les horaires de travail pour une date spécifique, procédez comme suit :

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Explication:
- Chargez le fichier de projet.
- Obtenez le calendrier par UID.
- Obtenez les horaires de travail pour la date spécifiée.

## Conclusion

Travailler avec des calendriers dans Aspose.Tasks pour .NET est crucial pour gérer efficacement les calendriers de projet. Avec les exemples fournis et les guides étape par étape, vous pouvez facilement manipuler les données du calendrier, calculer la durée des tâches et gérer efficacement les exceptions. En intégrant ces fonctionnalités dans vos applications, vous pouvez rationaliser les processus de gestion de projet et garantir une planification précise.

## FAQ

### Q1 : Ai-je besoin d’une licence pour utiliser Aspose.Tasks pour .NET ?

 A1 : Oui, vous avez besoin d'une licence valide pour utiliser Aspose.Tasks pour .NET dans vos applications. Vous pouvez acheter une licence complète ou obtenir une licence temporaire de 30 jours auprès de[ici](https://purchase.aspose.com/temporary-license/).

### Q2 : Puis-je modifier les exceptions du calendrier par programmation ?

A2 : Oui, vous pouvez ajouter, mettre à jour ou supprimer des exceptions de calendrier par programme à l'aide d'Aspose.Tasks pour les API .NET.

### Q3 : Comment puis-je calculer les dates de fin des tâches avec des durées personnalisées ?

 A3 : Aspose.Tasks pour .NET fournit des méthodes telles que`GetTaskFinishDateFromDuration()` pour calculer les dates de fin des tâches en fonction de durées personnalisées.

### Q4 : Est-il possible de créer des calendriers personnalisés, tels que des calendriers de nuit ?

A4 : Oui, vous pouvez créer des calendriers personnalisés tels que des calendriers de nuit à l'aide d'Aspose.Tasks pour les API .NET.

### Q5 : Puis-je récupérer des informations sur les exceptions de calendrier à partir des fichiers de projet ?

A5 : Oui, vous pouvez facilement récupérer des informations sur les exceptions de calendrier à partir des fichiers de projet à l'aide d'Aspose.Tasks pour .NET.