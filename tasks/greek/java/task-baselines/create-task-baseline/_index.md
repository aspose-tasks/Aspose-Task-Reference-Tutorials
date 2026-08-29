---
date: 2026-08-29
description: Μάθετε πώς να προσθέσετε task σε project σε Java, δημιουργήστε μια λίστα
  task και ορίστε μια baseline χωρίς Microsoft Project χρησιμοποιώντας Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Δημιουργία μιας Task Baseline στο Aspose.Tasks
og_description: Μάθετε πώς να προσθέσετε task σε project σε Java και να ορίσετε μια
  baseline χρησιμοποιώντας Aspose.Tasks. Αυτός ο οδηγός δείχνει κώδικα βήμα‑βήμα χωρίς
  την ανάγκη για Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Πώς να προσθέσετε task σε project σε Java και να ορίσετε μια baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Πώς να προσθέσετε task σε project σε Java και να ορίσετε μια baseline
url: /el/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε εργασία σε έργο σε Java και να ορίσετε μια βάση

## Εισαγωγή
Σε αυτό το σεμινάριο θα **προσθέσετε εργασία σε έργο** προγραμματιστικά, θα δημιουργήσετε μια βάση εργασίας Microsoft Project και θα αποθηκεύσετε το αρχείο—όλα χωρίς ποτέ να ανοίξετε το Microsoft Project. Το Aspose.Tasks for Java σας παρέχει ένα καθαρό‑Java API που λειτουργεί σε οποιαδήποτε πλατφόρμα, καθιστώντας το ιδανικό για αυτοματοποιημένες γραμμές κατασκευής, υπηρεσίες αναφοράς ή οποιαδήποτε λύση διακομιστή που χρειάζεται να χειριστεί αρχεία .mpp.

## Γρήγορες απαντήσεις
- **Τι κάνει το Aspose.Tasks;** Παρέχει ένα Java API για δημιουργία, ανάγνωση και επεξεργασία αρχείων Microsoft Project χωρίς να απαιτείται το Microsoft Project.  
- **Χρειάζεται να είναι εγκατεστημένο το Microsoft Project;** Όχι, η βιβλιοθήκη λειτουργεί εντελώς ανεξάρτητα.  
- **Ποια έκδοση Java απαιτείται;** JDK 8 ή νεότερη.  
- **Μπορώ να ορίσω βάση για μία μόνο εργασία;** Ναι – καλέστε `setBaseline` σε μια λίστα που περιέχει μόνο τις εργασίες που θέλετε.  
- **Απαιτείται άδεια για παραγωγή;** Ναι, μια εμπορική άδεια αφαιρεί τους περιορισμούς αξιολόγησης και ξεκλειδώνει όλες τις λειτουργίες.

## Τι είναι η βάση εργασίας;
Μια βάση εργασίας καταγράφει την αρχικά προγραμματισμένη ημερομηνία έναρξης, την ημερομηνία λήξης και την εργασία για μια εργασία τη στιγμή που το χρονοδιάγραμμα αποθηκεύεται για πρώτη φορά. Αυτό το στιγμιότυπο λειτουργεί ως σημείο αναφοράς, επιτρέποντας στους διαχειριστές έργων να συγκρίνουν την πραγματική πρόοδο και τα κόστη με το αρχικό σχέδιο και να υπολογίζουν αποκλίσεις για ανάλυση απόδοσης.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για να προσθέσετε εργασία σε έργο σε Java;
Μπορείτε να δημιουργήσετε, να τροποποιήσετε και να ορίσετε βάσεις εργασιών χωρίς καμία εγκατάσταση επιφάνειας εργασίας, κάτι που επιτρέπει πλήρως αυτοματοποιημένες ροές εργασίας. Το Aspose.Tasks υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να διαχειριστεί έργα με **εκατοντάδες εργασίες** διατηρώντας τη χρήση μνήμης κάτω από 200 MB, καθιστώντας το ιδανικό για υπηρεσίες cloud και CI/CD pipelines.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – εγκαταστήστε JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java** – κατεβάστε τη βιβλιοθήκη από το [download link](https://releases.aspose.com/tasks/java/).  

## Εισαγωγή πακέτων
Για να ξεκινήσετε να εργάζεστε με το Aspose.Tasks στο Java project σας, εισάγετε τα απαραίτητα πακέτα:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Βήμα 1: δημιουργία αντικειμένου έργου
Η κλάση `Project` είναι το κορυφαίο αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη. Η δημιουργία του σας δίνει ένα κενό έργο που μπορείτε να γεμίσετε με εργασίες, πόρους και ημερολόγια.

```java
Project project = new Project();
```
Εδώ δημιουργούμε ένα νέο αντικείμενο `Project` – αυτό αντιπροσωπεύει το αρχείο MS Project που θα περιέχει τη λίστα εργασιών μας.

## Βήμα 2: προσθήκη εργασίας στο έργο
Η κλάση `Task` αντιπροσωπεύει ένα μεμονωμένο αντικείμενο εργασίας σε ένα χρονοδιάγραμμα έργου. Κάθε `Task` μπορεί να έχει τη δική της διάρκεια, ημερομηνία έναρξης και αναθέσεις πόρων.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Χρησιμοποιώντας το `getRootTask()` προσπελαύνουμε τη ρίζα της ιεραρχίας του έργου και **προσθέτουμε εργασία στο Microsoft Project**. Η συμβολοσειρά `"Task"` είναι το όνομα της εργασίας· μπορείτε να το αντικαταστήσετε με οποιαδήποτε περιγραφή χρειάζεστε.

## Βήμα 3: ορισμός βάσης για συγκεκριμένες εργασίες
Το `BaselineType` είναι μια απαρίθμηση που ορίζει ποιο slot βάσης (Baseline, Baseline1 … Baseline10) θέλετε να γράψετε. Με τη μεταβίβαση λίστας εργασιών μπορείτε να ορίσετε βάση μόνο στα στοιχεία που επιλέγετε.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Για **ορισμό βάσης χωρίς MS Project**, δημιουργήστε μια λίστα με τις εργασίες που θέλετε να βάσετε (εδώ `myList`) και περάστε την στο `setBaseline`. Συμπληρώστε το `myList` με τις εργασίες που προσθέσατε αν χρειάζεστε μόνο επιλεκτική βάση.

## Βήμα 4: ορισμός βάσης για ολόκληρο το έργο
Το `setBaseline` γράφει τις επιλεγμένες τιμές βάσης σε κάθε εργασία του έργου.  
Αν προτιμάτε να βάσετε ολόκληρο το έργο με μία κλήση, απλώς καλέστε το `setBaseline` με το επιθυμητό `BaselineType`.

```java
project.setBaseline(BaselineType.Baseline);
```
Αυτή η κλήση γράφει τις επιλεγμένες τιμές βάσης για **κάθε εργασία** στο έργο, εξασφαλίζοντας ένα πλήρες στιγμιότυπο του αρχικού χρονοδιαγράμματος.

## Πώς να προσθέσετε εργασία στο Microsoft Project χρησιμοποιώντας το Aspose.Tasks
Η μέθοδος `add()` δημιουργεί μια νέα υποεργασία κάτω από την καθορισμένη γονική εργασία και επιστρέφει το νεοδημιουργημένο αντικείμενο `Task`.  
Προσθέτετε μια εργασία καλώντας `add()` σε ένα γονικό αντικείμενο `Task` (συνήθως τη ρίζα). Η μέθοδος επιστρέφει ένα νέο αντικείμενο `Task` που μπορείτε να διαμορφώσετε περαιτέρω—διάρκεια, ημερομηνία έναρξης, πόρους ή προσαρμοσμένα πεδία—πριν αποθηκεύσετε το αρχείο του έργου.

## Πώς να ορίσετε βάση χωρίς MS Project
Το Aspose.Tasks επιτρέπει τη δημιουργία βάσης εξ ολοκλήρου μέσω κώδικα. Επιλέξτε ένα `BaselineType` (π.χ., `BaselineType.Baseline`) και καλέστε `setBaseline`. Μπορείτε να επαναλάβετε τη διαδικασία με `Baseline1`‑`Baseline10` για να διατηρήσετε πολλαπλές εκδόσεις βάσης, όλα χωρίς άνοιγμα του Microsoft Project.

## Συνηθισμένα προβλήματα και λύσεις
- **Η βάση δεν εμφανίζεται:** Βεβαιωθείτε ότι καλείτε `project.save("output.mpp")` μετά τον ορισμό της βάσης (βήμα αποθήκευσης παραλείπεται εδώ για συντομία).  
- **Η λίστα εργασιών εμφανίζεται κενή:** Επαληθεύστε ότι προσθέτετε εργασίες στον σωστό γονέα (`getRootTask()` ή μια υποεργασία).  
- **Σφάλματα ασυμφωνίας εκδόσεων:** Χρησιμοποιήστε το πιο πρόσφατο JAR του Aspose.Tasks για να εγγυηθείτε συμβατότητα με νεότερες μορφές .mpp.

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java χωρίς εγκατεστημένο Microsoft Project;**  
Α: Ναι, το Aspose.Tasks λειτουργεί ανεξάρτητα και δεν απαιτεί Microsoft Project στο σύστημα.

**Ε: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές εκδόσεις του Microsoft Project;**  
Α: Απόλυτα. Η βιβλιοθήκη υποστηρίζει αρχεία Project από το 2007 έως τις πιο πρόσφατες εκδόσεις του 2024.

**Ε: Μπορώ να διαχειριστώ πόρους του έργου χρησιμοποιώντας το Aspose.Tasks for Java;**  
Α: Ναι, μπορείτε να προσθέτετε, να ενημερώνετε και να διαγράφετε πόρους προγραμματιστικά, όπως και τις εργασίες.

**Ε: Υποστηρίζει το Aspose.Tasks for Java τον ορισμό εξαρτήσεων εργασιών;**  
Α: Ναι, μπορείτε να ορίσετε σχέσεις προκάτορου‑ακόλουθου χρησιμοποιώντας την κλάση `TaskLink`.

**Ε: Διατίθεται τεχνική υποστήριξη για το Aspose.Tasks for Java;**  
Α: Ναι, μπορείτε να λάβετε βοήθεια μέσω του [support forum](https://forum.aspose.com/c/tasks/15), όπου το προσωπικό της Aspose και η κοινότητα απαντούν σε ερωτήματα.

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα έχετε μάθει πώς να **προσθέσετε εργασία σε έργο** σε Java, να δημιουργήσετε μια λίστα εργασιών και να **ορίσετε βάση χωρίς MS Project** χρησιμοποιώντας το Aspose.Tasks. Αυτή η προσέγγιση βελτιστοποιεί την αυτοματοποίηση έργων, αφαιρεί την ανάγκη για εγκατάσταση επιτραπέζιου Project και σας δίνει πλήρη προγραμματιστικό έλεγχο σε κάθε πτυχή του χρονοδιαγράμματός σας.

---

**Τελευταία ενημέρωση:** 2026-08-29  
**Δοκιμασμένο με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά σεμινάρια

- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [How to Set Baseline Duration in Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Create Tasks Aspose Java – Task Properties](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}