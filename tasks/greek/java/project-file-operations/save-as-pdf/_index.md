---
date: 2026-03-27
description: Μάθετε πώς να αποθηκεύσετε το έργο ως PDF χρησιμοποιώντας το Aspose.Tasks
  για Java, έναν απλό οδηγό για τη μετατροπή MPP σε PDF και την αποδοτική εξαγωγή
  αρχείων έργου.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να αποθηκεύσετε το έργο ως PDF με το Aspose.Tasks – Οδηγός εξαγωγής
url: /el/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποθηκεύσετε το έργο ως PDF με Aspise.Tasks – Οδηγός Εξαγωγής

## Εισαγωγή
Σε αυτό το σεμινάριο, θα ανακαλύψετε **how to save project as pdf** χρησιμοποιώντας το Aspose.Tasks για Java. Θα σας καθοδηγήσουμε από μια μετατροπή μίας γραμμής μέχρι προχωρημένη προσαρμογή PDF, ώστε να μετατρέψετε οποιοδήποτε αρχείο MPP (ή άλλο υποστηριζόμενο μορφότυπο) σε ένα επαγγελματικό, διαμοιραζόμενο έγγραφο PDF. Είτε χρειάζεστε μια γρήγορη εκτυπώσιμη αναφορά είτε ένα πλήρως μορφοποιημένο διάγραμμα Gantt, αυτά τα βήματα θα σας οδηγήσουν γρήγορα.

## Γρήγορες Απαντήσεις
- **What does “export PDF” mean in Aspose.Tasks?** Σημαίνει τη μετατροπή ενός αρχείου έργου (π.χ., MPP) σε έγγραφο PDF που διατηρεί τη οπτική διάταξη.  
- **Which library version is required?** Οποιαδήποτε έκδοση του Aspose.Tasks for Java που υποστηρίζει το `PdfSaveOptions` (συνιστάται η τελευταία έκδοση).  
- **Do I need a license for this conversion?** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για χρήση σε παραγωγή.  
- **Can I customize the PDF appearance?** Ναι – μπορείτε να ορίσετε την κλίμακα χρόνου, τις υπομνήματα και άλλες `PdfSaveOptions`.  
- **Is the conversion fast for large projects?** Συνήθως σε δευτερόλεπτα· η απόδοση εξαρτάται από το μέγεθος του έργου και τις επιλεγμένες επιλογές.

## Τι είναι το “save project as pdf” στο πλαίσιο του Aspose.Tasks;
Η αποθήκευση ενός έργου ως PDF με το Aspose.Tasks σημαίνει τη λήψη ενός αρχείου έργου (όπως `.mpp`, `.xml`, ή `.xlsx`) και η δημιουργία ενός PDF που αντικατοπτρίζει το διάγραμμα Gantt, την προβολή χρήσης εργασιών ή οποιαδήποτε άλλη μορφή παρουσίασης που έχετε ρυθμίσει. Αυτό είναι χρήσιμο για αναφορές, τεκμηρίωση ή διαμοιρασμό μόνο για ανάγνωση με μη‑τεχνικούς ενδιαφερόμενους.

## Γιατί να εξάγετε το Διάγραμμα Gantt σε PDF;
- **Universal readability:** Τα PDF ανοίγουν σε οποιαδήποτε συσκευή χωρίς την ανάγκη του αρχικού λογισμικού έργου.  
- **Professional presentation:** Διατηρεί χρώματα, γραμματοσειρές και διάταξη για αναφορές προς πελάτες.  
- **Easy distribution:** Μοιραστείτε μέσω email, εσωτερικού δικτύου ή αποθήκευσης στο σύννεφο χωρίς προβλήματα ελέγχου εκδόσεων.  
- **Compliance & archiving:** Τα PDF είναι ιδανικά για μακροπρόθεσμη αποθήκευση και συμμόρφωση με κανονισμούς.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

1. **Java Development Kit (JDK):** JDK 8 ή νεότερο εγκατεστημένο στον υπολογιστή σας.  
2. **Aspose.Tasks for Java Library:** Κατεβάστε τη βιβλιοθήκη από την επίσημη ιστοσελίδα [here](https://releases.aspose.com/tasks/java/).  
3. **A Project File:** Έχετε ένα υπάρχον αρχείο έργου (π.χ., `HomeMovePlan.mpp`) έτοιμο για μετατροπή.

## Εισαγωγή Πακέτων
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Οδηγός Βήμα‑βήμα

### Βήμα 1: Ανάγνωση του Αρχείου Εισόδου Έργου
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Αντικαταστήστε το `"Your Data Directory"` με το απόλυτο μονοπάτι όπου βρίσκεται το αρχείο `.mpp`. Αυτό φορτώνει το έργο στη μνήμη ώστε να μπορείτε να το επεξεργαστείτε ή να το εξάγετε.

### Βήμα 2: Αποθήκευση του Έργου ως PDF (Βασική Μετατροπή)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Η παραπάνω γραμμή εκτελεί μια απλή λειτουργία **save project as pdf**, δημιουργώντας το `Project5.pdf` στον ίδιο φάκελο.

### Βήμα 3: Προσαρμογή Περιεχομένου στο Μέγεθος Κελιού (Προηγμένες Επιλογές Αποθήκευσης PDF)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Εδώ δείχνουμε τη χρήση των **pdf save options** για έλεγχο της διάταξης:
- `setFitContent(true)` αναγκάζει το περιεχόμενο να ταιριάζει στο πλάτος του κελιού.  
- `setTimescale(Timescale.Months)` αλλάζει την κλίμακα χρόνου σε μήνες.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` επιλέγει την προβολή Χρήσης Εργασιών.

### Βήμα 4: Απόκρυψη Υπομνημάτων (Καθαρότερη Έξοδος)
```java
o.setLegendOnEachPage(false);
```
Η απενεργοποίηση των υπομνημάτων μπορεί να κάνει το PDF πιο συμπαγές, ειδικά για μεγάλα έργα.

### Βήμα 5: Αποθήκευση του Έργου με τις Εφαρμοσμένες Επιλογές
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Αυτό το τελικό βήμα γράφει το PDF χρησιμοποιώντας τις προσαρμοσμένες επιλογές που ορίστηκαν παραπάνω, παράγοντας ένα καθαρό έγγραφο με κλίμακα μηνών χωρίς υπομνήματα ανά σελίδα.

## Εξαγωγή Διάγραμμα Gantt σε PDF – Προσαρμοσμένο Στυλ
Αν θέλετε να εξάγετε μόνο το διάγραμμα Gantt με συγκεκριμένη εμφάνιση, ορίστε το `PresentationFormat` σε `GanttChart` και προσαρμόστε πρόσθετες επιλογές όπως `setBarColor` ή `setShowCriticalTasks`. Αυτή η προσέγγιση σας επιτρέπει να **export gantt chart to pdf** με πλήρη έλεγχο των οπτικών στοιχείων.

## Συχνά Προβλήματα & Συμβουλές
- **File not found:** Βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`) και δείχνει στον σωστό φάκελο.  
- **Blank pages:** Επαληθεύστε ότι το επιλεγμένο `PresentationFormat` ταιριάζει με την προβολή που επιθυμείτε (π.χ., Gantt, Task Usage).  
- **Large files take longer:** Σκεφτείτε να ορίσετε `o.setFitContent(false)` για πολύ μεγάλα έργα ώστε να μειώσετε το χρόνο επεξεργασίας.  

## Συχνές Ερωτήσεις

**Q: Is Aspose.Tasks compatible with all versions of Java?**  
A: Ναι, το Aspose.Tasks υποστηρίζει εκδόσεις Java ξεκινώντας από το JDK 6 και μετά.

**Q: Can I customize the appearance of the PDF output?**  
A: Απόλυτα! Το Aspose.Tasks παρέχει πολυάριθμες **pdf save options**—όπως κλίμακα χρόνου, ορατότητα υπομνημάτων και μορφή παρουσίασης—για να προσαρμόσετε το PDF στις ανάγκες σας.

**Q: Does Aspose.Tasks support other file formats for conversion?**  
A: Ναι, μπορείτε να μετατρέψετε μεταξύ MPP, XML, XLSX και πολλών άλλων μορφών, καθιστώντας το ένα ευέλικτο εργαλείο για **convert mpp to pdf** και άλλες μετατροπές.

**Q: Is there a trial version available for Aspose.Tasks?**  
A: Ναι, μπορείτε να αποκτήσετε μια δωρεάν δοκιμή του Aspose.Tasks από [here](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks?**  
A: Για υποστήριξη και βοήθεια, επισκεφθείτε το επίσημο [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό, τώρα γνωρίζετε **how to save project as pdf** από οποιοδήποτε έργο Java χρησιμοποιώντας το Aspose.Tasks, από μια απλή αποθήκευση μίας γραμμής μέχρι προχωρημένη προσαρμογή με `PdfSaveOptions`. Χρησιμοποιήστε αυτές τις τεχνικές για να παράγετε επαγγελματικά, διαμοιραζόμενα PDF για αναφορές, παρουσιάσεις σε πελάτες ή αρχειοθέτηση.

---

**Τελευταία Ενημέρωση:** 2026-03-27  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}