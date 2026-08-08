---
date: 2026-08-08
description: Apprenez à configurer le calendrier ms project, définir les heures de
  travail quotidiennes et ajouter des jours ouvrés le week‑end avec Aspose.Tasks for
  Java. Enregistrez le projet au format XML en quelques lignes de code.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Comment configurer le calendrier ms project et définir les jours de la
  semaine
og_description: Configurez le calendrier ms project, définissez les jours de la semaine
  et ajoutez des jours ouvrés le week‑end avec Aspose.Tasks for Java. Suivez ce tutoriel
  étape par étape et enregistrez au format XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Configurer le calendrier ms project avec Aspose.Tasks – guide Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Comment configurer le calendrier ms project et définir les jours de la semaine
url: /fr/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le calendrier MS Project et les jours de la semaine

Dans ce tutoriel, vous apprendrez **comment définir le calendrier MS Project** de manière programmatique, définir les jours de la semaine et configurer des jours ouvrés personnalisés à l'aide de la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un moteur de planification, intégriez des systèmes ERP, ou ayez simplement besoin de générer un plan de projet sans ouvrir Microsoft Project, les étapes ci‑dessous vous montrent comment créer un calendrier, définir les heures de travail quotidiennes et ajouter des jours ouvrés le week‑end en quelques lignes de code.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java.  
- **Puis‑je ajouter des jours ouvrés le week‑end ?** Oui – il suffit de marquer le samedi et le dimanche comme jours ouvrés.  
- **Comment enregistrer le projet ?** Appelez `prj.save(..., SaveFileFormat.Xml)`.  
- **Une licence est‑elle nécessaire ?** Un essai gratuit suffit pour l'évaluation ; une licence est requise pour une utilisation en production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure.

## Qu'est‑ce que la définition du calendrier MS Project ?
Définir le calendrier dans MS Project détermine quels jours sont considérés comme ouvrés, le nombre d'heures de travail chaque jour, ainsi que les éventuelles exceptions spéciales telles que les jours fériés ou les fermetures d'entreprise. Ces informations pilotent la planification des tâches, l'allocation des ressources et les échéanciers globaux du projet, garantissant que les calculs respectent les véritables habitudes de travail de l'organisation.

## Pourquoi utiliser Aspose.Tasks pour la manipulation de calendriers ?
Aspose.Tasks vous offre un contrôle programmatique sur les calendriers sans lancer l'interface Microsoft Project. Il fonctionne sur tout système d'exploitation supportant Java, prend en charge plus de 50 formats d'entrée et de sortie, et peut traiter des projets de plusieurs centaines de pages sans charger le fichier complet en mémoire, ce qui le rend idéal pour l'automatisation côté serveur.

## Prérequis
- **Java Development Kit (JDK) 8+** – téléchargez depuis le [site Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – obtenez le dernier JAR depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
- Un IDE ou un outil de construction (Maven/Gradle) pour ajouter le JAR Aspose.Tasks à votre classpath.

## Importer les packages
Importez les classes qui donnent accès aux projets, aux calendriers et aux objets de temps de travail.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guide étape par étape

### Étape 1 : créer une instance de projet
Instanciez un objet `Project`, qui représente le fichier MS Project que vous allez manipuler.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Étape 2 : définir un nouveau calendrier
`Calendar` représente un ensemble d'heures de travail, d'exceptions et de jours fériés pour un projet.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Étape 3 : ajouter les jours ouvrés standards (lundi‑jeudi)
`WeekDay` définit le temps de travail pour un jour spécifique de la semaine.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Étape 4 : ajouter des jours ouvrés le week‑end
Si votre projet fonctionne le week‑end, ajoutez le samedi et le dimanche comme jours ouvrés réguliers. Cela illustre **l'ajout de jours ouvrés le week‑end**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Étape 5 : définir une journée courte personnalisée (vendredi)
Configurez le vendredi avec une période du matin (9 h‑12 h) et une période de l'après‑midi (13 h‑16 h) pour illustrer **la définition des heures de travail quotidiennes** et une journée courte personnalisée.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Étape 6 : enregistrer le projet au format XML
`SaveFileFormat` énumère les formats de fichier pris en charge lors de l'enregistrement d'un projet, comme XML ou MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Heures de travail non appliquées** | Assurez‑vous que `setDayWorking(true)` est appelé sur chaque `WeekDay` personnalisé. |
| **Fichier introuvable lors de l'enregistrement** | Vérifiez que `dataDir` pointe vers un dossier existant et que l'application dispose des permissions d'écriture. |
| **Calendrier non reflété dans les tâches** | Assignez le calendrier nouvellement créé aux ressources ou aux tâches en utilisant `task.setCalendar(cal)`. |

## Questions fréquemment posées

**Q : Puis‑je définir des jours non ouvrés personnalisés avec Aspose.Tasks pour Java ?**  
R : Oui. Réglez la propriété `DayWorking` sur `false` pour tout `WeekDay` que vous souhaitez considérer comme jour non ouvré.

**Q : Comment ajouter des jours fériés ou des exceptions à l'échelle de l'entreprise ?**  
R : Créez des objets `CalendarException`, spécifiez les dates d'exception et ajoutez‑les à `cal.getExceptions()`.

**Q : La bibliothèque est‑elle compatible avec les anciennes versions de MS Project ?**  
R : Absolument. Aspose.Tasks prend en charge les formats MPP, MPT et XML sur plusieurs versions de Project.

**Q : Puis‑je modifier un calendrier existant dans un projet importé ?**  
R : Chargez le projet avec `new Project("existing.mpp")`, récupérez le calendrier souhaité, apportez les modifications et enregistrez.

**Q : Aspose.Tasks gère‑t‑il également les tâches récurrentes ?**  
R : Oui, vous pouvez créer et modifier des tâches récurrentes en utilisant la classe `RecurringTask`.

## Conclusion
Vous savez maintenant **comment définir le calendrier MS Project**, définir les jours de la semaine, ajouter des jours ouvrés le week‑end et configurer un horaire court le vendredi — le tout avec Aspose.Tasks pour Java. Enregistrez le résultat au format XML et intégrez la logique du calendrier dans toute solution de gestion de projet basée sur Java.

---

**Dernière mise à jour :** 2026-08-08  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter un calendrier à un projet avec Aspose.Tasks pour Java](/tasks/java/calendars/create/)
- [Déterminer les jours ouvrés et les heures de travail avec Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Ajouter des jours fériés au calendrier et enregistrer au format MPP avec Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}