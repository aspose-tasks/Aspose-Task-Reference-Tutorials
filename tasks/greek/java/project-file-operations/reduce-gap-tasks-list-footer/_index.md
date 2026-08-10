---
date: 2026-05-20
description: Μάθετε πώς να εξάγετε το έργο σε PDF, να μειώσετε το κενό του υποσέλιδου
  και να αποθηκεύσετε το έργο ως εικόνα χρησιμοποιώντας το Aspose.Tasks για Java.
  Βελτιστοποιήστε τη διάταξη του MS Project χωρίς κόπο.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Εξαγωγή έργου σε PDF και μείωση του κενού μεταξύ λίστας εργασιών και υποσέλιδου
  στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Εξαγωγή έργου σε PDF και μείωση του κενού μεταξύ λίστας εργασιών και υποσέλιδου
  στο Aspose.Tasks
url: /el/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εξαγωγή έργου σε PDF και μείωση του κενού μεταξύ λίστας εργασιών και υποσέλιδου στο Aspose.Tasks

## Εισαγωγή  
Σε αυτό το σεμινάριο θα ανακαλύψετε **πώς να εξάγετε ένα έργο σε PDF** ενώ ταυτόχρονα μειώνετε τον ανεπιθύμητο χώρο μεταξύ της λίστας εργασιών και του υποσέλιδου σε αρχεία Microsoft Project. Στο τέλος του οδηγού θα μπορείτε να δημιουργήσετε καθαρά PDF, εικόνες PNG και σελίδες HTML με συμπαγή διάταξη χρησιμοποιώντας το Aspose.Tasks για Java. Ας περάσουμε βήμα‑βήμα τη διαδικασία, και θα δείτε γιατί αυτό είναι σημαντικό για επαγγελματική αναφορά.

## Γρήγορες απαντήσεις  
- **Τι σημαίνει “export project to PDF”**? Μετατρέπει ένα αρχείο MPP σε έγγραφο PDF διατηρώντας τις εργασίες, τις χρονογραμμές και τη μορφοποίηση.  
- **Γιατί να μειώσετε το κενό του υποσέλιδου;** Ένα μικρότερο κενό δημιουργεί πιο σφιχτές, πιο επαγγελματικές αναφορές, ειδικά για έντυπα ή έγγραφα που προβάλλονται στο web.  
- **Μπορώ επίσης να αποθηκεύσω το έργο ως εικόνα;** Ναι – το Aspose.Tasks υποστηρίζει PNG, JPEG και άλλες μορφές εικόνας.  
- **Χρειάζομαι ειδική άδεια;** Διατίθεται δωρεάν δοκιμαστική έκδοση· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποια έκδοση της Java απαιτείται;** Η Java 8 ή νεότερη λειτουργεί με τη τρέχουσα βιβλιοθήκη Aspose.Tasks.  

## Τι είναι το “export project to PDF”;  
Η εξαγωγή ενός έργου σε PDF μετατρέπει τη εσωτερική δομή MPP σε ένα φορητό έγγραφο που μπορεί να ανοιχθεί σε οποιαδήποτε συσκευή χωρίς την ανάγκη του Microsoft Project. Αυτό είναι ιδανικό για την κοινή χρήση αναφορών κατάστασης, ενημερώσεων ενδιαφερομένων ή αρχειοθέτησης σχεδίων έργου. Διατηρεί την αρχική διάταξη, τα χρώματα και την ιεραρχία των εργασιών, εξασφαλίζοντας ότι το PDF φαίνεται ταυτόσημο με το αρχικό αρχείο.

## Γιατί να μειώσετε το κενό του υποσέλιδου;  
Το προεπιλεγμένο κενό του υποσέλιδου μπορεί να προσθέσει περιττό λευκό χώρο, προκαλώντας προβλήματα σελιδοποίησης και ανισορροπημένη εμφάνιση. Η μείωση του κενού εξασφαλίζει ότι το περιεχόμενό σας χρησιμοποιεί τη σελίδα αποδοτικά, κάνοντας το τελικό PDF ή την εικόνα πιο ευανάγνωστα. Μια πιο σφιχτή διάταξη μειώνει επίσης τον συνολικό αριθμό σελίδων, κάτι που μπορεί να μειώσει το κόστος εκτύπωσης και να βελτιώσει την πλοήγηση στην οθόνη.

## Πώς να μειώσετε το κενό μεταξύ λίστας εργασιών και υποσέλιδου;  
`setReduceFooterGap` είναι μια ιδιότητα Boolean που ελέγχει το διάστημα του υποσέλιδου κατά την εξαγωγή.  
Το Aspose.Tasks παρέχει την επιλογή `setReduceFooterGap(true)` για λειτουργίες αποθήκευσης εικόνας, PDF και HTML. Η ενεργοποίηση αυτής της σημαίας λέει στη μηχανή να συμπιέσει το χώρο μεταξύ της τελευταίας σειράς εργασίας και του υποσέλιδου της σελίδας. Όταν οριστεί σε true, ο renderer κόβει αυτόματα το περιθώριο χωρίς να αφαιρέσει δεδομένα εργασίας, οδηγώντας σε πιο καθαρή διάταξη σελίδας.

## Αποθήκευση έργου ως εικόνα με Aspose.Tasks  
`ImageSaveOptions` ρυθμίζει πώς ένα έργο αποδίδεται σε αρχείο εικόνας.  
Η κλάση `ImageSaveOptions` σας επιτρέπει να εξάγετε ένα στιγμιότυπο του χρονοδιαγράμματος ως PNG, JPEG ή BMP. Όταν επίσης ενεργοποιήσετε το `setReduceFooterGap(true)`, η παραγόμενη εικόνα αντικατοπτρίζει τη συμπαγή διάταξη του PDF, παρέχοντάς σας μια καθαρή οπτική για παρουσιάσεις ή πίνακες ελέγχου.

## Εξαγωγή έργου Java σε PDF  
Οι παρακάτω ενότητες περιγράφουν μια πλήρη ροή εργασίας **java project export**, από τη φόρτωση του αρχείου MPP έως την αποθήκευσή του σε τρία διαφορετικά μορφότυπα.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
1. Java Development Kit (JDK) – έκδοση 8 ή νεότερη.  
2. Aspose.Tasks for Java Library – κατεβάστε το από [here](https://releases.aspose.com/tasks/java/).  

## Εισαγωγή πακέτων  
Before diving into the coding part, let's import the necessary packages:

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

## Βήμα 1: Παρέχετε τη διαδρομή προς τον φάκελο δεδομένων σας  
```java
String dataDir = "Your Data Directory";
```  
Βεβαιωθείτε ότι αντικαθιστάτε `"Your Data Directory"` με τη διαδρομή προς τον πραγματικό φάκελο δεδομένων όπου βρίσκεται το αρχείο Microsoft Project (`HomeMovePlan.mpp` σε αυτό το παράδειγμα).

## Βήμα 2: Ανάγνωση του αρχείου MPP  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Αυτή η γραμμή κώδικα διαβάζει το αρχείο Microsoft Project με όνομα `HomeMovePlan.mpp`.

## Βήμα 3: Ορισμός ImageSaveOptions (Αποθήκευση έργου ως εικόνα)  
`ImageSaveOptions` ρυθμίζει πώς ένα έργο αποδίδεται σε αρχείο εικόνας.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Ρυθμίστε τις επιλογές αποθήκευσης εικόνας, ορίζοντας το `ReduceFooterGap` σε `true` για να μειώσετε το κενό μεταξύ της λίστας εργασιών και του υποσέλιδου.

## Βήμα 4: Αποθήκευση ως εικόνα  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Αποθηκεύστε το έργο ως εικόνα με τις ρυθμισμένες επιλογές.

## Βήμα 5: Ορισμός PdfSaveOptions (Εξαγωγή έργου σε PDF)  
`PdfSaveOptions` καθορίζει τις ρυθμίσεις για την εξαγωγή ενός έργου σε μορφή PDF.  
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

## Βήμα 7: Ορισμός HtmlSaveOptions  
`HtmlSaveOptions` ελέγχει τη μετατροπή ενός έργου σε HTML, συμπεριλαμβανομένων των επιλογών στυλ και διάταξης.  
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

## Κοινές περιπτώσεις χρήσης και συμβουλές  
- **Stakeholder reporting:** Εξαγωγή σε PDF με μειωμένο κενό υποσέλιδου για να διατηρούνται οι αναφορές σύντομες και φιλικές προς το εκτυπωτή.  
- **Dashboard snapshots:** Χρησιμοποιήστε την εξαγωγή εικόνας όταν χρειάζεστε μια γρήγορη οπτική για Power BI ή Confluence.  
- **Web publishing:** Η εξαγωγή HTML διατηρεί την αλληλεπιδραστικότητα και μπορεί να ενσωματωθεί απευθείας σε εσωτερικές πύλες.  
- **Pro tip:** Για πολύ μεγάλα έργα, αυξήστε το `Resolution` στο `ImageSaveOptions` σε 300 dpi για να διατηρήσετε την ευκρίνεια ενώ εξακολουθείτε να επωφελείστε από το μειωμένο κενό.

## Συχνές ερωτήσεις (Πρόσθετες)

**Q: Πώς η μείωση του κενού του υποσέλιδου επηρεάζει τη σελιδοποίηση;**  
A: Μειώνει τον κενό χώρο στο κάτω μέρος κάθε σελίδας, επιτρέποντας σε περισσότερες εργασίες να χωρέσουν σε μία σελίδα και μειώνοντας τον συνολικό αριθμό σελίδων.

**Q: Μπορώ να εφαρμόσω την ίδια ρύθμιση μείωσης κενού μόνο σε μία σελίδα;**  
A: Ναι, ορίζοντας το `setRenderToSinglePage(true)` στο `ImageSaveOptions` μπορείτε να ελέγξετε τη σελιδοποίηση ενώ εξακολουθείτε να μειώνετε το κενό.

**Q: Είναι η επιλογή `setReduceFooterGap` διαθέσιμη για άλλες μορφές εξόδου;**  
A: Προς το παρόν υποστηρίζεται για εξαγωγές PNG, PDF και HTML. Για άλλες μορφές ίσως χρειαστεί να προσαρμόσετε τη διάταξη χειροκίνητα.

**Q: Τι γίνεται αν το έργο μου περιέχει προσαρμοσμένα πεδία—διατηρούνται;**  
A: Όλα τα προσαρμοσμένα πεδία διατηρούνται κατά την εξαγωγή· οι προσαρμογές διάταξης επηρεάζουν μόνο το διάστημα, όχι τα δεδομένα.

**Q: Η βιβλιοθήκη διαχειρίζεται μεγάλα έργα αποδοτικά;**  
A: Το Aspose.Tasks μεταδίδει δεδομένα σε ροή και μπορεί να επεξεργαστεί αρχεία MPP με εκατοντάδες σελίδες χωρίς να φορτώσει ολόκληρο το αρχείο στη μνήμη· ωστόσο, διανείμετε επαρκή χώρο heap όταν εξάγετε εικόνες υψηλής ανάλυσης.

---

**Τελευταία ενημέρωση:** 2026-05-20  
**Δοκιμή με:** Aspose.Tasks 24.11 for Java  
**Συγγραφέας:** Aspose

## Σχετικά σεμινάρια

- [Αποθήκευση έργου ως εικόνα – Μορφή 24bppRgb με Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Αποθήκευση έργου ως πρότυπο, CSV και κείμενο με Aspose.Tasks για Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Πώς να δημιουργήσετε αρχείο MPP – Δημιουργία & αποθήκευση κενής έργου σε μορφή MPP με Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}