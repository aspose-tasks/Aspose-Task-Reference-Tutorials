---
date: 2026-01-10
description: Apprenez comment arrêter l’affectation, gérer les affectations de ressources
  et consulter un exemple d’affectation de ressources dans Aspose.Tasks for Java grâce
  à ce tutoriel étape par étape.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment arrêter l'affectation et reprendre les affectations de ressources dans
  Aspose.Tasks
url: /fr/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment arrêter une affectation et reprendre les affectations de ressources dans Aspose.Tasks

## Introduction
Dans ce tutoriel, **vous découvrirez comment arrêter une affectation** puis la reprendre ultérieurement à l’aide d’Aspose.Tasks pour Java. Aspose.Tasks est une puissante API Java qui vous permet de lire les formats de fichiers de projet Java, de manipuler les données Microsoft Project et de gérer les affectations de ressources sans avoir Microsoft Project installé. Nous parcourrons chaque étape, expliquerons pourquoi chaque ligne est importante et vous donnerons des conseils pratiques que vous pourrez appliquer à des projets réels.

## Réponses rapides
- **Que signifie « arrêter une affectation » ?** Cela marque une affectation de ressource comme temporairement inactive à partir d’une date d’arrêt spécifique.  
- **Puis‑je reprendre la même affectation plus tard ?** Oui, en définissant une date de reprise sur la même affectation.  
- **Ai‑je besoin de Microsoft Project pour utiliser cette API ?** Non, Aspose.Tasks fonctionne indépendamment de Microsoft Project.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur est recommandé.  
- **Où puis‑je télécharger la bibliothèque ?** Depuis la page officielle de téléchargement d’Aspose.Tasks Java.

## Qu’est‑ce que « arrêter une affectation » dans le contexte d’Aspose.Tasks ?
Arrêter une affectation indique au planificateur d’ignorer le travail attribué à une ressource après la **date d’arrêt** jusqu’à la **date de reprise** (le cas échéant). Cela est utile pour gérer les vacances, les pannes d’équipement ou toute période pendant laquelle une ressource ne doit pas être considérée comme active.

## Pourquoi utiliser Aspose.Tasks pour gérer les affectations de ressources ?
- **Pas besoin de Microsoft Project** – travaillez directement avec les fichiers .mpp.  
- **Contrôle total sur les dates** – vous pouvez vérifier et ajuster programmétiquement la date d’arrêt, la date de reprise, etc.  
- **Cross‑platform** – fonctionne sur tout OS supportant Java.  
- **API riche** – fournit un *exemple d’affectation de ressource* que vous pouvez étendre pour des rapports personnalisés.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Le Java Development Kit (JDK) installé sur votre système.  
- La bibliothèque Aspose.Tasks pour Java téléchargée. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/java/).  
- Une compréhension de base de la programmation Java.  

## Importer les packages
Tout d’abord, importons les packages nécessaires dans notre projet Java :

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Étape 1 : Charger le fichier de projet
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Ici, nous **lisons le fichier de projet Java** au format (`.mpp`) et créons un objet `Project` qui nous donne accès à toutes les données du projet, y compris les affectations de ressources.

## Étape 2 : Parcourir les affectations de ressources
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Nous définissons une **date minimale** pour filtrer les dates factices, puis nous parcourons chaque affectation. C’est le schéma typique d’un *exemple d’affectation de ressource* utilisé lorsque vous devez inspecter ou modifier des affectations.

## Étape 3 : Vérifier les dates d’arrêt et de reprise
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

Dans ce bloc, nous **vérifions la date d’arrêt** et **la date de reprise** pour chaque affectation. Si la date est antérieure à notre `minDate`, nous la considérons comme non définie (`"NA"`); sinon nous affichons la date réelle. Cette logique est essentielle pour **gérer correctement les affectations de ressources**.

## Problèmes courants et solutions
- **Dates nulles** – `ra.get(Asn.STOP)` peut renvoyer `null`. Protégez‑vous en ajoutant une vérification de null avant d’appeler `.before(minDate)`.  
- **Chemin de fichier incorrect** – Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) adapté à votre OS.  
- **Incompatibilité de version** – Utilisez la dernière version d’Aspose.Tasks pour Java afin d’éviter les valeurs d’énumération manquantes.

## FAQ
### Puis‑je utiliser Aspose.Tasks sans Microsoft Project installé ?
Oui, Aspose.Tasks vous permet de travailler avec les fichiers Microsoft Project sans avoir besoin de Microsoft Project installé sur votre système.

### Où puis‑je trouver plus de documentation ?
Vous pouvez trouver une documentation détaillée [ici](https://reference.aspose.com/tasks/java/).

### Existe‑t‑il un essai gratuit ?
Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

### Comment obtenir du support en cas de problème ?
Vous pouvez obtenir du support de la communauté [ici](https://forum.aspose.com/c/tasks/15).

### Puis‑je acheter une licence temporaire ?
Oui, vous pouvez acheter une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## Questions fréquentes

**Q : Comment définir programmétiquement une date d’arrêt pour une affectation ?**  
R : Utilisez `ra.set(Asn.STOP, votreObjetDate);` où `votreObjetDate` est un `java.util.Date`.

**Q : Que se passe‑t‑il si la date de reprise est antérieure à la date d’arrêt ?**  
R : L’API n’impose pas d’ordre chronologique ; cependant, le planificateur considérera l’affectation comme active uniquement après la date la plus tardive des deux, il vous revient donc de valider les dates vous‑même.

**Q : Puis‑je filtrer les affectations pour ne retenir que celles qui ont une date d’arrêt définie ?**  
R : Oui, parcourez `prj.getResourceAssignments()` et vérifiez `ra.get(Asn.STOP) != null`.

**Q : Est‑il possible de supprimer une date d’arrêt une fois définie ?**  
R : Définissez la date d’arrêt à `null` avec `ra.set(Asn.STOP, null);` puis enregistrez le projet.

**Q : Aspose.Tasks prend‑il en charge d’autres champs liés aux dates comme start, finish ou actual start ?**  
R : Absolument. L’énumération `Asn` fournit des constantes pour tous les champs d’affectation, tels que `Asn.START`, `Asn.FINISH`, etc.

## Conclusion
En suivant ces étapes, vous savez maintenant **comment arrêter une affectation**, inspecter les dates d’arrêt/reprise et reprendre l’affectation lorsque nécessaire. Cette capacité vous permet de **gérer les affectations de ressources** avec plus de précision, notamment dans des scénarios comme les vacances de ressources ou les pannes d’équipement. N’hésitez pas à étendre l’exemple pour mettre à jour les dates, générer des rapports ou l’intégrer à votre propre logique de planification.

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.Tasks pour Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}