---
title: Lire les propriétés de devise dans les projets Aspose.Tasks
linktitle: Lire les propriétés de devise dans les projets Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment extraire des informations monétaires à partir de fichiers MS Project à l'aide d'Aspose.Tasks pour Java. Guide étape par étape fourni.
type: docs
weight: 10
url: /fr/java/currency-properties/read-properties/
---
## Introduction
Dans ce didacticiel, nous apprendrons comment utiliser Aspose.Tasks pour Java pour lire les propriétés monétaires à partir des fichiers Microsoft Project. Aspose.Tasks est une API Java puissante qui permet aux développeurs de manipuler des documents Microsoft Project sans nécessiter l'installation de Microsoft Project. En suivant les étapes décrites ci-dessous, vous pourrez extraire facilement des informations relatives aux devises.
## Conditions préalables
Avant de poursuivre ce didacticiel, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Tasks for Java JAR : téléchargez la bibliothèque Aspose.Tasks for Java à partir de[ici](https://releases.aspose.com/tasks/java/) et incluez-le dans votre projet Java.
## Importer des packages
Commencez par importer les packages nécessaires dans votre classe Java :
```java
import com.aspose.tasks.*;
```
## Étape 1 : Configurez votre répertoire de projets
Tout d’abord, configurez le répertoire de votre projet où se trouve votre fichier Microsoft Project. Vous pouvez définir ce chemin de répertoire comme suit :
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin réel vers le répertoire de votre projet.
## Étape 2 : Créer une instance de lecteur de projet
 Instancier un`Project` objet en fournissant le chemin d'accès à votre fichier Microsoft Project :
```java
Project project = new Project(dataDir + "project.mpp");
```
 Assurez-vous de remplacer`"project.mpp"` avec le nom de votre fichier MS Project.
## Étape 3 : Afficher les propriétés de la devise
Récupérez et affichez les propriétés de la devise à partir du fichier projet :
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Ce segment de code récupère des informations telles que le code de devise, les chiffres, le symbole et la position du symbole à partir du fichier MS Project et les imprime sur la console.
## Étape 4 : Achèvement du processus
Enfin, imprimez un message indiquant la réussite du processus :
```java
System.out.println("Process completed Successfully");
```
## Conclusion
Dans ce didacticiel, nous avons expliqué comment lire les propriétés monétaires des fichiers Microsoft Project à l'aide d'Aspose.Tasks pour Java. En suivant les étapes décrites, vous pouvez facilement extraire par programme les informations relatives aux devises de vos fichiers de projet, permettant une intégration transparente dans vos applications Java.
## FAQ
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?
R : Aspose.Tasks prend en charge différentes versions de Microsoft Project, y compris les fichiers MPP générés par MS Project 2003-2021.
### Q : Puis-je modifier les propriétés de la devise à l'aide d'Aspose.Tasks ?
R : Oui, Aspose.Tasks vous permet à la fois de lire et de modifier les propriétés monétaires dans les fichiers MS Project par programme.
### Q : Aspose.Tasks est-il adapté à un usage commercial ?
 R : Oui, Aspose.Tasks est une bibliothèque commerciale conçue pour un usage professionnel. Vous pouvez acheter une licence[ici](https://purchase.aspose.com/buy).
### Q : Aspose.Tasks propose-t-il un essai gratuit ?
 R : Oui, vous pouvez bénéficier d’un essai gratuit d’Aspose.Tasks depuis[ici](https://releases.aspose.com/).
### Q : Où puis-je demander de l'aide ou du support pour Aspose.Tasks ?
 R : Vous pouvez visiter le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15) pour toute aide ou question.