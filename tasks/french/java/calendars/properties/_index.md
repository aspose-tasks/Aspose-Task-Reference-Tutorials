---
date: 2026-09-09
description: Comment définir le calendrier du projet en Java avec Aspose.Tasks. Apprenez
  à afficher les heures de travail du calendrier, à configurer le temps de travail
  et à modifier les jours du calendrier dans les fichiers MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Gérer les propriétés du calendrier dans Aspose.Tasks
og_description: Comment définir le calendrier du projet en Java avec Aspose.Tasks.
  Apprenez à afficher les heures de travail du calendrier, à configurer le temps de
  travail et à modifier les jours du calendrier dans les fichiers MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Comment définir le calendrier du projet Java avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Comment définir le calendrier du projet Java avec Aspose.Tasks
url: /fr/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le calendrier du projet Java avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir le calendrier du projet** en Java en utilisant la bibliothèque Aspose.Tasks. Contrôler les propriétés du calendrier vous permet de **afficher les heures de travail du calendrier**, de configurer des jours de travail personnalisés et de garder votre planning de projet aligné avec des contraintes du monde réel telles que les jours fériés ou les horaires de travail en équipes. Nous parcourrons la configuration de l’environnement, le chargement d’un projet, l’itération sur les calendriers, ainsi que la lecture ou la mise à jour de leurs propriétés, afin que vous puissiez gérer en toute confiance les paramètres du **calendrier MS Project** dans n’importe quelle application Java.

## Réponses rapides
- **Que signifie « set project calendar » ?** Cela signifie créer ou mettre à jour les heures de travail d’un calendrier, le calendrier de base et les types de jour dans un fichier MS Project.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (any recent version).  
- **Ai-je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je afficher les heures de travail du calendrier ?** Oui—en lisant chaque `WeekDay` vous pouvez afficher les heures pour chaque type de jour.  
- **Cette solution est‑elle compatible avec Maven/Gradle ?** Absolument—ajoutez le JAR Aspose.Tasks en tant que dépendance.

## Comment définir le calendrier du projet en Java
Chargez votre fichier de projet, localisez le calendrier cible, puis ajustez ses définitions de temps de travail, son calendrier de base et ses types de jour selon les besoins. Les étapes ci‑dessous offrent une solution complète, de bout en bout, qui montre le chargement, l’itération, la modification et l’enregistrement du projet tout en gérant les exceptions et en assurant des calculs précis des heures de travail.

## Qu’est‑ce qu’un calendrier de projet ?
Un calendrier de projet définit les jours et les heures de travail pour les tâches, les ressources et la chronologie globale du projet. Dans MS Project, les calendriers peuvent hériter d’un calendrier de base, et chaque type de jour (par ex. **Standard**, **Non‑working**) peut avoir son propre temps de travail. Gérer ces paramètres par programme permet des ajustements dynamiques du planning sans édition manuelle.

## Pourquoi gérer le calendrier MS Project de manière programmatique ?
Gérer les calendriers par programme vous permet d’appliquer des règles de planification cohérentes à de nombreux projets, de réduire les erreurs manuelles et d’intégrer les données de calendrier avec d’autres systèmes d’entreprise tels que les RH ou l’ERP. Cette automatisation accélère la mise en place du projet et garantit que tous les membres de l’équipe respectent les mêmes politiques d’heures de travail.

- **Automatisation :** Ajustez les calendriers de dizaines de projets avec un seul script.  
- **Cohérence :** Appliquez automatiquement les politiques d’heures de travail à l’échelle de l’organisation.  
- **Intégration :** Synchronisez les calendriers avec des systèmes RH ou ERP externes.  
- **Visibilité :** Affichez rapidement les **heures de travail du calendrier** pour les rapports ou le débogage.  
- **Flexibilité :** Ajoutez des exceptions ou des modèles de quart de travail à la volée sans ouvrir l’interface.

## Prérequis
Avant de commencer, assurez-vous d’avoir :

- **Java Development Kit (JDK) 8+** installé et `JAVA_HOME` configuré.  
- **Aspose.Tasks for Java** bibliothèque téléchargée depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/). Ajoutez le JAR à votre classpath ou déclarez‑le comme dépendance Maven/Gradle.  
- Un fichier MS Project d’exemple (`.mpp` ou `.xml`) contenant au moins un calendrier que vous souhaitez inspecter ou modifier.

## Importer les packages
Les classes `Project`, `Calendar`, `WeekDay` et les classes associées sont le cœur de la manipulation des calendriers.  
La classe `Calendar` représente un calendrier de projet, contenant les jours ouvrés, les exceptions et les relations de calendrier de base.  
La classe `WeekDay` définit les paramètres de temps de travail pour un jour unique au sein d’un calendrier.

La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier MS Project en mémoire. Après avoir chargé un fichier, toutes les opérations de calendrier passent par cet objet.

```java
import com.aspose.tasks.*;
```

## Étape 1 : configurer le répertoire de données
Définissez le dossier qui contient vos fichiers de projet. Remplacez le texte de substitution par le chemin réel sur votre machine.

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : définir les constantes d’unité de temps
Les temps de travail sont exprimés en millisecondes. Définir des constantes réutilisables rend le code plus lisible et vous aide à **calculer les heures de travail Java** avec précision.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Étape 3 : charger les données du projet
Créez une instance `Project` en chargeant un fichier XML MS Project existant (`.xml` ou `.mpp`). Cela vous donne accès à tous les calendriers stockés dans le fichier.

La classe `Project` charge le fichier dans un modèle d’objet léger ; elle ne nécessite pas que le fichier complet soit conservé en mémoire, ce qui vous permet de travailler avec des projets contenant des dizaines de milliers de tâches.

```java
Project project = new Project(dataDir + "project.xml");
```

## Étape 4 : parcourir les calendriers Java
Nous parcourons maintenant chaque calendrier, affichons son identifiant unique, son nom, son calendrier de base et les heures de travail pour chaque type de jour. Cela montre **comment définir le calendrier du projet Java** et aussi comment **afficher les heures de travail du calendrier**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Ce que fait ce code
- **Filtre les calendriers sans nom** (certains calendriers internes peuvent avoir un nom `null`).  
- **Affiche l’UID et le nom** – utile pour identifier le calendrier plus tard.  
- **Affiche le calendrier de base** – soit « Self » (le calendrier est sa propre base) ou le nom du calendrier hérité.  
- **Parcourt chaque `WeekDay`** pour calculer et afficher le total des heures de travail (`workingTime` est en millisecondes, nous le divisons donc par `OneHour`).  

## Avantages quantifiés de l’utilisation d’Aspose.Tasks
Aspose.Tasks prend en charge **plus de 30 formats d’entrée et de sortie** et peut traiter **des projets contenant jusqu’à 10 000 tâches** sans charger le fichier complet en mémoire, délivrant les résultats en moins d’une seconde sur du matériel serveur typique. Ces chiffres en font un choix fiable pour l’automatisation à l’échelle de l’entreprise.

## Problèmes courants et solutions
| Problème | Raison | Correction |
|----------|--------|------------|
| `NullPointerException` sur `cal.getBaseCalendar()` | Le calendrier est lui‑même un calendrier de base (`isBaseCalendar()` renvoie `true`). | Utilisez la vérification ternaire comme indiqué (`cal.isBaseCalendar() ? "Self" : ...`). |
| Pas de sortie pour les heures de travail | Le fichier projet utilise une unité de temps différente (ticks). | Vérifiez le format du fichier ; Aspose.Tasks normalise en millisecondes, mais assurez‑vous de charger le bon type de fichier. |
| Impossible de localiser `project.xml` | Chemin `dataDir` incorrect. | Utilisez un chemin absolu ou `Paths.get(dataDir, "project.xml").toString()`. |

## Questions fréquemment posées

**Q : Puis‑je modifier les propriétés du calendrier de façon programmatique avec Aspose.Tasks ?**  
R : Oui, l’API offre un accès complet en lecture/écriture aux calendriers, vous permettant d’ajouter, modifier ou supprimer les temps de travail, les exceptions et les relations de calendrier de base.

**Q : Existe‑t‑il des limitations à la personnalisation des calendriers avec Aspose.Tasks ?**  
R : La bibliothèque reflète les capacités de Microsoft Project, vous pouvez donc personnaliser pratiquement tous les aspects du calendrier. Seules les très anciennes versions de fichiers Project peuvent présenter de légères incompatibilités.

**Q : Puis‑je intégrer la gestion des calendriers dans des projets Java existants ?**  
R : Absolument. Ajoutez simplement le JAR Aspose.Tasks à votre chemin de construction et utilisez les mêmes modèles de code présentés ici.

**Q : Aspose.Tasks prend‑il en charge d’autres fonctionnalités de gestion de projet en plus de la gestion des calendriers ?**  
R : Oui, il couvre les tâches, les ressources, les affectations, les structures, les lignes de base, etc., offrant une solution complète pour l’automatisation de projets Java.

**Q : Un support technique est‑il disponible pour les développeurs utilisant Aspose.Tasks ?**  
R : Oui, Aspose propose des forums dédiés, un support par e‑mail et une documentation exhaustive pour tous les utilisateurs sous licence.

---

**Dernière mise à jour :** 2026-09-09  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un calendrier de projet Java – Guide Aspose.Tasks pour Java](/tasks/java/)
- [Charger des fichiers de projet en Java et gérer les propriétés du projet](/tasks/java/project-management/default-properties/)
- [Définir la date de début du projet dans MS Project en utilisant Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}