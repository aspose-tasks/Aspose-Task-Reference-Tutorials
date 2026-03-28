---
date: 2026-01-28
description: Apprenez à créer un calendrier de projet avec Aspose, à définir les jours
  de la semaine pour les exceptions de calendrier et à gérer un planning de jours
  non ouvrés en utilisant Aspose.Tasks pour Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Créer un calendrier de projet Aspose – Définir les jours de la semaine pour
  les exceptions du calendrier
url: /fr/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un calendrier de projet Aspose – Définir les jours de la semaine pour les exceptions de calendrier

### Introduction
Lorsque vous devez **create project calendar aspose**, vous devez pouvoir modéliser des jours de travail non standard tels que les jours fériés, les équipes spéciales ou les fermetures temporaires. Aspose.Tasks for Java vous offre un contrôle total sur les définitions de calendrier, vous permettant d’ajouter des exceptions qui reflètent les horaires du monde réel. Dans ce tutoriel, nous parcourrons les étapes exactes pour définir les jours de la semaine pour les exceptions de calendrier, afin que vos chronologies de projet restent précises et fiables. À la fin, vous verrez également comment cela s’insère dans une stratégie plus large de **non‑working days schedule** pour tout projet d’entreprise.

## Réponses rapides
- **Que signifie “create project calendar aspose” ?**  
  Il s'agit d'utiliser Aspose.Tasks pour créer un objet calendrier personnalisé qui pilote la planification des tâches.
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?**  
  Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.
- **Quels IDE sont pris en charge ?**  
  IntelliJ IDEA, Eclipse, NetBeans, ou tout IDE qui prend en charge Java 8+.
- **Puis‑je ajouter plusieurs exceptions au même calendrier ?**  
  Oui – vous pouvez ajouter autant d’objets `CalendarException` que nécessaire.
- **Dans quels formats de fichier puis‑je enregistrer le projet ?**  
  XML, MPP, et plusieurs autres formats pris en charge par Aspose.Tasks.

## Qu’est‑ce qu’un calendrier de projet dans Aspose.Tasks ?
Un **project calendar** définit les jours et heures de travail pour un projet. Il influence les dates de début/fin des tâches, l’allocation des ressources et les calculs globaux du planning. En personnalisant un calendrier, vous assurez que le planning respecte les contraintes du monde réel comme les jours fériés de l’entreprise ou les politiques de travail le week‑end.

## Pourquoi définir les jours de la semaine pour les exceptions de calendrier ?
- **Chronologies précises :** Les tâches ne seront pas planifiées les jours marqués comme non‑travail.  
- **Planification des ressources :** Les ressources ne sont allouées que les jours ouvrés valides.  
- **Conformité :** Aligne les calendriers de projet avec les politiques organisationnelles ou les jours fériés légaux.

## Calendrier des jours non ouvrés avec exceptions de calendrier
Lorsque vous maintenez un **non‑working days schedule**, vous avez généralement une liste maîtresse de jours fériés, de fenêtres de maintenance ou d’autres périodes d’interruption. Ajouter ces dates en tant qu’objets `CalendarException` garantit que chaque calcul — qu’il s’agisse d’analyse du chemin critique ou de nivellement des ressources — respecte automatiquement ces contraintes. Cette approche élimine les ajustements manuels de dates et réduit le risque de dérive du planning.

## Prérequis
1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez depuis la page officielle [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, ou tout éditeur compatible Java.  

## Comment créer un calendrier de projet aspose – Définir les jours de la semaine pour les exceptions de calendrier

### Guide étape par étape

### Étape 1 : Importer les packages requis
Nous avons besoin des classes principales d’Aspose.Tasks et du `GregorianCalendar` de Java pour la gestion des dates.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Étape 2 : Définir le répertoire de données
Spécifiez l’endroit où le fichier de projet généré sera enregistré.

```java
String dataDir = "Your Data Directory";
```

### Étape 3 : Créer une instance de projet
Instanciez un nouvel objet `Project` – il s’agit du conteneur de toutes les données du projet, y compris les calendriers.

```java
Project project = new Project();
```

### Étape 4 : Définir un calendrier
Ajoutez un calendrier personnalisé au projet. Ce calendrier contiendra nos exceptions.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Étape 5 : Définir l’exception des jours de la semaine
Créez un `CalendarException` qui marque une plage de jours (par ex., la dernière semaine de décembre) comme non‑travail.  
L’exemple définit l’exception du **24 Dec 2009** au **31 Dec 2009**, désactive le travail pour ces jours et traite l’exception comme un type quotidien.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Étape 6 : Enregistrer le projet
Enregistrez le projet, y compris le calendrier personnalisé et son exception, dans un fichier XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Dates d’exception non appliquées** | Assurez‑vous que `setEnteredByOccurrences(false)` et les valeurs correctes de `FromDate/ToDate` sont définies. |
| **Le fichier enregistré est vide** | Vérifiez que `dataDir` pointe vers un dossier accessible en écriture et que le nom de fichier se termine par `.xml`. |
| **Le calendrier n’est pas reflété dans la planification des tâches** | Assignez le calendrier aux tâches ou aux ressources en utilisant `task.setCalendar(cal)` ou `resource.setCalendar(cal)`. |

## Questions fréquentes

**Q : Puis‑je définir plusieurs exceptions pour différents jours de la semaine dans le même calendrier ?**  
R : Oui. Ajoutez des objets `CalendarException` supplémentaires à `cal.getExceptions()` pour chaque période ou règle distincte.

**Q : Aspose.Tasks for Java est‑il compatible avec différents IDE Java ?**  
R : Absolument. La bibliothèque fonctionne avec IntelliJ IDEA, Eclipse, NetBeans et tout IDE qui prend en charge les projets Java standard.

**Q : Puis‑je personnaliser les types d’exception autres que les exceptions quotidiennes ?**  
R : Oui. Utilisez `CalendarExceptionType.Weekly`, `Monthly` ou `Yearly` selon vos besoins de planification.

**Q : Comment puis‑je gérer les exceptions de manière dynamique en fonction des exigences du projet ?**  
R : Créez les objets d’exception programmatiquement—par ex., lisez les dates de vacances depuis une base de données ou un fichier de configuration et créez des instances `CalendarException` dans une boucle.

**Q : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for Java ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis la [page de téléchargement Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Conclusion
En suivant ces étapes, vous savez maintenant comment **create project calendar aspose** et définir des exceptions de jours de la semaine qui reflètent avec précision les jours fériés ou les périodes spéciales de non‑travail. Une configuration correcte du calendrier est essentielle pour des plannings réalistes, l’allocation des ressources et le succès global du projet. Explorez davantage en attachant le calendrier personnalisé aux tâches ou aux ressources et en expérimentant d’autres types d’exception afin de créer un **non‑working days schedule** complet pour tout projet.

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}