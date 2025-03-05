---
title: Χειριστείτε τις ιδιότητες καθυστέρησης ισοπέδωσης στο Aspose.Tasks
linktitle: Χειριστείτε τις ιδιότητες καθυστέρησης ισοπέδωσης για αναθέσεις πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να χειρίζεστε τις ιδιότητες καθυστέρησης ισοπέδωσης για αναθέσεις πόρων στο Aspose.Tasks για Java με αυτό το ολοκληρωμένο σεμινάριο.
type: docs
weight: 17
url: /el/java/resource-assignments/leveling-delay-properties/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα περιηγηθούμε στη διαδικασία χειρισμού των ιδιοτήτων καθυστέρησης ισοπέδωσης για αναθέσεις πόρων στο Aspose.Tasks για Java. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που σας επιτρέπει να εργάζεστε με αρχεία Microsoft Project χωρίς να απαιτείται η εγκατάσταση του Microsoft Project στο σύστημά σας.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το Java JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε και να το εγκαταστήσετε από το[δικτυακός τόπος](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Κάντε λήψη της βιβλιοθήκης Aspose.Tasks for Java από το[σελίδα λήψης](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Πρώτα, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java για να χρησιμοποιήσετε τις λειτουργίες Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Βήμα 1: Δημιουργήστε ένα αντικείμενο έργου
 Στιγμιότυπο α`Project` αντικείμενο:
```java
Project prj = new Project();
```
## Βήμα 2: Δημιουργήστε μια εργασία
Προσθέστε μια εργασία στο έργο:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Βήμα 3: Ορίστε την ημερομηνία έναρξης της εργασίας και τη διάρκεια
Ορίστε την ημερομηνία έναρξης και τη διάρκεια για την εργασία:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Βήμα 4: Προσθέστε έναν πόρο
Προσθέστε έναν πόρο στο έργο:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Βήμα 5: Δημιουργήστε μια ανάθεση πόρων
Δημιουργήστε μια ανάθεση πόρων για την εργασία και τον πόρο:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Βήμα 6: Ρύθμιση καθυστέρησης ισοπέδωσης
Ορίστε την καθυστέρηση ισοπέδωσης για την εργασία:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Βήμα 7: Εμφάνιση αποτελεσμάτων
Εκτυπώστε την καθυστέρηση ισοπέδωσης και άλλες σχετικές πληροφορίες:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να χειριζόμαστε ιδιότητες καθυστέρησης ισοπέδωσης για αναθέσεις πόρων στο Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τις αναθέσεις πόρων στα έργα σας Java.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες βιβλιοθήκες Java;

Α: Ναι, το Aspose.Tasks μπορεί να ενσωματωθεί με άλλες βιβλιοθήκες Java για τη βελτίωση των δυνατοτήτων διαχείρισης έργου.

### Ε: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;

Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα.

### Ε: Πού μπορώ να βρω πρόσθετη υποστήριξη για το Aspose.Tasks;

 Α: Μπορείτε να βρείτε υποστήριξη και πόρους στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).

### Ε: Μπορώ να δοκιμάσω το Aspose.Tasks πριν από την αγορά;

 Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Tasks από το[σελίδα εκδόσεων](https://releases.aspose.com/).

### Ε: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Tasks;

 Α: Μπορείτε να ζητήσετε μια προσωρινή άδεια από το[σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/) για σκοπούς αξιολόγησης.