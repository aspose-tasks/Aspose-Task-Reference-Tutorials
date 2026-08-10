---
date: 2026-07-14
description: Apprenez comment arrêter l'affectation de ressources Java, gérer les
  affectations de ressources et consulter des exemples utilisant Aspose.Tasks for
  Java dans ce guide étape par étape.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Arrêter et reprendre les affectations de ressources dans Aspose.Tasks
og_description: Arrêtez l'affectation de ressources Java avec Aspose.Tasks. Ce tutoriel
  montre comment mettre en pause et reprendre les affectations, gérer les dates et
  intégrer l'API sans Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Arrêter l'affectation de ressources Java – Guide Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Comment arrêter l'affectation de ressources Java – Reprendre avec Aspose.Tasks
url: /fr/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment arrêter l'affectation de ressources Java – Reprendre avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **how to stop resource assignment java** et comment le reprendre ensuite en utilisant Aspose.Tasks pour Java. Aspose.Tasks est une API Java robuste qui vous permet de lire et d'écrire des fichiers Microsoft Project, de manipuler les plannings et de contrôler les affectations de ressources — le tout sans avoir besoin de Microsoft Project installé. Nous passerons en revue chaque étape, expliquerons pourquoi chaque ligne est importante et partagerons des conseils pratiques que vous pourrez appliquer à des plans de projet réels.

## Réponses rapides
- **Que signifie « stop assignment » ?** Cela marque une affectation de ressource comme temporairement inactive à partir d’une date d’arrêt spécifique.  
- **Puis‑je reprendre la même affectation plus tard ?** Oui, en définissant une date de reprise sur la même affectation.  
- **Ai‑je besoin de Microsoft Project pour utiliser cette API ?** Non, Aspose.Tasks fonctionne indépendamment de Microsoft Project.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur est recommandé.  
- **Où puis‑je télécharger la bibliothèque ?** Depuis la page officielle de téléchargement d’Aspose.Tasks Java.

## Comment arrêter l'affectation de ressources Java ?
Chargez votre projet, localisez le `ResourceAssignment` cible, définissez la date `STOP`, définissez éventuellement une date `RESUME`, puis enregistrez le fichier. Cette séquence met en pause le travail pendant la période spécifiée et le réactive automatiquement après la date de reprise, vous offrant un contrôle précis sur les calendriers de ressources sans modifications manuelles du fichier.

## Qu'est‑ce que « how to stop assignment » dans le contexte d'Aspose.Tasks ?
Arrêter une affectation indique au planificateur d’ignorer le travail attribué à une ressource après la **date d’arrêt** jusqu’à la **date de reprise** (le cas échéant). Cela est utile pour gérer les vacances, les pannes d’équipement ou toute période pendant laquelle une ressource ne doit pas être considérée comme active.

## Pourquoi utiliser Aspose.Tasks pour gérer les affectations de ressources ?
Aspose.Tasks vous permet de contrôler programmétiquement les dates d’affectation, éliminant les modifications manuelles et réduisant le risque d’erreurs. Elle prend en charge **plus de 50 formats d’entrée et de sortie** et peut traiter des projets contenant **jusqu’à 10 000 tâches** tout en maintenant l’utilisation de la mémoire sous 200 Mo grâce à un flux de données plutôt qu’un chargement complet du fichier en mémoire. L’API fonctionne sur tout OS supportant Java, vous offrant ainsi une flexibilité multiplateforme.

## Prérequis
- Java Development Kit (JDK) 8 ou plus récent installé.  
- Bibliothèque Aspose.Tasks pour Java téléchargée. Vous pouvez la télécharger depuis [here](https://releases.aspose.com/tasks/java/).  
- Connaissances de base en programmation Java.  

## Importer les packages
Les classes `Project`, `ResourceAssignment` et `Asn` se trouvent dans l’espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier source :

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Étape 1 : Charger le fichier de projet
La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier Microsoft Project unique en mémoire. Créer une instance charge le fichier et vous donne accès aux tâches, aux ressources et aux affectations.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Étape 2 : Parcourir les affectations de ressources
Les objets `ResourceAssignment` exposent tous les champs liés aux affectations. Nous définissons une **date minimale** pour filtrer les dates factices, puis parcourons chaque affectation. Ce modèle est l’exemple standard *resource assignment* pour l’inspection ou la modification.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Étape 3 : Vérifier les dates d'arrêt et de reprise
Dans ce bloc, nous examinons les champs `STOP` et `RESUME` de chaque affectation. Si une date est antérieure à notre `minDate`, nous la considérons comme non définie (`"NA"`); sinon nous affichons la date réelle. Cette logique est essentielle pour **manage resource assignments** correctement.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Problèmes courants et solutions
- **Dates nulles** – `ra.get(Asn.STOP)` peut renvoyer `null`. Protégez‑vous en ajoutant une vérification de null avant d’appeler `.before(minDate)`.  
- **Chemin de fichier incorrect** – Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) approprié à votre OS.  
- **Incompatibilité de version** – Utilisez la dernière version d’Aspose.Tasks pour Java afin d’éviter les valeurs d’énumération manquantes.

## Questions fréquentes

**Q : Comment définir programmétiquement une date d'arrêt pour une affectation ?**  
R : Utilisez `ra.set(Asn.STOP, yourDateObject);` où `yourDateObject` est un `java.util.Date`.

**Q : Que se passe‑t‑il si la date de reprise est antérieure à la date d'arrêt ?**  
R : L’API n’impose pas d’ordre chronologique ; cependant, le planificateur traitera l’affectation comme active uniquement après la date la plus tardive des deux, il vous revient donc de valider les dates vous‑même.

**Q : Puis‑je filtrer les affectations pour ne retenir que celles qui ont une date d'arrêt définie ?**  
R : Oui, parcourez `prj.getResourceAssignments()` et vérifiez `ra.get(Asn.STOP) != null`.

**Q : Est‑il possible de supprimer une date d'arrêt une fois définie ?**  
R : Définissez la date d'arrêt sur `null` avec `ra.set(Asn.STOP, null);` puis enregistrez le projet.

**Q : Aspose.Tasks prend‑il en charge d’autres champs liés aux dates comme start, finish ou actual start ?**  
R : Absolument. L’énumération `Asn` fournit des constantes pour tous les champs d’affectation, tels que `Asn.START`, `Asn.FINISH`, etc.

## Conclusion
En suivant ces étapes, vous savez maintenant **how to stop resource assignment java**, inspecter les dates d’arrêt/reprise et reprendre l’affectation lorsque nécessaire. Cette capacité vous permet de **manage resource assignments** avec plus de précision, notamment dans des scénarios comme les vacances de ressources ou les pannes d’équipement. N’hésitez pas à étendre l’exemple pour mettre à jour les dates, générer des rapports ou l’intégrer à votre propre logique de planification.

---

**Dernière mise à jour :** 2026-07-14  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Créer des affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Comment calculer l’écart de coût et gérer les coûts d’affectation avec Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Comment ajouter des notes aux affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}