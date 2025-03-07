---
title: Δεδομένα χρονικής φάσης εργασιών στο Aspose.Tasks
linktitle: Δεδομένα χρονικής φάσης εργασιών στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Εξερευνήστε το Aspose.Tasks για Java και κύριες εργασίες διαχείρισης δεδομένων σε χρονική φάση. Κατεβάστε τη βιβλιοθήκη, απολαύστε μια δωρεάν δοκιμή και βελτιστοποιήστε την παρακολούθηση του έργου σας.
weight: 34
url: /el/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δεδομένα χρονικής φάσης εργασιών στο Aspose.Tasks

## Εισαγωγή
Στον τομέα της διαχείρισης έργου, η ακριβής παρακολούθηση των δεδομένων χρονικής φάσης εργασιών είναι ζωτικής σημασίας για την αποτελεσματική εκτέλεση του έργου. Το Aspose.Tasks για Java αναδεικνύεται ως ένα ισχυρό εργαλείο για τον εξορθολογισμό αυτής της διαδικασίας, προσφέροντας ισχυρές δυνατότητες και ευελιξία. Αυτό το σεμινάριο θα σας καθοδηγήσει στη χρήση του Aspose.Tasks για Java για την αποτελεσματική διαχείριση των δεδομένων χρονικής φάσης εργασιών.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας.
-  Aspose.Tasks for Java Library: Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη[εδώ](https://releases.aspose.com/tasks/java/).
- Κατάλογος εγγράφων: Ρυθμίστε έναν κατάλογο για τα έγγραφα του έργου σας.
## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα για το Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Βήμα 1: Ορίστε την ημερομηνία έναρξης του έργου
```java
Project project = new Project(dataDir + "project.xml");
// Πρόσθετος κωδικός για εισαγωγές πακέτων
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Επεξήγηση: Αρχικοποιήστε ένα αντικείμενο ημερολογίου, ορίστε την ημερομηνία έναρξης και εφαρμόστε το στο έργο.
## Βήμα 2: Καθορισμός Εργασίας και Πόρων
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Επεξήγηση: Δημιουργήστε μια εργασία και έναν πόρο, ορίζοντας ποσοστά για τυπικές και υπερωρίες.
## Βήμα 3: Ορίστε τη διάρκεια εργασίας
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Επεξήγηση: Καθορίστε τη διάρκεια της εργασίας (π.χ. 6 ημέρες).
## Βήμα 4: Εκχώρηση πόρου στην εργασία
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Επεξήγηση: Αναθέστε τον πόρο στην εργασία.
## Βήμα 5: Διαμόρφωση εκχώρησης πόρων
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Επεξήγηση: Ορίστε παραμέτρους όπως διακοπή, συνέχιση και περίγραμμα εργασίας για την εκχώρηση πόρων.
## Βήμα 6: Ορίστε τη γραμμή βάσης
```java
project.setBaseline(BaselineType.Baseline);
```
Εξήγηση: Καθορίστε μια γραμμή βάσης για το έργο.
## Βήμα 7: Ενημερώστε την Ολοκλήρωση Εργασίας
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Επεξήγηση: Αναφέρετε το ποσοστό ολοκλήρωσης της εργασίας.
## Βήμα 8: Ανάκτηση δεδομένων χρονικής φάσης
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Επεξήγηση: Ανάκτηση δεδομένων χρονικής φάσης για την ανάθεση εργασίας που απομένει.
## Βήμα 9: Εμφάνιση δεδομένων χρονικής φάσης
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Πρόσθετος κωδικός για την εμφάνιση άλλων τιμών
```
Επεξήγηση: Εξαγωγή και εμφάνιση των δεδομένων χρονικής φάσης.
## συμπέρασμα
Η αποτελεσματική διαχείριση των δεδομένων χρονικής φάσης εργασιών είναι απαραίτητη για την επιτυχία του έργου. Το Aspose.Tasks για Java απλοποιεί αυτή τη διαδικασία, παρέχοντας ένα ολοκληρωμένο σύνολο λειτουργιών. Ακολουθώντας αυτό το σεμινάριο, μπορείτε να ενσωματώσετε απρόσκοπτα το Aspose.Tasks στο έργο σας Java, διασφαλίζοντας ακριβή έλεγχο στα χρονοδιαγράμματα του έργου και την κατανομή πόρων.
## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java σε οποιοδήποτε έργο Java;
Α: Ναι, το Aspose.Tasks για Java είναι συμβατό με οποιοδήποτε έργο που βασίζεται σε Java.
### Ε: Πού μπορώ να βρω πρόσθετη υποστήριξη για το Aspose.Tasks για Java;
 Α: Επισκεφθείτε το[Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) για υποστήριξη και συζητήσεις.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Tasks για Java;
 Α: Μπορείτε να αποκτήσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να αγοράσω το Aspose.Tasks για Java;
 Α: Μπορείτε να αγοράσετε Aspose.Tasks για Java[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
