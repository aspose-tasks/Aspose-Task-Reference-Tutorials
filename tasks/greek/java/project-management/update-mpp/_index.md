---
title: Ενημερώστε το αρχείο MPP στο Aspose.Tasks
linktitle: Ενημερώστε το αρχείο MPP στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ενημερώνετε τα αρχεία MPP απρόσκοπτα χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για αποτελεσματική διαχείριση αρχείων έργου.
weight: 19
url: /el/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ενημερώστε το αρχείο MPP στο Aspose.Tasks

## Εισαγωγή
Στον τομέα της διαχείρισης έργων, ο χειρισμός και η ενημέρωση των αρχείων του έργου είναι ένα κρίσιμο έργο. Το Aspose.Tasks για Java παρέχει μια ισχυρή λύση για προγραμματιστές Java για τον απρόσκοπτο χειρισμό των αρχείων του Microsoft Project. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στην ενημέρωση αρχείων MPP χρησιμοποιώντας το Aspose.Tasks για Java.
## Προαπαιτούμενα
Πριν προχωρήσετε σε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
1. Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας.
2.  Aspose.Tasks για Java: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για Java από το[σελίδα λήψης](https://releases.aspose.com/tasks/java/).
3. Βασικές γνώσεις Java: Η εξοικείωση με τη γλώσσα προγραμματισμού Java είναι απαραίτητη για να ακολουθήσει μαζί με τα παραδείγματα.

## Εισαγωγή πακέτων
Πρώτον, πρέπει να εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java για να χρησιμοποιήσετε αποτελεσματικά τις λειτουργίες του Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Αυτή η γραμμή κώδικα εισάγει όλες τις βασικές κλάσεις και μεθόδους από τη βιβλιοθήκη Aspose.Tasks, επιτρέποντάς σας να εργάζεστε με αρχεία Microsoft Project χωρίς κόπο.

Τώρα, ας αναλύσουμε τη διαδικασία ενημέρωσης ενός αρχείου MPP χρησιμοποιώντας το Aspose.Tasks για Java σε διαχειρίσιμα βήματα.
## Βήμα 2: Ορισμός καταλόγου δεδομένων
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με την πραγματική διαδρομή όπου βρίσκεται το αρχείο MPP.
## Βήμα 3: Διαβάστε το υπάρχον έργο
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Αυτός ο κώδικας διαβάζει ένα υπάρχον αρχείο έργου MPP με το όνομα`SampleMSP2010.mpp` από τον καθορισμένο κατάλογο δεδομένων.
## Βήμα 4: Δημιουργήστε μια νέα εργασία
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Εδώ, προσθέτουμε μια νέα εργασία με το όνομα "Task1" στη βασική εργασία του έργου.
## Βήμα 5: Ορίστε ημερομηνίες έναρξης και λήξης
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Αυτές οι γραμμές κώδικα ορίζουν την ημερομηνία έναρξης και την ημερομηνία λήξης για τη νέα εργασία.
## Βήμα 6: Αποθηκεύστε το έργο
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Τέλος, αυτό το βήμα αποθηκεύει το ενημερωμένο έργο με την εργασία που προστέθηκε πρόσφατα σε ένα νέο αρχείο MPP με το όνομα`AfterLinking.mpp`.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο ενημέρωσης αρχείων MPP χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να χειριστείτε αποτελεσματικά τα αρχεία του Microsoft Project στις εφαρμογές σας Java.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks για Java να χειριστεί περίπλοκες δομές έργου;
Α: Ναι, το Aspose.Tasks για Java παρέχει ισχυρές δυνατότητες για αποτελεσματικό χειρισμό σύνθετων δομών έργων.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από το[δικτυακός τόπος](https://releases.aspose.com/).
### Ε: Το Aspose.Tasks για Java υποστηρίζει διαφορετικές εκδόσεις αρχείων Microsoft Project;
Α: Απολύτως, το Aspose.Tasks για Java υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.
### Ε: Μπορώ να λάβω προσωρινές άδειες για το Aspose.Tasks για Java;
 Α: Ναι, διατίθενται προσωρινές άδειες για δοκιμαστικούς σκοπούς. Μπορείτε να τα προμηθευτείτε από το[σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να αναζητήσω βοήθεια ή υποστήριξη σχετικά με το Aspose.Tasks για Java;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή απορία.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
