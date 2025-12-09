---
date: 2025-12-02
description: Apprenez comment ajouter un calendrier au projet, comment créer un calendrier
  MS Project et enregistrer le projet au format XML en utilisant Aspose.Tasks pour
  Java.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ajouter un calendrier au projet avec Aspose.Tasks pour Java
url: /fr/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un calendrier à un projet avec Aspose.Tasks pour Java

## Introduction
Dans les flux de travail modernes de gestion de projet, la capacité d'**ajouter un calendrier à un projet** de manière programmatique peut faire gagner des heures d'édition manuelle. Aspose.Tasks pour Java offre aux développeurs une API propre et typée pour manipuler les fichiers Microsoft Project sans jamais ouvrir le client de bureau. Dans ce tutoriel, vous apprendrez **comment ajouter un calendrier**, **comment créer un calendrier MS Project**, et **enregistrer le projet au format XML** — le tout en quelques lignes de code Java.

## Quick Answers
- **Que signifie « ajouter un calendrier à un projet » ?**  
  Cela signifie insérer une nouvelle définition de temps de travail (calendrier) dans un fichier Microsoft Project via le code.  
- **Quelle bibliothèque gère cela ?**  
  Aspose.Tasks pour Java fournit la classe `Calendar` et le conteneur `Project` pour gérer les calendriers.  
- **Ai‑je besoin d’une licence ?**  
  Une licence d’évaluation temporaire suffit pour les tests ; une licence complète est requise pour la production.  
- **Puis‑je enregistrer le fichier au format XML ?**  
  Oui — utilisez `SaveFileFormat.Xml` pour exporter le projet en fichier XML.  
- **Quelles sont les prérequis ?**  
  Java JDK 8+ et le JAR Aspose.Tasks pour Java dans votre classpath.

## What is “add calendar to project”?
Ajouter un calendrier à un projet crée un planning personnalisé qui définit les jours ouvrés, les jours fériés et les heures de travail quotidiennes. Ce calendrier peut ensuite être affecté aux tâches, aux ressources ou à l’ensemble du projet, garantissant que les calculs tels que les dates de début et les durées respectent le temps de travail défini.

## Why use Aspose.Tasks for Java to add calendar to project?
- **Contrôle total** – Aucun UI requis ; automatisez la création massive de calendriers sur de nombreux projets.  
- **Compatibilité multi‑versions** – Fonctionne avec les fichiers Project 2007, 2010, 2013, 2016 et versions ultérieures.  
- **Pas d’installation de Microsoft Project** – Fonctionne sur n’importe quel serveur ou pipeline CI.  
- **Flexibilité d’exportation** – Enregistrez au format XML, MPP ou autres formats supportés.

## Prerequisites
- **Java Development Kit (JDK) 8 ou plus récent** installé et configuré.  
- **Bibliothèque Aspose.Tasks pour Java** – téléchargez-la depuis le [site officiel](https://releases.aspose.com/tasks/java/) et ajoutez le JAR à votre classpath.  
- Un IDE ou un outil de construction (Maven/Gradle) de votre choix.

## Step‑by‑step guide

### Step 1: Import the required Aspose.Tasks package
Tout d'abord, importez les classes Aspose.Tasks afin de pouvoir travailler avec les projets et les calendriers.

```java
import com.aspose.tasks.*;
```

### Step 2: Set the data directory path
Définissez l’endroit où le fichier de projet généré sera écrit. Remplacez le texte de substitution par un chemin absolu ou relatif sur votre machine.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a new Project instance
Instanciez un objet `Project` – il représente un fichier Microsoft Project vide que vous pouvez remplir.

```java
Project prj = new Project();
```

### Step 4: Define the calendars you want to add
Utilisez la méthode `Calendars.add(String name)` pour créer de nouvelles entrées de calendrier. Dans cet exemple, nous ajoutons trois calendriers, mais vous pouvez en ajouter autant que nécessaire et configurer leurs heures de travail ultérieurement.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Astuce :** Après avoir ajouté un calendrier, vous pouvez personnaliser ses jours ouvrés avec `cal1.getWeekDays().add(...)` et définir les heures de travail quotidiennes à l’aide de `cal1.getBaseCalendar().setWorkingTime(...)`.

### Step 5: Save the project (save project as XML)
Enregistrez le projet, y compris les calendriers nouvellement ajoutés, dans un fichier XML. Ce format est facile à inspecter et compatible avec de nombreux outils.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 6: Display a completion message
Informez l’utilisateur que l’opération s’est terminée avec succès.

```java
System.out.println("Process completed Successfully");
```

En suivant ces six étapes concises, vous avez réussi à **ajouter un calendrier à un projet** et à enregistrer le résultat au format XML.

## Common Issues and Solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **`NullPointerException` sur `prj.getCalendars()`** | Objet Project non initialisé correctement. | Assurez‑vous que `new Project()` est appelé avant d’accéder aux calendriers. |
| **Fichier introuvable lors de l’enregistrement** | `dataDir` pointe vers un dossier inexistant. | Créez le répertoire d’abord ou utilisez un chemin absolu. |
| **Le nom du calendrier apparaît comme « no info »** | Des noms de substitution ont été utilisés dans l’exemple. | Remplacez‑les par des noms significatifs reflétant le planning (par ex., « Calendrier des vacances US »). |
| **Le XML enregistré ne peut pas être ouvert dans MS Project** | Utilisation d’une version obsolète d’Aspose.Tasks. | Mettez à jour vers la dernière version d’Aspose.Tasks pour Java. |

## Frequently Asked Questions

**Q : Aspose.Tasks peut‑il gérer des calendriers complexes avec de multiples exceptions ?**  
R : Oui – après avoir ajouté un calendrier, vous pouvez définir des exceptions, des heures de travail et des jours non ouvrés à l’aide des classes `WeekDay` et `Exception`.

**Q : Est‑il possible d’attribuer le nouveau calendrier à des tâches spécifiques ?**  
R : Absolument. Récupérez une tâche via `prj.getRootTask().getChildren().add("Task Name")` et définissez `task.set(Tsk.CALENDAR, cal3);`.

**Q : La bibliothèque prend‑elle en charge l’enregistrement dans d’autres formats comme MPP ?**  
R : Oui. Remplacez `SaveFileFormat.Xml` par `SaveFileFormat.Mpp` ou `SaveFileFormat.P6` selon les besoins.

**Q : Ai‑je besoin d’une licence pour les builds de développement ?**  
R : Une licence d’évaluation temporaire suffit pour les tests ; une licence complète est requise pour les déploiements en production.

**Q : Où puis‑je obtenir de l’aide en cas de problème ?**  
R : Le forum communautaire Aspose.Tasks est une excellente ressource : [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
En utilisant Aspose.Tasks pour Java, vous pouvez programmer **ajouter un calendrier à un projet**, personnaliser les règles de planification, et **enregistrer le projet au format XML** en quelques lignes de code seulement. Cette automatisation réduit les efforts manuels, élimine les erreurs humaines et permet le traitement par lots de grands portefeuilles de projets.

---

**Dernière mise à jour :** 2025-12-02  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}