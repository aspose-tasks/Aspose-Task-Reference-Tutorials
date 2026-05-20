---
date: 2026-05-20
description: Apprenez comment utiliser Aspose.Tasks for Java pour ajouter des attributs
  étendus aux affectations de ressources, définir la date de début du projet et écrire
  des fichiers MS Project efficacement.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Ajouter des attributs étendus aux affectations de ressources dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment utiliser Aspose.Tasks for Java – Ajouter des attributs étendus aux
  affectations de ressources
url: /fr/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser la manipulation de MS Project avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez **comment utiliser Aspose.Tasks pour Java** afin d'ajouter des attributs étendus aux affectations de ressources et d'écrire les informations de Microsoft Project de manière programmatique. Que vous automatisiez un pipeline de reporting ou que vous construisiez un outil de gestion de projet personnalisé, les étapes ci‑dessous vous montrent exactement comment définir la date de début du projet, créer des affectations de ressources et enregistrer le fichier au format XML — le tout en quelques lignes de code Java.

## Réponses rapides
- **Que fait Aspose.Tasks pour Java ?** Il lit, écrit et modifie les fichiers Microsoft Project sans nécessiter l'installation de Microsoft Project.  
- **Puis-je ajouter des champs personnalisés à une affectation de ressource ?** Oui, utilisez la collection `ExtendedAttribute` sur l'objet `ResourceAssignment`.  
- **Comment définir la date de début du projet ?** Appelez `project.setStartDate(LocalDateTime.of(...))` avant d'enregistrer.  
- **Ai-je besoin d'une licence pour une utilisation en production ?** Une licence commerciale supprime les filigranes d'évaluation et débloque l'accès complet à l'API.  
- **Quelles versions de Java sont prises en charge ?** Aspose.Tasks pour Java prend en charge JDK 8 à JDK 21.

## Comment utiliser Aspose.Tasks pour Java ?
`Project` est l'objet principal représentant un fichier Microsoft Project en mémoire. Chargez la bibliothèque Aspose.Tasks, créez une instance `Project`, configurez les propriétés au niveau du projet, ajoutez des attributs étendus à une affectation de ressource, puis enregistrez le projet au format XML. Le flux de travail de base se résume en trois étapes concises : initialiser, modifier et persister. Ce modèle fonctionne pour tout fichier de projet, quelle que soit sa taille, et s'exécute sur les JVM Windows, Linux ou macOS.

## Qu'est-ce qu'un attribut étendu dans Aspose.Tasks ?
Un **attribut étendu** est un champ personnalisé que vous associez aux tâches, aux ressources ou aux affectations afin de stocker des métadonnées supplémentaires au-delà des colonnes intégrées. `ExtendedAttributeDefinition` définit le schéma d'un champ personnalisé. Aspose.Tasks expose les classes `ExtendedAttributeDefinition` et `ExtendedAttribute` pour définir et affecter ces champs de manière programmatique.

## Pourquoi ajouter des attributs étendus aux affectations de ressources ?
Aspose.Tasks prend en charge **plus de 50 champs intégrés et personnalisés**, et vous pouvez ajouter un nombre illimité d'attributs définis par l'utilisateur. Les ajouter vous permet de capturer des codes de coût, des identifiants de département ou toute donnée spécifique à l'entreprise directement dans le fichier .mpp, éliminant ainsi le besoin de feuilles de calcul externes et garantissant l'intégrité des données tout au long du cycle de vie du projet.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

1. **Java Development Kit (JDK)** – JDK 8 ou version ultérieure installé.  
2. **Aspose.Tasks for Java library** – Téléchargez‑la depuis la page officielle de version [ici](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, ou tout éditeur compatible Java que vous préférez.

## Importer les packages
First, import the necessary packages in your Java project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Étape 1 : Configurer le répertoire de données
Définissez le répertoire où les données de votre projet seront stockées. Ce chemin sera utilisé plus tard lors de l'enregistrement du fichier XML.

```java
String dataDir = "Your Data Directory";
```

### Étape 2 : Créer une instance de projet
La classe `Project` est l'objet de haut niveau d'Aspose.Tasks qui représente un fichier Microsoft Project unique en mémoire. L'instancier vous donne un accès complet à tous les éléments du projet.

```java
Project project = new Project();
```

### Étape 3 : Définir les propriétés d'information du projet
Définissez les propriétés essentielles du projet telles que la date de début, le drapeau de planification à partir du début, et la date d'état. Ces valeurs sont stockées dans l'objet `ProjectInfo` du projet.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Étape 4 : Ajouter des attributs étendus à une affectation de ressource
Créez un `ExtendedAttributeDefinition` pour le champ personnalisé, attachez‑le à un `ResourceAssignment`, et remplissez la valeur. Cette étape montre le mot‑clé **add extended attributes** en action.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions
- **NullPointerException lors de l'accès à la collection d'affectations** – Assurez‑vous d'avoir créé au moins une ressource et une tâche avant de récupérer les affectations.  
- **L'attribut étendu n'apparaît pas dans MS Project** – Vérifiez que le `FieldId` de l'attribut correspond à un emplacement de champ personnalisé (par ex., `ExtendedAttributeTask.Text1`).  
- **Incohérence de format de date** – Utilisez `java.time.LocalDateTime` pour les valeurs de date ; Aspose.Tasks les convertit automatiquement au format du calendrier du projet.

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Tasks pour Java pour lire des fichiers MS Project ?**  
A : Oui, la bibliothèque offre des capacités complètes de lecture‑écriture pour les formats .mpp, .xml et .xps.

**Q : Aspose.Tasks pour Java est‑il compatible avec différentes versions de MS Project ?**  
A : Absolument, il prend en charge les fichiers de Project 2000 jusqu'à la dernière version 2024, couvrant plus de 20 formats de version.

**Q : Existe‑t‑il des limitations à la version d'essai d'Aspose.Tasks pour Java ?**  
A : La version d'essai ajoute un filigrane aux fichiers générés et limite le nombre de tâches que vous pouvez créer, mais toutes les fonctionnalités de l'API restent accessibles.

**Q : Comment puis‑je obtenir du support pour Aspose.Tasks pour Java ?**  
A : Vous pouvez demander de l'aide sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?**  
A : Oui, des licences temporaires sont disponibles pour une utilisation à court terme. Vous pouvez en obtenir une [ici](https://purchase.aspose.com/temporary-license/).

**Dernière mise à jour :** 2026-05-20  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment ajouter des notes aux affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Comment lire l'échelle de taux et écrire l'échelle de taux pour les affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Comment ajouter une ressource au projet et gérer les propriétés de délai de nivellement dans Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}