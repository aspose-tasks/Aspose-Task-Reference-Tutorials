---
date: 2026-02-26
description: Μάθετε πώς να χωρίζετε εργασίες με το Aspose.Tasks για Java – ο οριστικός
  οδηγός για το πώς να χωρίζετε εργασίες, να ορίζετε το ημερολόγιο του έργου και να
  δημιουργείτε ανάθεση πόρων.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να χωρίσετε εργασίες στο Aspose.Tasks
url: /el/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Διαχωρίσετε Εργασίες στο Aspose.Tasks

## Εισαγωγή
Αν ψάχνετε για **πώς να διαχωρίσετε εργασίες** σε ένα έργο βασισμένο σε Java, βρίσκεστε στο σωστό μέρος. Το Aspose.Tasks for Java σας παρέχει έναν καθαρό, προγραμματιστικό τρόπο για να χωρίσετε μια μακρά εργασία σε μικρότερα, διαχειρίσιμα τμήματα, κάτι που βοηθά στη σταθμισμένη κατανομή πόρων, στην ακριβή αναφορά και σε πιο σφιχτά χρονοδιαγράμματα έργου. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία — από τη ρύθμιση του ημερολογίου του έργου μέχρι τη δημιουργία ανάθεσης πόρου και, τέλος, το διαχωρισμό της εργασίας σε πολλαπλά τμήματα.

## Γρήγορες Απαντήσεις
- **Τι είναι ο διαχωρισμός εργασιών;** Διαίρεση μιας ενιαίας εργασίας σε αρκετά μικρότερα διαστήματα, διατηρώντας τη συνολική της διάρκεια.  
- **Γιατί να διαχωρίζω εργασίες σε Java;** Επιτρέπει ακριβή κατανομή πόρων και καλύτερη παρακολούθηση προόδου.  
- **Ποια βιβλιοθήκη βοηθά;** Το Aspose.Tasks for Java παρέχει ενσωματωμένες μεθόδους για διαχωρισμό και χρονική φάση.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται άδεια για παραγωγή.  
- **Ποια έκδοση Java υποστηρίζεται;** Η βιβλιοθήκη λειτουργεί με Java 8 και νεότερες.

## Προαπαιτούμενα
Πριν βυθιστείτε στο tutorial, βεβαιωθείτε ότι έχετε τα εξής:
- Εγκατεστημένο Java Development Kit (JDK) στο σύστημά σας.  
- Τη βιβλιοθήκη Aspose.Tasks for Java κατεβασμένη και προστιθέμενη στο έργο σας. Μπορείτε να τη κατεβάσετε από την [τεκμηρίωση Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο Java σας:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Βήμα 1: Δημιουργία Νέου Έργου
Ξεκινήστε δημιουργώντας ένα νέο έργο χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Βήμα 2: Ορισμός Ημερολογίου Έργου
Ο ορισμός του **ημερολογίου έργου** καθορίζει τις εργάσιμες ημέρες, τις αργίες και το συνολικό χρονοδιάγραμμα του προγράμματός σας. Αυτό το βήμα είναι ουσιώδες για ακριβείς υπολογισμούς χρονικής φάσης.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Βήμα 3: Προσθήκη Ριζικής Εργασίας
Κάθε έργο χρειάζεται ένα ριζικό κοντέινερ. Η προσθήκη μιας ριζικής εργασίας σας δίνει ένα σημείο στο οποίο μπορείτε να συνδέσετε όλες τις επόμενες εργασίες.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Βήμα 4: Προσθήκη Νέας Εργασίας για Διαχωρισμό
Δημιουργήστε την εργασία που σκοπεύετε να διαχωρίσετε. Εδώ ορίζουμε διάρκεια τριών ημερών ως παράδειγμα.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Βήμα 5: Δημιουργία Ανάθεσης Πόρου
Μια **ανάθεση πόρου** συνδέει έναν πόρο (ή placeholder) με την εργασία. Αυτό απαιτείται πριν δημιουργηθούν τα δεδομένα χρονικής φάσης.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Βήμα 6: Δημιουργία Δεδομένων Χρονικής Φάσης
Τα δεδομένα χρονικής φάσης αντιπροσωπεύουν πώς η εργασία κατανέμεται κατά τη διάρκεια της διάρκειάς της. Η δημιουργία τους προετοιμάζει την εργασία για διαχωρισμό.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Βήμα 7: Διαχωρισμός της Εργασίας
Τώρα **διαχωρίζουμε την εργασία σε τμήματα**. Σε αυτό το παράδειγμα διαιρούμε την τριήμερη εργασία σε τρία μονοήμερα τμήματα.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Γιατί να Διαχωρίζετε Εργασίες;
Ο διαχωρισμός εργασιών σας δίνει πιο λεπτομερή έλεγχο πάνω σε:
- **Σταθμισμένη κατανομή πόρων:** Αναθέστε διαφορετικούς πόρους σε κάθε τμήμα.  
- **Παρακολούθηση προόδου:** Ενημερώστε την κατάσταση ανά τμήμα.  
- **Αναφορές:** Δημιουργήστε πιο λεπτομερή διαγράμματα Gantt και αναφορές.

## Κοινά Προβλήματα και Λύσεις
- **Λείπουν δεδομένα ημερολογίου:** Βεβαιωθείτε ότι καλείτε `timephasedDataFromTaskDuration` πριν το διαχωρισμό.  
- **Τμήματα μηδενικής διάρκειας:** Επαληθεύστε ότι κάθε διάστημα διαχωρισμού έχει μη‑μηδενική διάρκεια· διαφορετικά η βιβλιοθήκη θα το αγνοήσει.  
- **Εξαιρέσεις άδειας:** Η εκτέλεση χωρίς έγκυρη άδεια μπορεί να προσθέσει υδατογράφημα στα εξαγόμενα αρχεία.

## Συχνές Ερωτήσεις
### Μπορώ να διαχωρίσω εργασίες με διαφορετικές διάρκειες;
Ναι, μπορείτε να προσαρμόσετε τη διάρκεια κάθε τμήματος ώστε να ταιριάζει στις απαιτήσεις του έργου σας.

### Είναι το Aspose.Tasks for Java συμβατό με όλες τις εκδόσεις Java;
Το Aspose.Tasks for Java σχεδιάστηκε ώστε να λειτουργεί άψογα με Java 8 και νεότερες, εξασφαλίζοντας ευρεία συμβατότητα.

### Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java δωρεάν;
Το Aspose.Tasks for Java προσφέρει δωρεάν δοκιμή, επιτρέποντάς σας να εξερευνήσετε τις δυνατότητές του πριν από την αγορά.

### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks for Java;
Επισκεφθείτε το [φόρουμ υποστήριξης Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15) για βοήθεια και σύνδεση με την κοινότητα.

### Χρειάζομαι προσωρινή άδεια για το Aspose.Tasks for Java;
Μπορείτε να αποκτήσετε προσωρινή άδεια από [αυτόν τον σύνδεσμο](https://purchase.aspose.com/temporary-license/) για δοκιμή και αξιολόγηση.

---

**Τελευταία Ενημέρωση:** 2026-02-26  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}