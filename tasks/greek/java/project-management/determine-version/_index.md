---
title: Προσδιορίστε την έκδοση MS Project με το Aspose.Tasks
linktitle: Προσδιορίστε την έκδοση έργου με το Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να προσδιορίζετε την έκδοση των αρχείων MS Project μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για Java. Οδηγός βήμα προς βήμα με παραδείγματα κώδικα.
weight: 12
url: /el/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσδιορίστε την έκδοση MS Project με το Aspose.Tasks

## Εισαγωγή
Αυτό το σεμινάριο θα σας καθοδηγήσει στη χρήση του Aspose.Tasks για Java για να προσδιορίσετε την έκδοση ενός αρχείου MS Project βήμα προς βήμα. Το Aspose.Tasks είναι ένα ισχυρό Java API που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία Microsoft Project χωρίς να απαιτείται η εγκατάσταση του Microsoft Project.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks for Java JAR αρχείο: Κάντε λήψη της βιβλιοθήκης Aspose.Tasks for Java από το[δικτυακός τόπος](https://releases.aspose.com/tasks/java/) και προσθέστε το στο έργο σας Java.
3. Αρχείο MS Project: Προετοιμάστε ένα αρχείο MS Project (μορφή XML) για δοκιμή.

## Εισαγωγή πακέτων
Πριν βουτήξουμε στον κώδικα, ας εισάγουμε τα απαραίτητα πακέτα:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Βήμα 1: Ρύθμιση του έργου
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με τη διαδρομή προς τον κατάλογο που περιέχει το αρχείο MS Project.
## Βήμα 2: Φορτώστε το έργο
```java
Project project = new Project(dataDir + "input.xml");
```
 Αντικαθιστώ`"input.xml"` με το όνομα του αρχείου MS Project.
## Βήμα 3: Προσδιορίστε την έκδοση έργου
```java
//Εμφάνιση ιδιοκτησίας έκδοσης έργου
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Αυτό το απόσπασμα κώδικα ανακτά και εκτυπώνει την έκδοση και την τελευταία ημερομηνία αποθήκευσης του αρχείου MS Project.
## Βήμα 4: Εμφάνιση αποτελεσμάτων
```java
//Εμφάνιση του αποτελέσματος της μετατροπής.
System.out.println("Process completed Successfully");
```
Αυτή η γραμμή υποδεικνύει την ολοκλήρωση της διαδικασίας.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να προσδιορίζετε την έκδοση ενός αρχείου MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να εργαστείτε αποτελεσματικά με αρχεία MS Project στις εφαρμογές σας Java χωρίς ταλαιπωρία.

## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;
Α: Ναι, το Aspose.Tasks υποστηρίζει πολλές γλώσσες προγραμματισμού, συμπεριλαμβανομένων .NET, Java και C++.
### Ε: Είναι το Aspose.Tasks κατάλληλο για έργα μεγάλης κλίμακας;
Α: Απολύτως, το Aspose.Tasks έχει σχεδιαστεί για να χειρίζεται έργα οποιουδήποτε μεγέθους με ευκολία.
### Ε: Μπορώ να προσαρμόσω τα δεδομένα του έργου χρησιμοποιώντας το Aspose.Tasks;
Α: Ναι, μπορείτε να χειριστείτε δεδομένα έργου, να τροποποιήσετε εργασίες, πόρους και πολλά άλλα χρησιμοποιώντας το Aspose.Tasks.
### Ε: Απαιτεί το Aspose.Tasks εγκατάσταση του Microsoft Project;
Α: Όχι, το Aspose.Tasks λειτουργεί ανεξάρτητα και δεν απαιτεί την εγκατάσταση του Microsoft Project.
### Ε: Είναι διαθέσιμη τεχνική υποστήριξη για το Aspose.Tasks;
 Α: Ναι, μπορείτε να λάβετε τεχνική υποστήριξη από το φόρουμ Aspose.Tasks στη διεύθυνση[εδώ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
