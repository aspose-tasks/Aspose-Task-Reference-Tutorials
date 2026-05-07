---
date: 2026-02-23
description: Μάθετε πώς να ορίζετε την ημερομηνία έναρξης του έργου, τη διάρκεια της
  εργασίας και να αποθηκεύετε το έργο ως MPP χρησιμοποιώντας το Aspose.Tasks for Java.
  Διαχειριστείτε αποτελεσματικά τις γονικές και θυγατρικές εργασίες.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ορίστε την ημερομηνία έναρξης του έργου και διαχειριστείτε τις γονικές και
  θυγατρικές εργασίες στο Aspose.Tasks
url: /el/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Ημερομηνίας Έναρξης Έργου και Διαχείριση Γονικών και Πατρικών Εργασιών στο Aspose.Tasks

## Εισαγωγή
Η αποτελεσματική οργάνωση των εργασιών αποτελεί τη ραχοκοκαλιά της επιτυχούς διαχείρισης έργων, και η **ρύθμιση της ημερομηνίας έναρξης του έργου** σωστά είναι το πρώτο βήμα προς ένα καλά δομημένο χρονοδιάγραμμα. Σε αυτό το σεμινάριο θα δείτε πώς να **ορίσετε την ημερομηνία έναρξης του έργου**, να διαμορφώσετε τις διάρκειες των εργασιών και να διαχειριστείτε τις σχέσεις γονέα‑παιδί χρησιμοποιώντας το Aspose.Tasks for Java. Στο τέλος, θα είστε έτοιμοι να **αποθηκεύσετε το έργο ως MPP**, να ενημερώσετε τα ποσοστά ολοκλήρωσης των εργασιών και να προσαρμόσετε τις ιδιότητες των εργασιών ώστε να ταιριάζουν σε οποιοδήποτε πραγματικό σενάριο.

## Γρήγορες Απαντήσεις
- **Πώς ορίζω την ημερομηνία έναρξης του έργου;** Χρησιμοποιήστε `proj.set(Prj.START_DATE, startDate);` μετά την αρχικοποίηση του αντικειμένου `Project`.  
- **Μπορώ να προσθέσω παιδικές εργασίες κάτω από μια γονική εργασία;** Ναι – καλέστε `parentTask.getChildren().add("Child Task")`.  
- **Σε ποια μορφή αποθηκεύει το Aspose.Tasks το αρχείο;** Χρησιμοποιήστε `SaveFileFormat.Mpp` για να **αποθηκεύσετε το έργο ως MPP**.  
- **Πώς ενημερώνω την ολοκλήρωση της εργασίας;** Ορίστε `Tsk.PERCENT_COMPLETE` στο αντικείμενο της εργασίας.  
- **Πού μπορώ να αποκτήσω προσωρινή άδεια;** Επισκεφθείτε τη σελίδα προσωρινής άδειας που συνδέεται στις Συχνές Ερωτήσεις.

## Προαπαιτούμενα
Πριν βυθιστείτε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
- Βασική κατανόηση του προγραμματισμού Java.  
- Εγκατεστημένη η βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να τη κατεβάσετε [εδώ](https://releases.aspose.com/tasks/java/).  
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) για Java εγκατεστημένο στο σύστημά σας.

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, εισάγετε τα απαραίτητα πακέτα στο έργο Java σας. Αυτά τα πακέτα διευκολύνουν την απρόσκοπτη ενσωμάτωση των λειτουργιών του Aspose.Tasks for Java.
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

## Βήμα 1: Ορισμός Ημερομηνίας Έναρξης Έργου
Ξεκινήστε ορίζοντας την ημερομηνία έναρξης του έργου και άλλες σχετικές παραμέτρους.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Βήμα 2: Προσθήκη Γονικής Εργασίας (Task 1)
Δημιουργήστε μια γονική εργασία με όνομα "Task 1" και διαμορφώστε τις ιδιότητές της, συμπεριλαμβανομένου του **ορισμού διάρκειας εργασίας**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Βήμα 3: Προσθήκη Γονικής Εργασίας (Task 2) με Παιδικές Εργασίες
Τώρα, προσθέστε μια άλλη γονική εργασία με όνομα "Task 2" και συμπεριλάβετε παιδικές εργασίες (Task 3 και Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Βήμα 4: Διαμόρφωση Παιδικών Εργασιών
Καθορίστε τις ημερομηνίες έναρξης, τις διάρκειες και τους περιορισμούς για τις εργασίες Task 3 και Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Βήμα 5: Ενημέρωση Ποσοστού Ολοκλήρωσης Εργασίας
Ρυθμίστε το ποσοστό ολοκλήρωσης για τις εργασίες Task 3 και Task 4 – αυτός είναι ο τρόπος για να **ενημερώσετε την ολοκλήρωση της εργασίας**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Βήμα 6: Αποθήκευση του Έργου
Τέλος, **αποθηκεύστε το έργο ως MPP** με τις εφαρμοσμένες αλλαγές.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να διαχειρίζεστε αποτελεσματικά γονικές και παιδικές εργασίες χρησιμοποιώντας το Aspose.Tasks for Java. Πειραματιστείτε με διαφορετικές ρυθμίσεις ώστε να ταιριάζουν στις απαιτήσεις του έργου σας.

## Γιατί να Προσαρμόσετε τις Ιδιότητες των Εργασιών;
Η προσαρμογή των ιδιοτήτων των εργασιών, όπως οι ημερομηνίες έναρξης, οι διάρκειες, οι περιορισμοί και τα ποσοστά ολοκλήρωσης, σας δίνει λεπτομερή έλεγχο της συμπεριφοράς του χρονοδιαγράμματος. Είτε χρειάζεται να ευθυγραμμίσετε τις εργασίες με τη διαθεσιμότητα πόρων είτε να επιβάλετε επιχειρηματικούς κανόνες, το Aspose.Tasks σας επιτρέπει να **προσαρμόσετε τις ιδιότητες των εργασιών** προγραμματιστικά.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|-------|----------|
| **Η ημερομηνία έναρξης δεν εφαρμόζεται** | Βεβαιωθείτε ότι καλείτε `proj.set(Prj.START_DATE, …)` **μετά** τη δημιουργία του αντικειμένου `Project` και πριν προσθέσετε εργασίες. |
| **Οι παιδικές εργασίες κληρονομούν λανθασμένους περιορισμούς** | Ορίστε ρητά το `ConstraintType` και το `ConstraintDate` για κάθε παιδική εργασία, όπως φαίνεται στο Βήμα 4. |
| **Το αποθηκευμένο αρχείο δεν μπορεί να ανοιχτεί στο MS Project** | Επικυρώστε ότι χρησιμοποιείτε την πιο πρόσφατη έκδοση του Aspose.Tasks και αποθηκεύστε με `SaveFileFormat.Mpp`. |
| **Το ποσοστό δεν εμφανίζεται στη διεπαφή χρήστη** | Μετά τον ορισμό του `Tsk.PERCENT_COMPLETE`, καλέστε `proj.calculateTaskSchedule()` εάν χρειάζεστε επανυπολογισμένες ημερομηνίες. |

## Συχνές Ερωτήσεις
### Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές μορφές αρχείων έργου;
Ναι, το Aspose.Tasks for Java υποστηρίζει διάφορες μορφές αρχείων έργου, συμπεριλαμβανομένων των MPP και XML.

### Μπορώ να προσαρμόσω τις ιδιότητες των εργασιών πέρα από ό,τι καλύπτεται σε αυτό το σεμινάριο;
Απολύτως! Το Aspose.Tasks for Java παρέχει εκτενείς επιλογές προσαρμογής για τις ιδιότητες των εργασιών.

### Υπάρχει φόρουμ κοινότητας για το Aspose.Tasks όπου μπορώ να ζητήσω υποστήριξη;
Ναι, μπορείτε να επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για υποστήριξη από την κοινότητα.

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks for Java;
Μπορείτε να αποκτήσετε μια προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση για το Aspose.Tasks for Java;
Η τεκμηρίωση είναι διαθέσιμη [εδώ](https://reference.aspose.com/tasks/java/).

**Πρόσθετες Ερωτήσεις & Απαντήσεις**

**Q: Πώς μπορώ προγραμματιστικά να αποκτήσω μια προσωρινή άδεια;**  
A: Φορτώστε το αρχείο προσωρινής άδειας χρησιμοποιώντας `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Μπορώ να αλλάξω τη προεπιλεγμένη μονάδα διάρκειας εργασίας;**  
A: Ναι – τροποποιήστε το όρισμα `TimeUnitType` στο `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: Ποια έκδοση του Aspose.Tasks απαιτείται για τη χρήση του `SaveFileFormat.Mpp`;**  
A: Όλες οι πρόσφατες εκδόσεις (2022‑2026) υποστηρίζουν την αποθήκευση ως MPP· ελέγξτε τις σημειώσεις έκδοσης για τυχόν αλλαγές που διακόπτουν τη λειτουργία.

---

**Τελευταία Ενημέρωση:** 2026-02-23  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}