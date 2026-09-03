---
date: 2026-06-05
description: Apprenez comment créer une Resource Assignment avec Aspose.Tasks pour
  Java, ajouter des ressources à un projet et gérer les propriétés de Leveling Delay.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Gérer les propriétés de Leveling Delay pour les Resource Assignments dans
  Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Créer une Resource Assignment avec Aspose.Tasks pour Java
url: /fr/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une affectation de ressources avec Aspose.Tasks pour Java

Dans ce guide complet, vous apprendrez **comment créer une affectation de ressources aspotasks** en utilisant la bibliothèque Aspose.Tasks pour Java. Que vous construisiez un moteur de planification personnalisé, automatisiez des mises à jour massives de projets, ou ayez simplement besoin de manipuler des fichiers Microsoft Project sans l'application de bureau, maîtriser ces étapes vous permet de garder vos données de projet précises et entièrement contrôlables.

## Réponses rapides
- **Que signifie “add resource to project” ?** Il crée une nouvelle entrée de ressource qui pourra ensuite être affectée aux tâches.  
- **Puis-je définir un délai de nivellement après l'affectation ?** Oui, en utilisant les champs `Asn.DELAY` ou `Asn.LEVELING_DELAY`.  
- **Ai-je besoin d'une licence pour exécuter ce code ?** Un essai gratuit fonctionne pour le développement ; une licence payante est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure.  
- **Cette solution est‑elle compatible avec tous les formats de fichiers MS Project ?** Aspose.Tasks prend en charge plus de 12 formats — y compris .MPP, .XML, .XER, .CSV, .PDF, et plus.

## Qu’est‑ce que “add resource to project” dans Aspose.Tasks ?
Ajouter une ressource à un projet signifie créer un objet `Resource` à l'intérieur du modèle `Project`. Cet objet pourra ensuite être lié aux tâches via `ResourceAssignment`, vous permettant de suivre le travail, les coûts et les paramètres de nivellement. En insérant une ressource, vous fournissez au planificateur quelque chose à allouer, et vous pourrez ensuite interroger ou modifier ses propriétés telles que la disponibilité, les tarifs et les affectations de calendrier.

## Pourquoi gérer les propriétés de délai de nivellement ?
Le délai de nivellement indique au planificateur de reporter le début d’une affectation sur‑allouée, répartissant le travail plus uniformément sur la chronologie. En configurant ce délai, vous évitez des dates de début irréalistes, réduisez les avertissements de sur‑allocation et produisez un planning qui reflète les contraintes réelles des ressources. Ajuster le délai vous donne également un contrôle fin sur la marge que le moteur peut insérer, vous aidant à respecter les échéances du projet tout en respectant les limites des ressources.

## Comment créer une affectation de ressources aspotasks ?
Chargez votre objet `Project`, ajoutez une tâche, créez une ressource, puis liez‑les avec un `ResourceAssignment`. Ce flux de bout en bout vous permet de construire programmétiquement une structure de projet complète et de contrôler immédiatement le délai de nivellement sur l’affectation. Le processus démontre le flux de travail principal : initialisation du projet, définition de la tâche, création de la ressource, liaison de l’affectation, puis application des paramètres de planification tels que le délai de nivellement.

## Prérequis
1. Java Development Kit (JDK) : Assurez‑vous d'avoir le JDK Java installé sur votre système. Vous pouvez le télécharger et l'installer depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Bibliothèque Aspose.Tasks pour Java : Téléchargez la bibliothèque Aspose.Tasks pour Java depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).

## Importer les packages
Les importations suivantes apportent les classes principales d'Aspose.Tasks nécessaires à la manipulation de projets.  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Comment créer une affectation de ressources aspotasks ?
Chargez votre objet `Project`, ajoutez une tâche, créez une ressource, puis liez‑les avec un `ResourceAssignment`. Ce flux de bout en bout vous permet de construire programmétiquement une structure de projet complète et de contrôler immédiatement le délai de nivellement sur l’affectation. Le processus démontre le flux de travail principal : initialisation du projet, définition de la tâche, création de la ressource, liaison de l’affectation, puis application des paramètres de planification tels que le délai de nivellement.

## Étape 1 : Créer un objet Project
La classe `Project` est le conteneur de niveau supérieur d'Aspose.Tasks qui représente un fichier de projet complet en mémoire. L’instancier vous donne une base vierge pour ajouter des tâches, des ressources et des affectations.  
```java
Project prj = new Project();
```

## Étape 2 : Créer une tâche
La classe `Task` représente un élément de travail unique dans le planning. Ajouter une tâche démontre **comment ajouter une tâche** programmétiquement et fournit une cible pour l’affectation de ressource à venir.  
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Étape 3 : Définir la date de début et la durée de la tâche
Définissez quand la tâche commence et combien de temps elle durera. Des dates de début correctes sont essentielles car les calculs de nivellement les utilisent comme base pour tout délai que vous spécifierez ultérieurement.  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Étape 4 : Ajouter une ressource
Nous **add resource to project** maintenant en créant une nouvelle entrée `Resource`. La classe `Resource` représente une personne, un équipement ou un matériau qui peut être affecté aux tâches.  
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Étape 5 : Créer une affectation de ressource
`ResourceAssignment` lie une `Task` et une `Resource`. Cette association vous permet d’enregistrer le travail, le coût et les détails de nivellement pour une ressource spécifique sur une tâche spécifique.  
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Étape 6 : Définir le délai de nivellement
Configurez le délai de nivellement pour l’affectation. Le régler à zéro signifie aucun délai supplémentaire, mais vous pouvez ajuster la valeur selon vos besoins. Le champ `Asn.DELAY` contient le délai en minutes ; `Asn.LEVELING_DELAY` est un alias qui fonctionne de la même manière.  
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Étape 7 : Afficher les résultats
Imprimez les propriétés importantes pour vérifier que tout a été correctement défini. Cette étape vous aide à confirmer que les valeurs de ressource, de tâche et de délai sont exactement celles attendues avant d’enregistrer le fichier.  
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Pièges courants et astuces
- **Piège :** Oublier de définir la date de début de la tâche peut entraîner que l'affectation prenne par défaut la date de début du projet.  
- **Astuce :** Utilisez `prj.getDuration(value, TimeUnitType.Day)` pour contrôler la granularité du délai.  
- **Astuce :** Après avoir ajouté plusieurs ressources, appelez `prj.updateResourceAssignments()` pour permettre au planificateur de recalculer le nivellement.  
- **Pro astuce :** Pour les grands projets (plus de 10 000 tâches), activez `prj.setAutoCalculate(false)` avant les mises à jour massives, puis appelez `prj.calculate()` une fois à la fin pour améliorer les performances.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Tasks s’intègre facilement avec des bibliothèques telles que Jackson pour la gestion JSON ou Apache POI pour des opérations supplémentaires sur les feuilles de calcul, vous permettant de créer des solutions de gestion de projet plus riches.

**Q : Aspose.Tasks est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Aspose.Tasks prend en charge plus de 12 formats — y compris .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML et .MPP12 — assurant une édition bidirectionnelle transparente sur toutes les principales versions de Project.

**Q : Où puis‑je trouver un support supplémentaire pour Aspose.Tasks ?**  
R : Vous pouvez trouver du support et des discussions communautaires sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q : Puis‑je essayer Aspose.Tasks avant d’acheter ?**  
R : Oui, un essai gratuit pleinement fonctionnel est disponible depuis la [page des releases](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour l’évaluation ?**  
R : Demandez une licence temporaire depuis la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) pour exécuter la bibliothèque sans restrictions d’évaluation.

**Dernière mise à jour** : 2026-06-05  
**Testé avec** : Aspose.Tasks for Java 24.11  
**Auteur** : Aspose

## Tutoriels associés

- [Créer des affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Gérer le budget d’affectation Java avec Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Comment arrêter une affectation et reprendre les affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}