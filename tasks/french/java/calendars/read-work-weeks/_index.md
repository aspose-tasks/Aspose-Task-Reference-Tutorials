---
date: 2025-12-03
description: Apprenez à lire les semaines de travail Java à partir d’un calendrier
  Microsoft Project en utilisant Aspose.Tasks. Suivez le guide étape par étape avec
  des exemples de code complets.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lire les semaines de travail Java depuis le calendrier MS Project Aspose.Tasks
url: /fr/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les semaines de travail Java à partir du calendrier MS Project Aspose.Tasks

## Introduction
Dans ce tutoriel, vous **liserez les semaines de travail Java** à partir d'un calendrier Microsoft Project en utilisant la bibliothèque Aspose.Tasks. Que vous construisiez un outil de reporting, synchronisiez des plannings ou automatisiez l'extraction de données de projet, pouvoir accéder programmatiquement aux définitions des semaines de travail fait gagner d'innombrables heures manuelles. Nous parcourrons la configuration requise, vous montrerons le code exact pour récupérer les détails des semaines de travail, et expliquerons chaque étape afin que vous puissiez adapter la solution à vos propres projets.

## Réponses rapides
- **Que signifie « read work weeks java » ?** Cela fait référence à l'extraction des définitions de semaines de travail d'un fichier Project à l'aide de code Java.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (essai gratuit disponible).  
- **Ai-je besoin d'une licence pour le développement ?** Un essai fonctionne pour les tests ; une licence commerciale est nécessaire pour la production.  
- **Quels formats de fichiers sont pris en charge ?** Les fichiers *.mpp* et les fichiers XML Project sont tous deux gérés.  
- **Combien de temps prend l'implémentation ?** Typiquement moins de 10 minutes une fois la bibliothèque installée.

## Qu'est-ce que « read work weeks java » ?
Lire les semaines de travail en Java signifie utiliser l'API Aspose.Tasks pour accéder à la `WorkWeekCollection` d'un objet calendrier à l'intérieur d'un fichier Microsoft Project. Chaque `WorkWeek` contient les dates de début/fin et les définitions d'heures de travail quotidiennes qui déterminent comment les ressources sont planifiées.

## Pourquoi lire les semaines de travail java depuis un calendrier Microsoft Project ?
- **Automatisation :** Éliminer le copier‑coller manuel des données de planning.  
- **Intégration :** Alimenter les informations de semaines de travail dans les systèmes ERP, RH ou de reporting personnalisés.  
- **Cohérence :** Garantir que tous les outils en aval respectent les mêmes règles de calendrier définies dans le fichier Project.

## Prérequis
1. **Java Development Kit (JDK)** – version 8 ou supérieure installée.  
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis le site officiel : [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **fichier Project d'exemple** (`ReadWorkWeeksInformation.mpp`) placé dans un dossier connu.

## Importer les packages
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

## Étape 1 : Configurer votre répertoire de données
Define the folder that contains the `.mpp` file. Replace the placeholder with the actual path on your machine:

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Créer une instance de Project et accéder au calendrier
Instantiate a `Project` object, pick the calendar you want (by UID), and obtain its `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Astuce :** Si vous ne connaissez pas le UID du calendrier, vous pouvez parcourir `project.getCalendars()` et afficher le nom et le UID de chaque calendrier.

## Étape 3 : Parcourir les semaines de travail
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

**Ce que vous verrez :** La console affiche l'étiquette de chaque semaine de travail (par ex., « Standard »), sa plage de dates effective, et vous pouvez détailler les heures de travail exactes pour chaque jour.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| `NullPointerException` lors de l'accès à `calendar` | UID incorrect ou le calendrier n'existe pas | Vérifiez le UID avec `project.getCalendars().size()` et listez d'abord les calendriers disponibles. |
| Aucun résultat pour les semaines de travail | Le calendrier sélectionné n'a pas de semaines de travail personnalisées (utilise le défaut) | Utilisez le calendrier par défaut (`project.getDefaultCalendar()`) ou créez une semaine de travail programmatique. |
| Le format de date semble étrange | `System.out.println` utilise le format par défaut de `java.util.Date` | Appliquez un `SimpleDateFormat` pour formater les dates selon vos besoins. |

## Questions fréquentes

**Q : Puis-je modifier les informations des semaines de travail avec Aspose.Tasks pour Java ?**  
R : Oui. L'API fournit des méthodes telles que `addWorkWeek()`, `removeWorkWeek()` et des setters de propriétés pour changer les noms, les dates et les heures de travail.

**Q : Aspose.Tasks est-il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. Il prend en charge les fichiers MPP de Project 98 jusqu'aux dernières versions, ainsi que les fichiers XML Project.

**Q : Puis-je intégrer Aspose.Tasks avec d'autres frameworks Java ?**  
R : Oui. La bibliothèque est pure Java, vous pouvez donc l'utiliser avec Spring, Jakarta EE ou tout autre framework.

**Q : Existe-t-il une version d'essai d'Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite de 30 jours depuis le site officiel : [Aspose.Tasks trial](https://releases.aspose.com/).

**Q : Où puis-je trouver du support pour Aspose.Tasks ?**  
R : Le forum communautaire d'Aspose est le meilleur endroit : [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Vous avez maintenant maîtrisé **read work weeks java** avec Aspose.Tasks. En suivant les étapes ci‑dessus, vous pouvez extraire programmatiquement les définitions de semaines de travail de n'importe quel calendrier MS Project, intégrer ces données dans vos applications et automatiser les flux de travail liés aux plannings. N'hésitez pas à expérimenter la création ou la mise à jour de semaines de travail — Aspose.Tasks rend cela simple.

---

**Last Updated:** 2025-12-03  
**Testé avec:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}