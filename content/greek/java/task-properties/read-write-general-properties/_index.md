---
title: Mastering Task Properties στο Aspose.Tasks
linktitle: Διαβάστε και γράψτε τις Γενικές ιδιότητες των εργασιών στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Εξερευνήστε τη δύναμη του Aspose.Tasks για Java στη διαχείριση των ιδιοτήτων εργασιών χωρίς κόπο. Διαβάστε και γράψτε με ευκολία χρησιμοποιώντας τον βήμα προς βήμα οδηγό μας.
type: docs
weight: 26
url: /el/java/task-properties/read-write-general-properties/
---
## Εισαγωγή
Ξεκλειδώστε το πλήρες δυναμικό της διαχείρισης εργασιών σε Java με το Aspose.Tasks. Σε αυτόν τον περιεκτικό οδηγό, θα εμβαθύνουμε στην ανάγνωση και τη σύνταξη γενικών ιδιοτήτων των εργασιών χρησιμοποιώντας το Aspose.Tasks για Java. Είτε είστε έμπειρος προγραμματιστής είτε αρχάριος, αυτό το σεμινάριο θα σας εξοπλίσει με τις δεξιότητες για να χειρίζεστε τις ιδιότητες εργασιών χωρίς κόπο.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
-  Λήψη και ρύθμιση της βιβλιοθήκης Aspose.Tasks για Java. Μπορείτε να βρείτε τον σύνδεσμο λήψης[εδώ](https://releases.aspose.com/tasks/java/).
- Ένα πρόγραμμα επεξεργασίας κώδικα όπως το IntelliJ IDEA ή το Eclipse.
## Εισαγωγή πακέτων
Για να ξεκινήσετε τα πράγματα, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java. Αυτό το βήμα διασφαλίζει ότι έχετε πρόσβαση στις λειτουργίες Aspose.Tasks. Ακολουθεί ένα απόσπασμα που θα σας καθοδηγήσει:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Διαβάζοντας τις Γενικές Ιδιότητες των Εργασιών
## Βήμα 1: Δημιουργήστε μια εργασία
Ξεκινήστε δημιουργώντας μια εργασία στο έργο σας. Αυτό περιλαμβάνει τη ρύθμιση του ονόματος της εργασίας, της ημερομηνίας έναρξης και άλλων σχετικών λεπτομερειών. Εδώ είναι ένα παράδειγμα:
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## Βήμα 2: Διαβάστε τις ιδιότητες εργασίας
Τώρα που δημιουργήσατε μια εργασία, ας ανακτήσουμε και ας εμφανίσουμε τις γενικές ιδιότητές της. Το παρακάτω απόσπασμα κώδικα το επιτυγχάνει αυτό:
```java
// Διαβάζοντας τις Γενικές Ιδιότητες των Εργασιών
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
## Συγγραφή Γενικών Ιδιοτήτων Εργασιών
## Βήμα 3: Φόρτωση έργου και δημιουργία συλλέκτη
 Για να γράψετε γενικές ιδιότητες, φορτώστε ένα υπάρχον έργο και ρυθμίστε ένα`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## Βήμα 4: Ανάλυση και εμφάνιση ιδιοτήτων
Τέλος, αναλύστε τις συλλεγμένες εργασίες και εμφανίστε τις ιδιότητές τους:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Συγχαρητήρια! Έχετε διαβάσει και γράψει με επιτυχία τις γενικές ιδιότητες των εργασιών χρησιμοποιώντας το Aspose.Tasks για Java.
## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε εξερευνήσει τα βασικά βήματα για τον απρόσκοπτο χειρισμό των ιδιοτήτων εργασιών με το Aspose.Tasks για Java. Κατακτώντας αυτές τις τεχνικές, μπορείτε να βελτιώσετε τις δεξιότητές σας στην ανάπτυξη Java και να βελτιώσετε τη διαχείριση εργασιών στα έργα σας.
## Συχνές ερωτήσεις
### Είναι το Aspose.Tasks συμβατό με Java 11;
Ναι, το Aspose.Tasks είναι συμβατό με Java 11 και νεότερες εκδόσεις.
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για εμπορικά έργα;
 Απολύτως! Το Aspose.Tasks είναι ένα ισχυρό εργαλείο τόσο για προσωπικά όσο και για εμπορικά έργα. Επίσκεψη[εδώ](https://purchase.aspose.com/buy) για να εξερευνήσετε τις επιλογές αδειοδότησης.
### Πώς μπορώ να πάρω μια προσωρινή άδεια για δοκιμαστικούς σκοπούς;
 Λάβετε προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/) για δοκιμές και αξιολόγηση.
### Πού μπορώ να βρω υποστήριξη κοινότητας για το Aspose.Tasks;
 Λάβετε μέρος στη συζήτηση της κοινότητας στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για βοήθεια και συνεργασία.
### Υπάρχουν διαθέσιμα δείγματα έργων για αναφορά;
 Εξερευνήστε την ενότητα παραδειγμάτων της τεκμηρίωσης[εδώ](https://reference.aspose.com/tasks/java/) για δείγματα έργων και αποσπάσματα κώδικα.