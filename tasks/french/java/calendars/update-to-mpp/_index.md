---
date: 2026-02-05
description: Apprenez comment ajouter des jours fériés à un calendrier, affecter le
  calendrier à un projet et enregistrer le fichier MS Project au format MPP à l’aide
  d’Aspose.Tasks pour Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ajouter des jours fériés au calendrier et enregistrer au format MPP avec Aspose.Tasks
url: /fr/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des jours fériés au calendrier et enregistrer en MPP avec Aspose.Tasks

## Introduction

Dans la gestion de projet moderne, il est souvent nécessaire d'**ajouter des jours fériés à des fichiers de calendrier**, de créer un **calendrier MS Project**, puis de partager le planning au format MPP natif. Que vous consolidiez des échéanciers provenant de sources multiples ou que vous migriez des données existantes, la génération automatisée d'un calendrier élimine les erreurs manuelles et accélère la livraison. Ce tutoriel vous guide pas à pas dans la création d'un calendrier dans MS Project, sa personnalisation avec les jours fériés, son **affectation à un projet** et enfin sa **conversion au format MPP** à l'aide de l'API Java Aspose.Tasks.

## Questions fréquentes
- **Que couvre ce tutoriel ?** L'ajout de jours fériés à un calendrier, son affectation à un projet et l'enregistrement du résultat au format MPP avec Aspose.Tasks pour Java.
- **Ai-je besoin d'une licence ?** Une version d'essai gratuite est disponible pour le développement ; une licence commerciale est requise pour la production.
- **Quelle version de Java est requise ?** Java 8 ou version ultérieure (JDK 8+). - **Puis-je personnaliser le calendrier ?** Oui, vous pouvez ajouter des heures de travail, des exceptions et des jours fériés.
- **Combien de temps faut-il pour l'implémentation ?** Environ 10 à 15 minutes pour un calendrier de base.

## Qu'est-ce que « create calendarMSProject » ?

Créer un calendrier MSProject consiste à définir par programmation les jours, les heures et les exceptions qui régissent la planification des tâches dans un fichier Microsoft Project. Avec Aspose.Tasks, vous pouvez **créer un calendrier de projet en Java**, le modifier et enregistrer les modifications sans ouvrir l'interface utilisateur de Microsoft Project.

## Pourquoi utiliser Aspose.Tasks pour cette tâche ?

- **Compatibilité .NET/Java totale** : fonctionne sur toute plateforme prenant en charge Java.
- **Aucune installation COM ou Office requise** : idéal pour l'automatisation côté serveur et la **génération automatisée de plannings**.
- **API riche** : prend en charge toutes les propriétés du calendrier, y compris les semaines de travail et les jours fériés personnalisés. - **Sortie MPP directe** – Vous pouvez **enregistrer votre projet au format MPP** sans conversion intermédiaire.

## Prérequis

1. **Java Development Kit (JDK) 8+** – Assurez-vous que la commande `java -version` renvoie 1.8 ou une version ultérieure.
2. **Aspose.Tasks pour Java** – Téléchargez le dernier fichier JAR depuis le [site web d'Aspose](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse ou tout autre éditeur de votre choix.
4. **Connaissances de base en Java** – Familiarité avec les classes, les méthodes et les entrées/sorties de fichiers.

## Comment ajouter des jours fériés au calendrier

Vous trouverez ci-dessous la description détaillée de chaque étape, de la configuration de l'environnement à l'enregistrement du fichier MPP final. Les blocs de code sont identiques à ceux du tutoriel original ; les explications ont été développées pour plus de clarté.

### Étape 1 : Importer les packages requis

Commencez par importer les classes Aspose.Tasks et les utilitaires Java.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Étape 2 : Configuration du répertoire de données

Définissez l’emplacement de vos fichiers de modèle d’entrée et de sortie. Remplacez l’espace réservé par le chemin d’accès réel sur votre ordinateur.

```java
String dataDir = "Your Data Directory";
```

### Étape 3 : Définition des noms des fichiers d’entrée et de sortie

Nous allons charger un fichier MPP existant (ou un projet vierge) et écrire le résultat dans un nouveau fichier.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Étape 4 : Chargement du projet et ajout d’un calendrier

Créez une instance de `Project` à partir du fichier source et ajoutez un calendrier nommé **« Calendar1 »**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Étape 5 : Personnalisation du calendrier (facultatif)

Si vous avez besoin de définir des horaires de travail, des jours fériés ou des exceptions spécifiques, appelez votre propre méthode d’assistance. L’exemple utilise `GetTestCalendar` par défaut.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Astuce :** Vous pouvez manipuler directement `cal1.getWeekDays()` pour définir les heures de travail pour chaque jour de la semaine, ou utiliser `cal1.getExceptions()` pour **ajouter des jours fériés au calendrier**.

### Étape 6 : Affecter le calendrier au projet

Indiquez au projet d’utiliser le calendrier nouvellement créé pour tous ses calculs de planification.

```java
project.set(Prj.CALENDAR, cal1);
```

### Étape 7 : Enregistrer le projet au format MPP

Convertissez maintenant le projet au format MPP en l’enregistrant avec l’option `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Étape 8 : Confirmer la réussite de l’opération

Un simple message dans la console vous confirme que le processus s’est terminé sans erreur.

```java
System.out.println("Process completed Successfully");
```

## Cas d'utilisation courants
- **Génération automatisée de plannings** pour les projets récurrents (ex. : sprints hebdomadaires).
- **Migration de calendriers CSV ou Excel existants** vers un fichier MS Project complet.
- **Génération de rapports côté serveur** où un service web renvoie un fichier MPP à la demande.

## Dépannage et pièges courants

| Problème | Cause | Solution |

|-------|-------|-----|
| `NullPointerException` lors de `project.save` | `dataDir` pointe vers un dossier inexistant | Assurez-vous que le répertoire existe ou créez-le par programmation. |
| Calendrier non appliqué aux tâches | Les tâches font toujours référence au calendrier par défaut | Après avoir défini `Prj.CALENDAR`, mettez également à jour le `Task.CALENDAR` de chaque tâche s'il a été précédemment modifié. |
| Fichier de sortie de 0 Ko | Autorisations d'écriture manquantes | Exécutez la JVM avec les droits d'accès appropriés au système de fichiers ou choisissez un chemin accessible en écriture. |

## Foire aux questions

**Q : Aspose.Tasks pour Java est-il compatible avec différentes versions de MS Project ?**

**R :** Oui, Aspose.Tasks pour Java prend en charge un large éventail de versions de MS Project, de Project 2007 à la dernière version, garantissant une compatibilité parfaite.

**Q : Puis-je personnaliser les calendriers en fonction des exigences spécifiques d'un projet ?**

**R :** Absolument. Vous pouvez définir les jours ouvrés, configurer des semaines de travail personnalisées, ajouter des jours fériés et même créer plusieurs calendriers dans un seul fichier de projet.

**Q : Aspose.Tasks pour Java offre-t-il une assistance pour le dépannage ?**

**R :** Oui, vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Existe-t-il une version d'essai gratuite d'Aspose.Tasks pour Java ?**

**R :** Oui, une version d'essai gratuite et entièrement fonctionnelle est disponible [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks pour Java ?**

**R :** Vous pouvez demander une licence temporaire sur le site web d'Aspose [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 05/02/2026
**Testé avec :** Aspose.Tasks pour Java 24.12
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}