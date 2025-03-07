---
title: Υποστήριξη Λειτουργιών αξιολόγησης στους τύπους Aspose.Tasks
linktitle: Υποστήριξη Λειτουργιών αξιολόγησης στους τύπους Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να υποστηρίζετε την αξιολόγηση των συναρτήσεων του MS Project σε τύπους Aspose.Tasks χρησιμοποιώντας Java. Ενισχύστε την παραγωγικότητά σας με το Aspose.Tasks.
weight: 10
url: /el/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Υποστήριξη Λειτουργιών αξιολόγησης στους τύπους Aspose.Tasks


## Εισαγωγή
Το Aspose.Tasks για Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να χειρίζονται αρχεία του Microsoft Project μέσω προγραμματισμού. Ένα από τα βασικά χαρακτηριστικά του είναι η δυνατότητα υποστήριξης της αξιολόγησης των λειτουργιών του MS Project μέσα στους τύπους Aspose.Tasks. Αυτή η δυνατότητα επιτρέπει στους χρήστες να εκτελούν πολύπλοκους υπολογισμούς και αναλύσεις απευθείας μέσα στις εφαρμογές Java τους.
## Προαπαιτούμενα
Πριν ξεκινήσετε με την ενσωμάτωση των συναρτήσεων του MS Project στους τύπους Aspose.Tasks, βεβαιωθείτε ότι έχετε τα εξής:
1. Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας μαζί με ένα συμβατό IDE για ανάπτυξη Java, όπως το IntelliJ IDEA ή το Eclipse.
2.  Aspose.Tasks for Java Library: Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks for Java στο έργο σας Java. Μπορείτε να το κατεβάσετε από το[Σελίδα λήψης Aspose.Tasks για Java](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στην τάξη Java για να χρησιμοποιήσετε τις λειτουργίες Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Βήμα 1: Δημιουργήστε ένα νέο αντικείμενο έργου
 Πρώτα, δημιουργήστε ένα νέο`Project`αντικείμενο εργασίας με:
```java
Project project = new Project();
```
Αυτό ξεκινά ένα νέο κενό έργο.
## Βήμα 2: Ορίστε ένα εκτεταμένο χαρακτηριστικό για τις εργασίες
Στη συνέχεια, ορίστε ένα εκτεταμένο χαρακτηριστικό για εργασίες. Αυτό το χαρακτηριστικό θα διατηρεί προσαρμοσμένα δεδομένα που σχετίζονται με εργασίες:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Εδώ, δημιουργούμε ένα εκτεταμένο χαρακτηριστικό τύπου`Number` με το όνομα "Sine" για εργασίες.
## Βήμα 3: Προσθέστε το Extended Attribute στο Project
Προσθέστε τον ορισμό του εκτεταμένου χαρακτηριστικού στη λίστα εκτεταμένων χαρακτηριστικών του έργου:
```java
project.getExtendedAttributes().add(attr);
```
Αυτό προσθέτει το προσαρμοσμένο χαρακτηριστικό στο έργο.
## Βήμα 4: Δημιουργήστε μια νέα εργασία
Τώρα, ας δημιουργήσουμε μια νέα εργασία μέσα στο έργο:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Αυτό προσθέτει μια νέα εργασία με το όνομα "Task" στο έργο.
## Βήμα 5: Συσχετίστε το εκτεταμένο χαρακτηριστικό με την εργασία
Συσχετίστε το εκτεταμένο χαρακτηριστικό που δημιουργήθηκε νωρίτερα με την εργασία:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Αυτό συσχετίζει το εκτεταμένο χαρακτηριστικό "Sine" με την εργασία.

## συμπέρασμα
Συμπερασματικά, η ενσωμάτωση των λειτουργιών του MS Project στους τύπους Aspose.Tasks στην Java είναι μια απλή διαδικασία. Ακολουθώντας τα παρεχόμενα βήματα, μπορείτε να χρησιμοποιήσετε αποτελεσματικά τις ισχυρές δυνατότητες του Aspose.Tasks για Java για χειρισμό και ανάλυση αρχείων Microsoft Project μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks για Java να χειριστεί πολύπλοκους τύπους MS Project;
Α: Ναι, το Aspose.Tasks για Java υποστηρίζει την αξιολόγηση ενός ευρέος φάσματος λειτουργιών του MS Project, επιτρέποντας σύνθετους υπολογισμούς εντός εφαρμογών Java.
### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;
Α: Ναι, το Aspose.Tasks για Java υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.
### Ε: Μπορώ να δοκιμάσω το Aspose.Tasks για Java πριν το αγοράσω;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.Tasks για Java από τον ιστότοπο[εδώ](https://purchase.aspose.com/buy).
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Υπάρχει διαθέσιμη προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια για σκοπούς δοκιμής από τον ιστότοπο Aspose[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
