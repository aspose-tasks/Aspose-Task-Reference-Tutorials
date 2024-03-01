---
title: Απόδοση χρήσης πόρων και προβολής φύλλων στο Aspose.Tasks
linktitle: Απόδοση χρήσης πόρων και προβολής φύλλων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να αποδίδετε τις προβολές χρήσης πόρων και φύλλων MS Project στο Aspose.Tasks για Java. Ακολουθήστε τον οδηγό βήμα προς βήμα για να δημιουργήσετε λεπτομερείς αναφορές PDF χωρίς κόπο.
type: docs
weight: 16
url: /el/java/resource-management/render-resource-usage-sheet-view/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθουμε πώς να χρησιμοποιούμε το Aspose.Tasks για Java για την απόδοση των προβολών χρήσης πόρων και φύλλων MS Project. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project χωρίς να απαιτείται η εγκατάσταση του Microsoft Project.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκατεστημένο το Java Development Kit στο σύστημά σας. Μπορείτε να κάνετε λήψη και εγκατάσταση της πιο πρόσφατης έκδοσης του JDK από τον ιστότοπο της Oracle.
2.  Aspose.Tasks για Java: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για Java από το[σελίδα λήψης](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Πρώτα, πρέπει να εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Βήμα 1: Διαβάστε το έργο Πηγή
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
// Διαβάστε την πηγή Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
Σε αυτό το βήμα, καθορίζουμε τη διαδρομή προς το αρχείο προέλευσης Project (`ResourceUsageView.mpp` ) και χρησιμοποιήστε το`Project` τάξη για να το διαβάσετε.
## Βήμα 2: Καθορίστε τις επιλογές αποθήκευσης με τις απαιτούμενες ρυθμίσεις χρονικής κλίμακας
```java
// Ορίστε τις SaveOptions με τις απαιτούμενες ρυθμίσεις TimeScale ως Ημέρες
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Εδώ, ορίζουμε το`SaveOptions` με τα απαιτούμενα`TimeScale` Ρυθμίσεις. Σε αυτό το παράδειγμα, ορίσαμε το`TimeScale` σημερινή.
## Βήμα 3: Ορίστε τη μορφή παρουσίασης σε ResourceUsage
```java
// Ορίστε τη μορφή παρουσίασης σε ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Ορίσαμε τη μορφή παρουσίασης σε`ResourceUsage`, υποδεικνύοντας ότι θέλουμε να αποδώσουμε την προβολή Χρήση πόρων.
## Βήμα 4: Αποθηκεύστε το έργο
```java
// Αποθηκεύστε το έργο
project.save(dataDir + days, options);
```
Τέλος, αποθηκεύουμε το Project με τις καθορισμένες επιλογές. Σε αυτό το παράδειγμα, το αρχείο εξόδου θα αποθηκευτεί ως`result_days.pdf`.
## Βήμα 5: Απόδοση προβολών για άλλες ρυθμίσεις χρονικής κλίμακας
Επαναλάβετε τα βήματα 2 έως 4 για απόδοση προβολών με διαφορετικές ρυθμίσεις TimeScale (ThirdsOfMonths και Months).
```java
// Ορίστε τις ρυθμίσεις χρονικής κλίμακας σε ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Αποθηκεύστε το έργο
project.save(thirds, options);
// Ορίστε τις ρυθμίσεις Χρονικής κλίμακας σε Μήνες
options.setTimescale(Timescale.Months);
// Αποθηκεύστε το έργο
project.save(dataDir + months, options);
```
 Φροντίστε να αλλάξετε το`Timescale` ρυθμίσεις ανάλογα για κάθε προβολή.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να χρησιμοποιήσουμε το Aspose.Tasks για Java για την απόδοση των προβολών χρήσης πόρων και φύλλων MS Project. Ακολουθώντας τα βήματα που περιγράφονται παραπάνω, μπορείτε να δημιουργήσετε αποτελεσματικά αυτές τις προβολές σε μορφή PDF, διευκολύνοντας την καλύτερη οπτικοποίηση και ανάλυση των δεδομένων του έργου σας.
## Συχνές ερωτήσεις
### Μπορεί το Aspose.Tasks να αποδώσει άλλες προβολές εκτός από τη Χρήση πόρων και το Φύλλο;
Το Aspose.Tasks υποστηρίζει την απόδοση διαφόρων προβολών, όπως οι προβολές Gantt Chart, Task Usage και Calendar, μεταξύ άλλων.
### Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;
Ναι, το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.
### Μπορώ να προσαρμόσω την εμφάνιση των αποδομένων προβολών χρησιμοποιώντας το Aspose.Tasks;
Απολύτως! Το Aspose.Tasks παρέχει εκτενείς επιλογές για την προσαρμογή της εμφάνισης και της διάταξης των προβολών που έχουν αποδοθεί ώστε να ταιριάζουν στις συγκεκριμένες απαιτήσεις σας.
### Το Aspose.Tasks απαιτεί την εγκατάσταση του Microsoft Project στο σύστημα;
Όχι, το Aspose.Tasks είναι μια αυτόνομη βιβλιοθήκη και δεν απαιτεί την εγκατάσταση του Microsoft Project για τη λειτουργία του.
### Είναι διαθέσιμη τεχνική υποστήριξη για τους χρήστες του Aspose.Tasks;
 Ναι, οι χρήστες του Aspose.Tasks μπορούν να επωφεληθούν από την τεχνική υποστήριξη μέσω του[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).