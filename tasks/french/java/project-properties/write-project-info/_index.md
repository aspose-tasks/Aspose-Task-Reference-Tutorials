---
date: 2025-12-31
description: Apprenez à définir la date de début du projet, à écrire les informations
  du projet et à enregistrer le projet au format XML en utilisant Aspose.Tasks pour
  Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Définir la date de début du projet dans MS Project à l’aide d’Aspose.Tasks
  pour Java
url: /fr/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la date de début du projet dans MS Project avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez comment **définir la date de début du projet** et écrire des informations supplémentaires de MS Project avec Aspose.Tasks pour Java. Que vous automatisiez des plannings de projet, génériez des rapports ou intégriez des données Project dans un système plus vaste, contrôler la date de début de façon programmatique vous donne une maîtrise précise de vos échéances. Nous parcourrons chaque étape — de la configuration de l’environnement à l’enregistrement du projet mis à jour au format XML— afin que vous puissiez appliquer ces techniques immédiatement.

## Quick Answers
- **Quelle est la classe principale pour manipuler un projet ?** `Project` de la bibliothèque Aspose.Tasks.  
- **Comment définir la date de début du projet ?** Utilisez `project.set(Prj.START_DATE, <date>)`.  
- **Puis-je également définir la date d’état ?** Oui, avec `project.set(Prj.STATUS_DATE, <date>)`.  
- **Quel format dois‑je utiliser pour exporter le projet ?** Enregistrez‑le au format XML avec `SaveFileFormat.Xml`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence valide d’Aspose.Tasks est requise pour la pleine fonctionnalité.

## Qu’est‑ce que **définir la date de début du projet** ?
Définir la date de début du projet indique le jour calendaire à partir duquel toutes les tâches planifiées commencent. C’est le point d’ancrage pour les calculs tels que les durées des tâches, les dépendances et les chemins critiques. En définissant cette date par programme, vous assurez la cohérence entre plusieurs fichiers de projet et éliminez les erreurs de saisie manuelle.

## Pourquoi utiliser Aspose.Tasks pour Java afin d’écrire des informations de projet ?
- **Couverture complète de l’API :** Lire, modifier et écrire chaque propriété du projet sans nécessiter Microsoft Project installé.  
- **Multiplateforme :** Fonctionne sous Windows, Linux et macOS.  
- **Prêt pour l’automatisation :** Idéal pour le traitement par lots, les pipelines CI ou les services back‑end qui génèrent des plannings de projet à la volée.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – toute version récente (8+ recommandée).  
2. **Bibliothèque Aspose.Tasks pour Java** – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse ou votre éditeur Java préféré.  

## Import Packages
Tout d’abord, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Étape 1 : Configurer le répertoire de données
Définissez le répertoire où vos données de projet seront stockées.
```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Créer une instance de projet
Initialisez une nouvelle instance de projet.
```java
Project project = new Project();
```

## Étape 3 : Définir les propriétés d’information du projet
Ici nous définissons la **date de début du projet**, le planning à partir du début, et la date d’état — couvrant les mots‑clés principaux *write project information* et *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Étape 4 : Enregistrer le projet au format XML
Enfin, persistez le fichier de projet mis à jour. Cela illustre le mot‑clé secondaire **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Date de début incorrecte** | Le mois du calendrier est indexé à zéro en Java. | Utilisez `Calendar.JULY` (ou ajoutez 1 à l’indice du mois) comme indiqué. |
| **Fichier non enregistré** | `dataDir` n’existe pas ou n’a pas les droits d’écriture. | Créez le répertoire au préalable ou choisissez un chemin accessible en écriture. |
| **Avertissement de licence** | L’exécution sans licence ajoute un filigrane. | Appliquez une licence valide d’Aspose.Tasks avant de créer l’objet `Project`. |

## FAQ
### Q : Puis‑je utiliser Aspose.Tasks pour Java afin de lire des fichiers MS Project ?
R : Oui, Aspose.Tasks pour Java offre des fonctionnalités robustes tant pour la lecture que pour l’écriture de fichiers MS Project.  
### Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de MS Project ?
R : Absolument, Aspose.Tasks pour Java prend en charge diverses versions de MS Project, garantissant la compatibilité avec différents formats de fichiers.  
### Q : Existe‑t‑il des limitations dans la version d’essai d’Aspose.Tasks pour Java ?
R : La version d’essai vous permet d’explorer les capacités de la bibliothèque, mais elle comporte certaines limitations comme des filigranes sur les fichiers de sortie.  
### Q : Comment obtenir du support pour Aspose.Tasks pour Java ?
R : Vous pouvez demander de l’aide sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).  
### Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?
R : Oui, des licences temporaires sont disponibles pour une utilisation à court terme. Vous pouvez en obtenir une [ici](https://purchase.aspose.com/temporary-license/).  

## Conclusion
Vous avez maintenant appris comment **définir la date de début du projet**, écrire les informations essentielles du projet, et **enregistrer le projet au format XML** avec Aspose.Tasks pour Java. Ces blocs de construction vous permettent d’automatiser les flux de travail de gestion de projet, de générer des plannings cohérents et d’intégrer les données MS Project dans vos applications Java.

---

**Dernière mise à jour :** 2025-12-31  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}