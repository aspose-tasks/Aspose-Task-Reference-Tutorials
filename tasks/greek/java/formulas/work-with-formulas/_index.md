---
title: MS Project Formulas με Aspose.Tasks για Java
linktitle: Εργαστείτε με τύπους στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να χειρίζεστε αρχεία MS Project σε Java χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks. Δημιουργήστε, τροποποιήστε και υπολογίστε χαρακτηριστικά με ευκολία.
weight: 11
url: /el/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Formulas με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εμβαθύνουμε στην εργασία με τους τύπους MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία του Microsoft Project μέσω προγραμματισμού. Με τις εκτεταμένες δυνατότητες του, μπορείτε εύκολα να δημιουργήσετε, να διαβάσετε, να τροποποιήσετε και να μετατρέψετε αρχεία έργου σε εφαρμογές Java.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
### Περιβάλλον Ανάπτυξης Java
Βεβαιωθείτε ότι έχετε εγκατεστημένο στο σύστημά σας ένα Java Development Kit (JDK). Μπορείτε να κάνετε λήψη και εγκατάσταση του πιο πρόσφατου JDK από τον ιστότοπο της Oracle.
### Aspose.Tasks Library
Πρέπει να προσθέσετε τη βιβλιοθήκη Aspose.Tasks στο έργο σας Java. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από το[Σελίδα λήψης Aspose.Tasks για Java](https://releases.aspose.com/tasks/java/) και συμπεριλάβετέ το στις εξαρτήσεις του έργου σας.

## Εισαγωγή πακέτων
Πριν βουτήξετε στα παραδείγματα, εισαγάγετε τα απαραίτητα πακέτα στον κώδικα Java σας:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα:
## Βήμα 1: Δημιουργήστε ένα δοκιμαστικό έργο με προσαρμοσμένο πεδίο
```java
Project project = CreateTestProjectWithCustomField();
```
 Αρχικά, δημιουργήστε ένα δοκιμαστικό έργο με ένα προσαρμοσμένο πεδίο χρησιμοποιώντας το`CreateTestProjectWithCustomField()` μέθοδος. Αυτή η μέθοδος θα επιστρέψει ένα αντικείμενο Project που αντιπροσωπεύει το νέο έργο.
## Βήμα 2: Ορίστε έναν εκτεταμένο ορισμό χαρακτηριστικών
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Ανακτήστε τον εκτεταμένο ορισμό χαρακτηριστικών από το έργο και ορίστε το ψευδώνυμο και τον τύπο του. Σε αυτό το παράδειγμα, ορίζουμε ένα χαρακτηριστικό για τον υπολογισμό του αριθμού των ημερών από την ημερομηνία λήξης έως την προθεσμία.
## Βήμα 3: Ορίστε την προθεσμία για μια εργασία
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Δημιουργήστε ένα αντικείμενο Ημερολογίου και ορίστε την ημερομηνία λήξης. Στη συνέχεια, ανακτήστε μια εργασία από το έργο και ορίστε την προθεσμία της χρησιμοποιώντας το αντικείμενο Ημερολόγιο.
## Βήμα 4: Αποθηκεύστε το έργο
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Τέλος, αποθηκεύστε το έργο σε ένα αρχείο με το καθορισμένο όνομα και μορφή. Σε αυτήν την περίπτωση, το αποθηκεύουμε ως αρχείο MPP.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να εργαζόμαστε με τους τύπους MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειρίζεστε αποτελεσματικά τα αρχεία έργου μέσω προγραμματισμού, προσθέτοντας προσαρμοσμένα πεδία και υπολογίζοντας χαρακτηριστικά με βάση τύπους.

## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες γλώσσες προγραμματισμού, όπως Java, .NET και άλλες.
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks;
 Α: Μπορείτε να βρείτε την τεκμηρίωση για το Aspose.Tasks[εδώ](https://reference.aspose.com/tasks/java/).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Α: Για υποστήριξη, μπορείτε να επισκεφτείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
### Ε: Χρειάζομαι μια προσωρινή άδεια χρήσης για τη χρήση του Aspose.Tasks;
Α: Εάν χρειάζεστε πρόσθετες λειτουργίες, μπορείτε να αποκτήσετε προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
