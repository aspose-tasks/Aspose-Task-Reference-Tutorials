---
date: 2026-03-27
description: Apprenez à récupérer les codes de plan d’ensemble de MS Project de manière
  programmatique en utilisant Aspose.Tasks pour Java. Améliorez vos compétences en
  gestion de projet.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Récupérer les codes de plan d’ensemble de MS Project dans Aspose.Tasks
url: /fr/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Récupérer les codes d'outline MS Project avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez **comment récupérer les codes d'outline MS Project** à l'aide d'Aspose.Tasks pour Java. Les codes d'outline dans MS Project offrent un moyen puissant de catégoriser les tâches, les ressources et les affectations, et y accéder programmaticalement vous permet de créer des rapports personnalisés, de l'automatisation ou des solutions d'intégration. Nous parcourrons un exemple complet, étape par étape, que vous pourrez copier dans votre propre projet.

## Réponses rapides
- **Que fait le code ?** Il charge un fichier Project et affiche chaque définition de code d'outline, ses masques et ses valeurs.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (toute version récente).  
- **Ai‑je besoin d'une licence ?** Une version d'essai fonctionne pour le développement ; une licence complète est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure.  
- **Puis‑je modifier les codes après les avoir récupérés ?** Oui – la même API vous permet d'ajouter, de modifier ou de supprimer des codes d'outline.

## Qu'est-ce que les codes d'outline MS Project ?
Les codes d'outline sont des champs personnalisés qui permettent aux chefs de projet de regrouper et filtrer les tâches au‑delà de la hiérarchie par défaut. Ils peuvent être de simples valeurs numériques, des chaînes de caractères, ou même des codes personnalisés à l'échelle de l'entreprise définis au niveau de l'organisation. En lisant ces codes, vous pouvez alimenter des tableaux de bord, exporter des données ou appliquer automatiquement des conventions de nommage.

## Pourquoi récupérer les codes d'outline MS Project avec Aspose.Tasks ?
- **Automatisation :** Générer des rapports ou déclencher des flux de travail sans exportation manuelle.  
- **Intégration :** Synchroniser les codes d'outline avec les ERP, PPM ou outils BI.  
- **Personnalisation :** Appliquer des règles métier basées sur les valeurs des codes (p. ex., allocation des coûts).  
- **Cross‑platform :** Fonctionne sous Windows, Linux et macOS, indépendamment de l'interface Microsoft Project.

## Comment lire les fichiers MPP pour les codes d'outline ?
Lire un fichier MPP (Microsoft Project) est la première étape pour extraire les codes d'outline. Aspose.Tasks abstrait le format de fichier, vous n’avez donc pas besoin d’analyser vous‑même la structure binaire. La classe `Project` gère le travail lourd, vous permettant de vous concentrer sur les données dont vous avez réellement besoin.

## Champs personnalisés dans MS Project
Les codes d'outline sont un type de **champs personnalisés** dans MS Project. Alors que les champs standard couvrent les dates, les durées et les ressources, les champs personnalisés vous permettent de stocker des informations spécifiques à l'organisation. Les accéder via Aspose.Tasks vous offre la même flexibilité programmatiquement.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les prérequis suivants configurés :

### 1. Environnement de développement Java
Assurez‑vous d'avoir le Java Development Kit (JDK) installé sur votre système. Vous pouvez télécharger et installer le JDK depuis le site d'Oracle.

### 2. Bibliothèque Aspose.Tasks
Téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet Java. Vous pouvez télécharger la bibliothèque depuis la [Page de téléchargement d'Aspose.Tasks pour Java](https://releases.aspose.com/tasks/java/).

## Importer les packages
Tout d'abord, importez les packages nécessaires d'Aspose.Tasks dans votre code Java :
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Now let's break down the provided example code into multiple steps:
Maintenant, décomposons le code d'exemple fourni en plusieurs étapes :

## Étape 1 : Charger le projet
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Dans cette étape, nous chargeons le fichier Microsoft Project dans un objet `Project` en utilisant le nom de fichier fourni.

## Étape 2 : Récupérer les codes d'outline
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Nous parcourons chaque définition de code d'outline dans le projet.

## Étape 3 : Accéder aux propriétés du code d'outline
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Nous récupérons et affichons diverses propriétés de la définition du code d'outline telles que Alias, Field ID et Field Name.

## Étape 4 : Vérifier le code personnalisé d'entreprise
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Nous vérifions si le code d'outline est un code personnalisé d'entreprise et affichons le résultat en conséquence.

## Étape 5 : Afficher les masques du code d'outline
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Nous parcourons chaque masque associé au code d'outline et affichons son niveau ainsi que la valeur du masque.

## Étape 6 : Afficher les valeurs du code d'outline
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Nous parcourons chaque valeur de code d'outline et affichons sa description, son ID de valeur, sa valeur et son type.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Pas de sortie** | Chemin du fichier projet incorrect | Vérifiez que `projectName` pointe vers un fichier `.mpp` valide. |
| **Valeurs nulles** | Code d'outline non défini dans le fichier | Assurez‑vous que le fichier Project contient réellement des codes d'outline (vérifiez dans l'interface MS Project). |
| **LicenseException** | Utilisation d'une version d'essai sans activation correcte | Appliquez une licence temporaire ou complète via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## FAQ
**Q : Puis‑je utiliser Aspose.Tasks pour Java afin de modifier les codes d'outline dans un fichier Project ?**  
R : Oui, Aspose.Tasks pour Java fournit des API permettant de modifier les codes d'outline programmatiquement. Vous pouvez ajouter, modifier ou supprimer des définitions en utilisant le même objet `Project`.

**Q : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks pour Java depuis le [site Web d'Aspose.Tasks](https://releases.aspose.com/).

**Q : Comment obtenir le support technique pour Aspose.Tasks pour Java ?**  
R : Vous pouvez obtenir le support technique en visitant le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) et en y postant vos questions.

**Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez acheter une licence temporaire pour Aspose.Tasks pour Java depuis la [page d'achat](https://purchase.aspose.com/temporary-license/).

**Q : Où trouver la documentation complète d'Aspose.Tasks pour Java ?**  
R : Vous pouvez consulter la [documentation](https://reference.aspose.com/tasks/java/) pour des informations détaillées sur l'utilisation d'Aspose.Tasks pour Java.

## Conclusion
Dans ce tutoriel, nous avons appris comment récupérer les **codes d'outline MS Project** à l'aide d'Aspose.Tasks pour Java. En suivant les étapes fournies, vous pouvez accéder et manipuler efficacement les codes d'outline dans vos applications Java, permettant des capacités avancées de gestion de projet telles que des rapports personnalisés, l'automatisation et l'intégration avec d'autres systèmes d'entreprise.

---

**Dernière mise à jour :** 2026-03-27  
**Testé avec :** Aspose.Tasks pour Java (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}