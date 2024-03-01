---
title: Το WBS συσχετίζεται με το Task στο Aspose.Tasks
linktitle: Το WBS συσχετίζεται με το Task στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Master WBS με Aspose.Tasks για Java - Μάθετε να διαβάζετε και να επαναριθμείτε τους κωδικούς WBS εργασιών. Ενισχύστε την αποτελεσματικότητα διαχείρισης έργου!
type: docs
weight: 36
url: /el/java/task-properties/wbs-associated-with-task/
---
## Εισαγωγή
Καλώς ήρθατε στον κόσμο της διαχείρισης έργων με το Aspose.Tasks για Java! Σε αυτό το σεμινάριο, θα εμβαθύνουμε στις περιπλοκές της Δομής Ανάλυσης Εργασίας (WBS) που σχετίζεται με εργασίες που χρησιμοποιούν το Aspose.Tasks για Java. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτός ο οδηγός θα σας βοηθήσει να πλοηγηθείτε στα βασικά στοιχεία της αποτελεσματικής διαχείρισης των κωδικών WBS.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο μηχάνημά σας.
-  Η βιβλιοθήκη Aspose.Tasks για Java έγινε λήψη και προσθήκη στο έργο σας. Μπορείτε να το πάρετε από[εδώ](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Βεβαιωθείτε ότι εισάγετε τα απαραίτητα πακέτα για να ξεκινήσετε το έργο σας:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Διαβάστε τους κωδικούς WBS
Ας ξεκινήσουμε διαβάζοντας τους κωδικούς WBS που σχετίζονται με εργασίες. Ακολουθήστε αυτά τα βήματα:
## Βήμα 1: Φορτώστε το έργο
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Βήμα 2: Συλλέξτε εργασίες
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Βήμα 3: Ανάλυση και προσαρμογή
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Αυτό το απόσπασμα διαβάζει και προσαρμόζει τους κωδικούς WBS που σχετίζονται με εργασίες στο έργο σας.
## Επαναρίθμηση Κωδικών Εργασίας WBS
Τώρα, ας εξερευνήσουμε την επαναρίθμηση των κωδικών WBS για εργασίες:
## Βήμα 1: Φορτώστε το έργο
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Βήμα 2: Επιλέξτε Όλες οι εργασίες
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Βήμα 3: Εξαγωγή αρχικών κωδικών WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Βήμα 4: Επαναριθμήστε τους κωδικούς WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Βήμα 5: Εξαγωγή ενημερωμένων κωδικών WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Ακολουθώντας αυτά τα βήματα, θα επαναριθμήσετε αποτελεσματικά τους κωδικούς WBS για εργασίες στο έργο σας.
## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να εργάζεστε με κωδικούς WBS χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η γνώση θα σας δώσει τη δυνατότητα να διαχειριστείτε αποτελεσματικά και να προσαρμόσετε την ιεραρχία εργασιών του έργου σας.
## Συχνές ερωτήσεις
### Ε: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Tasks για Java;
 Α: Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/tasks/java/).
### Ε: Πώς μπορώ να κατεβάσω το Aspose.Tasks για Java;
 Α: Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/java/).
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
 Α: Επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για υποστήριξη.
### Ε: Μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Tasks για Java;
 Α: Ναι, πάρτε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).