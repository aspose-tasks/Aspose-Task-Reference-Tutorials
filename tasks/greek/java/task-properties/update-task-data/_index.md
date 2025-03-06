---
title: Ενημερώστε τα δεδομένα εργασιών σε μορφή MPP στο Aspose.Tasks
linktitle: Ενημερώστε τα δεδομένα εργασιών σε μορφή MPP στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ενημερώνετε τα δεδομένα εργασιών σε μορφή MPP χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για αποτελεσματική διαχείριση έργου.
weight: 35
url: /el/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ενημερώστε τα δεδομένα εργασιών σε μορφή MPP στο Aspose.Tasks

## Εισαγωγή
Καλώς ήρθατε στον αναλυτικό οδηγό μας για την ενημέρωση των δεδομένων εργασιών σε μορφή MPP χρησιμοποιώντας το Aspose.Tasks για Java. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία, διασφαλίζοντας ότι καταλαβαίνετε κάθε βήμα με σαφήνεια. Το Aspose.Tasks για Java παρέχει μια ισχυρή λύση για εργασία με αρχεία Microsoft Project και μέχρι το τέλος αυτού του οδηγού, θα μπορείτε να ενημερώνετε αποτελεσματικά τα δεδομένα εργασιών σε μορφή MPP.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Aspose.Tasks για Java: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Tasks. Μπορείτε να το κατεβάσετε από το[σελίδα έκδοσης](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας.
- Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Χρησιμοποιήστε ένα IDE της επιλογής σας για την ανάπτυξη Java.
## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο σας Java. Το ακόλουθο απόσπασμα δείχνει τον τρόπο εισαγωγής πακέτων:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Δημιουργήστε και διαμορφώστε την αρχική εργασία
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Συνέχεια με τον υπόλοιπο κώδικα)
```
## 2. Ορίστε την ημερομηνία έναρξης και τη διάρκεια
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Συνέχεια με τον υπόλοιπο κώδικα)
```
## 3. Δημιουργήστε μια εργασία σύνοψης
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Συνέχεια με τον υπόλοιπο κώδικα)
```
## 4. Ορίστε Σημειώσεις προθεσμίας και εργασιών
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Συνέχεια με τον υπόλοιπο κώδικα)
```
## 5. Ρυθμίστε τους περιορισμούς εργασιών
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Συνέχεια με τον υπόλοιπο κώδικα)
```
## 6. Δημιουργήστε πρόσθετες εργασίες
```java
//Δημιουργήστε 10 νέες εργασίες
for (int i = 0; i < 10; i++) {
    //... (Συνέχεια με τον υπόλοιπο κώδικα)
}
//... (Συνέχεια με τον υπόλοιπο κώδικα)
```
## 7. Αποθηκεύστε το έργο
```java
// Αποθηκεύστε το έργο
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Ακολουθώντας αυτά τα βήματα, έχετε ενημερώσει με επιτυχία τα δεδομένα εργασιών σε μορφή MPP χρησιμοποιώντας το Aspose.Tasks για Java.
## συμπέρασμα
Συγχαρητήρια! Ολοκληρώσατε έναν ολοκληρωμένο οδηγό για την ενημέρωση των δεδομένων εργασιών σε μορφή MPP χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η ισχυρή βιβλιοθήκη απλοποιεί τις εργασίες διαχείρισης έργου, καθιστώντας την ένα πολύτιμο εργαλείο για προγραμματιστές Java.
## Συχνές ερωτήσεις
### Ε: Πού μπορώ να βρω την τεκμηρίωση Aspose.Tasks για Java;
 Α: Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/tasks/java/).
### Ε: Πώς μπορώ να κατεβάσω το Aspose.Tasks για Java;
 Α: Μπορείτε να το κατεβάσετε από το[σελίδα έκδοσης](https://releases.aspose.com/tasks/java/).
### Ε: Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Α: Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
 Α: Επισκεφτείτε το φόρουμ υποστήριξης[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Προσφέρετε προσωρινές άδειες για δοκιμαστικούς σκοπούς;
 Α: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
