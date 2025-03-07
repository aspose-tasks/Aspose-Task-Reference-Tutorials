---
title: Διαχωρισμός εργασιών στο Aspose.Tasks
linktitle: Διαχωρισμός εργασιών στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Κατακτήστε τη διαχείριση εργασιών σε Java με το Aspose.Tasks! Μάθετε πώς να διαχωρίζετε τις εργασίες αποτελεσματικά για βελτιστοποιημένα χρονοδιαγράμματα έργων. Κατεβάστε τώρα!
weight: 29
url: /el/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαχωρισμός εργασιών στο Aspose.Tasks

## Εισαγωγή
Δυσκολεύεστε με τη διαχείριση εργασιών στο έργο σας Java; Το Aspose.Tasks για Java παρέχει μια ισχυρή λύση για τον αποτελεσματικό διαχωρισμό εργασιών, ενισχύοντας τις δυνατότητες διαχείρισης έργου. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία διαχωρισμού εργασιών χρησιμοποιώντας το Aspose.Tasks για Java, βοηθώντας σας να βελτιστοποιήσετε τα χρονοδιαγράμματα του έργου σας και τις κατανομές πόρων.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο μηχάνημά σας.
-  Η βιβλιοθήκη Aspose.Tasks για Java έγινε λήψη και προσθήκη στο έργο σας. Μπορείτε να το κατεβάσετε από το[Aspose.Tasks για τεκμηρίωση Java](https://reference.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο σας Java:
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
## Βήμα 1: Δημιουργήστε ένα νέο έργο
Ξεκινήστε δημιουργώντας ένα νέο έργο χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks:
```java
// Δημιουργήστε ένα νέο έργο
Project splitTaskProject = new Project();
```
## Βήμα 2: Ορισμός Ημερολογίου Έργου
Ορίστε τις ρυθμίσεις ημερολογίου του έργου για να καθορίσετε το χρονοδιάγραμμα:
```java
// Αποκτήστε ένα τυπικό ημερολόγιο
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Ορίστε τις ρυθμίσεις ημερολογίου του έργου
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (συνεχίστε με το παράδειγμα)
```
## Βήμα 3: Προσθέστε μια εργασία ρίζας
Προσθέστε μια εργασία root στο έργο σας:
```java
// Εργασία ρίζας
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Βήμα 4: Προσθέστε μια νέα εργασία στο διαχωρισμό
Προσθέστε μια νέα εργασία στο έργο σας που θέλετε να χωρίσετε:
```java
// Προσθήκη νέας εργασίας
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Βήμα 5: Δημιουργήστε μια ανάθεση πόρων
Δημιουργήστε μια νέα ανάθεση πόρων για την εργασία:
```java
// Δημιουργήστε μια νέα ανάθεση πόρων
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Βήμα 6: Δημιουργήστε δεδομένα χρονικής φάσης
Δημιουργήστε δεδομένα χρονικής φάσης εκχώρησης πόρων:
```java
// Δημιουργήστε δεδομένα χρονικής φάσης εκχώρησης πόρων
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Βήμα 7: Διαχωρίστε την εργασία
Χωρίστε την εργασία σε πολλά μέρη:
```java
// Χωρίστε την εργασία σε 3 μέρη
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (συνεχίστε με το παράδειγμα)
```
## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να χωρίζετε εργασίες χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η ισχυρή βιβλιοθήκη απλοποιεί τη διαχείριση εργασιών σε έργα Java, παρέχοντας αποτελεσματικές λύσεις για τη βελτιστοποίηση των χρονοδιαγραμμάτων έργων και την κατανομή πόρων.
## Συχνές Ερωτήσεις
### Μπορώ να χωρίσω εργασίες με διαφορετικές διάρκειες;
Ναι, μπορείτε να προσαρμόσετε τη διάρκεια των εργασιών σύμφωνα με τις απαιτήσεις του έργου σας.
### Είναι το Aspose.Tasks για Java συμβατό με όλες τις εκδόσεις Java;
Το Aspose.Tasks για Java έχει σχεδιαστεί για να λειτουργεί απρόσκοπτα με διάφορες εκδόσεις Java, διασφαλίζοντας τη συμβατότητα.
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java δωρεάν;
Το Aspose.Tasks για Java προσφέρει μια δωρεάν δοκιμή, επιτρέποντάς σας να εξερευνήσετε τις δυνατότητές του πριν κάνετε μια αγορά.
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
 Επισκέψου το[Aspose.Tasks for Java υποστήριξης φόρουμ](https://forum.aspose.com/c/tasks/15) για να λάβετε βοήθεια και να συνδεθείτε με την κοινότητα.
### Χρειάζομαι μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Μπορείτε να αποκτήσετε προσωρινή άδεια από[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/) για σκοπούς δοκιμών και αξιολόγησης.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
