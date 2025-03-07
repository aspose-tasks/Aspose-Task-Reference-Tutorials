---
title: Récupérer les codes de plan MS Project dans Aspose.Tasks
linktitle: Récupérer les codes hiérarchiques dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment récupérer les codes hiérarchiques de Microsoft Project par programmation à l'aide d'Aspose.Tasks pour Java. Améliorez vos capacités de gestion de projet.
weight: 15
url: /fr/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Récupérer les codes de plan MS Project dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous apprendrons comment récupérer les codes hiérarchiques de Microsoft Project à l'aide d'Aspose.Tasks pour Java. Les codes hiérarchiques dans MS Project fournissent un moyen structuré de catégoriser et d'organiser les tâches, les ressources et les affectations du projet. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de manipuler et de gérer les fichiers Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir configuré les conditions préalables suivantes :
### 1. Environnement de développement Java
Assurez-vous que le kit de développement Java (JDK) est installé sur votre système. Vous pouvez télécharger et installer JDK à partir du site Web d'Oracle.
### 2. Bibliothèque Aspose.Tasks
 Téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet Java. Vous pouvez télécharger la bibliothèque à partir du[Aspose.Tasks pour la page de téléchargement Java](https://releases.aspose.com/tasks/java/).
## Importer des packages
Tout d’abord, importez les packages nécessaires depuis Aspose.Tasks dans votre code Java :
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Décomposons maintenant l'exemple de code fourni en plusieurs étapes :
## Étape 1 : Charger le projet
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Dans cette étape, nous chargeons le fichier Microsoft Project dans un`Project` objet en utilisant le nom de fichier fourni.
## Étape 2 : Récupérer les codes hiérarchiques
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Nous parcourons chaque définition de code hiérarchique du projet.
## Étape 3 : accéder aux propriétés du code hiérarchique
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Nous récupérons et imprimons diverses propriétés de la définition du code hiérarchique telles que l'alias, l'ID de champ et le nom du champ.
## Étape 4 : Vérifiez le code personnalisé de l'entreprise
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Nous vérifions si le code hiérarchique est un code personnalisé d'entreprise et imprimons le résultat en conséquence.
## Étape 5 : Afficher les masques de code hiérarchique
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Nous parcourons chaque masque associé au code hiérarchique et imprimons son niveau et sa valeur de masque.
## Étape 6 : Afficher les valeurs du code hiérarchique
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Nous parcourons chaque valeur de code hiérarchique et imprimons sa description, son ID de valeur, sa valeur et son type.
## Conclusion
Dans ce didacticiel, nous avons appris à récupérer les codes hiérarchiques MS Project à l'aide d'Aspose.Tasks pour Java. En suivant les étapes fournies, vous pouvez accéder et manipuler efficacement les codes hiérarchiques dans vos applications Java, permettant ainsi des fonctionnalités avancées de gestion de projet.
## FAQ
### Q1 : Puis-je utiliser Aspose.Tasks pour Java pour modifier les codes hiérarchiques dans un fichier projet ?
R : Oui, Aspose.Tasks for Java fournit des API pour modifier les codes hiérarchiques dans les fichiers MS Project par programme.
### Q2 : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks pour Java à partir du[Site Web Aspose.Tasks](https://releases.aspose.com/).
### Q3 : Comment puis-je obtenir une assistance technique pour Aspose.Tasks pour Java ?
 R : Vous pouvez obtenir une assistance technique en visitant le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) et en y postant vos requêtes.
### Q4 : Puis-je acheter une licence temporaire pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez acheter une licence temporaire pour Aspose.Tasks for Java auprès du[page d'achat](https://purchase.aspose.com/temporary-license/).
### Q5 : Où puis-je trouver la documentation complète d'Aspose.Tasks pour Java ?
 R : Vous pouvez vous référer au[Documentation](https://reference.aspose.com/tasks/java/) pour des informations détaillées sur l’utilisation d’Aspose.Tasks pour Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
