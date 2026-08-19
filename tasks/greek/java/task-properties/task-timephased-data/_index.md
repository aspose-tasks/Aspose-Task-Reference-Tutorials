---
date: 2026-02-28
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Tasks για Java για τη διαχείριση
  δεδομένων χρονικής φάσης των εργασιών, κατεβάστε τη βιβλιοθήκη, δοκιμάστε το δωρεάν
  και βελτιώστε την παρακολούθηση του έργου.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να χρησιμοποιήσετε το Aspose.Tasks για τη διαχείριση δεδομένων εργασιών
  χρονικής φάσης (Java)
url: /el/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε το Aspose.Tasks για δεδομένα εργασιών με χρονοδιάγραμμα

## Εισαγωγή
Αν ψάχνετε για **πώς να χρησιμοποιήσετε το Aspose** ώστε να έχετε πλήρη έλεγχο στο χρονοδιάγραμμα του έργου σας, βρίσκεστε στο σωστό μέρος. Η ακριβής παρακολούθηση των δεδομένων εργασιών με χρονοδιάγραμμα αποτελεί θεμέλιο της επιτυχημένης διαχείρισης έργων, και το Aspose.Tasks for Java σας παρέχει τα εργαλεία για να αυτοματοποιήσετε αυτή τη διαδικασία. Σε αυτό το tutorial θα περάσουμε από ένα πλήρες, ολοκληρωμένο παράδειγμα που δείχνει πώς να χρησιμοποιήσετε το Aspose.Tasks για να δημιουργήσετε ένα έργο, να αναθέσετε πόρους, να ορίσετε βάσεις και τελικά να ανακτήσετε και να εμφανίσετε τα δεδομένα με χρονοδιάγραμμα.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “timephased data”;** Είναι δεδομένα που διασπώνται σε χρονικά διαστήματα (ημέρες, εβδομάδες, μήνες) που δείχνουν εργασία, κόστος ή εναπομείνασα εργασία κατά τη διάρκεια του χρονοδιαγράμματος του έργου.  
- **Ποια βιβλιοθήκη παρέχει αυτή τη δυνατότητα;** Aspose.Tasks for Java.  
- **Χρειάζομαι άδεια για να εκτελέσω το δείγμα;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται άδεια για παραγωγή.  
- **Ποια έκδοση της Java απαιτείται;** Java 8 ή νεότερη.  
- **Μπορώ να εξάγω τα αποτελέσματα σε Excel;** Ναι – μπορείτε να επαναλάβετε τη συλλογή `TimephasedData` και να γράψετε τις τιμές σε οποιαδήποτε μορφή χρειάζεστε.

## Τι είναι τα Δεδομένα Εργασίας με Χρονοδιάγραμμα;
Τα δεδομένα εργασίας με χρονοδιάγραμμα αντιπροσωπεύουν το ποσό εργασίας (ή κόστους) που έχει προγραμματιστεί για μια εργασία σε κάθε χρονική φέτα του ημερολογίου του έργου. Σας επιτρέπουν να δείτε πώς κατανέμεται η εργασία, να εντοπίσετε υπερπρογραμματισμό και να συγκρίνετε το προγραμματισμένο με το πραγματικό πρόοδο.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για τη διαχείριση δεδομένων με χρονοδιάγραμμα;
- **Πλήρης έλεγχος** – δημιουργία, τροποποίηση και ερώτηση πληροφοριών με χρονοδιάγραμμα προγραμματιστικά, χωρίς το άνοιγμα του Microsoft Project.  
- **Διαπλατφόρμα** – λειτουργεί σε οποιοδήποτε λειτουργικό σύστημα που υποστηρίζει Java.  
- **Χωρίς εξαρτήσεις COM** – ιδανικό για αυτοματοποίηση στο διακομιστή.  
- **Πλούσιο API** – υποστηρίζει βάσεις, καμπύλες εργασίας και προσαρμοσμένα πεδία έτοιμα προς χρήση.

## Προαπαιτούμενα
Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε:

- **Περιβάλλον Ανάπτυξης Java** – εγκατεστημένο JDK 8+ και ρυθμισμένο `JAVA_HOME`.  
- **Βιβλιοθήκη Aspose.Tasks for Java** – Κατεβάστε και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη [εδώ](https://releases.aspose.com/tasks/java/).  
- **Φάκελος Εγγράφων** – Ένας φάκελος στον υπολογιστή σας όπου θα διαβαστεί και θα γραφτεί το δείγμα αρχείου έργου (`project.xml`).

## Εισαγωγή Πακέτων
Στο έργο Java, εισάγετε τις απαραίτητες κλάσεις του Aspose.Tasks:

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

## Βήμα 1: Ορισμός Ημερομηνίας Έναρξης Έργου
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Επεξήγηση:* Δημιουργούμε μια παρουσία `Project`, αρχικοποιούμε ένα `Calendar` στην επιθυμητή ημερομηνία έναρξης και το αναθέτουμε στην ιδιότητα `START_DATE` του έργου.

## Βήμα 2: Ορισμός Εργασίας και Πόρου
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Επεξήγηση:* Προστίθεται μια νέα εργασία με όνομα **Task** κάτω από τη ρίζα. Δημιουργούμε επίσης έναν πόρο με όνομα **Rsc** και ορίζουμε τα τυπικά και υπερωριακά του ποσοστά.

## Βήμα 3: Ορισμός Διάρκειας Εργασίας
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Επεξήγηση:* Η εργασία προγραμματίζεται για διάρκεια **6 ημερών**.

## Βήμα 4: Ανάθεση Πόρου στην Εργασία
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Επεξήγηση:* Ο προηγουμένως ορισμένος πόρος συνδέεται με την εργασία μέσω ενός `ResourceAssignment`.

## Βήμα 5: Διαμόρφωση Ανάθεσης Πόρου
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Επεξήγηση:* Ορίζουμε τις ημερομηνίες διακοπής και συνέχειας της ανάθεσης (χρησιμοποιώντας μια placeholder τιμή) και εφαρμόζουμε μια καμπύλη εργασίας **Back‑Loaded**, η οποία μετατοπίζει περισσότερη εργασία προς το τέλος της ανάθεσης.

## Βήμα 6: Ορισμός Βάσης
```java
project.setBaseline(BaselineType.Baseline);
```
*Επεξήγηση:* Η λήψη μιας βάσης σας επιτρέπει να συγκρίνετε τις προγραμματισμένες τιμές με τις πραγματικές αργότερα.

## Βήμα 7: Ενημέρωση Ολοκλήρωσης Εργασίας
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Επεξήγηση:* Η εργασία σημειώνεται ως **50 % ολοκληρωμένη**, κάτι που επηρεάζει τους υπολογισμούς εναπομείνασας εργασίας.

## Βήμα 8: Ανάκτηση Δεδομένων με Χρονοδιάγραμμα
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Επεξήγηση:* Αυτή η κλήση εξάγει την **εναπομείνασα εργασία** για την ανάθεση, διασπασμένη ανά χρονικά διαστήματα του έργου.

## Βήμα 9: Εμφάνιση Δεδομένων με Χρονοδιάγραμμα
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Επεξήγηση:* Εκτυπώνουμε απλώς τον αριθμό των καταχωρίσεων με χρονοδιάγραμμα και την τιμή της πρώτης καταχώρισης. Σε πραγματικό σενάριο θα επαναλαμβάνατε τη λίστα και θα εξάγετε τα δεδομένα σε αναφορά ή UI.

## Κοινά Προβλήματα και Λύσεις
- **NullPointerException στο `getTimephasedData`** – Βεβαιωθείτε ότι οι ημερομηνίες `START` και `FINISH` της ανάθεσης έχουν οριστεί πριν καλέσετε τη μέθοδο.  
- **Λανθασμένη καμπύλη εργασίας** – Επαληθεύστε ότι το `WorkContourType` που επιλέγετε ταιριάζει με τη στρατηγική χρονοπρογραμματισμού· το `BackLoaded` είναι μόνο μία από τις πολλές επιλογές.  
- **Η βάση δεν αντανακλά τις αλλαγές** – Θυμηθείτε να καλέσετε `project.setBaseline` *μετά* τον ορισμό των εργασιών, των πόρων και των αναθέσεων.

## Συχνές Ερωτήσεις
### Μ: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java σε οποιοδήποτε έργο Java;
Α: Ναι, το Aspose.Tasks for Java είναι συμβατό με οποιοδήποτε έργο βασισμένο σε Java.

### Μ: Πού μπορώ να βρω πρόσθετη υποστήριξη για το Aspose.Tasks for Java;
Α: Επισκεφθείτε το [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) για υποστήριξη και συζητήσεις.

### Μ: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Tasks for Java;
Α: Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

### Μ: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks for Java;
Α: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Μ: Πού μπορώ να αγοράσω το Aspose.Tasks for Java;
Α: Μπορείτε να αγοράσετε το Aspose.Tasks for Java [εδώ](https://purchase.aspose.com/buy).

---

**Τελευταία ενημέρωση:** 2026-02-28  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}