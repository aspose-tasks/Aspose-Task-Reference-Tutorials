---
title: Διαχείριση εργασιών γονέα και παιδιού στο Aspose.Tasks
linktitle: Διαχείριση εργασιών γονέα και παιδιού στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Βελτιώστε την αποτελεσματικότητα διαχείρισης έργου με το Aspose.Tasks για Java. Μάθετε να διαχειρίζεστε τις εργασίες γονέα και παιδιού βήμα προς βήμα. Ξεκινήστε τώρα!
weight: 24
url: /el/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαχείριση εργασιών γονέα και παιδιού στο Aspose.Tasks

## Εισαγωγή
Στον τομέα της διαχείρισης έργων, η αποτελεσματική οργάνωση εργασιών είναι ζωτικής σημασίας. Το Aspose.Tasks για Java παρέχει μια ισχυρή λύση για την αποτελεσματική διαχείριση των εργασιών γονέα και παιδιού. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία χρήσης του Aspose.Tasks για Java για τον εξορθολογισμό των εργασιών του έργου σας.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασική κατανόηση προγραμματισμού Java.
-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Tasks για Java. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/java/).
- Ένα Java Integrated Development Environment (IDE) που έχει ρυθμιστεί στο σύστημά σας.
## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java. Αυτά τα πακέτα διευκολύνουν την απρόσκοπτη ενσωμάτωση με τις λειτουργίες Aspose.Tasks για Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Βήμα 1: Ορίστε την ημερομηνία έναρξης του έργου
Ξεκινήστε ορίζοντας την ημερομηνία έναρξης του έργου και άλλες σχετικές παραμέτρους.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Πρόσθετος κωδικός για εισαγωγές πακέτων μπορεί να προστεθεί εδώ
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Βήμα 2: Προσθήκη γονικής εργασίας (Εργασία 1)
Δημιουργήστε μια γονική εργασία με το όνομα "Εργασία 1" και διαμορφώστε τις ιδιότητές της.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Βήμα 3: Προσθήκη Parent Task (Εργασία 2) με Child Tasks
Τώρα, προσθέστε μια άλλη γονική εργασία με το όνομα "Εργασία 2" και συμπεριλάβετε θυγατρικές εργασίες (Εργασία 3 και Εργασία 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Προσθήκη θυγατρικών εργασιών στην Εργασία 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Πρόσθετες ρυθμίσεις παραμέτρων για το Task 3 και το Task 4 μπορούν να προστεθούν εδώ
```
## Βήμα 4: Διαμόρφωση Child Tasks
Καθορίστε ημερομηνίες έναρξης, διάρκειες και περιορισμούς για την Εργασία 3 και την Εργασία 4.
```java
// Διαμόρφωση Εργασίας 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Διαμόρφωση Εργασίας 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Βήμα 5: Ενημερώστε το ποσοστό ολοκλήρωσης εργασιών
Προσαρμόστε το ποσοστό ολοκλήρωσης για την Εργασία 3 και την Εργασία 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Βήμα 6: Αποθηκεύστε το έργο
Τέλος, αποθηκεύστε το έργο με τις αλλαγές που εφαρμόστηκαν.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Αυτός ο οδηγός βήμα προς βήμα δείχνει πώς να διαχειριστείτε αποτελεσματικά τις εργασίες γονέα και παιδιού χρησιμοποιώντας το Aspose.Tasks για Java. Πειραματιστείτε με διαφορετικές διαμορφώσεις που ταιριάζουν στις απαιτήσεις του έργου σας.
## συμπέρασμα
Συμπερασματικά, το Aspose.Tasks για Java δίνει στους προγραμματιστές τη δυνατότητα να χειρίζονται αποτελεσματικά τις εργασίες του έργου, διασφαλίζοντας απρόσκοπτη οργάνωση και παρακολούθηση. Εφαρμόστε τα βήματα που περιγράφονται για να βελτιώσετε τις δυνατότητες διαχείρισης του έργου σας.
## Συχνές ερωτήσεις
### Είναι το Aspose.Tasks για Java συμβατό με διαφορετικές μορφές αρχείων έργου;
Ναι, το Aspose.Tasks για Java υποστηρίζει διάφορες μορφές αρχείων έργου, συμπεριλαμβανομένων MPP και XML.
### Μπορώ να προσαρμόσω τις ιδιότητες της εργασίας πέρα από αυτό που καλύπτεται σε αυτό το σεμινάριο;
Απολύτως! Το Aspose.Tasks για Java παρέχει εκτενείς επιλογές προσαρμογής για ιδιότητες εργασιών.
### Υπάρχει κάποιο φόρουμ κοινότητας για το Aspose.Tasks όπου μπορώ να αναζητήσω υποστήριξη;
 Ναι, μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Tasks για Java;
 Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
