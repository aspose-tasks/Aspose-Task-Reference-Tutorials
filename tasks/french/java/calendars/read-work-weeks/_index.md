---
date: 2026-08-13
description: Apprenez à lire les semaines de travail à partir d'un calendrier MS Project
  en utilisant Aspose.Tasks pour Java. Suivez le guide étape par étape avec des exemples
  de code et des conseils de dépannage.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Lire les semaines de travail du calendrier avec Aspose.Tasks
og_description: Comment lire les semaines de travail à partir d'un calendrier MS Project
  en utilisant Aspose.Tasks pour Java. Suivez le tutoriel concis avec les étapes d'installation,
  les extraits de code et les conseils de dépannage.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Comment lire les semaines de travail du calendrier MS avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Comment lire les semaines de travail du calendrier MS avec Aspose.Tasks
url: /fr/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire les semaines de travail à partir du calendrier MS avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous **apprendrez comment lire les semaines de travail** à partir d'un calendrier Microsoft Project en utilisant la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un tableau de bord de reporting, synchronisiez les plannings avec un système ERP, ou automatisiez l'extraction de données pour l'analyse, l'accès programmatique aux définitions de semaines de travail économise d'innombrables heures manuelles. Aspose.Tasks prend en charge **plus de 50 formats d'entrée et de sortie** et peut traiter des fichiers de projet de plusieurs centaines de pages sans charger le fichier complet en mémoire, vous offrant à la fois flexibilité et performance.

## Réponses rapides
- **Que signifie « lire les semaines de travail » ?** Cela fait référence à l'extraction des définitions de semaines de travail (dates et règles d'heures de travail quotidiennes) d'un fichier Project via du code Java.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (essai gratuit disponible).  
- **Ai‑je besoin d'une licence pour le développement ?** Un essai fonctionne pour les tests ; une licence commerciale est requise pour les déploiements en production.  
- **Quels formats de fichiers sont pris en charge ?** Les fichiers *.mpp* et Project XML sont gérés, ainsi que plus de 50 autres formats pour l'import/export.  
- **Combien de temps prend l'implémentation ?** Typiquement moins de 10 minutes une fois la bibliothèque configurée.

## Qu'est‑ce qu'une semaine de travail dans MS Project ?
Une semaine de travail définit les règles du calendrier qui déterminent quand les ressources sont disponibles pendant une période donnée. Elle comprend une date de début, une date de fin et des intervalles de temps de travail quotidiens (par ex., 9 h–17 h). Dans MS Project, chaque calendrier peut contenir plusieurs semaines de travail, vous permettant de modéliser les jours fériés, les horaires de poste ou les plannings saisonniers.

## Comment Aspose.Tasks lit‑il les semaines de travail à partir d'un calendrier ?
Aspose.Tasks expose la `WorkWeekCollection` d'un objet `Calendar`. En créant une instance `Project`, en sélectionnant le calendrier souhaité (par UID ou nom), et en itérant sur sa `WorkWeekCollection`, vous pouvez récupérer le libellé de chaque semaine de travail, la plage de dates effective, ainsi que les créneaux horaires quotidiens détaillés. L'API gère toutes les conversions de date‑heure et respecte automatiquement les paramètres de fuseau horaire du projet.

## Pourquoi lire les semaines de travail en Java à partir d'un calendrier Microsoft Project ?
Lire les semaines de travail de façon programmatique élimine le copier‑coller manuel, garantit que les systèmes en aval (ERP, RH, reporting) utilisent exactement les mêmes règles de planification, et assure la cohérence entre plusieurs projets. L'automatisation réduit également les erreurs humaines et accélère les pipelines d'intégration, surtout lorsque vous devez traiter des dizaines de fichiers de projet chaque nuit.

## Prérequis
1. **Java Development Kit (JDK)** – version 8 ou supérieure installée.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis le site officiel : [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **fichier Project d'exemple** (`ReadWorkWeeksInformation.mpp`) placé dans un dossier connu sur votre machine.

## Importer les packages
Tout d'abord, importez les classes dont nous aurons besoin pour interagir avec les calendriers et les semaines de travail :

`Project` représente un fichier Microsoft Project, `Calendar` fournit ses calendriers, `WorkWeek` définit une semaine de travail, et `WeekDay` représente un jour.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Étape 1 : configurer votre répertoire de données
Définissez le dossier qui contient le fichier `.mpp`. Remplacez le texte de substitution par le chemin réel sur votre machine :

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : créer une instance Project et accéder au calendrier
La classe `Project` représente un fichier Microsoft Project et fournit l'accès à ses structures de données, y compris les calendriers, les tâches et les ressources.  
Instanciez un objet `Project`, choisissez le calendrier souhaité (par UID), et obtenez sa `WorkWeekCollection` :

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Astuce :** Si vous ne connaissez pas l'UID du calendrier, itérez sur `project.getCalendars()` et affichez d'abord le nom et l'UID de chaque calendrier.

## Étape 3 : itérer à travers les semaines de travail
La classe `WorkWeek` encapsule une définition de semaine de travail, contenant les dates de début/fin et les paramètres d'heures de travail quotidiennes.  
Parcourez chaque `WorkWeek` pour afficher son nom, ses dates de début/fin et les heures de travail quotidiennes :

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

**Ce que vous verrez :** La console affiche le libellé de chaque semaine de travail (par ex., « Standard »), sa plage de dates effective, et vous pouvez détailler les heures exactes de travail pour chaque jour.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| `NullPointerException` lors de l'accès à `calendar` | UID incorrect ou le calendrier n'existe pas | Vérifiez l'UID avec `project.getCalendars().size()` et listez d'abord les calendriers disponibles. |
| Pas de sortie pour les semaines de travail | Le calendrier sélectionné n'a pas de semaines de travail personnalisées (utilise le défaut) | Utilisez le calendrier par défaut (`project.getDefaultCalendar()`) ou créez une semaine de travail programmatiquement. |
| Le format de date semble étrange | `System.out.println` utilise le format par défaut de `java.util.Date` | Appliquez un `SimpleDateFormat` pour formater les dates selon les besoins. |

## Questions fréquemment posées
**Q : Puis-je modifier les informations des semaines de travail en utilisant Aspose.Tasks pour Java ?**  
R : Oui. L'API fournit `addWorkWeek()`, `removeWorkWeek()`, et des setters de propriétés pour changer les noms, les dates et les heures de travail.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. Il prend en charge les fichiers MPP de Project 98 jusqu'aux dernières versions, ainsi que les fichiers Project XML.

**Q : Puis‑je intégrer Aspose.Tasks avec d'autres frameworks Java ?**  
R : Oui. La bibliothèque est pure Java, vous pouvez donc l'utiliser avec Spring, Jakarta EE ou tout autre framework.

**Q : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger un essai gratuit de 30 jours depuis le site officiel : [Aspose.Tasks trial](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.Tasks ?**  
R : Le forum communautaire Aspose est le meilleur endroit : [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-08-13  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks pour Java](/tasks/java/calendars/create/)
- [Récupérer les exceptions de calendrier avec Aspose.Tasks – tutoriel asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Comment définir le calendrier et les jours de la semaine dans MS Project avec Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}