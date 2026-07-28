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

# Comment lire les semaines de travail Java à partir du calendrier MS Project Aspose.Tasks

## Introduction
Dans ce tutoriel, vous **apprenez comment lire les semaines de travail Java** à partir d'un calendrier Microsoft Project en utilisant la bibliothèque Aspose.Tasks. Que vous construisiez un outil de reporting, synchronisiez des planifications ou automatisiez l'extraction de données de projet, puissiez accéder programméement aux définitions des semaines de travail vous fait gagner d'innombrables heures manuelles. Nous passerons en revue la configuration requise, vous montrerons le code exact pour récupérer les détails des semaines de travail, et expliquerons chaque étape afin que vous puissiez adapter la solution à vos propres projets.

## Réponses rapides
- **Que signifie « read workweeks java » ?**Cela désigne l'extraction des définitions de semaines de travail d'un fichier Project à l'aide de code Java.
- **Quelle bibliothèque est requise?**Aspose.Tasks pour Java (essai gratuit disponible).
- **Ai‑je besoin d’une licence pour le développement?**Un essai fonctionne pour les tests; une licence commerciale est nécessaire pour la production.
- **Quels formats de fichiers sont pris en charge ?**Les fichiers *.mpp* et les fichiers Project XML sont gérés.
- **Combien de temps prend l’implémentation?**Typiquement moins de 10minutes une fois la bibliothèque installée.

## Comment lire les semaines de travail Java à partir d'un calendrier Microsoft Project
Lire les semaines de travail en Java signifie utiliser l’API Aspose.Tasks pour accéder à la `WorkWeekCollection` d’un objet calendrier à l’intérieur d’un fichier Microsoft Project. Chaque `WorkWeek` contient les dates de début/fin et les définitions quotidiennes du temps de travail qui déterminent comment les ressources sont planifiées.

## Pourquoi lire les semaines de travail Java à partir d'un calendrier Microsoft Project ?
- **Automatisation :** Éliminez la copie‑collage manuel des données de planification.
- **Intégration:** Alimentez les informations de semaine de travail dans les ERP, RH ou systèmes de reporting personnalisés.
- **Cohérence :** Assurez-vous que tous les outils en aval respectent les mêmes règles de calendrier définies dans le fichier Project.

## Prérequis
Avant de sous-marin dans le code, assurez-vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure installée.
2. **Aspose.Tasks for Java** – téléchargez le JAR le plus récent depuis le site officiel : [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).
3. Un **fichier Project d’exemple** (`ReadWorkWeeksInformation.mpp`) placé dans un dossier connu.

## Importer des packages
Tout d’abord, importez les cours dont nous aurons besoin pour interagir avec les calendriers et les semaines de travail :

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Étape 1 : Configurer votre répertoire de données
Définissez le dossier contenant le fichier `.mpp`. Remplacez l’espace réservé par le chemin d’accès réel sur votre ordinateur :

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Créer une instance de projet et accéder au calendrier
Instanciez un objet `Project`, sélectionnez le calendrier souhaité (par son UID) et obtenez sa `WorkWeekCollection` :

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Astuce :** Si vous ne connaissez pas l’UID d’un calendrier, vous pouvez parcourir `project.getCalendars()` et afficher le nom et l’UID de chaque calendrier.

## Étape 3 : Parcourir les semaines de travail
Parcourez chaque `WorkWeek` pour afficher son nom, ses dates de début et de fin, ainsi que les heures de travail quotidiennes :

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

**Ce que vous verrez :** La console affiche l’étiquette de chaque semaine de travail (par exemple, « Standard »), sa période de validité et vous permet d’afficher les heures de travail exactes de chaque jour.

## Problèmes courants et solutions
| Problème | Cause | Solution |

|-------|--------|-----|
| `NullPointerException` lors de l’accès à `calendar` | UID incorrect ou calendrier inexistant | Vérifiez l’UID avec `project.getCalendars().size()` et listez d’abord les calendriers disponibles. |
| Aucun affichage pour les semaines de travail | Le calendrier sélectionné ne contient aucune semaine de travail personnalisée (utilisation des semaines par défaut) | Utilisez le calendrier par défaut (`project.getDefaultCalendar()`) ou créez une semaine de travail par programmation. |
| Format de date incorrect | `System.out.println` utilise le format par défaut `java.util.Date` | Appliquez un `SimpleDateFormat` pour formater les dates comme vous le souhaitez. |

## Questions fréquemment posées

**Q : Puis‑je modifier les informations des semaines de travail avec Aspose.Tasks for Java ?**
R : Oui. L'API fournit des méthodes telles que `addWorkWeek()`, `removeWorkWeek()` et des setters de propriétés pour changer les noms, les dates et les heures de travail.

**Q : Aspose.Tasks est-il compatible avec différentes versions de fichiers Microsoft Project ?**
R : Absolument. Il prend en charge les fichiers MPP de Project98 jusqu'aux versions les plus récentes, ainsi que les fichiers Project XML.

**Q : Puis‑je intégrer Aspose.Tasks avec d’autres frameworks Java ?**
R : Oui. La bibliothèque est pure Java, vous pouvez donc l’utiliser avec Spring, Jakarta EE ou tout autre framework.

**Q : Existe‑t‑il une version d’essai d’Aspose.Tasks?**
R : Oui, vous pouvez télécharger un essai gratuit de 30 jours depuis le site officiel : [Aspose.Tasks trial](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.Tasks ?**
R : Le forum communautaire Aspose est le meilleur endroit : [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Vous avez maintenant maîtrisé **comment lire les workweeks Java** en utilisant Aspose.Tasks. En suivant les étapes ci-dessus, vous pouvez extraire programméement les définitions de semaines de travail de n'importe quel calendrier MS Project, intégrer ces données dans vos applications et automatiser les flux de travail liés aux plannings. N’hésitez pas à expérimenter la création ou la mise à jour de workweeks—Aspose.Les tâches rendent cela très simple.

---

**Dernière mise à jour :** 2026-02-05
**Testé avec :** Aspose.Tasks pour Java 24.12 (dernière version au moment de la rédaction)
**Auteur :** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}