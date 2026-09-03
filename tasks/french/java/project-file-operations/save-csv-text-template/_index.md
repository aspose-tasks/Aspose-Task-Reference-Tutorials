---
date: 2026-05-26
description: Apprenez comment exporter MPP en CSV, enregistrer le projet en tant que
  modèle et convertir MPP en texte à l'aide d'Aspose.Tasks pour Java.
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: Exporter MPP en CSV, texte et modèle avec Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Exporter MPP en CSV, texte et modèle avec Aspose.Tasks Java
url: /fr/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exporter MPP en CSV, texte et modèle avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez **comment exporter MPP en CSV**, créer des modèles de projet réutilisables et générer des extraits en texte brut à l'aide de la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un pipeline de reporting, automatisiez la création de projets ou intégriez d'autres systèmes, ces étapes vous permettront de passer d'un fichier MPP brut à la sortie exacte dont vous avez besoin—rapidement et sans installer Microsoft Project.

## Réponses rapides
- **Puis-je exporter MPP en CSV ?** Oui – appelez `project.save("output.csv", SaveFileFormat.CSV)`.  
- **Comment exporter en texte brut ?** Utilisez `SaveFileFormat.TEXT` avec la méthode `save`.  
- **Que fait « enregistrer le projet en tant que modèle » ?** Cela crée un fichier `.mpt` qui supprime les dates et les lignes de base, ne laissant que le squelette.  
- **Ai-je besoin d'une licence ?** Une version d'essai fonctionne pour l'évaluation ; une licence commerciale supprime les limites d'évaluation.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur est entièrement pris en charge.

## Qu'est-ce que « enregistrer le projet en tant que modèle » ?
Enregistrer un projet en tant que modèle (`.mpt`) capture la structure, la hiérarchie des tâches et les affectations de ressources tout en supprimant les dates réelles de début/fin et les données de lignes de base. Cela rend le modèle idéal pour réutiliser une structure de projet standard sur plusieurs nouveaux projets. Il conserve tous les champs personnalisés, les taux de coûts et les détails d'affectation, garantissant que le modèle peut être appliqué à tout nouveau projet sans perdre la configuration essentielle.

## Pourquoi utiliser Aspose.Tasks pour Java ?
Exportez MPP en CSV, texte ou modèle directement depuis Java sans Microsoft Project. Aspose.Tasks prend en charge **plus de 20 versions de Microsoft Project** (2000‑2024) et peut traiter des fichiers jusqu'à **500 Mo** en mode mémoire efficace, ce qui le rend idéal pour l'automatisation côté serveur, les pipelines CI et les utilitaires multiplateformes.

## Prérequis
- Java Development Kit 8 ou supérieur installé.  
- Bibliothèque Aspose.Tasks pour Java ajoutée à votre projet – téléchargez-la depuis [ici](https://releases.aspose.com/tasks/java/).  
- Vous pouvez également explorer d'autres bibliothèques Aspose sur [ici](https://releases.aspose.com/).  
- Connaissances de base en Java et en configuration de projet Maven/Gradle.

## Importer les packages
La classe `Project` est l'objet principal d'Aspose.Tasks qui représente un fichier Microsoft Project en mémoire. Après avoir ajouté la bibliothèque à votre fichier de construction, importez les classes requises :

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Enregistrer le projet en CSV (Exporter MPP en CSV)
Exporter un fichier MPP en CSV vous permet d'alimenter les données de tâches dans Excel, Power BI ou toute plateforme d'analyse.

### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Étape 2 : Enregistrer en CSV
`SaveFileFormat.CSV` indique à Aspose.Tasks de produire le projet au format CSV.  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Enregistrer le projet en texte (Comment exporter en texte)
Un fichier texte brut fournit un vidage rapide et lisible par l'homme des tâches, ressources et affectations.

### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Étape 2 : Enregistrer en texte
`SaveFileFormat.TEXT` indique à la bibliothèque de générer une représentation texte brute du projet.  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Enregistrer le projet en tant que modèle (Créer un modèle de projet Java)

### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Étape 2 : Définir les options du modèle
Utilisez `Project.save` avec `SaveFileFormat.MPT` (ou `SaveFileFormat.TEMPLATE`) pour créer un fichier modèle qui supprime les dates et les lignes de base.  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Étape 3 : Enregistrer en tant que modèle
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Problèmes courants et astuces
- **Fichier non trouvé :** Vérifiez le chemin vers `YourProject.mpp` ou utilisez un chemin absolu.  
- **Exceptions de licence :** Sans licence valide, la bibliothèque fonctionne en mode évaluation et peut ajouter des filigranes. Appliquez votre licence tôt (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Grands projets :** Pour les fichiers supérieurs à 200 Mo, augmentez le tas JVM (`-Xmx2g`) pour éviter `OutOfMemoryError`.  
- **Performance :** Lors de la conversion de nombreux projets, réutilisez une seule instance `Project` lorsque cela est possible afin de réduire la surcharge de création d'objets.

## Conclusion
Nous avons montré comment **exporter MPP en CSV**, **convertir MPP en texte**, et **enregistrer le projet en tant que modèle** en utilisant Aspose.Tasks pour Java. Ces capacités vous permettent d'automatiser le reporting, de créer des squelettes de projet standardisés et d'intégrer les données de projet dans tout système en aval—sans avoir besoin d'installer Microsoft Project.

## Questions fréquemment posées

**Q : Aspose.Tasks pour Java peut‑il gérer des projets complexes et multi‑phases ?**  
R : Oui, il prend en charge pleinement les tâches, ressources, affectations, lignes de base et champs personnalisés pour toutes les versions de Project jusqu'à 2024.

**Q : Une version d'essai est‑elle disponible ?**  
R : Absolument – téléchargez un essai gratuit depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l'aide si je rencontre des problèmes ?**  
R : Le forum officiel de support se trouve sur [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) où le personnel et les membres de la communauté répondent aux questions.

**Q : Puis‑je obtenir une licence temporaire pour une évaluation à court terme ?**  
R : Oui, achetez une licence temporaire sur [ici](https://purchase.aspose.com/temporary-license/).

**Q : Aspose.Tasks fonctionne‑t‑il sur Linux et macOS ?**  
R : Il est entièrement multiplateforme et fonctionne sous Windows, macOS et Linux avec n'importe quel runtime Java 8+.

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose

## Tutoriels associés

- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Charger un fichier MPP Java – Gérer les propriétés du projet avec Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Comment exporter MPP vers Excel avec Aspose.Tasks pour Java](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}