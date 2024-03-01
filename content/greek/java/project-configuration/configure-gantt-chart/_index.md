---
title: Διαμορφώστε την προβολή γραφήματος Gantt στα έργα Aspose.Tasks
linktitle: Διαμορφώστε την προβολή γραφήματος Gantt στα έργα Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαμορφώνετε την προβολή γραφήματος έργου Gantt MS στο Aspose.Tasks χρησιμοποιώντας Java. Προσαρμόστε το έργο και οπτικοποιήστε το στο γράφημα Gantt βήμα προς βήμα.
type: docs
weight: 10
url: /el/java/project-configuration/configure-gantt-chart/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να διαμορφώνετε την προβολή γραφήματος έργου Gantt MS σε έργα Aspose.Tasks χρησιμοποιώντας Java. Το Aspose.Tasks είναι ένα ισχυρό Java API που σας επιτρέπει να εργάζεστε με αρχεία Microsoft Project μέσω προγραμματισμού. Ακολουθώντας αυτά τα βήματα, θα μπορείτε να προσαρμόσετε την προβολή γραφήματος Gantt σύμφωνα με τις απαιτήσεις του έργου σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας.
2.  Aspose.Tasks Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Ολοκληρωμένο περιβάλλον ανάπτυξης (IDE): Επιλέξτε ένα IDE της επιλογής σας. Αυτό το σεμινάριο χρησιμοποιεί το IntelliJ IDEA, αλλά μπορείτε να χρησιμοποιήσετε οποιοδήποτε IDE με το οποίο αισθάνεστε άνετα.
## Εισαγωγή πακέτων
Αρχικά, πρέπει να εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με το Aspose.Tasks στο έργο σας Java. Προσθέστε τις ακόλουθες δηλώσεις εισαγωγής στο αρχείο Java σας:
```java
import com.aspose.tasks.*;
```
Τώρα, ας αναλύσουμε τη διαδικασία διαμόρφωσης της προβολής γραφήματος έργου Gantt MS σε οδηγίες βήμα προς βήμα:
## Βήμα 1: Ρύθμιση καταλόγου δεδομένων
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με τη διαδρομή προς τον κατάλογο δεδομένων του έργου σας.
## Βήμα 2: Φόρτωση αρχείου έργου
```java
Project project = new Project(dataDir + "project.mpp");
```
Φορτώστε το αρχείο του έργου σας (`project.mpp` σε αυτό το παράδειγμα) χρησιμοποιώντας το`Project` τάξη από το Aspose.Tasks.
## Βήμα 3: Προσθήκη νέας δραστηριότητας
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Δημιουργήστε μια νέα εργασία στο έργο σας χρησιμοποιώντας το`Task` τάξη και προσθέστε το στα παιδιά της ρίζας εργασίας.
## Βήμα 4: Ορισμός προσαρμοσμένου χαρακτηριστικού
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Ορίστε ένα νέο προσαρμοσμένο χαρακτηριστικό χρησιμοποιώντας το`ExtendedAttributeDefinition`τάξη και προσθέστε το στα εκτεταμένα χαρακτηριστικά του έργου.
## Βήμα 5: Προσθέστε προσαρμοσμένο χαρακτηριστικό στο Task
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Προσθέστε το προσαρμοσμένο χαρακτηριστικό στην εργασία που δημιουργήθηκε χρησιμοποιώντας το`createExtendedAttribute` μέθοδος.
## Βήμα 6: Προσαρμογή πίνακα
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Προσαρμόστε τον πίνακα προσθέτοντας το πεδίο χαρακτηριστικού κειμένου με καθορισμένο πλάτος, τίτλο και στοίχιση.
## Βήμα 7: Αποθήκευση έργου
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Αποθηκεύστε το έργο με τη διαμορφωμένη προβολή γραφήματος έργου Gantt MS. Το αρχείο που προκύπτει μπορεί να ανοίξει στο Microsoft Project 2010.
## συμπέρασμα
Συγχαρητήρια! Διαμορφώσατε με επιτυχία την προβολή γραφήματος έργου Gantt MS σε έργα Aspose.Tasks χρησιμοποιώντας Java. Τώρα μπορείτε να προσαρμόσετε τα χαρακτηριστικά του έργου και να τα οπτικοποιήσετε στο γράφημα Gantt σύμφωνα με τις ανάγκες του έργου σας.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;
Α: Ναι, το Aspose.Tasks είναι διαθέσιμο για πολλές γλώσσες προγραμματισμού, συμπεριλαμβανομένων .NET, Java και C++.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;
Α: Μπορείτε να βρείτε υποστήριξη και να κάνετε ερωτήσεις στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
### Ε: Πώς μπορώ να αγοράσω άδεια χρήσης για το Aspose.Tasks;
 Α: Μπορείτε να αγοράσετε μια άδεια από[εδώ](https://purchase.aspose.com/buy).
### Ε: Χρειάζομαι μια προσωρινή άδεια για σκοπούς δοκιμής;
 Α: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/).