---
date: 2025-12-17
description: Μάθετε πώς να αποθηκεύετε το έργο ως εικόνα και να αλλάζετε την ανάλυση
  της εικόνας σε Java χρησιμοποιώντας το Aspose.Tasks for Java. Αυτός ο βήμα‑βήμα
  οδηγός δείχνει την απόδοση των δεδομένων του MS Project με μορφή 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Αποθήκευση έργου ως εικόνα – μορφή 24bppRgb με το Aspose.Tasks
url: /el/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση Έργου ως Εικόνα – Μορφή 24bppRgb με Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε πώς να **save project as image** χρησιμοποιώντας τη μορφή pixel 24bppRgb με το Aspose.Tasks για Java. Η απόδοση δεδομένων MS Project σε εικόνα είναι χρήσιμη όταν χρειάζεται να μοιραστείτε μια οπτική στιγμιότυπο ενός χρονοδιαγράμματος, να ενσωματώσετε μια γραμμή χρόνου σε μια αναφορά ή να δημιουργήσετε μικρογραφίες για μια πύλη έργου. Θα σας δείξουμε επίσης πώς να **change image resolution java** για να καλύψετε τις απαιτήσεις ποιότητας σας.

## Γρήγορες Απαντήσεις
- **Μπορώ να αποδώσω ένα έργο σε εικόνα;** Yes, Aspose.Tasks lets you save a project as TIFF, PNG, JPEG, etc.  
- **Ποια μορφή pixel παρέχει το καλύτερο βάθος χρώματος;** `Format24bppRgb` provides true‑color (24‑bit) images.  
- **Πώς μπορώ να ρυθμίσω την ανάλυση της εικόνας;** Use `setHorizontalResolution` and `setVerticalResolution` on `ImageSaveOptions`.  
- **Χρειάζομαι άδεια για παραγωγή;** A commercial license is required for non‑evaluation use.  
- **Είναι συμβατό με όλες τις εκδόσεις της Java;** Works with Java 8 and newer.

## Τι είναι το “save project as image”;
Η αποθήκευση ενός έργου ως εικόνα μετατρέπει την οπτική αναπαράσταση ενός αρχείου Microsoft Project (`.mpp`) σε μορφή raster (π.χ., TIFF). Το παραγόμενο αρχείο μπορεί να εμφανιστεί σε προγράμματα περιήγησης, να ενσωματωθεί σε έγγραφα ή να εκτυπωθεί χωρίς την ανάγκη της αρχικής εφαρμογής Project.

## Γιατί να χρησιμοποιήσετε τη μορφή 24bppRgb;
Η μορφή pixel 24bppRgb αποθηκεύει κάθε pixel με 8 bits για κόκκινο, πράσινο και μπλε, παρέχοντας ποιότητα αληθινών χρωμάτων χωρίς κανάλι άλφα. Αυτό είναι ιδανικό για αναφορές υψηλής καθαρότητας όπου η πιστότητα του χρώματος είναι σημαντική, ενώ διατηρεί τα μεγέθη αρχείων λογικά σε σύγκριση με μορφές 32‑bit.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – JDK 8 ή νεότερο εγκατεστημένο στο σύστημά σας.  
2. **Aspose.Tasks for Java** – Κατεβάστε και εγκαταστήστε από [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Η εξοικείωση με τη σύνταξη της Java και τη ρύθμιση του έργου θα σας βοηθήσει να ακολουθήσετε τα αποσπάσματα κώδικα.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαιτούμενες κλάσεις του Aspose.Tasks στο έργο Java σας:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Οδηγός Βήμα‑Βήμα

### Βήμα 1: Ορισμός Καταλόγου Δεδομένων
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή όπου βρίσκεται το αρχείο `.mpp` σας.

### Βήμα 2: Φόρτωση Αρχείου Έργου
```java
Project project = new Project(dataDir + "project.mpp");
```
Αυτή η γραμμή διαβάζει το αρχείο Microsoft Project (`project.mpp`) και δημιουργεί ένα αντικείμενο `Project` που το Aspose.Tasks μπορεί να χειριστεί.

### Βήμα 3: Διαμόρφωση Επιλογών Αποθήκευσης Εικόνας
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Εδώ ορίζουμε τη μορφή εξόδου σε TIFF, καθορίζουμε ανάλυση **72 dpi** (μπορείτε να αλλάξετε αυτές τις τιμές ώστε να ταιριάζουν στις ανάγκες σας – εδώ είναι που κάνετε **change image resolution java**), και επιλέγουμε τη μορφή pixel 24bppRgb για έξοδο αληθινών χρωμάτων.

### Βήμα 4: Αποθήκευση Δεδομένων Έργου ως Εικόνα
```java
project.save(dataDir + "resFile.tif", options);
```
Η μέθοδος `save` γράφει την αποδομένη εικόνα στο `resFile.tif` χρησιμοποιώντας τις παραπάνω επιλογές.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Κενή έξοδος εικόνας** | The project view may be empty. | Call `project.setDefaultView(ViewType.Gantt);` before saving. |
| **Εικόνα χαμηλής ποιότητας** | Resolution set too low. | Increase `setHorizontalResolution` and `setVerticalResolution` (e.g., 150 dpi). |
| **Μη υποστηριζόμενη μορφή pixel** | Using an older Aspose.Tasks version. | Upgrade to the latest Aspose.Tasks for Java release. |

## Συμπέρασμα
Τώρα γνωρίζετε πώς να **save project as image** με τη μορφή 24bppRgb και να ρυθμίσετε την ανάλυση χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η προσέγγιση σας επιτρέπει να δημιουργείτε καθαρές, χρωματικά ακριβείς οπτικές αναπαραστάσεις των χρονοδιαγραμμάτων του έργου σας για κοινή χρήση, αναφορές ή αρχειοθέτηση.

## Συχνές Ερωτήσεις
### Q: Μπορώ να αποδώσω δεδομένα έργου σε άλλες μορφές εικόνας;
A: Ναι, το Aspose.Tasks υποστηρίζει την απόδοση δεδομένων έργου σε διάφορες μορφές εικόνας όπως PNG, JPEG, BMP κ.λπ.

### Q: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις του MS Project;
A: Ναι, το Aspose.Tasks υποστηρίζει πολλαπλές εκδόσεις του MS Project, συμπεριλαμβανομένων των 2003, 2007, 2010, 2013 και 2016.

### Q: Μπορώ να προσαρμόσω την ανάλυση και τη μορφή pixel της αποδομένης εικόνας;
A: Ναι, μπορείτε να προσαρμόσετε την ανάλυση και τη μορφή pixel σύμφωνα με τις απαιτήσεις σας χρησιμοποιώντας το Aspose.Tasks.

### Q: Το Aspose.Tasks απαιτεί άδεια για εμπορική χρήση;
A: Ναι, χρειάζεται να αγοράσετε άδεια για εμπορική χρήση του Aspose.Tasks. Μπορείτε να αποκτήσετε προσωρινή άδεια για δοκιμαστικούς σκοπούς από [here](https://purchase.aspose.com/temporary-license/).

### Q: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
A: Μπορείτε να λάβετε υποστήριξη για το Aspose.Tasks από το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Τελευταία Ενημέρωση:** 2025-12-17  
**Δοκιμή Με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}