---
title: Ανάκτηση εξαιρέσεων ημερολογίου με το Aspose.Tasks
linktitle: Ανάκτηση εξαιρέσεων ημερολογίου με το Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ανακτάτε εξαιρέσεις ημερολογίου από το MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Βήμα προς βήμα μάθημα για απρόσκοπτη ενσωμάτωση.
weight: 13
url: /el/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάκτηση εξαιρέσεων ημερολογίου με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να ανακτήσετε εξαιρέσεις ημερολογίου από το MS Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Το Aspose.Tasks είναι ένα ισχυρό εργαλείο που επιτρέπει στους προγραμματιστές να χειρίζονται τα αρχεία του Microsoft Project μέσω προγραμματισμού. Θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα, αναλύοντας κάθε παράδειγμα σε πολλά βήματα για εύκολη κατανόηση.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks για Java: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για Java από[εδώ](https://releases.aspose.com/tasks/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Μπορείτε να χρησιμοποιήσετε οποιοδήποτε IDE της επιλογής σας, όπως το IntelliJ IDEA ή το Eclipse.

## Εισαγωγή πακέτων
Αρχικά, πρέπει να εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με το Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Βήμα 1: Ρύθμιση του καταλόγου δεδομένων σας
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
```
 Φροντίστε να αντικαταστήσετε`"Your Data Directory"` με τη διαδρομή προς τον κατάλογό σας που περιέχει το αρχείο MS Project.
## Βήμα 2: Φορτώστε το αρχείο MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```
 Αυτή η γραμμή προετοιμάζει μια νέα`Project` αντικείμενο φορτώνοντας το αρχείο MS Project που καθορίζεται από τη διαδρομή.
## Βήμα 3: Ανάκτηση εξαιρέσεων ημερολογίου
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Εδώ, επαναλαμβάνουμε κάθε ημερολόγιο στο έργο και, στη συνέχεια, σε κάθε εξαίρεση ημερολογίου εντός αυτού του ημερολογίου. Εκτυπώνουμε τις ημερομηνίες έναρξης και λήξης κάθε εξαίρεσης.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ανακτούμε εξαιρέσεις ημερολογίου από το MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα απλά βήματα, μπορείτε να ενσωματώσετε απρόσκοπτα αυτή τη λειτουργία στις εφαρμογές σας Java.
## Συχνές Ερωτήσεις
### Μπορεί το Aspose.Tasks να χειριστεί διαφορετικές εκδόσεις αρχείων MS Project;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων MS Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks για Java;
 Μπορείτε να ανατρέξετε στην τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/java/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Μπορείτε να λάβετε υποστήριξη από το φόρουμ της κοινότητας[εδώ](https://forum.aspose.com/c/tasks/15).
### Υπάρχει επιλογή για προσωρινές άδειες για το Aspose.Tasks;
 Ναι, μπορείτε να λάβετε προσωρινές άδειες από[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
