---
date: 2026-09-25
description: Μάθετε πώς να δημιουργήσετε χρονοδιάγραμμα έργου σε Java χρησιμοποιώντας
  το Aspose.Tasks. Αυτός ο οδηγός σας δείχνει πώς να προσθέσετε συνοπτικές εργασίες,
  να διαχειριστείτε την ιεραρχία του έργου και να ορίσετε τον φάκελο εγγράφων αποδοτικά.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Δημιουργία εργασιών στο Aspose.Tasks
og_description: Μάθετε πώς να δημιουργήσετε χρονοδιάγραμμα έργου σε Java χρησιμοποιώντας
  το Aspose.Tasks. Ακολουθήστε βήμα-βήμα οδηγίες για να προσθέσετε συνοπτικές εργασίες,
  να διαχειριστείτε την ιεραρχία και να ορίσετε τον φάκελο εγγράφων.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Πώς να δημιουργήσετε χρονοδιάγραμμα έργου με το Aspose.Tasks για Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Πώς να δημιουργήσετε χρονοδιάγραμμα έργου με το Aspose.Tasks για Java
url: /el/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε χρονοδιάγραμμα έργου με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το μάθημα θα μάθετε πώς να **δημιουργήσετε χρονοδιάγραμμα έργου** σε μια εφαρμογή Java χρησιμοποιώντας το Aspose.Tasks. Είτε δημιουργείτε μια απλή λίστα εργασιών είτε έναν πολύπλοκο προγραμματιστή επιπέδου επιχείρησης, τα παρακάτω βήματα σας καθοδηγούν στην προσθήκη εργασιών σύνοψης, τη διαχείριση της ιεραρχίας του έργου και τον ορισμό του φακέλου εγγράφου — όλα με σαφή, εκτελέσιμα αποσπάσματα κώδικα. Στο τέλος, θα έχετε ένα πλήρως δομημένο χρονοδιάγραμμα έτοιμο για περαιτέρω επεξεργασία ή εξαγωγή.

## Γρήγορες απαντήσεις
- **Τι διαχειρίζεται το Aspose.Tasks;** Διαχειρίζεται ιεραρχίες εργασιών, πόρους, ημερολόγια και μορφές αρχείων έργου (MS‑Project, Primavera κ.λπ.).  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποια έκδοση της Java υποστηρίζεται;** Η Java 8 και νεότερες υποστηρίζονται πλήρως.  
- **Μπορώ να προσθέσω προσαρμοσμένα πεδία σε εργασίες;** Ναι, μπορείτε να επεκτείνετε τις εργασίες με πεδία που ορίζονται από τον χρήστη μέσω του API.  
- **Υπάρχει ενσωματωμένη υποστήριξη για διαγράμματα Gantt;** Το Aspose.Tasks μπορεί να εξάγει σε PDF/HTML που περιλαμβάνουν οπτικοποιήσεις Gantt.

## Τι είναι το χρονοδιάγραμμα έργου στο Aspose.Tasks;
Ένα χρονοδιάγραμμα έργου είναι το πλήρες σύνολο εργασιών, εξαρτήσεων και χρονοδιαγραμμάτων που ορίζουν πώς θα εκτελεστεί η εργασία. Το Aspose.Tasks αποθηκεύει αυτές τις πληροφορίες σε ένα αντικείμενο `Project` που μπορείτε να διαβάσετε, να τροποποιήσετε και να αποθηκεύσετε σε διάφορες μορφές. Περιλαμβάνει ημερομηνίες έναρξης και λήξης, περιορισμούς και αναθέσεις πόρων, επιτρέποντας ολοκληρωμένο προγραμματισμό και αναφορά.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για διαχείριση έργων Java;
Το Aspose.Tasks υποστηρίζει **πάνω από 30 μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί έργα με **έως 10.000 εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας υψηλή απόδοση για μεγάλης κλίμακας σενάρια διαχείρισης έργων Java.

## Προαπαιτούμενα
- **Java Development Kit (JDK)** – JDK 8 ή νεότερο εγκατεστημένο στο σύστημά σας.  
- **Aspose.Tasks for Java library** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από [Λήψη Aspose.Tasks για Java](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Χρησιμοποιήστε Eclipse, IntelliJ IDEA ή οποιοδήποτε IDE φιλικό προς τη Java που προτιμάτε.

## Εισαγωγή πακέτων
`Project`, `Task` και σχετικές κλάσεις βρίσκονται στον χώρο ονομάτων `com.aspose.tasks`. Εισάγετέ τις στην αρχή του αρχείου Java:

Η κλάση `Project` αντιπροσωπεύει ένα πλήρες χρονοδιάγραμμα έργου και παρέχει μεθόδους για τη διαχείριση εργασιών και πόρων.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Η κλάση `Project` είναι το σημείο εισόδου για όλες τις λειτουργίες σε ένα αρχείο έργου.

## Πώς να δημιουργήσετε χρονοδιάγραμμα έργου με Aspose.Tasks;

Φορτώστε ένα νέο αντικείμενο `Project`, ορίστε τον φάκελο εγγράφου και αρχίστε να προσθέτετε εργασίες. Αυτή η παράγραφος εξηγεί τη βασική ροή: δημιουργείτε ένα `Project`, διαμορφώνετε το `RootFolder` του (τον φάκελο εγγράφου), στη συνέχεια προσθέτετε μια εργασία σύνοψης ακολουθούμενη από υποεργασίες. Όλες οι αλλαγές διατηρούνται στη μνήμη μέχρι να καλέσετε το `save` για να αποθηκεύσετε το χρονοδιάγραμμα σε αρχείο.

### Βήμα 1: ορίστε τον φάκελο εγγράφου
Ορίστε πού θα γραφτεί το τελικό αρχείο έργου. Ο καθορισμός του φακέλου νωρίς εξασφαλίζει ότι όλες οι επόμενες λειτουργίες αποθήκευσης θα χρησιμοποιούν συνεπή διαδρομή.

Η ιδιότητα `RootFolder` καθορίζει τον βασικό φάκελο από όπου διαβάζονται ή γράφονται τα αρχεία έργου.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Βήμα 2: δημιουργήστε ένα νέο έργο
Δημιουργήστε ένα νέο αντικείμενο `Project` που θα περιέχει το χρονοδιάγραμμα σας. Μπορείτε προαιρετικά να περάσετε μια υπάρχουσα διαδρομή αρχείου για να φορτώσετε ένα υπάρχον χρονοδιάγραμμα προς τροποποίηση.

Ο κατασκευαστής `Project` δημιουργεί ένα κενό χρονοδιάγραμμα έτοιμο για προσθήκη εργασιών.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Βήμα 3: προσθέστε μια εργασία σύνοψης
Μια εργασία σύνοψης ομαδοποιεί σχετικές υποεργασίες και εμφανίζεται ως ένας ανασπαστέος κόμβος στα διαγράμματα Gantt. Χρησιμοποιήστε την κλάση `Task` και ορίστε το `IsSummary` σε `true`.

Η μέθοδος `addTask` δημιουργεί μια νέα εργασία κάτω από έναν καθορισμένο γονέα και επιστρέφει το ID της.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Βήμα 4: προσθέστε μια υποεργασία
Οι υποεργασίες κληρονομούν τις ημερομηνίες έναρξης/λήξης από την εργασία σύνοψης γονέα, εκτός αν τις παρακάμπνετε. Η προσθήκη μιας υποεργασίας είναι τόσο απλή όσο η επανάκληση του `addTask` και ο καθορισμός του ID του γονέα.

Καλώντας το `addTask` με ένα ID γονέα προσθέτει μια υποεργασία κάτω από αυτήν την εργασία σύνοψης.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Συνεχίστε να προσθέτετε όσες εργασίες και υποεργασίες χρειάζεστε για το έργο σας. Κάθε βήμα συμβάλλει στην κατασκευή μιας δομημένης ιεραρχίας έργου που μπορεί να εξαχθεί σε MS‑Project, PDF ή άλλες υποστηριζόμενες μορφές.

## Συχνά προβλήματα και λύσεις
- **Πρόβλημα:** “Ο φάκελος εγγράφου δεν βρέθηκε.”  
  **Λύση:** Επαληθεύστε ότι η διαδρομή που ορίζετε στο `RootFolder` υπάρχει στο σύστημα αρχείων και ότι η διαδικασία Java έχει δικαιώματα εγγραφής.
- **Πρόβλημα:** Οι υποεργασίες δεν εμφανίζονται κάτω από την εργασία σύνοψης.  
  **Λύση:** Βεβαιωθείτε ότι περνάτε το σωστό ID γονικής εργασίας όταν καλείτε το `addTask`. Το API απαιτεί το ID γονέα ως δεύτερο όρισμα.
- **Πρόβλημα:** Μεγάλα έργα προκαλούν OutOfMemoryError.  
  **Λύση:** Το Aspose.Tasks επεξεργάζεται τις εργασίες σε λειτουργία ροής· αυξήστε το μέγεθος της μνήμης heap της JVM (`-Xmx2g`) ή χωρίστε το χρονοδιάγραμμα σε πολλαπλά αρχεία.

## Συχνές ερωτήσεις
**Ε: Είναι το Aspose.Tasks κατάλληλο για μικρής κλίμακας έργα;**  
Α: Απόλυτα. Η βιβλιοθήκη κλιμακώνεται από μια λίστα μίας εργασίας έως χρονοδιαγράμματα επιπέδου επιχείρησης με χιλιάδες εργασίες.

**Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks για Java;**  
Α: Ανατρέξτε στην τεκμηρίωση [Αναφορά API Aspose.Tasks Java](https://reference.aspose.com/tasks/java/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks;**  
Α: Επισκεφθείτε τη [σελίδα αίτησης προσωρινής άδειας](https://purchase.aspose.com/temporary-license/) για μια άδεια περιορισμένου χρόνου που λειτουργεί για ανάπτυξη και δοκιμή.

**Ε: Μπορώ να προσαρμόσω τα χαρακτηριστικά των εργασιών χρησιμοποιώντας το Aspose.Tasks;**  
Α: Ναι, μπορείτε να επεκτείνετε τις εργασίες με προσαρμοσμένα πεδία, να αναθέσετε πόρους και να τροποποιήσετε τα ημερολόγια προγραμματιστικά.

**Ε: Υπάρχει κοινότητα υποστήριξης για χρήστες του Aspose.Tasks;**  
Α: Απόλυτα! Εγγραφείτε στην κοινότητα Aspose.Tasks στο [φόρουμ υποστήριξης](https://forum.aspose.com/c/tasks/15).

**Τελευταία ενημέρωση:** 2026-09-25  
**Δοκιμάστηκε με:** Aspose.Tasks 24.12 for Java  
**Συγγραφέας:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Σχετικά Μαθήματα

- [Ορισμός ημερομηνίας έναρξης έργου στο MS Project χρησιμοποιώντας Aspose.Tasks για Java](/tasks/java/project-properties/write-project-info/)
- [Δημιουργία εξαρτήσεων εργασιών διαχείρισης έργου στο Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Πώς να προσθέσετε πόρο σε έργο και να δημιουργήσετε αναθέσεις πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}