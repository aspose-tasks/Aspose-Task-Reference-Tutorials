---
date: 2025-12-21
description: Apprenez à enregistrer un projet en tant que modèle, à exporter un MPP
  au format CSV et à convertir un MPP en texte à l'aide d'Aspose.Tasks pour Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Enregistrer le projet en tant que modèle, CSV et texte avec Aspose.Tasks pour
  Java
url: /fr/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le projet en tant que modèle, CSV et texte avec Aspise.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **comment enregistrer un projet en tant que modèle** et également comment exporter vos fichiers Microsoft Project (MPP) aux formats CSV et texte brut à l’aide de la bibliothèque Aspose.Tasks pour Java. Que vous ayez besoin de créer un modèle de projet réutilisable, de générer des rapports CSV pour l’analyse, ou de produire de simples extraits texte pour l’intégration, ces étapes vous guideront rapidement et efficacement.

## Réponses rapides
- **Puis-je exporter un MPP en CSV ?** Oui – utilisez `project.save(..., SaveFileFormat.CSV)`.  
- **Comment exporter du texte ?** Enregistrez avec `SaveFileFormat.TEXT`.  
- **Que fait « enregistrer le projet en tant que modèle » ?** Cela crée un fichier `.mpt` qui supprime les valeurs réelles et de référence, prêt à être réutilisé.  
- **Ai-je besoin d’une licence ?** Un essai est disponible ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est requise ?** Java 8+ est pris en charge.

## Qu’est-ce que « enregistrer le projet en tant que modèle » ?
Enregistrer un projet sous forme de modèle (`.mpt`) capture la structure, la hiérarchie des tâches et les affectations de ressources tout en supprimant les dates de début/fin réelles ainsi que les données de ligne de base. Cela rend le modèle idéal pour réutiliser une mise en page de projet standard dans plusieurs nouveaux projets.

## Pourquoi utiliser Aspose.Tasks pour Java ?
Aspose.Tasks vous permet de manipuler les fichiers Microsoft Project sans installer Microsoft Project lui‑même. Il prend en charge **comment exporter MPP**, **comment exporter du texte**, et **convertir MPP en CSV**, le tout depuis du code Java pur, ce qui est parfait pour l’automatisation côté serveur, les pipelines CI ou les utilitaires de bureau.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. Java Development Kit (JDK) 8 ou supérieur installé.  
2. Bibliothèque Aspose.Tasks pour Java ajoutée à votre projet. Téléchargez‑la depuis [here](https://releases.aspose.com/tasks/java/).  
3. Familiarité de base avec la syntaxe Java et la configuration de projet Maven/Gradle.

## Importer les packages
Tout d'abord, importez les classes requises dans votre fichier source Java :

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Enregistrer le projet en CSV (Exporter MPP en CSV)
Exporter un fichier MPP en CSV est utile pour l'analyse de données dans Excel ou les outils BI.

### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Étape 2 : Enregistrer en CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Enregistrer le projet en texte (Comment exporter du texte)
Si vous avez besoin d’une représentation texte brut des tâches, ressources ou affectations, enregistrez le projet sous forme de fichier texte.

### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Étape 2 : Enregistrer en texte
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Enregistrer le projet en tant que modèle (Créer un modèle de projet Java)
Créer un modèle réutilisable supprime les dates réelles et les lignes de base, laissant un squelette propre pour les nouveaux projets.

### Étape 1 : Charger le projet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Étape 2 : Définir les options du modèle
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
- **Fichier non trouvé :** Assurez‑vous que le chemin vers `YourProject.mpp` est correct ou utilisez un chemin absolu.  
- **Exceptions de licence :** Sans licence valide, la bibliothèque fonctionne en mode évaluation et peut ajouter des filigranes. Appliquez votre licence tôt dans le code (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Grands projets :** Pour des fichiers MPP très volumineux, envisagez d'augmenter la taille du tas JVM (`-Xmx2g`) afin d'éviter `OutOfMemoryError`.

## Conclusion
Nous avons couvert **comment enregistrer un projet en tant que modèle**, ainsi que **comment exporter MPP en CSV** et **convertir MPP en texte** à l’aide d’Aspose.Tasks pour Java. Ces capacités vous permettent d’automatiser la gestion des données de projet, de générer des modèles réutilisables et d’intégrer les informations de projet dans d’autres systèmes—le tout sans nécessiter l’installation de Microsoft Project.

## FAQ
### Q : Aspose.Tasks pour Java peut‑il gérer des fichiers de projet complexes ?
R : Absolument ! Aspose.Tasks pour Java peut gérer des projets de complexité variable avec aisance, offrant un support complet des formats de fichiers Microsoft Project.  
### Q : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks pour Java ?
R : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Tasks pour Java depuis [here](https://releases.aspose.com/).  
### Q : Où puis‑je trouver du support pour Aspose.Tasks pour Java ?
R : Vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question concernant Aspose.Tasks pour Java.  
### Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?
R : Oui, vous pouvez acheter une licence temporaire depuis [here](https://purchase.aspose.com/temporary-license/), vous permettant d’évaluer tout le potentiel de la bibliothèque.  
### Q : Aspose.Tasks pour Java est‑il compatible avec différents systèmes d'exploitation ?
R : Oui, Aspose.Tasks pour Java est compatible avec divers systèmes d'exploitation, y compris Windows, macOS et Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest)  
**Auteur :** Aspose  

---