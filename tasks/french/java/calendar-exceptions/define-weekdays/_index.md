---
date: 2026-07-29
description: Découvrez comment planifier les jours non ouvrés en créant un project
  calendar avec Aspose.Tasks for Java, en définissant des weekday exceptions et en
  gérant les holiday schedules.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Planifier les jours non ouvrés – Créer un calendrier de projet Aspose
og_description: Planifiez les jours non ouvrés avec Aspose.Tasks for Java. Découvrez
  comment définir les weekdays, ajouter des calendar exceptions, et gérer les holiday
  schedules efficacement.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Planifier les jours non ouvrés – Créer un calendrier de projet Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Planifier les jours non ouvrés – Créer un calendrier de projet Aspose
url: /fr/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Planifier les jours non ouvrés – Créer un calendrier de projet Aspose

### Introduction
Lorsque vous devez **planifier les jours non ouvrés** pour un projet, vous devez pouvoir modéliser les congés, les équipes spéciales ou les fermetures temporaires directement dans le plan du projet. Aspose.Tasks for Java vous donne un contrôle total sur les définitions de calendrier, vous permettant d’ajouter des exceptions qui reflètent les horaires du monde réel. Dans ce tutoriel, nous parcourrons les étapes exactes pour définir les jours de la semaine pour les exceptions de calendrier, afin que les échéances de votre projet restent précises et fiables. À la fin, vous verrez également comment cela s’inscrit dans une stratégie plus large de **planification des jours non ouvrés** pour tout projet d’entreprise.

## Réponses rapides
- **Que signifie « planifier les jours non ouvrés » ?**  
  Cela signifie utiliser Aspose.Tasks pour créer un calendrier qui marque des dates spécifiques comme non ouvrées, influençant automatiquement les dates des tâches.  
- **Ai-je besoin d’une licence pour exécuter l’exemple ?**  
  Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quels IDE sont pris en charge ?**  
  IntelliJ IDEA, Eclipse, NetBeans ou tout IDE prenant en charge Java 8+.  
- **Puis-je ajouter plusieurs exceptions au même calendrier ?**  
  Oui – vous pouvez ajouter autant d’objets `CalendarException` que nécessaire.  
- **Dans quels formats de fichier puis-je enregistrer le projet ?**  
  XML, MPP et plusieurs autres formats pris en charge par Aspose.Tasks.  

## Qu’est‑ce qu’un calendrier de projet dans Aspose.Tasks ?
Le **calendrier de projet** est l’objet de niveau supérieur d’Aspose.Tasks qui définit les jours et heures de travail pour un projet. Il influence directement les dates de début/fin des tâches, l’allocation des ressources et les calculs d’échéancier globaux. En personnalisant un calendrier, vous vous assurez que le planning respecte les contraintes du monde réel telles que les congés d’entreprise ou les politiques de travail le week‑end.

## Pourquoi définir les jours de la semaine pour les exceptions de calendrier ?
Définir des exceptions pour les jours de la semaine garantit que le moteur de projet considère ces jours comme non ouvrés, empêchant les tâches d’être planifiées automatiquement sur ceux‑ci et maintenant la chronologie alignée avec les contraintes du monde réel telles que les congés, les fenêtres de maintenance ou les modèles d’équipes spéciales au sein de l’organisation.

- **Chronologies précises :** Les tâches ne seront pas placées pendant les congés ou les périodes d’interruption.  
- **Planification des ressources :** Les ressources sont allouées uniquement les jours ouvrés valides, évitant la surallocation.  
- **Conformité :** Les plannings suivent automatiquement les politiques organisationnelles ou les calendriers de congés légaux.  

## Planification des jours non ouvrés avec des exceptions de calendrier
Lorsque vous maintenez un **plan de jours non ouvrés**, vous avez généralement une liste maîtresse de congés, de fenêtres de maintenance ou d’autres périodes d’interruption. Ajouter ces dates en tant qu’objets `CalendarException` garantit que chaque calcul—qu’il s’agisse d’une analyse du chemin critique ou d’un nivellement des ressources—respecte automatiquement ces contraintes. Cette approche élimine les ajustements manuels de dates et réduit le risque de dérive du planning.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez depuis la page officielle [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse, NetBeans ou tout éditeur compatible Java.  

## Comment planifier les jours non ouvrés à l’aide d’exceptions de calendrier
Chargez votre projet, créez un calendrier personnalisé et ajoutez des objets `CalendarException` qui marquent les jours de la semaine souhaités comme non ouvrés. Ce processus complet peut être réalisé en quelques étapes simples, et le calendrier résultant influencera automatiquement toute la logique de planification des tâches.

### Guide étape par étape

### Étape 1 : Importer les packages requis
Nous avons besoin des classes principales d’Aspose.Tasks et du `GregorianCalendar` de Java pour la gestion des dates.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Étape 2 : Définir le répertoire de données
Spécifiez l’endroit où le fichier de projet généré sera enregistré.

```java
String dataDir = "Your Data Directory";
```

### Étape 3 : Créer une instance de projet
`Project` est l’objet principal qui contient toutes les données du projet, y compris les tâches, les ressources et les calendriers.

```java
Project project = new Project();
```

### Étape 4 : Définir un calendrier
`Calendar` représente un planning des périodes de travail et non‑travail au sein d’un projet.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Étape 5 : Définir une exception de jours de la semaine
`CalendarException` représente une période marquée comme non ouvrée dans un calendrier.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Étape 6 : Enregistrer le projet
Enregistrez le projet, y compris le calendrier personnalisé et son exception, dans un fichier XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Dates d'exception non appliquées** | Assurez‑vous que `setEnteredByOccurrences(false)` et les valeurs correctes de `FromDate/ToDate` sont définies. |
| **Le fichier enregistré est vide** | Vérifiez que `dataDir` pointe vers un dossier accessible en écriture et que le nom de fichier se termine par `.xml`. |
| **Le calendrier n’est pas reflété dans la planification des tâches** | Attribuez le calendrier aux tâches ou aux ressources en utilisant `task.setCalendar(cal)` ou `resource.setCalendar(cal)`. |

## Questions fréquentes

**Q : Puis‑je définir plusieurs exceptions pour différents jours de la semaine dans le même calendrier ?**  
A : Oui. Ajoutez des objets `CalendarException` supplémentaires à `cal.getExceptions()` pour chaque période ou règle distincte.

**Q : Aspose.Tasks for Java est‑il compatible avec différents IDE Java ?**  
A : Absolument. La bibliothèque fonctionne avec IntelliJ IDEA, Eclipse, NetBeans et tout IDE qui prend en charge les projets Java standard.

**Q : Puis‑je personnaliser les types d’exception autres que les exceptions quotidiennes ?**  
A : Oui. Utilisez `CalendarExceptionType.Weekly`, `Monthly` ou `Yearly` pour répondre à vos besoins de planification.

**Q : Comment gérer les exceptions de façon dynamique en fonction des exigences du projet ?**  
A : Construisez les objets d’exception de manière programmatique—par exemple, lisez les dates de congés depuis une base de données ou un fichier de configuration et créez des instances `CalendarException` dans une boucle.

**Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?**  
A : Oui, vous pouvez télécharger une version d’essai gratuite depuis la [page de téléchargement Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Conclusion
En suivant ces étapes, vous savez maintenant comment **planifier les jours non ouvrés** en créant un calendrier de projet et en définissant des exceptions de jours de la semaine qui reflètent avec précision les congés ou les périodes spéciales non ouvrées. Une configuration correcte du calendrier est essentielle pour des plannings réalistes, l’allocation des ressources et le succès global du projet. Explorez davantage en attachant le calendrier personnalisé aux tâches ou aux ressources et en expérimentant d’autres types d’exception afin de construire un **plan de jours non ouvrés** complet pour tout projet.

---

**Dernière mise à jour :** 2026-07-29  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter un calendrier au projet avec Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Créer une exception de calendrier Aspose pour Java](/tasks/java/calendar-exceptions/add-remove/)
- [Comment définir le calendrier et les jours de la semaine dans MS Project avec Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}