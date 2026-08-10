---
date: 2026-05-15
description: Apprenez comment définir la date de début du projet, rédiger les informations
  du projet et enregistrer le projet au format XML en utilisant Aspose.Tasks pour
  Java.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: Écrire les informations du projet dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Définir la date de début du projet dans MS Project avec Aspose.Tasks pour Java
url: /fr/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la date de début du projet dans MS Project à l'aide d'Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez comment **définir la date de début du projet** et écrire des informations supplémentaires de MS Project avec Aspose.Tasks pour Java. Que vous automatisiez des plannings de projet, génériez des rapports ou intégriez des données Project dans un système plus vaste, contrôler la date de début de façon programmatique vous donne un contrôle précis sur vos échéances. Nous parcourrons chaque étape — de la configuration de l'environnement à l'enregistrement du projet mis à jour au format XML — afin que vous puissiez appliquer ces techniques immédiatement.

## Réponses rapides
- **Quelle est la classe principale pour manipuler un projet ?** `Project` de la bibliothèque Aspose.Tasks.  
  La classe `Project` représente un fichier MS Project en mémoire.  
- **Comment définir la date de début du projet ?** Utilisez `project.set(Prj.START_DATE, <date>)`.  
  `Prj.START_DATE` est la clé de propriété utilisée pour définir la date de début du projet.  
- **Puis-je également définir la date d’état ?** Oui, avec `project.set(Prj.STATUS_DATE, <date>)`.  
  `Prj.STATUS_DATE` spécifie la date qui reflète l’état actuel du projet.  
- **Quel format dois‑je utiliser pour exporter le projet ?** Enregistrez‑le au format XML avec `SaveFileFormat.Xml`.  
  `SaveFileFormat.Xml` indique que le projet sera sauvegardé au format XML.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence valide d’Aspose.Tasks est requise pour bénéficier de toutes les fonctionnalités.  
- **Quels environnements Aspose.Tasks prend‑il en charge ?** Windows, Linux et macOS avec Java 8+.

## Qu’est‑ce que la définition de la date de début du projet ?
Définir la date de début du projet détermine le jour calendaire auquel le planning commence, établissant la base pour tous les calculs de tâches, dépendances et analyses du chemin critique. En définissant cette date de façon programmatique, vous garantissez que chaque fichier de projet généré débute au même point, éliminant les erreurs de saisie manuelle et assurant des résultats reproductibles entre les builds.

## Pourquoi utiliser Aspose.Tasks pour Java afin d’écrire des informations de projet ?
Aspose.Tasks pour Java offre **plus de 150 propriétés de projet configurables** et prend en charge **plus de 30 formats de fichiers**, vous permettant de lire, modifier et écrire des données MS Project sans avoir Microsoft Project installé. La bibliothèque fonctionne sous Windows, Linux et macOS, traite des fichiers de plusieurs centaines de pages en mode mémoire efficace, et peut être intégrée aux pipelines CI/CD, services de traitement par lots ou back‑ends cloud. Ces capacités quantifiées en font le choix le plus fiable pour l’automatisation à l’échelle d’entreprise.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – toute version récente (8+ recommandée).  
2. **Bibliothèque Aspose.Tasks pour Java** – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse ou votre éditeur Java préféré.  

## Importer les packages
Tout d’abord, importez les packages nécessaires dans votre projet Java :
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
La classe `Project` est l’objet de haut niveau d’Aspose.Tasks qui représente un fichier MS Project unique en mémoire. L’initialiser crée un planning vide que vous pouvez immédiatement commencer à remplir.
```java
Project project = new Project();
```

## Étape 3 : Définir les propriétés d’information du projet
Ici nous définissons la **date de début du projet**, le drapeau « schedule‑from‑start », et la date d’état — couvrant les mots‑clés principaux et secondaires *écrire des informations de projet* et *comment définir la date d’état*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Étape 4 : Enregistrer le projet au format XML
Enfin, persistez le fichier de projet mis à jour. L’enregistrement au format XML garantit une compatibilité maximale avec les outils en aval et maintient la taille du fichier réduite.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Date de début incorrecte** | Le mois du calendrier est indexé à zéro en Java. | Utilisez `Calendar.JULY` (ou ajoutez 1 à l’indice du mois) comme indiqué. |
| **Fichier non enregistré** | `dataDir` n’existe pas ou n’a pas les droits d’écriture. | Créez le répertoire au préalable ou choisissez un chemin accessible en écriture. |
| **Avertissement de licence** | L’exécution sans licence ajoute un filigrane. | Appliquez une licence valide d’Aspose.Tasks avant de créer l’objet `Project`. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks pour Java afin de lire des fichiers MS Project ?**  
R : Oui, Aspose.Tasks pour Java offre des fonctionnalités robustes tant pour la lecture que pour l’écriture de fichiers MS Project.

**Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de MS Project ?**  
R : Absolument, Aspose.Tasks pour Java prend en charge diverses versions de MS Project, assurant une manipulation fluide des formats MPP, XML et Primavera.

**Q : Existe‑t‑il des limitations dans la version d’essai d’Aspose.Tasks pour Java ?**  
R : La version d’essai permet d’explorer toutes les fonctionnalités mais insère un filigrane sur les fichiers générés et limite le nombre d’entités de projet que vous pouvez créer.

**Q : Comment obtenir du support pour Aspose.Tasks pour Java ?**  
R : Vous pouvez demander de l’aide sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?**  
R : Oui, des licences temporaires sont disponibles pour une utilisation à court terme. Vous pouvez en obtenir une [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous avez maintenant appris comment **définir la date de début du projet**, écrire les informations essentielles du projet, et **enregistrer le projet au format XML** à l’aide d’Aspose.Tasks pour Java. Ces blocs de construction vous permettent d’automatiser les flux de travail de gestion de projet, de générer des plannings cohérents et d’intégrer les données MS Project dans vos applications Java. Ensuite, explorez comment ajouter des tâches, des ressources et des champs personnalisés pour enrichir davantage vos plannings automatisés.

---

**Dernière mise à jour :** 2026-05-15  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment définir le calendrier du projet avec Aspose.Tasks pour Java](/tasks/java/calendars/properties/)
- [Comment lire les informations du projet depuis Microsoft Project avec Aspose.Tasks pour Java](/tasks/java/project-properties/read-project-info/)
- [Charger un fichier MPP Java – Gérer les propriétés du projet avec Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}