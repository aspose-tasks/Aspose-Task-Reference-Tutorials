---
date: 2025-12-17
description: Μάθετε πώς να εξάγετε το έργο σε PDF, να μειώσετε το κενό του υποσέλιδου
  και να αποθηκεύσετε το έργο ως εικόνα χρησιμοποιώντας το Aspose.Tasks για Java.
  Βελτιστοποιήστε το στυλ του MS Project σας χωρίς κόπο.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Εξαγωγή έργου σε PDF και μείωση του κενού μεταξύ λίστας εργασιών και υποσέλιδου
  στο Aspose.Tasks
url: /el/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εξαγωγή Έργου σε PDF και Μείωση του Κενού μεταξύ Λίστας Εργασιών και Υποσέλιδου στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial θα ανακαλύψετε **πώς να εξηγήσετε ένα έργο σε PDF** ενώ ταυτόχρονα μειώνετε το όνομα μεταξύ της λίστας εργασιών και του υποσέλιδου σε αρχεία Microsoft Project. Στο τέλος του οδηγού μπορείτε να δημιουργήσετε καθαρά PDF, εικόνες PNG και σελίδες HTML με συμπαγή διάταξη χρησιμοποιώντας το Aspose.Tasks για Java. Ας προχωρήσουμε βήμα‑βήμα.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “export project to PDF”;** Μετατρέπει ένα αρχείο MPP σε έγγραφο PDF διατηρώντας τις εργασίες, τα χρονοδιαγράμματα και τη μορφοποίηση.
- **Γιατί να μειώσω το κενό του υποσέλιδου;** Ένα μικρότερο κενό δημιουργεί πιο πυκνά, επαγγελματικές αναφορές, ειδικά για έγγραφα που εκτυπώνονται ή προβάλλονται στο web.
- **Μπορώ επίσης να αποθηκεύσω το έργο ως εικόνα;** Ναι – το Aspose.Tasks υποστηρίζει PNG, JPEG και άλλες μορφές εικόνας.
- **Χρειάζομαι ειδική άδεια;** Διατίθεται δωρεάν δοκιμαστική έκδοση· παρέχεται εμπορική άδεια για παραγωγική χρήση.
- **Ποια έκδοση της Java χρειάζεται;** Η Java8 ή νεότερη λειτουργεί με τη τρέχουσα βιβλιοθήκη Aspose.Tasks.

## Τι είναι η "εξαγωγή έργου σε PDF";
Η εξαγωγή ενός έργου σε PDF μετατρέπει την εσωτερική δομή MPP σε ένα φορητό έγγραφο που μπορεί να ανοιχθεί σε συσκευή χωρίς την ανάγκη του Microsoft Project. Είναι για κοινή χρήση αναφορών κατάστασης, ενημερώσεων σε συμμετέχοντες ή αρχειοθέτηση σχεδίων έργου.

## Γιατί να μειώσουμε το κενό υποσέλιδου;
Το προεπιλεγμένο κενό του υποσέλιδου μπορεί να προσθέσει περισσότερο λευκό χώρο, προκαλώντας προβλήματα σελιδοποίησης και ανισορροπίας στην εμφάνιση. Η μείωση του κενού σας εξασφαλίζει ότι το περιεχόμενό σας αξιοποιηθεί καλύτερα, κάνοντας το τελικό PDF ή την εικόνα πιο ευανάγνωστα.

## Πώς να μειώσετε το χάσμα μεταξύ της λίστας εργασιών και του υποσέλιδου;
Το Aspose.Tasks παρέχει την επιλογή `setReduceFooterGap(true)` για αποθήκευση εικόνας, PDF και HTML. Η ενεργοποίηση αυτής της Σημαίας λέει στη μηχανή να συμπιέσει το κενό μεταξύ της τελευταίας γραμμής εργασίας και του υποσέλιδου.

## Αποθήκευση έργου ως εικόνας με το Aspose.Tasks
Αν χρειάζεστε μια οπτική λήψη του χρονοδιαγράμματος σας, μπορείτε **να αποθηκεύσετε το έργο ως εικόνα** (PNG) εφαρμόζοντας τις ρυθμίσεις μείωσης του κενού.

## Java Project Εξαγωγή σε PDF
Οι παρακάτω ενότητες περιγράφουν μια πλήρη ροή εργασίας **java project export**, από τη φόρτωση του αρχείου MPP μέχρι την αποθήκευση του σε τρεις διαφορετικές μορφές.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω:
1. Java Development Kit (JDK) – έκδοση8 ή νεότερη.
2. Aspose.Tasks for Java Library – κατεβάστε το από [εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Πριν προχωρήσουμε στον κώδικα, ας εισάγουμε τα απαραίτητα πακέτα:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Βήμα 1: Δώστε τη διαδρομή προς τον κατάλογο δεδομένων σας
```java
String dataDir = "Your Data Directory";
```
Βεβαιωθείτε ότι αντικαθιστάτε το `"Your Data Directory"` με τη διαδρομή προς το πραγματικό φάκελο δεδομένων όπου βρίσκεται το αρχείο Microsoft Project (`HomeMovePlan.mpp` σε αυτό το παράδειγμα).

## Βήμα 2: Διαβάστε το αρχείο MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Αυτή η γραμμή κώδικα διαβάζει το αρχείο Microsoft Project με όνομα `HomeMovePlan.mpp`.

## Βήμα 3: Ορίστε το ImageSaveOptions (Αποθήκευση έργου ως εικόνα)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Διαμορφώστε τις επιλογές αποθήκευσης εικόνας, ορίζοντας το `ReduceFooterGap` σε `true` για να μειώσετε το κενό μεταξύ της λίστας εργασιών και του υποσέλιδου.

## Βήμα 4: Αποθήκευση ως εικόνα
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Αποθηκεύστε το έργο ως εικόνα με τις ρυθμισμένες επιλογές.

## Βήμα 5: Ορίστε το PdfSaveOptions (Εξαγωγή έργου σε PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Ορίστε τις επιλογές αποθήκευσης PDF, διασφαλίζοντας ότι το `ReduceFooterGap` είναι `true`.

## Βήμα 6: Αποθήκευση ως PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Αποθηκεύστε το έργο ως PDF με τις ρυθμισμένες επιλογές.

## Βήμα 7: Ορίστε το HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Καθορίστε τις επιλογές αποθήκευσης HTML, ορίζοντας το `ReduceFooterGap` σε `true`.

## Βήμα 8: Αποθήκευση ως HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Αποθηκεύστε το έργο ως αρχείο HTML με τις ρυθμισμένες επιλογές.

## Συμπέρασμα
Συνοψίζοντας, η μείωση του κενού μεταξύ της λίστας εργασιών και του υποσέλιδου σε αρχεία Microsoft Project είναι μια απλή διαδικασία με το Aspose.Tasks for Java. Ακολουθώντας τα βήματα του tutorial, μπορείτε αποτελεσματικά **να εξάγετε το έργο σε PDF**, να το αποθηκεύσετε ως εικόνα ή να δημιουργήσετε HTML διατηρώντας μια πυκνή και επαγγελματική διάταξη.

## Συχνές Ερωτήσεις (Επιπλέον)

**Ε: Πώς επηρεάζει τη σελιδοποίηση η μείωση του κενού υποσέλιδου;**
Α: Μειώνει τον κενό χώρο στο κάτω μέρος κάθε σελίδας, επιτρέποντας την εμφάνιση περισσότερων εργασιών σε μία σελίδα και μειώνοντας τον συνολικό αριθμό σελίδων.

**Ε: Μπορώ να εφαρμόσω την ίδια ρύθμιση μείωσης κενού μόνο σε μία σελίδα;**
A: Ναι, ορίζοντας `setRenderToSinglePage(true)` στο `ImageSaveOptions`μπορείτε να ελέγξετε τη σελιδοποίηση ενώ διατηρείτε τη μείωση του κενού.

**Ε: Είναι η επιλογή "setReduceFooterGap" διαθέσιμη για άλλες μορφές εξόδου;**
A: Προς το παρόν υποστηρίζεται για εξαγωγές PNG, PDF και HTML. Για άλλες μορφές ίσως να προσαρμόσετε τη διάταξη χειροκίνητα.

**Ε: Τι γίνεται αν το έργο μου περιέχει προσαρμοσμένα πεδία—διατηρούνται;**
Α: Όλα τα προσαρμοσμένα πεδία διατηρούνται κατά την εξαγωγή· οι ρυθμίσεις επηρεάζουν μόνο το κενό, όχι τα δεδομένα.

**Ε: Η βιβλιοθήκη χειρίζεται αποτελεσματικά μεγάλα έργα;**
A: Το Aspose.Tasks κάνει streaming των δεδομένων και μπορεί να επεξεργαστεί μεγάλα αρχεία MPP· ωστόσο, βεβαιωθείτε ότι έχετε επαρκή μνήμη κατά την εξαγωγή σε εικόνες υψηλής ανάλυσης.

---

**Τελευταία ενημέρωση: ** 17-12-2025
**Δοκιμασμένο με:** Aspose.Tasks 24.11 για Java
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}