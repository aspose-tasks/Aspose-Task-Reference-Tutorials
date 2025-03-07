---
title: Αποθήκευση ως CSV, κείμενο και πρότυπο στο Aspose.Tasks
linktitle: Αποθήκευση ως CSV, κείμενο και πρότυπο στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να αποθηκεύετε αρχεία Microsoft Project σε μορφές CSV, Text και Template χρησιμοποιώντας το Aspose.Tasks για Java.
weight: 16
url: /el/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση ως CSV, κείμενο και πρότυπο στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο αποθήκευσης αρχείων έργου σε διάφορες μορφές όπως CSV, Text και Template χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project χωρίς να απαιτείται η εγκατάσταση του Microsoft Project.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Λήψη και διαμόρφωση της βιβλιοθήκης Aspose.Tasks για Java στο έργο σας Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Βασικές γνώσεις γλώσσας προγραμματισμού Java.

## Εισαγωγή πακέτων
Πρώτα, πρέπει να εισαγάγετε τα απαραίτητα πακέτα στο αρχείο Java σας:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Αποθήκευση έργου ως CSV
Ας αναλύσουμε τα βήματα για την αποθήκευση ενός έργου ως CSV:
### Βήμα 1: Φορτώστε το έργο
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Βήμα 2: Αποθήκευση ως CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Αποθήκευση έργου ως κείμενο
Δείτε πώς μπορείτε να αποθηκεύσετε ένα έργο ως κείμενο:
### Βήμα 1: Φορτώστε το έργο
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Βήμα 2: Αποθήκευση ως κείμενο
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Αποθήκευση έργου ως πρότυπο
Η αποθήκευση ενός έργου ως πρότυπο περιλαμβάνει τα ακόλουθα βήματα:
### Βήμα 1: Φορτώστε το έργο
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Βήμα 2: Ορίστε τις επιλογές προτύπου
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Βήμα 3: Αποθήκευση ως πρότυπο
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να αποθηκεύουμε αρχεία Microsoft Project ως CSV, Κείμενο και Πρότυπο χρησιμοποιώντας το Aspose.Tasks για Java. Με αυτά τα απλά βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τα αρχεία του έργου σας σε διάφορες μορφές, βελτιώνοντας την παραγωγικότητά σας ως προγραμματιστής Java.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks για Java να χειριστεί πολύπλοκα αρχεία έργου;
Α: Απολύτως! Το Aspose.Tasks για Java μπορεί να χειριστεί έργα διαφορετικής πολυπλοκότητας με ευκολία, παρέχοντας ολοκληρωμένη υποστήριξη για μορφές αρχείων Microsoft Project.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Tasks για Java από[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks για Java;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή απορία σχετικά με το Aspose.Tasks για Java.
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/), επιτρέποντάς σας να αξιολογήσετε πλήρως τις δυνατότητες της βιβλιοθήκης.
### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικά λειτουργικά συστήματα;
Α: Ναι, το Aspose.Tasks για Java είναι συμβατό με διάφορα λειτουργικά συστήματα, συμπεριλαμβανομένων των Windows, macOS και Linux.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
