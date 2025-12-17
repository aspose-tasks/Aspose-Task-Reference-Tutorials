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

## Introduction  
Σε αυτό το tutorial θα ανακαλύψετε **πώς να εξάγετε ένα έργο σε PDF** ενώ ταυτόχρονα μειώνετε το ανεπιθύμητο κενό μεταξύ της λίστας εργασιών και του υποσέλιδου σε αρχεία Microsoft Project. Στο τέλος του οδηγού θα μπορείτε να δημιουργήσετε καθαρά PDF, εικόνες PNG και σελίδες HTML με συμπαγή διάταξη χρησιμοποιώντας το Aspose.Tasks for Java. Ας προχωρήσουμε βήμα‑βήμα.

## Quick Answers  
- **Τι σημαίνει “export project to PDF”;** Μετατρέπει ένα αρχείο MPP σε έγγραφο PDF διατηρώντας τις εργασίες, τα χρονοδιαγράμματα και τη μορφοποίηση.  
- **Γιατί να μειώσω το κενό του υποσέλιδου;** Ένα μικρότερο κενό δημιουργεί πιο πυκνά, επαγγελματικά αναφορές, ειδικά για έγγραφα που εκτυπώνονται ή προβάλλονται στο web.  
- **Μπορώ επίσης να αποθηκεύσω το έργο ως εικόνα;** Ναι – το Aspose.Tasks υποστηρίζει PNG, JPEG και άλλες μορφές εικόνας.  
- **Χρειάζομαι ειδική άδεια;** Διατίθεται δωρεάν δοκιμαστική έκδοση· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποια έκδοση της Java απαιτείται;** Η Java 8 ή νεότερη λειτουργεί με τη τρέχουσα βιβλιοθήκη Aspose.Tasks.

## What is “export project to PDF”?  
Η εξαγωγή ενός έργου σε PDF μετατρέπει την εσωτερική δομή MPP σε ένα φορητό έγγραφο που μπορεί να ανοιχθεί σε οποιαδήποτε συσκευή χωρίς την ανάγκη του Microsoft Project. Είναι ιδανική για κοινή χρήση αναφορών κατάστασης, ενημερώσεων σε ενδιαφερόμενους ή αρχειοθέτηση σχεδίων έργου.

## Why Reduce Footer Gap?  
Το προεπιλεγμένο κενό του υποσέλιδου μπορεί να προσθέσει περιττό λευκό χώρο, προκαλώντας προβλήματα σελιδοποίησης και ανισορροπία στην εμφάνιση. Η μείωση του κενού εξασφαλίζει ότι το περιεχόμενό σας αξιοποιείται αποδοτικότερα, κάνοντας το τελικό PDF ή την εικόνα πιο ευανάγνωστα.

## How to Reduce Gap Between Tasks List and Footer?  
Το Aspose.Tasks παρέχει την επιλογή `setReduceFooterGap(true)` για αποθήκευση εικόνας, PDF και HTML. Η ενεργοποίηση αυτής της σημαίας λέει στη μηχανή να συμπιέσει το κενό μεταξύ της τελευταίας γραμμής εργασίας και του υποσέλιδου.

## Save Project as Image with Aspose.Tasks  
Αν χρειάζεστε μια οπτική λήψη του χρονοδιαγράμματος σας, μπορείτε **να αποθηκεύσετε το έργο ως εικόνα** (PNG) εφαρμόζοντας τις ίδιες ρυθμίσεις μείωσης του κενού.

## Java Project Export to PDF  
Οι παρακάτω ενότητες περιγράφουν μια πλήρη ροή εργασίας **java project export**, από τη φόρτωση του αρχείου MPP μέχρι την αποθήκευση του σε τρεις διαφορετικές μορφές.

## Prerequisites
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω:
1. Java Development Kit (JDK) – έκδοση 8 ή νεότερη.  
2. Aspose.Tasks for Java Library – κατεβάστε το από [here](https://releases.aspose.com/tasks/java/).  

## Import Packages
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

## Step 1: Provide the Path to Your Data Directory
```java
String dataDir = "Your Data Directory";
```
Βεβαιωθείτε ότι αντικαθιστάτε το `"Your Data Directory"` με τη διαδρομή προς το πραγματικό φάκελο δεδομένων όπου βρίσκεται το αρχείο Microsoft Project (`HomeMovePlan.mpp` σε αυτό το παράδειγμα).

## Step 2: Read the MPP File
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Αυτή η γραμμή κώδικα διαβάζει το αρχείο Microsoft Project με όνομα `HomeMovePlan.mpp`.

## Step 3: Set ImageSaveOptions (Save Project as Image)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Διαμορφώστε τις επιλογές αποθήκευσης εικόνας, ορίζοντας το `ReduceFooterGap` σε `true` για να μειώσετε το κενό μεταξύ της λίστας εργασιών και του υποσέλιδου.

## Step 4: Save as Image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Αποθηκεύστε το έργο ως εικόνα με τις ρυθμισμένες επιλογές.

## Step 5: Set PdfSaveOptions (Export Project to PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Ορίστε τις επιλογές αποθήκευσης PDF, διασφαλίζοντας ότι το `ReduceFooterGap` είναι `true`.

## Step 6: Save as PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Αποθηκεύστε το έργο ως PDF με τις ρυθμισμένες επιλογές.

## Step 7: Set HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Καθορίστε τις επιλογές αποθήκευσης HTML, ορίζοντας το `ReduceFooterGap` σε `true`.

## Step 8: Save as HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Αποθηκεύστε το έργο ως αρχείο HTML με τις ρυθμισμένες επιλογές.

## Conclusion  
Συνοψίζοντας, η μείωση του κενού μεταξύ της λίστας εργασιών και του υποσέλιδου σε αρχεία Microsoft Project είναι μια απλή διαδικασία με το Aspose.Tasks for Java. Ακολουθώντας τα βήματα του tutorial, μπορείτε αποτελεσματικά **να εξάγετε το έργο σε PDF**, να το αποθηκεύσετε ως εικόνα ή να δημιουργήσετε HTML διατηρώντας μια πυκνή και επαγγελματική διάταξη.

## FAQ's

### Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?

A: Το Aspose.Tasks υποστηρίζει μορφές Microsoft Project 2003‑2019, εξασφαλίζοντας συμβατότητα με διάφορες εκδόσεις.

### Q: Can I customize the appearance of the footer in my project documents?

A: Ναι, το Aspose.Tasks παρέχει εκτενείς επιλογές προσαρμογής του υποσέλιδου, συμπεριλαμβανομένης της μείωσης των κενών και της ρύθμισης της τοποθέτησης του περιεχομένου.

### Q: Does Aspose.Tasks support saving projects in formats other than PNG, PDF, and HTML?

A: Ναι, το Aspose.Tasks υποστηρίζει μια ευρεία γκάμα μορφών, όπως XLSX, XML και MPP, μεταξύ άλλων.

### Q: Is there a trial version available for Aspose.Tasks?

A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks από [here](https://releases.aspose.com/).

### Q: Where can I get support if I encounter any issues while using Aspose.Tasks?

A: Μπορείτε να λάβετε βοήθεια από το φόρουμ της κοινότητας Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Frequently Asked Questions (Additional)

**Q: How does reducing the footer gap affect pagination?**  
A: Μειώνει τον κενό χώρο στο κάτω μέρος κάθε σελίδας, επιτρέποντας την εμφάνιση περισσότερων εργασιών σε μία σελίδα και μειώνοντας τον συνολικό αριθμό σελίδων.

**Q: Can I apply the same gap‑reduction setting to a single page only?**  
A: Ναι, ορίζοντας `setRenderToSinglePage(true)` στο `ImageSaveOptions` μπορείτε να ελέγξετε τη σελιδοποίηση ενώ διατηρείτε τη μείωση του κενού.

**Q: Is the `setReduceFooterGap` option available for other output formats?**  
A: Προς το παρόν υποστηρίζεται για εξαγωγές PNG, PDF και HTML. Για άλλες μορφές ίσως χρειαστεί να προσαρμόσετε τη διάταξη χειροκίνητα.

**Q: What if my project contains custom fields—are they preserved?**  
A: Όλα τα προσαρμοσμένα πεδία διατηρούνται κατά την εξαγωγή· οι ρυθμίσεις διάταξης επηρεάζουν μόνο το κενό, όχι τα δεδομένα.

**Q: Does the library handle large projects efficiently?**  
A: Το Aspose.Tasks κάνει streaming των δεδομένων και μπορεί να επεξεργαστεί μεγάλα αρχεία MPP· ωστόσο, βεβαιωθείτε ότι έχετε επαρκή μνήμη κατά την εξαγωγή σε εικόνες υψηλής ανάλυσης.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}