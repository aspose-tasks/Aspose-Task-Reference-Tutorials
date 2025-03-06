---
title: Ajouter des attributs étendus aux tâches dans Aspose.Tasks
linktitle: Ajouter des attributs étendus aux tâches dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez la puissance d'Aspose.Tasks Java pour personnaliser les fichiers Microsoft Project avec des attributs étendus. Améliorez vos capacités de gestion de projet sans effort.
weight: 11
url: /fr/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des attributs étendus aux tâches dans Aspose.Tasks

## Introduction
L'amélioration de vos capacités de gestion de projet est cruciale pour un suivi efficace des tâches et une gestion des ressources. Aspose.Tasks for Java fournit une solution puissante permettant aux développeurs Java de manipuler les fichiers Microsoft Project de manière transparente. Dans ce didacticiel, nous verrons comment ajouter des attributs étendus aux tâches à l'aide d'Aspose.Tasks pour Java, vous permettant ainsi de personnaliser et d'organiser les données de votre projet en fonction de vos besoins spécifiques.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Connaissance de base de la programmation Java.
-  Aspose.Tasks pour la bibliothèque Java installée. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/tasks/java/).
- Un environnement de développement intégré (IDE) Java installé sur votre système.
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour accéder aux fonctionnalités Aspose.Tasks :
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Maintenant, décomposons chaque exemple en plusieurs étapes :
## 1. Ajout d'un attribut de texte brut
1. Définissez le chemin du répertoire du document :
```java
String dataDir = "Your Document Directory";
```
2. Créez un nouveau projet :
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Créez une définition d'attribut étendue de type Text1 :
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Ajoutez la définition à la collection d'attributs étendus du projet :
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Ajoutez une tâche au projet :
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Créez un attribut étendu à partir de la définition d'attribut :
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Attribuez une valeur à l'attribut étendu généré :
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Ajoutez l'attribut étendu à la tâche :
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Enregistrez le projet :
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Ajout d'un attribut de texte avec l'option de recherche
Suivez les mêmes étapes que ci-dessus, en remplaçant Text1 par Text2 et en personnalisant les valeurs de recherche.
## 3. Ajout d'un attribut de durée avec l'option de recherche
Suivez les mêmes étapes que ci-dessus, en remplaçant Text1 par Duration2 et en personnalisant les valeurs de recherche.
## Conclusion
En suivant ce guide étape par étape, vous avez appris à exploiter Aspose.Tasks pour Java pour ajouter des attributs étendus aux tâches de vos fichiers Microsoft Project. Cette personnalisation vous permet d'adapter votre approche de gestion de projet, améliorant ainsi la flexibilité et l'efficacité.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.Tasks pour Java avec d'autres bibliothèques Java ?
R : Oui, Aspose.Tasks for Java peut être intégré de manière transparente à vos projets Java et fonctionne bien avec d'autres bibliothèques Java.
### : Aspose.Tasks for Java est-il adapté aux applications de gestion de projets à grande échelle ?
R : Absolument, Aspose.Tasks for Java est conçu pour gérer des projets de différentes tailles, y compris des applications à grande échelle.
### Q : Existe-t-il des considérations en matière de licence pour l'utilisation d'Aspose.Tasks for Java dans un projet commercial ?
 R : Oui, assurez-vous de consulter les informations de licence fournies sur le[Site Web Aspose.Tasks](https://purchase.aspose.com/buy).
### Q : Comment puis-je obtenir de l'aide ou de l'assistance concernant Aspose.Tasks pour Java ?
 R : Visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien et les discussions de la communauté.
### Q : Puis-je essayer Aspose.Tasks pour Java avant d'acheter ?
 R : Oui, vous pouvez accéder à une version d'essai gratuite[ici](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
