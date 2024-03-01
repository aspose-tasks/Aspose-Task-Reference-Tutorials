---
title: Formules MS Project avec Aspose.Tasks pour Java
linktitle: Travailler avec des formules dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à manipuler les fichiers MS Project en Java à l'aide de la bibliothèque Aspose.Tasks. Créez, modifiez et calculez facilement des attributs.
type: docs
weight: 11
url: /fr/java/formulas/work-with-formulas/
---
## Introduction
Dans ce didacticiel, nous aborderons l'utilisation des formules MS Project à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une bibliothèque puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme. Grâce à ses fonctionnalités étendues, vous pouvez facilement créer, lire, modifier et convertir des fichiers de projet dans des applications Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir configuré les conditions préalables suivantes :
### Environnement de développement Java
Assurez-vous qu'un kit de développement Java (JDK) est installé sur votre système. Vous pouvez télécharger et installer le dernier JDK à partir du site Web d'Oracle.
### Bibliothèque Aspose.Tasks
Vous devez ajouter la bibliothèque Aspose.Tasks à votre projet Java. Vous pouvez télécharger la bibliothèque à partir du[Page de téléchargement d'Aspose.Tasks pour Java](https://releases.aspose.com/tasks/java/) et incluez-le dans les dépendances de votre projet.

## Importer des packages
Avant de plonger dans les exemples, importez les packages nécessaires dans votre code Java :
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : Créer un projet de test avec un champ personnalisé
```java
Project project = CreateTestProjectWithCustomField();
```
 Tout d'abord, créez un projet de test avec un champ personnalisé à l'aide du`CreateTestProjectWithCustomField()` méthode. Cette méthode renverra un objet Project représentant le projet nouvellement créé.
## Étape 2 : Définir une définition d'attribut étendue
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Récupérez la définition d'attribut étendu du projet et définissez son alias et sa formule. Dans cet exemple, nous définissons un attribut pour calculer le nombre de jours entre la date de fin et la date limite.
## Étape 3 : Définir la date limite pour une tâche
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Créez un objet Calendrier et définissez la date limite. Ensuite, récupérez une tâche du projet et fixez sa date limite à l'aide de l'objet Calendrier.
## Étape 4 : Enregistrez le projet
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Enfin, enregistrez le projet dans un fichier avec le nom et le format spécifiés. Dans ce cas, nous l'enregistrons en tant que fichier MPP.

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser les formules MS Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez manipuler efficacement les fichiers de projet par programme, en ajoutant des champs personnalisés et en calculant des attributs basés sur des formules.

## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres langages de programmation ?
R : Oui, Aspose.Tasks prend en charge divers langages de programmation, notamment Java, .NET, etc.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez télécharger un essai gratuit d'Aspose.Tasks à partir de[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de la documentation pour Aspose.Tasks ?
 R : Vous pouvez trouver la documentation pour Aspose.Tasks[ici](https://reference.aspose.com/tasks/java/).
### Q : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?
 R : Pour obtenir de l'aide, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Q : Ai-je besoin d’une licence temporaire pour utiliser Aspose.Tasks ?
R : Si vous avez besoin de fonctionnalités supplémentaires, vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).