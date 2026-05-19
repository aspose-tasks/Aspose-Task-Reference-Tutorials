---
date: 2026-01-15
description: Μάθετε πώς να αποθηκεύετε ένα έργο ως PDF και να αποδίδετε τις προβολές
  Resource Usage και Sheet του MS Project χρησιμοποιώντας το Aspose.Tasks για Java.
  Ακολουθήστε τον βήμα‑βήμα οδηγό μας για να εξάγετε το έργο σε PDF χωρίς κόπο.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Αποθήκευση έργου ως PDF – Απόδοση χρήσης πόρων και προβολής φύλλου στο Aspose.Tasks
url: /el/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση Έργου ως PDF – Απόδοση Χρήσης Πόρων και Προβολής Φύλλου στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial θα ανακαλύψετε πώς να **αποθηκεύσετε το έργο ως PDF** ενώ αποδίδετε τις προβολές Χρήσης Πόρων και Φύλλου ενός αρχείου Microsoft Project. Είτε χρειάζεστε να δημιουργήσετε μια εκτυπώσιμη αναφορά για τα ενδιαφερόμενα μέρη είτε να μετατρέψετε αρχεία MPP σε μορφή που μπορεί να προβληθεί παγκοσμίως, το Aspose.Tasks for Java κάνει τη διαδικασία απλή—χωρίς να απαιτείται εγκατάσταση του Microsoft Project.

## Γρήγορες Απαντήσεις
- **Τι κάνει η «αποθήκευση έργου ως pdf»;** Μετατρέπει ένα αρχείο Project (MPP) σε έγγραφο PDF διατηρώντας την επιλεγμένη προβολή.  
- **Ποια προβολή μπορεί να εξαχθεί;** Χρήση Πόρων, Φύλλο, Gantt, Χρήση Εργασιών και άλλα.  
- **Μπορώ να αλλάξω την κλίμακα χρόνου στο PDF;** Ναι—οι επιλογές περιλαμβάνουν Ημέρες, ThirdsOfMonths και Μήνες.  
- **Χρειάζεται να είναι εγκατεστημένο το Microsoft Project;** Όχι, το Aspose.Tasks λειτουργεί ανεξάρτητα.  
- **Απαιτείται άδεια για παραγωγική χρήση;** Ναι, απαιτείται εμπορική άδεια για χρήση εκτός δοκιμής.

## Τι είναι η «αποθήκευση έργου ως PDF»;
Η αποθήκευση ενός έργου ως PDF δημιουργεί μια στατική, υψηλής ανάλυσης αναπαράσταση μιας επιλεγμένης προβολής Project. Αυτό είναι ιδανικό για κοινή χρήση με πελάτες, αρχειοθέτηση ή εκτύπωση χωρίς να αποκαλύπτεται το υποκείμενο αρχείο έργου.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για εξαγωγή έργου σε PDF;
- **Χωρίς εξωτερικές εξαρτήσεις** – λειτουργεί σε οποιαδήποτε πλατφόρμα που υποστηρίζει Java.  
- **Ακριβής έλεγχος** – μπορείτε να επιλέξετε την προβολή, την κλίμακα χρόνου και τη διάταξη.  
- **Υψηλή πιστότητα** – το PDF αντικατοπτρίζει την εμφάνιση της αρχικής προβολής Project.  
- **Έτοιμο για αυτοματοποίηση** – ενσωματώστε το σε CI pipelines, υπηρεσίες αναφοράς ή μαζικούς μετατροπείς.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – συνιστάται η τελευταία έκδοση.  
2. **Aspose.Tasks for Java** – κατεβάστε από τη [σελίδα λήψης](https://releases.aspose.com/tasks/java/).  

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαραίτητες κλάσεις στο Java project σας:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Οδηγός Βήμα‑βήμα

### Βήμα 1: Ανάγνωση του Πηγαίου Έργου
Φορτώστε το αρχείο MPP που θέλετε να μετατρέψετε.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Βήμα 2: Ορισμός SaveOptions με Απαιτούμενη Κλίμακα Χρόνου (Εξαγωγή Έργου σε PDF)
Διαμορφώστε τις επιλογές εξαγωγής PDF και ορίστε την επιθυμητή κλίμακα χρόνου.  
*Εδώ χρησιμοποιούμε **Days** ως παράδειγμα.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Βήμα 3: Ορισμός Μορφής Παρουσίασης σε ResourceUsage
Επιλέξτε την προβολή που θέλετε να αποδώσετε. Σε αυτήν την περίπτωση, η προβολή **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Βήμα 4: Αποθήκευση του Έργου (Μετατροπή MPP σε PDF)
Εκτελέστε τη μετατροπή και δημιουργήστε το αρχείο PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Βήμα 5: Απόδοση Προβολών για Άλλες Ρυθμίσεις Κλίμακας Χρόνου (Αλλαγή Κλίμακας Χρόνου PDF)
Επαναλάβετε τα προηγούμενα βήματα για να παραγάγετε PDFs με διαφορετικές κλίμακες χρόνου όπως **ThirdsOfMonths** και **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Συνηθισμένα Προβλήματα και Λύσεις
- **Σφάλματα αρχείου δεν βρέθηκε** – Επαληθεύστε ότι το `dataDir` δείχνει στο σωστό φάκελο και ότι το όνομα του αρχείου MPP ταιριάζει ακριβώς.  
- **Κενό PDF εξόδου** – Βεβαιωθείτε ότι το `PresentationFormat` ταιριάζει με μια προβολή που περιέχει δεδομένα (π.χ., ResourceUsage).  
- **Λανθασμένη κλίμακα χρόνου** – Ελέγξτε ξανά ότι το `options.setTimescale()` καλείται πριν από κάθε `project.save()`.

## Συχνές Ερωτήσεις

### Μπορεί το Aspose.Tasks να αποδώσει άλλες προβολές εκτός από τη Χρήση Πόρων και το Φύλλο;
Το Aspose.Tasks υποστηρίζει την απόδοση διαφόρων προβολών όπως Gantt Chart, Task Usage και Calendar, μεταξύ άλλων.

### Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;
Ναι, το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων Microsoft Project, συμπεριλαμβανομένων των MPP, MPT και XML.

### Μπορώ να προσαρμόσω την εμφάνιση των αποδιδόμενων προβολών χρησιμοποιώντας το Aspose.Tasks;
Απολύτως! Το Aspose.Tasks παρέχει εκτενείς επιλογές για προσαρμογή της εμφάνισης και της διάταξης των αποδιδόμενων προβολών ώστε να ταιριάζουν στις συγκεκριμένες απαιτήσεις σας.

### Απαιτείται το Microsoft Project να είναι εγκατεστημένο στο σύστημα για το Aspose.Tasks;
Όχι, το Aspose.Tasks είναι μια αυτόνομη βιβλιοθήκη και δεν απαιτεί εγκατάσταση του Microsoft Project για τη λειτουργία του.

### Διατίθεται τεχνική υποστήριξη για χρήστες του Aspose.Tasks;
Ναι, οι χρήστες του Aspose.Tasks μπορούν να επωφεληθούν από τεχνική υποστήριξη μέσω του [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-01-15  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

---