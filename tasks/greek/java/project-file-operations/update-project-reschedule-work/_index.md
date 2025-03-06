---
title: Ενημέρωση & Επαναπρογραμματισμός Έργου MS στο Aspose.Tasks
linktitle: Ενημέρωση έργου και επαναπρογραμματισμός μη ολοκληρωμένης εργασίας στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ενημερώνετε και να επαναπρογραμματίζετε τα αρχεία MS Project μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για Java.
weight: 23
url: /el/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ενημέρωση & Επαναπρογραμματισμός Έργου MS στο Aspose.Tasks

## Εισαγωγή
Το Microsoft Project είναι ένα ευρέως χρησιμοποιούμενο λογισμικό διαχείρισης έργων που επιτρέπει στους χρήστες να διαχειρίζονται αποτελεσματικά εργασίες, πόρους και χρονοδιαγράμματα. Το Aspose.Tasks για Java παρέχει ένα ισχυρό σύνολο API για το χειρισμό αρχείων Microsoft Project μέσω προγραμματισμού. Σε αυτό το σεμινάριο, θα μάθουμε πώς να ενημερώνουμε τα αρχεία του MS Project και να επαναπρογραμματίζουμε ανολοκλήρωτες εργασίες χρησιμοποιώντας το Aspose.Tasks για Java.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Aspose.Tasks για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Βασική κατανόηση της γλώσσας προγραμματισμού Java.

## Εισαγωγή πακέτων
Πρώτα, εισαγάγετε τα απαραίτητα πακέτα στον κώδικα Java σας:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Βήμα 1: Ρύθμιση του έργου
Αρχικοποιήστε ένα νέο αντικείμενο Project και ορίστε εργασίες μέσα σε αυτό μαζί με τις διάρκειες και τις εξαρτήσεις τους.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Καθορίστε τις εργασίες και τη διάρκειά τους
// ...
// Καθορίστε τις εξαρτήσεις εργασιών
// ...
// Αποθηκεύστε την αρχική κατάσταση του έργου
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Βήμα 2: Ενημερώστε την εργασία έργου
Ενημερώστε την εργασία του έργου για να την επισημάνετε ως ολοκληρωμένη μέχρι μια συγκεκριμένη ημερομηνία.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Αποθηκεύστε το ενημερωμένο έργο
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Βήμα 3: Επαναπρογραμματισμός μη ολοκληρωμένης εργασίας
Προγραμματίστε εκ νέου οποιαδήποτε μη ολοκληρωμένη εργασία για να ξεκινήσει μετά από μια καθορισμένη ημερομηνία.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Αποθηκεύστε το επαναπρογραμματισμένο έργο
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ενημερώνουμε τα αρχεία του MS Project και να επαναπρογραμματίζουμε τις μη ολοκληρωμένες εργασίες χρησιμοποιώντας το Aspose.Tasks για Java. Αυτό μπορεί να είναι ιδιαίτερα χρήσιμο σε σενάρια όπου τα χρονοδιαγράμματα του έργου χρειάζονται προσαρμογή με βάση την πρόοδο ή την αλλαγή προτεραιοτήτων.

## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks για Java να χειριστεί περίπλοκες δομές έργου;
Α: Ναι, το Aspose.Tasks για Java παρέχει ισχυρά API για την αποτελεσματική διαχείριση εργασιών, εξαρτήσεων, πόρων και άλλων στοιχείων έργου.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή απορία.
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Α: Ναι, οι προσωρινές άδειες είναι διαθέσιμες για αγορά[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks για Java;
 Α: Μπορείτε να ανατρέξετε στην τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/java/) για αναλυτικούς οδηγούς και αναφορές API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
