---
title: Διαβάστε τα δεδομένα πίνακα από το αρχείο στο Aspose.Tasks
linktitle: Διαβάστε τα δεδομένα πίνακα από το αρχείο στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Ξεκλειδώστε τη δύναμη του Aspose.Tasks για Java. Μάθετε να εξάγετε δεδομένα πίνακα από αρχεία σε αυτό το περιεκτικό σεμινάριο.
weight: 17
url: /el/java/project-data-reading/read-table-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε τα δεδομένα πίνακα από το αρχείο στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να διαβάζουμε δεδομένα πίνακα από ένα αρχείο χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να εργάζονται με έγγραφα του Microsoft Project μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε και να το εγκαταστήσετε από τον ιστότοπο της Oracle.
2.  Αρχείο Aspose.Tasks for Java JAR: Κάντε λήψη της βιβλιοθήκης Aspose.Tasks for Java από το[σύνδεσμος λήψης](https://releases.aspose.com/tasks/java/) και να το συμπεριλάβετε στο έργο σας Java.

## Εισαγωγή πακέτων
Εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με το Aspose.Tasks στο έργο σας Java:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## Βήμα 1: Ρυθμίστε τον Κατάλογο δεδομένων
Καθορίστε τη διαδρομή προς τον κατάλογο όπου βρίσκεται το αρχείο Project:
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με την πραγματική διαδρομή προς τον κατάλογο δεδομένων σας.
## Βήμα 2: Φορτώστε το Αρχείο Έργου
Φορτώστε το αρχείο Project χρησιμοποιώντας το Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Φροντίστε να αντικαταστήσετε`"Project2003.mpp"` με το όνομα του αρχείου του έργου σας.
## Βήμα 3: Ανάκτηση πληροφοριών πίνακα
Λάβετε τον πίνακα από το έργο και επαναλάβετε τα πεδία του:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Αυτό το απόσπασμα κώδικα ανακτά πληροφορίες σχετικά με τα πεδία του πίνακα, όπως πλάτος, τίτλος και στοίχιση.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να διαβάζουμε δεδομένα πίνακα από ένα αρχείο χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να εξαγάγετε και να χειρίζεστε αποτελεσματικά δεδομένα από έγγραφα του Microsoft Project στις εφαρμογές σας Java.
## Συχνές ερωτήσεις
### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;
Α: Το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις του Microsoft Project, συμπεριλαμβανομένων των Project 2003, 2007, 2010, 2013 και 2016.
### Ε: Μπορώ να τροποποιήσω τα δεδομένα του πίνακα και να τα αποθηκεύσω ξανά στο αρχείο Project;
Α: Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.Tasks για να τροποποιήσετε τα δεδομένα πίνακα μέσω προγραμματισμού και να αποθηκεύσετε τις αλλαγές στο αρχικό αρχείο Project.
### Ε: Το Aspose.Tasks απαιτεί ξεχωριστή άδεια για εμπορική χρήση;
 Α: Ναι, πρέπει να αγοράσετε μια άδεια χρήσης για το Aspose.Tasks εάν σκοπεύετε να τη χρησιμοποιήσετε σε εμπορικό περιβάλλον. Μπορείτε να λάβετε άδεια από το[σελίδα αγοράς](https://purchase.aspose.com/buy).
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.Tasks από το[σελίδα εκδόσεων](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω βοήθεια και υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15)για βοήθεια και υποστήριξη από την κοινότητα και την ομάδα Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
