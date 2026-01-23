---
date: 2026-01-23
description: Apprenez à identifier les tâches inter‑projets à l’aide d’Aspose.Tasks
  pour Java. Découvrez une intégration transparente et une gestion efficace.
linktitle: Identify Cross Project Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Identifier les tâches inter‑projets dans Aspose.Tasks
url: /fr/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identifier les tâches, ce guide vous accompagnera à chaqueité dans vos applicationsjets » ?** Cela signifie localiser les tâches qui font référence ou dépendent de tâches dans un autre fichier de projet.  
- **Quelle affiche l'ID de la tâche ?** Utilisez `externalTask.get(Tsk.ID)` pour afficher l'ID de la tâche.  
- **Comment définir le répertoire du document ?** Assignez le chemin du dossier à une variable `String` (par ex., `dataDir`).  
- **Quelle propriété récupère une tâche par UID ?** Appelez `getChildren().getByUid(yourUid)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Oui, une licence valide d’Aspose.Tasks est requise pour les déploiements commerciaux.

## Qu’est‑ce que « identifier les tâches inter‑projets » ?
Identifier les tâches inter‑projets vous permet de tracer les relations entre des tâches réparties dans plusieurs fichiers Microsoft Project. Cela est essentiel pour les portefeuilles de projets à grande échelle où les tâches sont partagées ou dépendent de calendriers externes.

## Pourquoi utiliser Aspose.Tasks pour Java ?
- **Aucun Microsoft Project requis** – travaillez directement avec les fichiers .mpp en Java.  
- **Accès complet à l'API** – récupérez les IDs, les IDs externes, les UID, etc.  
- **Cross‑platform** – exécutez sur tout environnement compatible JVM.

## Prérequis
- Connaissances de base en programmation Java.  
- Aspose.Tasks pour Java installé. Vous pouvez le télécharger **[ici](https://releases.aspose.com/tasks/java/)**.

## Importer les packages
Tout d'abord, importez les classes essentielles d'Aspose.Tasks qui permettent la manipulation de projets.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Étape 1 : Définir le répertoire du document
Définissez le dossier où résident vos fichiers .mpp. Cette étape correspond au mot‑clé secondaire **set document directory**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Étape 2 : Charger le projet externe
Chargez le fichier de projet externe (par ex., *External.mpp*) afin de pouvoir inspecter ses tâches.

```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Étape 3 : Récupérer la tâche externe par UID
Utilisez le **UID** (Identifiant Unique) de la tâche pour récupérer la tâche spécifique qui vous intéresse. Cela répond au mot‑clé secondaire **get task uid**.

```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Étape 4 : Afficher l'ID de la tâche (cas d'utilisation principal)
Maintenant que vous avez l'objet tâche, affichez son ID interne. Cela illustre le mot‑clé secondaire **print task id**.

```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Étape 5 : Afficher l'ID de la tâche originale (externe)
Vous pouvez également récupérer l'ID que la tâche possédait dans son fichier de projet original.

```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Répétez les étapes ci‑dessus pour toutes les tâches supplémentaires que vous devez suivre entre les projets.

## Problèmes courants et astuces
- **Erreurs de chemin** – Assurez‑vous que `dataDir` se termine par le séparateur de fichiers approprié (`/` ou `\\`).  
- **UID non trouvé** – Vérifiez que l'UID existe dans le projet externe ; utilisez `externalProject.getRootTask().getChildren().size()` pour lister les UID disponibles.  
- **Exceptions de licence** – Une licence manquante ou invalide déclenchera une exception de licence à l'exécution.

## FAQ

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks prend en charge plusieurs langages, dont Java, .NET et d’autres.

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks pour Java ?**  
R : Consultez la documentation **[ici](https://reference.aspose.com/tasks/java/)**.

**Q : Existe‑t‑il un essai gratuit d’Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez obtenir un essai gratuit **[ici](https://releases.aspose.com/)**.

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks ?**  
R : Obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Besoin d’aide ou avez‑vous des questions spécifiques ?**  
R : Visitez le forum de support Aspose.Tasks **[ici](https://forum.aspose.com/c/tasks/15)**.

---

**Dernière mise à jour :** 2026-01-23  
**Testé avec :** Aspose.Tasks for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}