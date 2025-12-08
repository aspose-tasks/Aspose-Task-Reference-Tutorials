---
date: 2025-12-04
description: Apprenez à définir le calendrier du projet et à gérer les propriétés
  du calendrier MS Project en Java avec Aspose.Tasks. Guide étape par étape pour afficher
  les heures de travail du calendrier et personnaliser les plannings.
language: fr
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment définir le calendrier du projet avec Aspose.Tasks pour Java
url: /java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le calendrier du projet avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez **comment définir le calendrier du projet** de manière programmatique à l’aide de la bibliothèque Aspose.Tasks pour Java. Contrôler les propriétés du calendrier vous permet de **afficher les heures de travail du calendrier**, de définir des jours de travail personnalisés et d’aligner le planning de votre projet avec des contraintes du monde réel. Nous parcourrons chaque étape — de la configuration de l’environnement à l’itération sur les calendriers et à la lecture de leurs propriétés— afin que vous puissiez gérer les calendriers MS Project en toute confiance dans vos applications.

## Réponses rapides
- **Que signifie « définir le calendrier du projet » ?** Cela consiste à créer ou mettre à jour les heures de travail, le calendrier de base et les types de jour d’un calendrier dans un fichier MS Project.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (toute version récente).  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je afficher les heures de travail du calendrier ?** Oui — en lisant chaque `WeekDay`, vous pouvez afficher les heures pour chaque type de jour.  
- **Est‑ce compatible avec Maven/Gradle ?** Absolument — ajoutez le JAR Aspose.Tasks en tant que dépendance.

## Qu’est‑ce qu’un calendrier de projet ?
Un calendrier de projet définit les jours et les heures de travail pour les tâches, les ressources et la chronologie globale du projet. Dans MS Project, les calendriers peuvent hériter d’un calendrier de base, et chaque type de jour (par ex. **Standard**, **Non‑travail**) peut avoir son propre horaire de travail. Gérer ces paramètres de façon programmatique permet d’ajuster dynamiquement le planning sans édition manuelle.

## Pourquoi gérer le calendrier MS Project de façon programmatique ?
- **Automatisation :** Ajustez les calendriers de nombreux projets avec un seul script.  
- **Cohérence :** Appliquez les politiques d’heures de travail à l’échelle de l’organisation.  
- **Intégration :** Synchronisez les calendriers avec des systèmes externes (RH, ERP).  
- **Visibilité :** Affichez rapidement **les heures de travail du calendrier** pour les rapports ou le débogage.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- **Java Development Kit (JDK) 8+** installé et la variable `JAVA_HOME` configurée.  
- **Aspose.Tasks pour Java** téléchargé depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/). Ajoutez le JAR au classpath de votre projet ou aux dépendances Maven/Gradle.  

## Importer les packages
Tout d’abord, importez les classes principales d’Aspose.Tasks que nous utiliserons tout au long du tutoriel :

```java
import com.aspose.tasks.*;
```

## Étape 1 : Configurer le répertoire de données
Définissez le dossier contenant vos fichiers de projet. Remplacez le texte de substitution par le chemin réel sur votre machine.

```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Définir les unités de temps
Les heures de travail sont exprimées en millisecondes. Définir des constantes réutilisables rend le code plus lisible.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Étape 3 : Charger les données du projet
Créez une instance `Project` en chargeant un fichier XML MS Project existant (`.xml` ou `.mpp`). Cela vous donne accès à tous les calendriers stockés dans le fichier.

```java
Project project = new Project(dataDir + "project.xml");
```

## Étape 4 : Parcourir les calendriers et afficher les heures de travail
Nous parcourons maintenant chaque calendrier, affichons son identifiant unique, son nom, son calendrier de base et les heures de travail pour chaque type de jour. Cela montre **comment définir le calendrier du projet** et aussi comment **afficher les heures de travail du calendrier**.

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
- **Affiche l’UID et le nom** – utile pour identifier le calendrier ultérieurement.  
- **Montre le calendrier de base** – soit « Self » (le calendrier est son propre base) soit le nom du calendrier hérité.  
- **Itère chaque `WeekDay`** pour calculer et afficher le total des heures de travail (`workingTime` est en millisecondes, nous le divisons donc par `OneHour`).  

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| `NullPointerException` sur `cal.getBaseCalendar()` | Le calendrier est lui‑même un calendrier de base (`isBaseCalendar()` renvoie `true`). | Utilisez la vérification ternaire comme indiqué (`cal.isBaseCalendar() ? "Self" : ...`). |
| Aucun affichage des heures de travail | Le fichier projet utilise une unité de temps différente (ticks). | Vérifiez le format du fichier ; Aspose.Tasks normalise en millisecondes, mais assurez‑vous de charger le bon type de fichier. |
| Impossible de localiser `project.xml` | Chemin `dataDir` incorrect. | Utilisez un chemin absolu ou `Paths.get(dataDir, "project.xml").toString()`. |

## Questions fréquentes

**Q : Puis‑je modifier les propriétés du calendrier de façon programmatique avec Aspose.Tasks ?**  
R : Oui, l’API offre un accès complet en lecture/écriture aux calendriers, vous permettant d’ajouter, modifier ou supprimer les heures de travail, les exceptions et les relations de calendrier de base.

**Q : Existe‑t‑il des limites à la personnalisation du calendrier avec Aspose.Tasks ?**  
R : La bibliothèque reproduit les capacités de Microsoft Project, vous pouvez donc personnaliser pratiquement tous les aspects du calendrier. Seules les très anciennes versions de fichiers Project peuvent présenter de légères incompatibilités.

**Q : Puis‑je intégrer la gestion du calendrier dans des projets Java existants ?**  
R : Absolument. Ajoutez simplement le JAR Aspose.Tasks à votre chemin de construction et utilisez les mêmes modèles de code présentés ici.

**Q : Aspose.Tasks prend‑il en charge d’autres fonctionnalités de gestion de projet en plus de la gestion des calendriers ?**  
R : Oui, il couvre les tâches, les ressources, les affectations, les structures, les lignes de base, etc.—une solution complète pour l’automatisation de projets en Java.

**Q : Un support technique est‑il disponible pour les développeurs utilisant Aspose.Tasks ?**  
R : Oui, Aspose propose des forums dédiés, un support par e‑mail et une documentation exhaustive pour tous les utilisateurs sous licence.

## Conclusion
En suivant ce guide, vous savez maintenant **comment définir le calendrier du projet**, lire et **afficher les heures de travail du calendrier**, et intégrer ces capacités dans n’importe quelle application Java grâce à Aspose.Tasks. Cela vous permet d’automatiser les ajustements de planning, d’appliquer des politiques de travail cohérentes et de créer des solutions de gestion de projet plus riches.

---

**Dernière mise à jour :** 2025-12-04  
**Testé avec :** Aspose.Tasks pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}