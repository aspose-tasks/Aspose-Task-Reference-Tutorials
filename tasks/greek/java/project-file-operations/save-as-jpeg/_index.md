---
title: Μετατροπή έργου MS ως JPEG στο Aspose.Tasks
linktitle: Αποθήκευση έργου ως JPEG στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να μετατρέπετε εύκολα αρχεία Microsoft Project σε εικόνες JPEG χρησιμοποιώντας το Aspose.Tasks για Java. Ενισχύστε την παραγωγικότητά σας.
weight: 20
url: /el/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή έργου MS ως JPEG στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να αποθηκεύσετε ένα αρχείο Microsoft Project ως εικόνα JPEG χρησιμοποιώντας το Aspose.Tasks για Java. Αυτό μπορεί να είναι ιδιαίτερα χρήσιμο για την κοινή χρήση οπτικοποιήσεων έργων ή την ενσωμάτωση δεδομένων έργου σε αναφορές ή παρουσιάσεις.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας. Μπορείτε να κατεβάσετε και να εγκαταστήσετε την πιο πρόσφατη έκδοση από το[Ιστοσελίδα Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks για Java: Κατεβάστε και ρυθμίστε το Aspose.Tasks για Java ακολουθώντας τις οδηγίες που παρέχονται στο[τεκμηρίωση](https://reference.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Πρώτα, εισαγάγετε τα απαραίτητα πακέτα στο αρχείο Java σας:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Βήμα 1: Ορισμός καταλόγου δεδομένων
Ορίστε τη διαδρομή προς τον κατάλογο δεδομένων σας όπου βρίσκεται το αρχείο MS Project.
```java
String dataDir = "Your Data Directory";
```
## Βήμα 2: Φορτώστε το αρχείο MS Project
Φορτώστε το αρχείο MS Project χρησιμοποιώντας το Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Βήμα 3: Διαμόρφωση ποιότητας JPEG (Προαιρετικό)
 Εάν θέλετε να προσαρμόσετε την ποιότητα JPEG, μπορείτε να τη ρυθμίσετε χρησιμοποιώντας το`ImageSaveOptions` τάξη. Η ποιότητα κυμαίνεται από 0 έως 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Ρυθμίστε την ποιότητα JPEG στο 50
```
## Βήμα 4: Αποθήκευση έργου ως JPEG
Αποθηκεύστε το αρχείο MS Project ως εικόνα JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να αποθηκεύουμε ένα αρχείο Microsoft Project ως εικόνα JPEG χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η δυνατότητα επιτρέπει την εύκολη κοινή χρήση και ενσωμάτωση δεδομένων έργου σε διάφορα έγγραφα και παρουσιάσεις.
## Συχνές ερωτήσεις
### Ε: Μπορώ να προσαρμόσω την ποιότητα της εικόνας JPEG;
 Α: Ναι, μπορείτε να προσαρμόσετε την ποιότητα χρησιμοποιώντας το`setJpegQuality()` μέθοδος, με εύρος από 0 έως 100.
### Ε: Τι γίνεται αν δεν προσδιορίσω την ποιότητα JPEG;
Α: Εάν δεν καθορίσετε την ποιότητα, θα χρησιμοποιηθεί η προεπιλεγμένη ποιότητα.
### Ε: Είναι το Aspose.Tasks για Java δωρεάν;
 Α: Το Aspose.Tasks για Java είναι μια εμπορική βιβλιοθήκη, αλλά μπορείτε να εξερευνήσετε τις δυνατότητές της με μια δωρεάν δοκιμή. Επισκέψου το[δωρεάν δοκιμαστική σελίδα](https://releases.aspose.com/) Για περισσότερες πληροφορίες.
### Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια για το Aspose.Tasks;
 Α: Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
