---
title: Configurer la vue Diagramme de Gantt dans les projets Aspose.Tasks
linktitle: Configurer la vue Diagramme de Gantt dans les projets Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment configurer la vue Diagramme de Gantt MS Project dans Aspose.Tasks à l'aide de Java. Personnalisez le projet et visualisez-le dans le diagramme de Gantt étape par étape.
weight: 10
url: /fr/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurer la vue Diagramme de Gantt dans les projets Aspose.Tasks

## Introduction
Dans ce didacticiel, vous apprendrez à configurer la vue Diagramme de Gantt MS Project dans les projets Aspose.Tasks à l'aide de Java. Aspose.Tasks est une puissante API Java qui vous permet de travailler avec des fichiers Microsoft Project par programme. En suivant ces étapes, vous pourrez personnaliser la vue du diagramme de Gantt en fonction des exigences de votre projet.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :
1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système.
2.  Bibliothèque Aspose.Tasks : téléchargez et installez la bibliothèque Aspose.Tasks. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
3. Environnement de développement intégré (IDE) : choisissez un IDE de votre choix. Ce didacticiel utilise IntelliJ IDEA, mais vous pouvez utiliser n'importe quel IDE avec lequel vous êtes à l'aise.
## Importer des packages
Tout d’abord, vous devez importer les packages nécessaires pour travailler avec Aspose.Tasks dans votre projet Java. Ajoutez les instructions d'importation suivantes à votre fichier Java :
```java
import com.aspose.tasks.*;
```
Maintenant, décomposons le processus de configuration de la vue du diagramme de projet Gantt MS en instructions étape par étape :
## Étape 1 : configurer le répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin d'accès au répertoire de données de votre projet.
## Étape 2 : Charger le fichier de projet
```java
Project project = new Project(dataDir + "project.mpp");
```
Chargez votre fichier de projet (`project.mpp` dans cet exemple) en utilisant le`Project` classe d’Aspose.Tasks.
## Étape 3 : Ajouter une nouvelle activité
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Créez une nouvelle tâche dans votre projet à l'aide du`Task` classe et ajoutez-le aux enfants de la tâche racine.
## Étape 4 : Définir un attribut personnalisé
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Définissez un nouvel attribut personnalisé à l'aide de l'outil`ExtendedAttributeDefinition`classe et ajoutez-la aux attributs étendus du projet.
## Étape 5 : ajouter un attribut personnalisé à la tâche
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Ajoutez l'attribut personnalisé à la tâche créée à l'aide du`createExtendedAttribute` méthode.
## Étape 6 : Personnaliser le tableau
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
Personnalisez le tableau en ajoutant le champ d'attribut de texte avec la largeur, le titre et l'alignement spécifiés.
## Étape 7 : Enregistrer le projet
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Enregistrez le projet avec la vue de diagramme de projet Gantt MS configurée. Le fichier résultant peut être ouvert dans Microsoft Project 2010.
## Conclusion
Toutes nos félicitations! Vous avez configuré avec succès la vue Diagramme de Gantt MS Project dans les projets Aspose.Tasks à l'aide de Java. Vous pouvez désormais personnaliser les attributs du projet et les visualiser dans le diagramme de Gantt en fonction des besoins de votre projet.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres langages de programmation ?
R : Oui, Aspose.Tasks est disponible pour plusieurs langages de programmation, notamment .NET, Java et C.++.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de l'aide pour Aspose.Tasks ?
R : Vous pouvez trouver de l'aide et poser des questions sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Q : Comment puis-je acheter une licence pour Aspose.Tasks ?
 R : Vous pouvez acheter une licence auprès de[ici](https://purchase.aspose.com/buy).
### Q : Ai-je besoin d’une licence temporaire à des fins de test ?
 R : Oui, vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
