---
date: 2026-02-26
description: Μάθετε πώς να δημιουργείτε έργα Aspose Java για εργασίες και να λαμβάνετε
  την ημερομηνία έναρξης της εργασίας χρησιμοποιώντας το Aspose.Tasks for Java. Ένας
  οδηγός βήμα‑βήμα για την ανάγνωση και την εγγραφή γενικών ιδιοτήτων εργασιών.
linktitle: Read and Write General Properties of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Δημιουργία Εργασίας Aspose Java – Κατάκτηση Ιδιοτήτων Εργασίας
url: /el/java/task-properties/read-write-general-properties/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Εργασίας Aspose Java – Κατάκτηση Ιδιοτήτων Εργασίας

## Εισαγωγή
Αποκτήστε το πλήρες δυναμικό της διαχείρισης εργασιών σε Java με το Aspose.Tasks. Σε αυτόν τον ολοκληρωμένο οδηγό, **θα μάθετε πώς να δημιουργήσετε έργα task Aspose Java**, να διαβάζετε και να γράφετε γενικές ιδιότητες, και ακόμη **να λάβετε την ημερομηνία έναρξης της εργασίας** για οποιαδήποτε εργασία στο πρόγραμμα σας. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτό το tutorial σας εξοπλίζει με πρακτικό κώδικα που μπορείτε να αντιγράψετε‑επικολλήσετε στις δικές σας εφαρμογές.

## Γρήγορες Απαντήσεις
- **Τι μπορώ να κάνω με το Aspose.Tasks for Java;** Διαβάστε και γράψτε ιδιότητες εργασιών, συμπεριλαμβανομένων των ημερομηνιών έναρξης, διάρκειας και προσαρμοσμένων πεδίων.  
- **Πώς δημιουργώ μια νέα εργασία;** Χρησιμοποιήστε `project.getRootTask().getChildren().add("TaskName")` και ορίστε τις ιδιότητες μέσω του enum `Tsk`.  
- **Πώς μπορώ να ανακτήσω την ημερομηνία έναρξης μιας εργασίας;** Καλέστε `task.get(Tsk.START)` μετά τη φόρτωση του έργου ή τη δημιουργία της εργασίας.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια προσωρινή άδεια λειτουργεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποια έκδοση της Java υποστηρίζεται;** Το Aspose.Tasks λειτουργεί με Java 8 και νεότερες, συμπεριλαμβανομένων των Java 11 και Java 17.

## Τι είναι το “create task Aspose Java”;
Η δημιουργία μιας εργασίας με το Aspose.Tasks σημαίνει προγραμματιστική προσθήκη μιας νέας εγγραφής στο χρονοδιάγραμμα του έργου, ορίζοντας το όνομα, την ώρα έναρξης, την ώρα λήξης και άλλα χαρακτηριστικά χωρίς να χρειάζεται η χειροκίνητη επεξεργασία ενός αρχείου XML ή MPP.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για Java;
- **Πλήρης έλεγχος** πάνω σε κάθε χαρακτηριστικό εργασίας (ID, UID, όνομα, ημερομηνίες κ.λπ.).  
- **Διαπλατφορμικό** – λειτουργεί σε Windows, Linux και macOS.  
- **Χωρίς εξαρτήσεις COM ή Office** – καθαρή βιβλιοθήκη Java.  
- **Πλούσιο API** για ανάγνωση, εγγραφή και επικύρωση δεδομένων έργου.

## Προαπαιτούμενα
Πριν βυθιστούμε στον οδηγό, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
- Java Development Kit (JDK) εγκατεστημένο στο σύστημά σας.  
- Βιβλιοθήκη Aspose.Tasks for Java ληφθείσα και ρυθμισμένη. Μπορείτε να βρείτε τον σύνδεσμο λήψης [εδώ](https://releases.aspose.com/tasks/java/).  
- Ένα πρόγραμμα επεξεργασίας κώδικα όπως IntelliJ IDEA ή Eclipse.

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, εισάγετε τα απαραίτητα πακέτα στο έργο Java σας. Αυτό το βήμα εξασφαλίζει ότι έχετε πρόσβαση στις λειτουργίες του Aspose.Tasks. Ακολουθεί ένα απόσπασμα για καθοδήγηση:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Πώς να δημιουργήσετε task Aspose Java
### Βήμα 1: Δημιουργία Εργασίας
Ξεκινήστε δημιουργώντας μια εργασία στο έργο σας. Αυτό περιλαμβάνει τον καθορισμό του ονόματος της εργασίας, της ημερομηνίας έναρξης και άλλων σχετικών λεπτομερειών. Ο παρακάτω κώδικας δείχνει τη διαδικασία:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```

### Βήμα 2: Ανάγνωση Ιδιοτήτων Εργασίας
Τώρα που έχετε δημιουργήσει μια εργασία, ας ανακτήσουμε και εμφανίσουμε τις γενικές της ιδιότητες, συμπεριλαμβανομένης της ημερομηνίας έναρξης που μόλις ορίσατε:

```java
// Reading General Properties of Tasks
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```

## Πώς να λάβετε την ημερομηνία έναρξης της εργασίας
Εάν χρειάζεστε **να λάβετε την ημερομηνία έναρξης της εργασίας** για περαιτέρω υπολογισμούς (π.χ., προγραμματισμό ή αναφορές), απλώς καλέστε την ιδιότητα `Tsk.START` σε οποιοδήποτε αντικείμενο `Task`, όπως φαίνεται στον παραπάνω βρόχο. Η επιστρεφόμενη τιμή είναι ένα `java.util.Date` που μπορείτε να μορφοποιήσετε ή να συγκρίνετε όπως χρειάζεται.

## Εγγραφή Γενικών Ιδιοτήτων Εργασιών
### Βήμα 3: Φόρτωση Έργου και Δημιουργία Συλλέκτη
Για να γράψετε ή να ενημερώσετε γενικές ιδιότητες, φορτώστε ένα υπάρχον έργο και δημιουργήστε έναν `ChildTasksCollector`:

```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```

### Βήμα 4: Ανάλυση και Εμφάνιση Ιδιοτήτων
Τέλος, επαναλάβετε τις συλλεγμένες εργασίες και εμφανίστε (ή τροποποιήστε) τις ιδιότητές τους:

```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```

> **Συμβουλή:** Μετά την ενημέρωση οποιασδήποτε ιδιότητας, καλέστε `prj.save("output.xml")` για να αποθηκεύσετε τις αλλαγές σε ένα νέο αρχείο έργου.

Συγχαρητήρια! Διαβάσατε, γράψατε και ερωτήσατε επιτυχώς τις γενικές ιδιότητες των εργασιών χρησιμοποιώντας το Aspose.Tasks for Java.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| `NullPointerException` κατά την πρόσβαση στο `task.get(Tsk.START)` | Η εργασία δεν προστέθηκε στην ιεραρχία του έργου. | Βεβαιωθείτε ότι προσθέτετε την εργασία στο `project.getRootTask().getChildren()` πριν ορίσετε τις ιδιότητες. |
| Οι ημερομηνίες εμφανίζονται με διαφορά μιας ημέρας | Διαφορές ζώνης ώρας μεταξύ του Java `Date` και του αρχείου έργου. | Χρησιμοποιήστε `java.util.Calendar` με ρητή ζώνη ώρας ή αποθηκεύστε τις ημερομηνίες σε UTC. |
| Οι αλλαγές δεν αποθηκεύονται | Ξεχάσατε να καλέσετε το `project.save(...)`. | Πάντα αποθηκεύετε το έργο μετά τις τροποποιήσεις. |

## Συχνές Ερωτήσεις

**Ε: Είναι το Aspose.Tasks συμβατό με Java 11;**  
Α: Ναι, το Aspose.Tasks είναι συμβατό με Java 11 και μεταγενέστερες εκδόσεις.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για εμπορικά έργα;**  
Α: Απόλυτα! Το Aspose.Tasks είναι ένα ισχυρό εργαλείο για προσωπικά και εμπορικά έργα. Επισκεφθείτε [εδώ](https://purchase.aspose.com/buy) για να εξερευνήσετε τις επιλογές αδειοδότησης.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
Α: Αποκτήστε μια προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/) για δοκιμές και αξιολόγηση.

**Ε: Πού μπορώ να βρω υποστήριξη κοινότητας για το Aspose.Tasks;**  
Α: Συμμετέχετε στη συζήτηση της κοινότητας στο [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για βοήθεια και συνεργασία.

**Ε: Υπάρχουν δείγματα έργων διαθέσιμα για αναφορά;**  
Α: Εξερευνήστε την ενότητα παραδειγμάτων της τεκμηρίωσης [εδώ](https://reference.aspose.com/tasks/java/) για δείγματα έργων και αποσπάσματα κώδικα.

## Συμπέρασμα
Σε αυτόν τον οδηγό, εξετάσαμε τα βασικά βήματα για **να δημιουργήσετε έργα task Aspose Java**, να διαβάσετε και να γράψετε γενικές ιδιότητες, και **να λάβετε την ημερομηνία έναρξης της εργασίας** με ευκολία. Με την κατάκτηση αυτών των τεχνικών, μπορείτε να βελτιστοποιήσετε τη διαχείριση εργασιών σε οποιαδήποτε εφαρμογή χρονοπρογραμματισμού βασισμένη σε Java και να προσφέρετε πιο πλούσιες δυνατότητες προγραμματισμού έργων στους χρήστες σας.

---

**Τελευταία Ενημέρωση:** 2026-02-26  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}