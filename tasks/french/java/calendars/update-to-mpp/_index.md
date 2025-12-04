---
date: 2025-12-03
description: Apprenez à créer un calendrier MS Project, à convertir un projet en MPP
  et à enregistrer un projet MPP sans effort en utilisant Aspose.Tasks pour Java.
language: fr
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Créer un calendrier MS Project et l’enregistrer au format MPP avec Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un calendrier MS Project et l’enregistrer au format MPP avec Aspose.Tasks

## Introduction

Dans la gestion de projet moderne, vous devez souvent **créer des fichiers de calendrier MS Project** puis les partager au format natif MPP. Que vous consolidiez des plannings provenant de multiples sources ou que vous migriez des données héritées, pouvoir générer un calendrier de façon programmatique fait gagner du temps et élimine les erreurs manuelles. Ce tutoriel vous guide à travers le processus complet de création d’un calendrier dans MS Project, de sa personnalisation, puis **de la conversion du projet en MPP** à l’aide de l’API Aspose.Tasks pour Java.

## Réponses rapides
- **Que couvre ce tutoriel ?** Création d’un calendrier dans MS Project et enregistrement au format MPP avec Aspose.Tasks pour Java.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise en production.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur (JDK 8+).  
- **Puis‑je personnaliser le calendrier ?** Oui – vous pouvez ajouter des heures de travail, des exceptions et des jours fériés.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un calendrier de base.

## Qu’est‑ce que « créer un calendrier MS Project » ?

Créer un calendrier MS Project signifie définir programmatique les jours ouvrés, les heures et les exceptions qui pilotent la planification des tâches dans un fichier Microsoft Project. En utilisant Aspose.Tasks, vous pouvez construire, modifier et persister ces calendriers sans jamais ouvrir l’interface Microsoft Project.

## Pourquoi utiliser Aspose.Tasks pour cette tâche ?

- **Compatibilité .NET/Java complète** – fonctionne sur toute plateforme supportant Java.  
- **Pas de COM ni d’installation d’Office** – idéal pour l’automatisation côté serveur.  
- **API riche** – prend en charge chaque propriété de calendrier, y compris les semaines de travail personnalisées et les jours fériés.  
- **Sortie directe en MPP** – vous pouvez **enregistrer le projet en MPP** sans conversions intermédiaires.

## Prérequis

1. **Java Development Kit (JDK) 8+** – assurez‑vous que `java -version` renvoie 1.8 ou une version supérieure.  
2. **Aspose.Tasks pour Java** – téléchargez le JAR le plus récent depuis le [site Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou tout éditeur de votre choix.  
4. **Connaissances de base en Java** – familiarité avec les classes, méthodes et I/O de fichiers.

## Guide étape par étape

### Étape 1 : Importer les packages requis

Tout d’abord, importez les classes Aspose.Tasks et les utilitaires Java.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Étape 2 : Configurer le répertoire de données

Définissez où vos modèles d’entrée et vos fichiers de sortie seront stockés. Remplacez le texte de substitution par le chemin réel sur votre machine.

```java
String dataDir = "Your Data Directory";
```

### Étape 3 : Définir les noms de fichiers d’entrée et de sortie

Nous chargerons un fichier MPP existant (ou un projet vierge) et écrirons le résultat dans un nouveau fichier.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Étape 4 : Charger le projet et ajouter un nouveau calendrier

Créez une instance `Project` à partir du fichier source et ajoutez un calendrier nommé **« Calendar 1 »**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Étape 5 : Personnaliser le calendrier (facultatif)

Si vous avez besoin d’heures de travail spécifiques, de jours fériés ou d’exceptions, appelez votre propre méthode d’assistance. L’exemple utilise `GetTestCalendar` comme espace réservé.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Astuce :** Vous pouvez manipuler directement `cal1.getWeekDays()` pour définir les heures de travail de chaque jour de la semaine.

### Étape 6 : Assigner le calendrier au projet

Indiquez au projet d’utiliser le calendrier nouvellement créé pour tous ses calculs de planification.

```java
project.set(Prj.CALENDAR, cal1);
```

### Étape 7 : Enregistrer le projet au format MPP

Maintenant **convertissez le projet en MPP** en l’enregistrant avec l’option `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Étape 8 : Confirmer la réussite

Un simple message console vous indique que le processus s’est terminé sans erreur.

```java
System.out.println("Process completed Successfully");
```

## Cas d’utilisation courants

- **Génération automatisée d’horaires** pour des projets récurrents (par ex., sprints hebdomadaires).  
- **Migration de calendriers CSV ou Excel hérités** vers un fichier MS Project complet.  
- **Reporting côté serveur** où un service web renvoie un fichier MPP à la demande.  

## Dépannage & pièges courants

| Problème | Cause | Solution |
|----------|-------|----------|
| `NullPointerException` sur `project.save` | `dataDir` pointe vers un dossier inexistant | Vérifiez que le répertoire existe ou créez‑le programmatique. |
| Le calendrier n’est pas appliqué aux tâches | Les tâches référencent encore le calendrier par défaut | Après avoir défini `Prj.CALENDAR`, mettez également à jour chaque `Task.CALENDAR` si elles avaient été surchargées. |
| Fichier de sortie de 0 KB | Permissions d’écriture manquantes | Exécutez la JVM avec les droits d’accès appropriés ou choisissez un chemin accessible en écriture. |

## Foire aux questions

**Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de MS Project ?**  
R : Oui, Aspose.Tasks pour Java prend en charge une large gamme de versions de MS Project, de Project 2007 jusqu’à la dernière version, garantissant une compatibilité fluide.

**Q : Puis‑je personnaliser les calendriers selon les exigences spécifiques d’un projet ?**  
R : Absolument. Vous pouvez définir les jours ouvrés, créer des semaines de travail personnalisées, ajouter des jours fériés et même créer plusieurs calendriers dans un même fichier projet.

**Q : Aspose.Tasks pour Java propose‑t‑il une assistance pour le dépannage ?**  
R : Oui, vous pouvez obtenir de l’aide sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Existe‑t‑il un essai gratuit d’Aspose.Tasks pour Java ?**  
R : Oui, un essai gratuit pleinement fonctionnel est disponible [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks pour Java ?**  
R : Les licences temporaires peuvent être demandées via le site Aspose [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2025-12-03  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}