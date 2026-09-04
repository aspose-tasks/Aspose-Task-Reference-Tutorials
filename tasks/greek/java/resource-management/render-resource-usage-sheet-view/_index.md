---
date: 2026-06-15
description: Μάθετε πώς να μετατρέψετε mpp σε pdf και να αποδώσετε τις προβολές Χρήσης
  Πόρων και Sheet χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθήστε τον βήμα‑βήμα
  οδηγό μας για να ορίσετε την κλίμακα χρόνου και να δημιουργήσετε λεπτομερείς PDF
  reports χωρίς κόπο.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Μετατροπή MPP σε PDF και Απόδοση της Προβολής Χρήσης Πόρων – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Μετατροπή MPP σε PDF και Απόδοση της Προβολής Χρήσης Πόρων – Aspose.Tasks
url: /el/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή MPP σε PDF και Απόδοση Προβολής Χρήσης Πόρων – Aspose.Tasks

Σε αυτό το σεμινάριο θα μάθετε **πώς να μετατρέψετε mpp σε pdf** ενώ αποδίδετε τις προβολές Χρήσης Πόρων και Φύλλου ενός αρχείου Microsoft Project. Η χρήση του Aspose.Tasks για Java εξαλείφει την ανάγκη για Microsoft Project στον διακομιστή, παρέχοντάς σας έναν γρήγορο, αξιόπιστο τρόπο δημιουργίας αναφορών PDF από αρχεία MPP. Θα σας δείξουμε επίσης **πώς να ορίσετε την κλίμακα χρόνου** ώστε το αποτέλεσμα να ταιριάζει με τις απαιτήσεις αναφοράς σας.

## Γρήγορες Απαντήσεις
- **Τι κάνει το Aspose.Tasks;** Διαβάζει, τροποποιεί και μετατρέπει αρχεία Microsoft Project (MPP) χωρίς να χρειάζεται εγκατάσταση του MS Project.  
- **Μπορώ να μετατρέψω MPP σε PDF με μία γραμμή κώδικα;** Ναι – φορτώστε το Project, ορίστε τις SaveOptions και καλέστε `save`.  
- **Ποιες κλίμακες χρόνου υποστηρίζονται;** Ημέρες, ThirdsOfMonths και Μήνες.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια για μη‑δοκιμαστικές εγκαταστάσεις.  
- **Είναι η βιβλιοθήκη συμβατή με Java 8+;** Απόλυτα – υποστηρίζει Java 8 και μεταγενέστερες εκδόσεις.

## Τι είναι η μετατροπή mpp σε pdf;
*Convert mpp to pdf* αναφέρεται στη διαδικασία λήψης ενός αρχείου Microsoft Project (.mpp) και δημιουργίας μιας έκδοσης Portable Document Format (PDF) που αναπαράγει πιστά τους πίνακες, τα χρονοδιαγράμματα, τα γραφήματα και τις κατανομές πόρων του έργου. Το παραγόμενο PDF μπορεί να μοιραστεί, εκτυπωθεί και αρχειοθετηθεί εύκολα χωρίς να απαιτείται εγκατάσταση του Microsoft Project στον υπολογιστή του παραλήπτη.

## Γιατί να μετατρέψετε το Project σε PDF με το Aspose.Tasks;
Το Aspose.Tasks υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να αποδώσει έργα με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, μειώνοντας τη χρήση RAM έως και 70 %. Η έξοδος PDF διατηρεί πίνακες, γραφήματα και κατανομές πόρων, καθιστώντας την ιδανική για διανομή σε ενδιαφερόμενους και αρχειοθέτηση.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – Java 8 ή νεότερη έκδοση εγκατεστημένη στο σύστημά σας.  
2. **Aspose.Tasks for Java** – κατεβάστε το τελευταίο JAR από τη [σελίδα λήψης](https://releases.aspose.com/tasks/java/).

## Πώς να μετατρέψετε mpp σε pdf χρησιμοποιώντας το Aspose.Tasks για Java;
Φορτώστε το πηγαίο αρχείο MPP, διαμορφώστε την επιθυμητή κλίμακα χρόνου, ορίστε τη μορφή παρουσίασης σε **ResourceUsage** και αποθηκεύστε το αποτέλεσμα ως PDF. Αυτή η ολοκληρωμένη ροή απαιτεί μόνο λίγες κλήσεις API και εκτελείται σε λιγότερο από ένα δευτερόλεπτο για τυπικά μεγέθη έργων.

### Βήμα 1: Ανάγνωση του Πηγαίου Project
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που έχει φορτωθεί στη μνήμη, παρέχοντας πρόσβαση στα δεδομένα και τη δομή του.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Βήμα 2: Ορισμός SaveOptions με τις Απαιτούμενες Ρυθμίσεις TimeScale
`SaveOptions` διαμορφώνει τον τρόπο αποθήκευσης του project, επιτρέποντάς σας να ορίσετε ρυθμίσεις ειδικές για τη μορφή, όπως η κλίμακα χρόνου.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Βήμα 3: Ορισμός της Μορφής Παρουσίασης σε ResourceUsage
`PresentationFormat` καθορίζει ποια προβολή του Project (π.χ., ResourceUsage) θα αποδοθεί στο έγγραφο εξόδου.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Βήμα 4: Αποθήκευση του Project ως PDF
`project.save` γράφει το project σε αρχείο χρησιμοποιώντας τις παρεχόμενες `SaveOptions`, παράγοντας το τελικό PDF.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Βήμα 5: Απόδοση Προβολών για Άλλες Ρυθμίσεις TimeScale
Επαναλάβετε τα προηγούμενα βήματα, αλλάζοντας την τιμή `TimeScale` για να αποδώσετε πρόσθετες προβολές κλίμακας χρόνου.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Βήμα 6: Προαιρετικά – Μετατροπή Πολλαπλών Projects σε Παρτίδα
Εάν χρειάζεται να **μετατρέψετε project σε pdf** για πολλά αρχεία, τοποθετήστε τη λογική που περιγράφηκε παραπάνω μέσα σε βρόχο που διατρέχει έναν φάκελο με αρχεία *.mpp*. Αυτή η προσέγγιση **αποθηκεύει αρχεία ms project pdf** μαζικά με ελάχιστες αλλαγές κώδικα.  
Ο παρακάτω κώδικας δείχνει ένα πλήρες παράδειγμα μετατροπής ενός αρχείου MPP σε PDF με τις επιθυμητές ρυθμίσεις.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Συχνά Προβλήματα και Λύσεις
- **Λείπουν γραμματοσειρές στο PDF** – Βεβαιωθείτε ότι οι απαιτούμενες γραμματοσειρές είναι εγκατεστημένες στον διακομιστή ή ενσωματώστε τις μέσω `PdfSaveOptions`.  
- **Μεγάλα αρχεία project προκαλούν OutOfMemoryError** – Χρησιμοποιήστε `LoadOptions.setLoadAllResources(false)` για φόρτωση πόρων κατά απαίτηση.  
- **Λανθασμένη απόδοση κλίμακας χρόνου** – Επαληθεύστε ότι το `options.setTimeScale(TimeScale.Days)` (ή άλλο enum) ταιριάζει με την επιθυμητή λεπτομέρεια.

## Συχνές Ερωτήσεις

**Ε: Μπορεί το Aspose.Tasks να αποδώσει άλλες προβολές εκτός από Resource Usage και Sheet;**  
Α: Ναι, υποστηρίζει επίσης Gantt Chart, Task Usage, Calendar και πολλές επιπλέον προβολές.

**Ε: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;**  
Α: Απόλυτα – διαχειρίζεται μορφές MPP, MPT και XML από το Project 2000 έως το Project 2021.

**Ε: Μπορώ να προσαρμόσω την εμφάνιση των αποδιδόμενων προβολών;**  
Α: Ναι, μπορείτε να τροποποιήσετε χρώματα, γραμματοσειρές και διατάξεις στηλών μέσω `PdfSaveOptions` και `PresentationOptions`.

**Ε: Απαιτεί το Aspose.Tasks εγκατάσταση του Microsoft Project;**  
Α: Όχι, είναι μια ανεξάρτητη βιβλιοθήκη και λειτουργεί σε οποιοδήποτε περιβάλλον συμβατό με Java.

**Ε: Πού μπορώ να λάβω τεχνική υποστήριξη;**  
Α: Η υποστήριξη είναι διαθέσιμη μέσω του [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Τελευταία Ενημέρωση:** 2026-06-15  
**Δοκιμή Με:** Aspose.Tasks 24.12 for Java  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Απόδοση Προβολής Χρήσης Πόρων και Φύλλου στο Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Πώς να Εξάγετε PDF στο Aspose.Tasks – Αποθήκευση ως PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Πώς να Δημιουργήσετε Αρχεία MPP με το Aspose.Tasks για Java](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}