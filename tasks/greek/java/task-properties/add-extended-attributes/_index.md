---
title: Προσθέστε εκτεταμένα χαρακτηριστικά στα Tasks στο Aspose.Tasks
linktitle: Προσθέστε εκτεταμένα χαρακτηριστικά στα Tasks στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Εξερευνήστε τη δύναμη της Java Aspose.Tasks στην προσαρμογή των αρχείων Microsoft Project με εκτεταμένα χαρακτηριστικά. Βελτιώστε τις δυνατότητες διαχείρισης του έργου σας χωρίς κόπο.
weight: 11
url: /el/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθέστε εκτεταμένα χαρακτηριστικά στα Tasks στο Aspose.Tasks

## Εισαγωγή
Η ενίσχυση των δυνατοτήτων διαχείρισης του έργου σας είναι ζωτικής σημασίας για την αποτελεσματική παρακολούθηση εργασιών και διαχείριση πόρων. Το Aspose.Tasks για Java παρέχει μια ισχυρή λύση για προγραμματιστές Java για τον απρόσκοπτο χειρισμό των αρχείων του Microsoft Project. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να προσθέσετε εκτεταμένα χαρακτηριστικά σε εργασίες χρησιμοποιώντας το Aspose.Tasks για Java, επιτρέποντάς σας να προσαρμόσετε και να οργανώσετε τα δεδομένα του έργου σας σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Tasks για Java. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://releases.aspose.com/tasks/java/).
- Ένα Java Integrated Development Environment (IDE) εγκατεστημένο στο σύστημά σας.
## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα για πρόσβαση στις λειτουργίες Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα:
## 1. Προσθήκη χαρακτηριστικού απλού κειμένου
1. Ορίστε τη διαδρομή καταλόγου εγγράφου:
```java
String dataDir = "Your Document Directory";
```
2. Δημιουργήστε ένα νέο έργο:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Δημιουργήστε έναν εκτεταμένο ορισμό χαρακτηριστικού τύπου Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Προσθέστε τον ορισμό στη συλλογή Extended Attributes του έργου:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Προσθέστε μια εργασία στο έργο:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Δημιουργήστε ένα εκτεταμένο χαρακτηριστικό από τον ορισμό χαρακτηριστικών:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Εκχωρήστε μια τιμή στο εκτεταμένο χαρακτηριστικό που δημιουργήθηκε:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Προσθέστε το Extended Attribute στην εργασία:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Αποθηκεύστε το έργο:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Προσθήκη χαρακτηριστικού κειμένου με την επιλογή αναζήτησης
Ακολουθήστε τα ίδια βήματα όπως παραπάνω, αντικαθιστώντας το Text1 με Text2 και προσαρμόζοντας τις τιμές αναζήτησης.
## 3. Προσθήκη χαρακτηριστικού διάρκειας με την επιλογή αναζήτησης
Ακολουθήστε τα ίδια βήματα όπως παραπάνω, αντικαθιστώντας το Text1 με το Duration2 και προσαρμόζοντας τις τιμές αναζήτησης.
## συμπέρασμα
Ακολουθώντας αυτόν τον αναλυτικό οδηγό, μάθατε πώς να αξιοποιείτε το Aspose.Tasks για Java για να προσθέτετε εκτεταμένα χαρακτηριστικά σε εργασίες στα αρχεία του Microsoft Project. Αυτή η προσαρμογή σάς επιτρέπει να προσαρμόσετε την προσέγγιση διαχείρισης του έργου σας, ενισχύοντας την ευελιξία και την αποτελεσματικότητα.
## Συχνές Ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java με άλλες βιβλιοθήκες Java;
Α: Ναι, το Aspose.Tasks για Java μπορεί να ενσωματωθεί απρόσκοπτα στα έργα σας Java και λειτουργεί καλά με άλλες βιβλιοθήκες Java.
### Ε: Είναι το Aspose.Tasks για Java κατάλληλο για εφαρμογές διαχείρισης έργων μεγάλης κλίμακας;
Α: Απολύτως, το Aspose.Tasks για Java έχει σχεδιαστεί για να χειρίζεται έργα διαφόρων μεγεθών, συμπεριλαμβανομένων εφαρμογών μεγάλης κλίμακας.
### Ε: Υπάρχουν ζητήματα αδειοδότησης για τη χρήση του Aspose.Tasks για Java σε ένα εμπορικό έργο;
 Α: Ναι, φροντίστε να διαβάσετε τις πληροφορίες αδειοδότησης που παρέχονται στο[Ιστότοπος Aspose.Tasks](https://purchase.aspose.com/buy).
### Ε: Πώς μπορώ να λάβω υποστήριξη ή βοήθεια με το Aspose.Tasks για Java;
 Α: Επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για κοινοτική υποστήριξη και συζητήσεις.
### Ε: Μπορώ να δοκιμάσω το Aspose.Tasks για Java πριν το αγοράσω;
 Α: Ναι, μπορείτε να αποκτήσετε πρόσβαση σε μια δωρεάν δοκιμαστική έκδοση[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
