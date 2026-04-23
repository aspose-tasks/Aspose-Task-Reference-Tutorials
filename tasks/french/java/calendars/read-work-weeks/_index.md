---
date: 2026-02-05
description: Apprenez à lire les semaines de travail Java à partir d’un calendrier
  Microsoft Project à l’aide d’Aspose.Tasks. Suivez le guide étape par étape avec
  des exemples de code complets.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment lire les Workweeks Java depuis le calendrier MS Project avec Aspose.Tasks
url: /fr/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read Workweeks Java from MS Project Calendar Aspose.Tasks

## Introduction
Dans ce tutoriel, vous **apprendrez comment lire les workweeks Java** à partir d’un calendrier Microsoft Project en utilisant la bibliothèque Aspose.Tasks. Que vous construisiez un outil de reporting, synchronisiez des plannings ou automatisiez l’extraction de données de projet, pouvoir accéder programmétiquement aux définitions des semaines de travail vous fait gagner d’innombrables heures manuelles. Nous passerons en revue la configuration requise, vous montrerons le code exact pour récupérer les détails des work‑weeks, et expliquerons chaque étape afin que vous puissiez adapter la solution à vos propres projets.

## Quick Answers
- **Que signifie “read workweeks java” ?** Cela désigne l’extraction des définitions de semaines de travail d’un fichier Project à l’aide de code Java.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (essai gratuit disponible).  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai fonctionne pour les tests ; une licence commerciale est nécessaire pour la production.  
- **Quels formats de fichiers sont pris en charge ?** Les fichiers *.mpp* et les fichiers Project XML sont gérés.  
- **Combien de temps prend l’implémentation ?** Typiquement moins de 10 minutes une fois la bibliothèque installée.

## How to Read Workweeks Java from a Microsoft Project Calendar
Lire les work weeks en Java signifie utiliser l’API Aspose.Tasks pour accéder à la `WorkWeekCollection` d’un objet calendrier à l’intérieur d’un fichier Microsoft Project. Chaque `WorkWeek` contient les dates de début/fin et les définitions quotidiennes du temps de travail qui déterminent comment les ressources sont planifiées.

## Why read workweeks Java from a Microsoft Project calendar?
- **Automatisation :** Éliminez la copie‑collage manuelle des données de planning.  
- **Intégration :** Alimentez les informations de semaine de travail dans les ERP, RH ou systèmes de reporting personnalisés.  
- **Cohérence :** Assurez‑vous que tous les outils en aval respectent les mêmes règles de calendrier définies dans le fichier Project.

## Prerequisites
Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure installée.  
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis le site officiel : [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **fichier Project d’exemple** (`ReadWorkWeeksInformation.mpp`) placé dans un dossier connu.

## Import Packages
First, import the classes we’ll need to interact with calendars and work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: Set Up Your Data Directory
Define the folder that contains the `.mpp` file. Replace the placeholder with the actual path on your machine:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Create a Project Instance and Access the Calendar
Instantiate a `Project` object, pick the calendar you want (by UID), and obtain its `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** If you’re not sure about the calendar UID, you can iterate through `project.getCalendars()` and print each calendar’s name and UID.

## Step 3: Iterate Through Work Weeks
Loop through each `WorkWeek` to display its name, start/end dates, and the daily working times:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**What you’ll see:** The console prints each work‑week’s label (e.g., “Standard”), its effective date range, and you can drill down to the exact working hours for each day.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Wrong UID or calendar does not exist | Verify the UID with `project.getCalendars().size()` and list available calendars first. |
| No output for work weeks | The selected calendar has no custom work weeks (uses default) | Use the default calendar (`project.getDefaultCalendar()`) or create a work week programmatically. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Apply a `SimpleDateFormat` to format dates as needed. |

## Frequently Asked Questions

**Q : Puis‑je modifier les informations des work weeks avec Aspose.Tasks for Java ?**  
R : Oui. L’API fournit des méthodes telles que `addWorkWeek()`, `removeWorkWeek()` et des setters de propriétés pour changer les noms, les dates et les heures de travail.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. Il prend en charge les fichiers MPP de Project 98 jusqu’aux versions les plus récentes, ainsi que les fichiers Project XML.

**Q : Puis‑je intégrer Aspose.Tasks avec d’autres frameworks Java ?**  
R : Oui. La bibliothèque est pure Java, vous pouvez donc l’utiliser avec Spring, Jakarta EE ou tout autre framework.

**Q : Existe‑t‑il une version d’essai d’Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger un essai gratuit de 30 jours depuis le site officiel : [Aspose.Tasks trial](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.Tasks ?**  
R : Le forum communautaire Aspose est le meilleur endroit : [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Vous avez maintenant maîtrisé **comment lire les workweeks Java** en utilisant Aspose.Tasks. En suivant les étapes ci‑dessus, vous pouvez extraire programmétiquement les définitions de semaines de travail de n’importe quel calendrier MS Project, intégrer ces données dans vos applications et automatiser les flux de travail liés aux plannings. N’hésitez pas à expérimenter la création ou la mise à jour de work weeks — Aspose.Tasks rend cela très simple.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}