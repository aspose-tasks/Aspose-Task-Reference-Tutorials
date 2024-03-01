---
title: Διαχείριση διάρκειας εργασιών στο Aspose.Tasks
linktitle: Διαχείριση διάρκειας εργασιών στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Εξερευνήστε το Aspose.Tasks για Java και μάθετε να διαχειρίζεστε τη διάρκεια εργασιών χωρίς κόπο. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για αποτελεσματικό σχεδιασμό και εκτέλεση έργου.
type: docs
weight: 20
url: /el/java/task-properties/manage-durations/
---
## Εισαγωγή
Το Aspose.Tasks για Java παρέχει μια ισχυρή λύση για την αποτελεσματική διαχείριση των εργασιών και των διάρκειων του έργου. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να διαχειριστείτε τη διάρκεια των εργασιών χρησιμοποιώντας το Aspose.Tasks, καθοδηγώντας σας σε κάθε βήμα. Είτε είστε έμπειρος προγραμματιστής είτε αρχάριος, αυτός ο οδηγός θα σας βοηθήσει να κατανοήσετε τα βασικά στοιχεία της εργασίας με τη διάρκεια εργασιών στα έργα σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
-  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στον υπολογιστή σας. Μπορείτε να το κατεβάσετε[εδώ](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη[εδώ](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με το Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Βήμα 1: Ρύθμιση του έργου σας
```java
// Δημιουργήστε ένα νέο έργο
Project project = new Project();
```
## Βήμα 2: Προσθήκη νέας εργασίας
```java
// Προσθέστε μια νέα εργασία στο έργο
Task task = project.getRootTask().getChildren().add("Task");
```
## Βήμα 3: Λήψη και μετατροπή της διάρκειας εργασίας
```java
// Λάβετε τη διάρκεια εργασίας σε ημέρες (προεπιλεγμένη μονάδα χρόνου)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Μετατροπή διάρκειας σε μονάδα χρόνου ώρας
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Βήμα 4: Ενημερώστε τη διάρκεια εργασίας σε 1 εβδομάδα
```java
// Αυξήστε τη διάρκεια της εργασίας σε 1 εβδομάδα
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Βήμα 5: Μειώστε τη διάρκεια εργασίας
```java
// Μειώστε τη διάρκεια εργασίας
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Ακολουθώντας αυτά τα βήματα, διαχειριστήκατε με επιτυχία τη διάρκεια των εργασιών στο έργο Aspose.Tasks για Java.
## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε καλύψει τα βασικά για τη διαχείριση της διάρκειας εργασιών χρησιμοποιώντας το Aspose.Tasks για Java. Τώρα, μπορείτε να ενσωματώσετε με σιγουριά αυτές τις τεχνικές στα έργα σας για αποτελεσματική διαχείριση της διάρκειας εργασιών.
## Συχνές ερωτήσεις
### Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις Java;
Το Aspose.Tasks είναι συμβατό με Java 6 και νεότερες εκδόσεις.
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για εμπορικά έργα;
 Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.Tasks τόσο για προσωπικά όσο και για εμπορικά έργα. Επίσκεψη[εδώ](https://purchase.aspose.com/buy) για λεπτομέρειες αδειοδότησης.
### Πού μπορώ να βρω πρόσθετη υποστήριξη και πόρους;
 Επισκέψου το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη και συζητήσεις.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για δοκιμαστικούς σκοπούς;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/) για δοκιμές και αξιολόγηση.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/) για να εξερευνήσετε το Aspose.Tasks πριν κάνετε μια αγορά.