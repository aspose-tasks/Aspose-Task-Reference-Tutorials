---
date: 2026-08-03
description: Apprenez à créer un calendrier MS Project, ajouter le calendrier à un
  projet et enregistrer le projet au format XML à l'aide d'Aspose.Tasks for Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Ajouter un calendrier à un projet avec Aspose.Tasks
og_description: Créez un calendrier MS Project de manière programmatique avec Aspose.Tasks
  for Java. Ajoutez des calendriers, personnalisez les plannings et exportez au format
  XML en quelques minutes.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Créer un calendrier MS Project avec Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Créer un calendrier MS Project avec Aspose.Tasks for Java
url: /fr/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un calendrier MS Project avec Aspose.Tasks pour Java

## Introduction
Dans les flux de travail modernes de gestion de projet, la capacité de **créer un calendrier ms project** de manière programmatique peut faire gagner des heures d'édition manuelle. Aspose.Tasks pour Java vous offre une API propre et sûre au niveau du typage pour manipuler les fichiers Microsoft Project sans jamais ouvrir le client de bureau. Dans ce tutoriel, vous apprendrez comment ajouter un calendrier, comment créer un calendrier MS Project, et comment enregistrer le projet au format XML — le tout en quelques lignes de code Java.

## Réponses rapides
- **Que signifie « créer un calendrier ms project » ?**  
  Cela signifie insérer une nouvelle définition de temps de travail (calendrier) dans un fichier Microsoft Project via du code.  
- **Quelle bibliothèque gère cela ?**  
  Aspose.Tasks pour Java fournit la classe `Calendar` et le conteneur `Project` pour gérer les calendriers.  
- **Ai-je besoin d'une licence ?**  
  Une licence d'évaluation temporaire fonctionne pour les tests ; une licence complète est requise pour une utilisation en production.  
- **Puis-je enregistrer le fichier au format XML ?**  
  Oui — utilisez `SaveFileFormat.Xml` pour exporter le projet en fichier XML.  
- **Quels sont les prérequis ?**  
  Java JDK 8+ et le JAR Aspose.Tasks pour Java dans votre classpath.

## Qu'est-ce que créer un calendrier ms project ?
Créer un calendrier MS Project signifie ajouter de manière programmatique une nouvelle définition de calendrier à un fichier Project, en spécifiant les jours ouvrés, les exceptions et les heures de travail quotidiennes, puis en affectant ce calendrier aux tâches, aux ressources ou à l'ensemble du projet afin que les calculs d'échéancier respectent le temps de travail défini.

## Pourquoi utiliser Aspose.Tasks pour Java pour ajouter un calendrier à un projet ?
Vous devriez utiliser Aspose.Tasks pour Java car il fournit une API entièrement sûre au niveau du typage qui fonctionne sans Microsoft Project installé, prend en charge toutes les principales versions de Project (2007‑2021, couvrant plus de 5 versions), et peut exporter vers XML, MPP et **10+** autres formats, permettant la création automatisée de calendriers en masse sur n'importe quel serveur.

## Prérequis
- **Kit de développement Java (JDK) 8 ou plus récent** installé et configuré.  
- **Bibliothèque Aspose.Tasks pour Java** – téléchargez-la depuis le [site officiel](https://releases.aspose.com/tasks/java/) et ajoutez le JAR au classpath de votre projet.  
- Un IDE ou un outil de construction (Maven/Gradle) de votre choix.

## Guide étape par étape

### Étape 1 : importer le package Aspose.Tasks requis
Tout d'abord, importez les classes Aspose.Tasks afin de pouvoir travailler avec les projets et les calendriers.

```java
import com.aspose.tasks.*;
```

### Étape 2 : définir le chemin du répertoire de données
Définissez l'endroit où le fichier de projet généré sera écrit. Remplacez le texte de substitution par un chemin absolu ou relatif sur votre machine.

```java
String dataDir = "Your Data Directory";
```

### Étape 3 : créer une nouvelle instance de Project
`Project` est la classe principale qui représente un fichier Microsoft Project en mémoire.

```java
Project prj = new Project();
```

### Étape 4 : définir les calendriers que vous souhaitez ajouter
`Calendar` définit un planning avec les jours ouvrés, les exceptions et les heures de travail pour un projet.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Astuce :** Après avoir ajouté un calendrier, vous pouvez personnaliser ses jours ouvrés avec `cal1.getWeekDays().add(...)` et définir les heures de travail quotidiennes en utilisant `cal1.getBaseCalendar().setWorkingTime(...)`.

### Étape 5 : enregistrer le projet (enregistrer le projet au format XML)
`SaveFileFormat.Xml` indique à Aspose.Tasks d'écrire le projet au format XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Étape 6 : afficher un message de fin
Informez l'utilisateur que l'opération s'est terminée avec succès.

```java
System.out.println("Process completed Successfully");
```

En suivant ces six étapes concises, vous avez réussi à **ajouter un calendrier à un projet** et à enregistrer le résultat sous forme de fichier XML.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **`NullPointerException` sur `prj.getCalendars()`** | Objet Project non initialisé correctement. | Assurez-vous que `new Project()` est appelé avant d'accéder aux calendriers. |
| **Fichier non trouvé lors de l'enregistrement** | `dataDir` pointe vers un dossier inexistant. | Créez le répertoire d'abord ou utilisez un chemin absolu. |
| **Le nom du calendrier apparaît comme « no info »** | Des noms de substitution ont été utilisés dans l'exemple. | Remplacez-les par des noms significatifs reflétant le planning (par ex., « Calendrier des vacances US »). |
| **Le XML enregistré ne peut pas être ouvert dans MS Project** | Utilisation d'une version obsolète d'Aspose.Tasks. | Mettez à jour vers la dernière version d'Aspose.Tasks pour Java. |

## Questions fréquemment posées

**Q : Aspose.Tasks peut‑il gérer des calendriers complexes avec de multiples exceptions ?**  
R : Oui — après avoir ajouté un calendrier, vous pouvez définir des exceptions, des heures de travail et des jours non ouvrés en utilisant les classes `WeekDay` et `Exception`.

**Q : Est‑il possible d'assigner le nouveau calendrier à des tâches spécifiques ?**  
R : Absolument. Récupérez une tâche via `prj.getRootTask().getChildren().add("Task Name")` et définissez `task.set(Tsk.CALENDAR, cal3);`.

**Q : La bibliothèque prend‑elle en charge l'enregistrement dans d'autres formats comme MPP ?**  
R : Oui. Remplacez `SaveFileFormat.Xml` par `SaveFileFormat.Mpp` ou `SaveFileFormat.P6` selon les besoins ; Aspose.Tasks prend en charge **12** formats de sortie.

**Q : Ai‑je besoin d'une licence pour les builds de développement ?**  
R : Une licence d'évaluation temporaire suffit pour les tests ; une licence complète est requise pour les déploiements en production.

**Q : Où puis‑je obtenir de l'aide en cas de problème ?**  
R : Le forum communautaire Aspose.Tasks est une excellente ressource : [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-08-03  
**Testé avec :** Aspose.Tasks pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment définir les jours de la semaine dans les calendriers MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Comment définir le calendrier du projet Java avec Aspose.Tasks](/tasks/java/calendars/properties/)
- [Créer des exceptions de calendrier personnalisées avec Aspose.Tasks pour Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}