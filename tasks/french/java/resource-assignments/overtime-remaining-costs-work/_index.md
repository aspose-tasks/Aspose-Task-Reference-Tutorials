---
title: Surveillez les heures supplémentaires, les coûts restants et le travail dans Aspose.Tasks
linktitle: Surveillez les heures supplémentaires, les coûts restants et le travail dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment surveiller les heures supplémentaires, les coûts restants et travailler sur des projets Java à l'aide d'Aspose.Tasks. Étapes simples pour une gestion de projet efficace.
weight: 18
url: /fr/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Surveillez les heures supplémentaires, les coûts restants et le travail dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous allons apprendre à utiliser Aspose.Tasks pour Java pour surveiller les heures supplémentaires, les coûts restants et travailler sur un projet. Cela peut être inestimable pour les chefs de projet et les chefs d’équipe afin de garantir que les projets restent sur la bonne voie et dans les limites du budget.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : Aspose.Tasks pour Java nécessite Java SE 6 ou version ultérieure.
2.  Aspose.Tasks for Java Library : téléchargez et installez la bibliothèque à partir de[ici](https://releases.aspose.com/tasks/java/).
3. Environnement de développement intégré (IDE) : tout IDE Java tel qu'Eclipse, IntelliJ IDEA ou NetBeans.

## Importer des packages
Commencez par importer les packages nécessaires dans votre fichier Java :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Étape 1 : configurer le répertoire de données
Définissez le répertoire où se trouve votre fichier projet :
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin d'accès à votre fichier de projet.
## Étape 2 : Charger le projet
 Instancier un`Project` objet et chargez le fichier projet :
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Remplacer`"ResourceAssignmentOvertimes.mpp"` avec le nom de votre fichier projet.
## Étape 3 : Parcourir les affectations de ressources
Parcourez chaque affectation de ressource dans le projet :
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Étape 4 : Imprimer les coûts et le travail des heures supplémentaires
Récupérez et imprimez les coûts des heures supplémentaires et le travail pour chaque affectation de ressource :
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Étape 5 : Imprimer les coûts et le travail restants
Récupérez et imprimez les coûts et le travail restants pour chaque affectation de ressource :
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Étape 6 : Imprimer les coûts et le travail des heures supplémentaires restants
Récupérez et imprimez les coûts des heures supplémentaires et le travail restants pour chaque affectation de ressource :
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Conclusion
Le suivi des heures supplémentaires, des coûts restants et du travail dans un projet est crucial pour une gestion de projet réussie. Avec Aspose.Tasks pour Java, vous pouvez facilement accéder et suivre ces informations, garantissant ainsi que vos projets respectent le calendrier et le budget.
## FAQ
### Puis-je utiliser Aspose.Tasks pour Java avec d’autres bibliothèques Java ?
Oui, Aspose.Tasks for Java est compatible avec d'autres bibliothèques et frameworks Java.
### Aspose.Tasks prend-il en charge différents formats de fichiers de projet ?
Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet, notamment MPP, XML, etc.
### Existe-t-il une version d'essai disponible ?
 Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
### Où puis-je trouver de l'aide si je rencontre des problèmes ?
 Vous pouvez visiter le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15) pour le soutien.
### Comment puis-je acheter une licence pour Aspose.Tasks ?
 Vous pouvez acheter une licence auprès de[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
