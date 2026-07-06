---
date: 2026-02-07
description: Apprenez comment définir le code de devise Java dans les projets Aspose.Tasks,
  modifier le symbole monétaire et appliquer un format de devise personnalisé aux
  fichiers Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Code de devise Java – Comment le définir dans les projets Aspose.Tasks
url: /fr/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le code de devise dans Aspose.Tasks – Guide Java

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir le code de devise java** pour un fichier Microsoft Project en utilisant l'API Java d'Aspose.Tasks. Que vous ayez besoin de *modifier la devise* pour des équipes internationales, d'ajuster le *symbole de devise*, ou d'appliquer un **format de devise personnalisé**, les étapes ci‑dessous vous guideront à travers le processus avec des explications claires et du code prêt à l'exécution.

## Quick Answers
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java.  
- **Puis-je changer le symbole de devise ?** Oui – utilisez `CurrencySymbolPositionType` et `Prj.CURRENCY_SYMBOL`.  
- **Quels formats de fichier sont pris en charge ?** XML, MPP, et bien d'autres via `SaveFileFormat`.  
- **Ai‑je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.  
- **Combien de temps prend l'implémentation ?** Environ 5‑10 minutes pour une configuration de base.

## How to Set Currency Code Java in Aspose.Tasks
La devise d’un projet définit la façon dont les valeurs de coût sont affichées — le code (par ex., `AUD`), le nombre de décimales, le symbole (`$`) et la position du symbole. La définition de ces propriétés garantit que chaque champ lié aux coûts (taux des ressources, budgets des tâches, etc.) reflète le format monétaire correct pour votre public.

## Why Use Aspose.Tasks to Change Currency?
- **Aucune installation de Microsoft Project requise** – manipulez les fichiers sur n’importe quel serveur.  
- **Couverture complète de l’API** – tous les champs liés à la devise sont exposés via les constantes `Prj`.  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS avec n’importe quel IDE compatible Java.  
- **Haute performance** – traitez rapidement et de manière fiable de gros fichiers de projet.  
- **Prise en charge du format de devise personnalisé** – vous pouvez définir les symboles, le nombre de décimales et le positionnement pour correspondre aux normes régionales.

## Prerequisites
Avant de commencer, assurez-vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis la [page de téléchargement d'Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA, ou tout éditeur de votre choix.  
4. **Un dossier accessible en écriture** – où le fichier de projet généré sera enregistré.

## Import Packages
First, import the classes that provide access to project properties and file handling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Specify the folder that contains your source files and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object. This object represents an in‑memory Microsoft Project file.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Here’s where we **how to set currency** details such as code, digits, symbol, and symbol position.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Conseil pro :** Si vous devez **modifier la devise du projet** pour un fichier existant, chargez‑le simplement avec `new Project("file.mpp")` avant d’appliquer les paramètres ci‑dessus.

### Step 4: Save the Updated Project
Write the project back to disk in the desired format. In this example we use the XML format, but you can also choose `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Print a friendly message so you know the operation completed without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **`NullPointerException` sur `project.save`** | `dataDir` n’est pas un chemin valide ou n’a pas les permissions d’écriture. | Assurez‑vous que le répertoire existe et que votre processus Java dispose des droits d’écriture. |
| **Le symbole de devise n’apparaît pas** | La position du symbole est définie de manière incorrecte pour votre paramètre régional. | Utilisez `CurrencySymbolPositionType.Before` si le symbole doit précéder le montant. |
| **Le fichier de projet ne s’ouvre pas dans MS Project** | Enregistrement dans un format plus ancien avec des paramètres incompatibles. | Enregistrez avec `SaveFileFormat.MPP` pour une compatibilité totale avec les versions récentes de MS Project. |

## Frequently Asked Questions

**Q : Puis‑je définir plusieurs devises dans un même projet avec Aspose.Tasks ?**  
R : Oui, Aspose.Tasks vous permet de gérer plusieurs devises dans un même fichier de projet en définissant les propriétés de devise par ressource ou par tâche.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Absolument. La bibliothèque prend en charge les fichiers MPP de Project 2000 jusqu’aux dernières versions, ainsi que XML et d’autres formats.

**Q : Aspose.Tasks offre‑t‑il la prise en charge des formats de devise personnalisés ?**  
R : Oui, vous pouvez définir des symboles, le nombre de décimales et le positionnement personnalisés pour répondre à n’importe quelle exigence régionale.

**Q : Puis‑je intégrer Aspose.Tasks avec d’autres bibliothèques ou frameworks Java ?**  
R : Bien sûr. L’API est pure Java, elle fonctionne donc parfaitement avec Spring, Hibernate, Maven, Gradle et d’autres écosystèmes.

**Q : Où puis‑je trouver un support ou une assistance supplémentaire pour Aspose.Tasks ?**  
R : Consultez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour l’aide de la communauté, ou référez‑vous à la documentation officielle pour des références détaillées de l’API.

## Conclusion
Vous savez maintenant **comment définir le code de devise java**, comment **modifier les valeurs de devise**, et comment **modifier le symbole de devise** en utilisant Aspose.Tasks pour Java. Ces fonctionnalités vous permettent d’adapter les données de coûts pour des équipes mondiales, de générer des rapports spécifiques à une locale, et de garder vos fichiers de projet cohérents à travers les frontières.

---

**Dernière mise à jour :** 2026-02-07  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}