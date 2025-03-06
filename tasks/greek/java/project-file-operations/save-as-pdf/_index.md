---
title: Αποθήκευση ως PDF στο Aspose.Tasks
linktitle: Αποθήκευση ως PDF στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να μετατρέπετε αρχεία έργου σε PDF χρησιμοποιώντας το Aspose.Tasks για Java. Απλά βήματα για αποτελεσματική μετατροπή.
type: docs
weight: 17
url: /el/java/project-file-operations/save-as-pdf/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία αποθήκευσης ενός έργου ως PDF χρησιμοποιώντας το Aspose.Tasks για Java. Με το Aspose.Tasks, μπορείτε να μετατρέψετε αποτελεσματικά τα αρχεία του έργου σας σε μορφή PDF, διασφαλίζοντας συμβατότητα και ευκολία κοινής χρήσης. Ας βουτήξουμε στα βήματα:
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks for Java Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks. Μπορείτε να βρείτε τον σύνδεσμο λήψης[εδώ](https://releases.aspose.com/tasks/java/).
3. Ένα αρχείο έργου: Έχετε έτοιμο ένα αρχείο έργου (π.χ. HomeMovePlan.mpp) που θέλετε να μετατρέψετε σε PDF.

## Εισαγωγή πακέτων
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Βήμα 1: Διαβάστε το αρχείο εισόδου έργου
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Βεβαιωθείτε ότι έχετε αντικαταστήσει`"Your Data Directory"` με τη διαδρομή προς τον κατάλογο δεδομένων σας που περιέχει το αρχείο του έργου.
## Βήμα 2: Αποθηκεύστε το έργο ως PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Αυτό το απόσπασμα κώδικα αποθηκεύει το έργο ως αρχείο PDF με το όνομα "Project5.pdf".
## Βήμα 3: Προσαρμογή περιεχομένου στο μέγεθος κελιού
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Εδώ, ορίζουμε επιλογές για την αποθήκευση του PDF, συμπεριλαμβανομένου του κατάλληλου περιεχομένου, της χρονικής κλίμακας και της μορφής παρουσίασης.
## Βήμα 4: Απόκρυψη Legends
```java
o.setLegendOnEachPage(false);
```
Αυτό το βήμα κρύβει θρύλους σε κάθε σελίδα του PDF.
## Βήμα 5: Αποθηκεύστε το Έργο με τις Εφαρμοσμένες Επιλογές
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Τέλος, αυτός ο κώδικας αποθηκεύει το έργο με εφαρμοσμένες επιλογές σε ένα αρχείο PDF.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να χρησιμοποιούμε το Aspose.Tasks για Java για να αποθηκεύσουμε ένα έργο ως PDF. Ακολουθώντας αυτά τα απλά βήματα, μπορείτε να μετατρέψετε αποτελεσματικά τα αρχεία του έργου σας για εύκολη κοινή χρήση και διανομή.
## Συχνές ερωτήσεις
### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις της Java;
Α: Ναι, το Aspose.Tasks υποστηρίζει εκδόσεις Java ξεκινώντας από JDK 6 και νεότερη έκδοση.
### Ε: Μπορώ να προσαρμόσω την εμφάνιση της εξόδου PDF;
Α: Απολύτως! Το Aspose.Tasks παρέχει διάφορες επιλογές για να προσαρμόσετε την έξοδο PDF σύμφωνα με τις απαιτήσεις σας.
### Ε: Το Aspose.Tasks υποστηρίζει άλλες μορφές αρχείων για μετατροπή;
Α: Ναι, το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων, συμπεριλαμβανομένων των MPP, XML, XLSX και άλλων.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;
 Α: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Α: Για υποστήριξη και βοήθεια, μπορείτε να επισκεφτείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).