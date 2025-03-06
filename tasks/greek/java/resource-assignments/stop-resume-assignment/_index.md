---
title: Διακοπή και συνέχιση εργασιών πόρων στο Aspose.Tasks
linktitle: Διακοπή και συνέχιση εργασιών πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά τις αναθέσεις πόρων στο Aspose.Tasks για Java με αυτό το βήμα προς βήμα σεμινάριο.
weight: 23
url: /el/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διακοπή και συνέχιση εργασιών πόρων στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθουμε πώς να σταματήσουμε και να συνεχίσουμε τις αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι ένα ισχυρό API Java που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project χωρίς να απαιτείται εγκατάσταση του Microsoft Project στα συστήματά τους. Θα αναλύσουμε τη διαδικασία σε διαχειρίσιμα βήματα για να είναι εύκολη η παρακολούθηση.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
-  Λήψη Aspose.Tasks για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
- Βασική κατανόηση προγραμματισμού Java.
## Εισαγωγή πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα στο έργο Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Βήμα 1: Φορτώστε το Αρχείο Έργου
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
// Φορτώστε το αρχείο του έργου
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Σε αυτό το βήμα, φορτώνουμε το αρχείο του έργου σε a`Project` αντικείμενο χρησιμοποιώντας τη διαδρομή αρχείου.
## Βήμα 2: Επανάληψη μέσω αναθέσεων πόρων
```java
// Καθορίστε την ελάχιστη ημερομηνία
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Επαναλάβετε μέσω αναθέσεων πόρων
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Εδώ, ορίζουμε μια ελάχιστη ημερομηνία και ξεκινάμε την επανάληψη σε κάθε ανάθεση πόρων στο έργο.
## Βήμα 3: Ελέγξτε τις ημερομηνίες διακοπής και συνέχισης
```java
    // Ελέγξτε την ημερομηνία διακοπής
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Ελέγξτε την ημερομηνία συνέχισης
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Σε αυτό το βήμα, ελέγχουμε εάν οι ημερομηνίες διακοπής και συνέχισης κάθε ανάθεσης πόρων είναι πριν από την ελάχιστη ημερομηνία. Εάν είναι, τυπώνουμε "NA", διαφορετικά, τυπώνουμε τις αντίστοιχες ημερομηνίες.
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να σταματήσουμε και να συνεχίσουμε τις αναθέσεις πόρων στο Aspose.Tasks για Java. Ακολουθώντας τα βήματα που παρέχονται, μπορείτε εύκολα να εφαρμόσετε αυτήν τη λειτουργία στα έργα σας Java.

## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks χωρίς εγκατεστημένο το Microsoft Project;
Ναι, το Aspose.Tasks σάς επιτρέπει να εργάζεστε με αρχεία Microsoft Project χωρίς να απαιτείται εγκατάσταση του Microsoft Project στο σύστημά σας.
### Πού μπορώ να βρω περισσότερα έγγραφα;
 Μπορείτε να βρείτε αναλυτική τεκμηρίωση[εδώ](https://reference.aspose.com/tasks/java/).
### Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη εάν αντιμετωπίζω προβλήματα;
Μπορείτε να λάβετε υποστήριξη από την κοινότητα[εδώ](https://forum.aspose.com/c/tasks/15).
### Μπορώ να αγοράσω μια προσωρινή άδεια;
 Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
