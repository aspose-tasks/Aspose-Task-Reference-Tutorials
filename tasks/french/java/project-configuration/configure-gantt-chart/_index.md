---
date: 2025-12-09
description: Apprenez à définir le répertoire de données et à configurer la vue du
  diagramme de Gantt dans Aspose.Tasks en Java. Ce guide montre également comment
  personnaliser les champs du tableau et configurer les projets Java de diagramme
  de Gantt étape par étape.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Définir le répertoire de données pour la vue du diagramme de Gantt dans Aspose.Tasks
url: /fr/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir le répertoire de données pour la vue du diagramme de Gantt dans Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir le répertoire de données** et configurer la vue du diagramme de Gantt MS Project dans les projets Aspose.Tasks en Java. Aspose.Tasks est une API Java robuste qui vous permet de manipuler les fichiers Microsoft Project de manière programmatique. À la fin de ce guide, vous serez capable de **personnaliser les champs de tableau**, d’ajuster le répertoire de données et de visualiser votre projet exactement comme vous le souhaitez.

## Quick Answers
- **Quelle est la première étape ?** Définir le chemin du répertoire de données où résident vos fichiers de projet.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (téléchargeable depuis le site officiel).  
- **Puis‑je ajouter des attributs personnalisés ?** Oui – vous pouvez définir des attributs étendus et les afficher dans le diagramme de Gantt.  
- **Ai‑je besoin d’une licence pour les tests ?** Une licence temporaire est disponible à des fins d’évaluation.  
- **Quel IDE fonctionne le mieux ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans) fonctionnera.

## Qu’est‑ce que le « set data directory » et pourquoi est‑ce important ?
Définir le répertoire de données indique à Aspose.Tasks où lire et écrire les fichiers de projet. Sans un chemin correct, l’API ne peut pas localiser vos fichiers `.mpp`, ce qui entraîne des erreurs FileNotFound. Définir ce répertoire au début de votre code rend le reste du flux de travail propre et reproductible.

## Pourquoi personnaliser les champs de tableau dans un diagramme de Gantt ?
Les champs de tableau personnalisés vous permettent d’afficher des informations supplémentaires – telles que des attributs personnalisés, des données de ressources ou des notes spécifiques au projet – directement dans la vue Gantt. Cela rend le diagramme plus informatif pour les parties prenantes et réduit le besoin de basculer entre plusieurs rapports.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – toute version récente (8+).  
2. **Bibliothèque Aspose.Tasks** – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou tout éditeur compatible Java que vous préférez.

## Import Packages
Tout d’abord, importez l’espace de noms Aspose.Tasks afin de pouvoir travailler avec ses classes :

```java
import com.aspose.tasks.*;
```

## Guide étape par étape

### Étape 1 : Configurer le répertoire de données
Définissez le dossier qui contient vos fichiers de projet. Il s’agit de l’étape **set data directory** sur laquelle se concentre le tutoriel.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu du dossier où `project.mpp` est stocké.

### Étape 2 : Charger le fichier de projet
Créez une instance `Project` en chargeant un fichier Microsoft Project existant.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Étape 3 : Ajouter une nouvelle activité
Insérez une nouvelle tâche (activité) à la racine du projet.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Étape 4 : Définir un attribut personnalisé
Créez une définition d’attribut personnalisé que vous pourrez ensuite associer aux tâches.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Étape 5 : Ajouter l’attribut personnalisé à la tâche
Attribuez l’attribut nouvellement défini à la tâche que vous avez créée.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Étape 6 : Personnaliser le tableau – **customize table fields**
Ajoutez l’attribut personnalisé comme colonne dans le tableau du diagramme de Gantt, en spécifiant la largeur, le titre et l’alignement.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Étape 7 : Enregistrer le projet
Persistiez les modifications dans un nouveau fichier qui pourra être ouvert dans Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **FileNotFoundException** lors du chargement du projet | Le chemin **set data directory** est incorrect ou il manque une barre oblique finale. | Vérifiez que `dataDir` pointe exactement vers le dossier et incluez le séparateur de fichiers approprié (`/` ou `\\`). |
| Attribut personnalisé non visible dans la vue Gantt | Le champ de tableau a été ajouté à un mauvais indice ou la largeur de la colonne est trop petite. | Assurez‑vous que `table.getTableFields().add(3, attrField);` utilise un indice valide et ajustez `setWidth` si nécessaire. |
| LicenseException lors de l’enregistrement | Aucune licence valide n’a été appliquée pour une utilisation en production. | Appliquez une licence temporaire ou permanente avant d’appeler `project.save()`. |

## Foire aux questions

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks est disponible pour plusieurs langages dont .NET, Java et C++.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger un essai gratuit depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Vous pouvez obtenir du support et poser des questions sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q : Comment puis‑je acheter une licence pour Aspose.Tasks ?**  
R : Vous pouvez acheter une licence depuis [ici](https://purchase.aspose.com/buy).

**Q : Ai‑je besoin d’une licence temporaire à des fins de test ?**  
R : Oui, vous pouvez obtenir une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous avez maintenant appris comment **définir le répertoire de données**, ajouter une nouvelle activité, définir et associer un attribut personnalisé, et **personnaliser les champs de tableau** dans une vue de diagramme de Gantt à l’aide d’Aspose.Tasks pour Java. Ces étapes vous donnent un contrôle complet sur la façon dont les données du projet sont affichées, rendant vos diagrammes de Gantt plus informatifs et adaptés aux besoins de vos parties prenantes.

---

**Dernière mise à jour :** 2025-12-09  
**Testé avec :** Aspose.Tasks Java 24.12 (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}