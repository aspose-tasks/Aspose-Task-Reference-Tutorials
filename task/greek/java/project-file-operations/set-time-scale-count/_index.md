---
title: Mastering MS Project Time Scale Count στο Aspose.Tasks
linktitle: Ορισμός μέτρησης κλίμακας χρόνου στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τον αριθμό της κλίμακας χρόνου στο MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιστοποιήστε την οπτικοποίηση και τη διαχείριση του έργου χωρίς κόπο.
type: docs
weight: 22
url: /el/java/project-file-operations/set-time-scale-count/
---
## Εισαγωγή
Η διαχείριση του πλήθους χρονικής κλίμακας στο MS Project μπορεί να επηρεάσει σημαντικά την οπτικοποίηση και τη διαχείριση του έργου. Με το Aspose.Tasks για Java, ένα ισχυρό API για προγραμματισμό χειρισμού εργασιών διαχείρισης έργου, μπορείτε να χειριστείτε αποτελεσματικά τον αριθμό της κλίμακας χρόνου για να προσαρμόσετε τις προβολές του έργου στις συγκεκριμένες ανάγκες σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
1. Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε εγκατεστημένο το Java Development Kit (JDK) στο σύστημά σας.
2.  Aspose.Tasks for Java Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να το πάρετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Βασικές γνώσεις προγραμματισμού Java: Η εξοικείωση με τη γλώσσα προγραμματισμού Java θα είναι επωφελής.

## Εισαγωγή πακέτων
Εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Βήμα 1: Ορισμός καταλόγου δεδομένων
Καθορίστε τη διαδρομή προς τον κατάλογο δεδομένων όπου θα αποθηκευτούν τα αρχεία του έργου σας:
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με τη διαδρομή προς τον κατάλογο δεδομένων σας.
## Βήμα 2: Δημιουργία παρουσίας έργου
 Δημιουργήστε ένα νέο`Project` αντικείμενο:
```java
Project project = new Project();
```
Αυτό δημιουργεί ένα νέο αντικείμενο έργου.
## Βήμα 3: Διαμορφώστε την προβολή γραφήματος Gantt
 Δημιουργώ ένα`GanttChartView` αντικείμενο για τη διαμόρφωση της προβολής γραφήματος Gantt:
```java
GanttChartView view = new GanttChartView();
```
## Βήμα 4: Ορισμός μέτρησης κλίμακας χρόνου για το κατώτερο επίπεδο
Ορίστε την ορατότητα του πλήθους και των τικ για το κατώτερο επίπεδο χρονικής κλίμακας:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Αυτό καθορίζει το πλήθος των διαστημάτων και αν θα εμφανιστούν τικ για την κάτω βαθμίδα.
## Βήμα 5: Ορισμός μέτρησης χρονικής κλίμακας για τη μεσαία βαθμίδα
Ομοίως, διαμορφώστε τη μεσαία βαθμίδα χρονικής κλίμακας:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Βήμα 6: Προσθήκη προβολής στο έργο
Προσθέστε τη διαμορφωμένη προβολή στο έργο:
```java
project.getViews().add(view);
```
Αυτό προσθέτει την προσαρμοσμένη προβολή στο έργο.
## Βήμα 7: Προσθήκη δεδομένων δοκιμής στο Project
Προσθέστε μερικά δεδομένα δοκιμής στο έργο για επίδειξη:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Αυτό δημιουργεί δύο εργασίες με καθορισμένη διάρκεια.
## Βήμα 8: Αποθήκευση έργου ως PDF
Αποθηκεύστε το έργο ως αρχείο PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Αυτό αποθηκεύει το έργο με τις εφαρμοσμένες διαμορφώσεις σε ένα αρχείο PDF.

## συμπέρασμα
Η αποτελεσματική διαχείριση του πλήθους χρονικής κλίμακας στο MS Project χρησιμοποιώντας το Aspose.Tasks για Java σάς δίνει τη δυνατότητα να προσαρμόσετε τις προβολές του έργου για καλύτερη οπτικοποίηση και διαχείριση.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks για Java να χειριστεί αρχεία έργων μεγάλης κλίμακας;
Α: Ναι, το Aspose.Tasks για Java είναι σε θέση να χειρίζεται αποτελεσματικά αρχεία έργων μεγάλης κλίμακας.
### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικά Java IDE;
Α: Ναι, το Aspose.Tasks για Java λειτουργεί άψογα με δημοφιλή Java Integrated Development Environments (IDE) όπως το Eclipse και το IntelliJ IDEA.
### Ε: Μπορώ να προσαρμόσω την εμφάνιση των διαγραμμάτων Gantt χρησιμοποιώντας το Aspose.Tasks για Java;
Α: Απολύτως, το Aspose.Tasks για Java παρέχει εκτεταμένες δυνατότητες για την προσαρμογή της εμφάνισης των διαγραμμάτων Gantt σύμφωνα με τις απαιτήσεις σας.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμαστική έκδοση από[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
 Α: Μπορείτε να βρείτε υποστήριξη και βοήθεια στο φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).