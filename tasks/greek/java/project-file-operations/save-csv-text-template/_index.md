---
date: 2026-05-26
description: Μάθετε πώς να εξάγετε MPP σε CSV, να αποθηκεύσετε το έργο ως πρότυπο
  και να μετατρέψετε MPP σε κείμενο χρησιμοποιώντας το Aspose.Tasks για Java.
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: Εξαγωγή MPP σε CSV, κείμενο & πρότυπο με Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Εξαγωγή MPP σε CSV, κείμενο & πρότυπο με Aspose.Tasks Java
url: /el/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εξαγωγή MPP σε CSV, Κείμενο & Πρότυπο με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το tutorial θα ανακαλύψετε **πώς να εξάγετε MPP σε CSV**, να δημιουργήσετε επαναχρησιμοποιήσιμα πρότυπα έργων και να δημιουργήσετε εξαγωγές απλού κειμένου χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε χτίζετε μια αλυσίδα αναφορών, αυτοματοποιείτε τη δημιουργία έργων, είτε ενσωματώνετε με άλλα συστήματα, αυτά τα βήματα θα σας μεταφέρουν από ένα ακατέργαστο αρχείο MPP στην ακριβή έξοδο που χρειάζεστε—γρήγορα και χωρίς εγκατάσταση του Microsoft Project.

## Γρήγορες Απαντήσεις
- **Μπορώ να εξάγω MPP σε CSV;** Ναι – καλέστε `project.save("output.csv", SaveFileFormat.CSV)`.  
- **Πώς εξάγω σε απλό κείμενο;** Χρησιμοποιήστε `SaveFileFormat.TEXT` με τη μέθοδο `save`.  
- **Τι κάνει η επιλογή “save project as template”;** Δημιουργεί ένα αρχείο `.mpt` που αφαιρεί τις ημερομηνίες και τις βάσεις, αφήνοντας μόνο το σκελετό.  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική έκδοση λειτουργεί για αξιολόγηση· μια εμπορική άδεια αφαιρεί τους περιορισμούς αξιολόγησης.  
- **Ποια έκδοση της Java απαιτείται;** Η Java 8 ή νεότερη υποστηρίζεται πλήρως.

## Τι είναι το “save project as template”;
Η αποθήκευση ενός έργου ως πρότυπο (`.mpt`) καταγράφει τη δομή, την ιεραρχία εργασιών και τις αναθέσεις πόρων, ενώ αφαιρεί τις πραγματικές ημερομηνίες έναρξης/λήξης και τα δεδομένα βάσης. Αυτό κάνει το πρότυπο ιδανικό για επαναχρησιμοποίηση μιας τυπικής διάταξης έργου σε πολλαπλά νέα έργα. Διατηρεί όλα τα προσαρμοσμένα πεδία, τις τιμές κόστους και τις λεπτομέρειες ανάθεσης, εξασφαλίζοντας ότι το πρότυπο μπορεί να εφαρμοστεί σε οποιοδήποτε νέο έργο χωρίς να χάσει βασικές ρυθμίσεις.

## Γιατί να χρησιμοποιήσετε Aspose.Tasks για Java;
Εξάγετε MPP σε CSV, κείμενο ή πρότυπο απευθείας από τη Java χωρίς το Microsoft Project. Το Aspose.Tasks υποστηρίζει **πάνω από 20 εκδόσεις του Microsoft Project** (2000‑2024) και μπορεί να επεξεργαστεί αρχεία έως **500 MB** σε λειτουργία εξοικονόμησης μνήμης, καθιστώντας το ιδανικό για αυτοματοποίηση στο διακομιστή, CI pipelines και εργαλεία πολλαπλών πλατφορμών.

## Προαπαιτούμενα
- Εγκατεστημένο Java Development Kit 8 ή νεότερο.  
- Προσθέστε τη βιβλιοθήκη Aspose.Tasks for Java στο έργο σας – κατεβάστε την από [εδώ](https://releases.aspose.com/tasks/java/).  
- Μπορείτε επίσης να εξερευνήσετε άλλες βιβλιοθήκες Aspose στο [εδώ](https://releases.aspose.com/).  
- Βασικές γνώσεις Java και ρύθμισης έργου Maven/Gradle.

## Εισαγωγή Πακέτων
Η κλάση `Project` είναι το βασικό αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη. Αφού προσθέσετε τη βιβλιοθήκη στο αρχείο κατασκευής σας, εισάγετε τις απαιτούμενες κλάσεις:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Αποθήκευση Έργου ως CSV (Εξαγωγή MPP σε CSV)
Η εξαγωγή ενός αρχείου MPP σε CSV σας επιτρέπει να μεταφέρετε τα δεδομένα εργασιών σε Excel, Power BI ή οποιαδήποτε πλατφόρμα ανάλυσης.

### Βήμα 1: Φόρτωση του Έργου
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Βήμα 2: Αποθήκευση ως CSV
`SaveFileFormat.CSV` λέει στο Aspose.Tasks να εξάγει το έργο σε μορφή CSV.  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Αποθήκευση Έργου ως Κείμενο (Πώς να Εξάγετε Κείμενο)
Ένα αρχείο απλού κειμένου παρέχει μια γρήγορη, αναγνώσιμη από άνθρωπο εξαγωγή των εργασιών, των πόρων και των αναθέσεων.

### Βήμα 1: Φόρτωση του Έργου
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Βήμα 2: Αποθήκευση ως Κείμενο
`SaveFileFormat.TEXT` οδηγεί τη βιβλιοθήκη να δημιουργήσει μια αναπαράσταση σε απλό κείμενο του έργου.  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Αποθήκευση Έργου ως Πρότυπο (Δημιουργία Προτύπου Έργου Java)

### Βήμα 1: Φόρτωση του Έργου
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Βήμα 2: Ορισμός Επιλογών Προτύπου
Χρησιμοποιήστε `Project.save` με `SaveFileFormat.MPT` (ή `SaveFileFormat.TEMPLATE`) για να δημιουργήσετε ένα αρχείο προτύπου που αφαιρεί τις ημερομηνίες και τις βάσεις.  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Βήμα 3: Αποθήκευση ως Πρότυπο
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Συχνά Προβλήματα & Συμβουλές
- **File Not Found:** Επαληθεύστε τη διαδρομή προς το `YourProject.mpp` ή χρησιμοποιήστε απόλυτη διαδρομή.  
- **License Exceptions:** Χωρίς έγκυρη άδεια η βιβλιοθήκη λειτουργεί σε λειτουργία αξιολόγησης και μπορεί να προσθέσει υδατογραφήματα. Εφαρμόστε την άδειά σας νωρίς (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Large Projects:** Για αρχεία μεγαλύτερα από 200 MB, αυξήστε τη μνήμη heap της JVM (`-Xmx2g`) για να αποφύγετε `OutOfMemoryError`.  
- **Performance:** Κατά τη μετατροπή πολλών έργων, επαναχρησιμοποιήστε μια μόνο παρουσία `Project` όπου είναι δυνατόν για να μειώσετε το κόστος δημιουργίας αντικειμένων.

## Συμπέρασμα
Σας δείξαμε πώς να **εξάγετε MPP σε CSV**, **μετατρέψετε MPP σε κείμενο**, και **αποθηκεύσετε το έργο ως πρότυπο** χρησιμοποιώντας το Aspose.Tasks για Java. Αυτές οι δυνατότητες σας επιτρέπουν να αυτοματοποιήσετε την αναφορά, να δημιουργήσετε τυποποιημένα σκελετά έργων και να ενσωματώσετε τα δεδομένα του έργου σε οποιοδήποτε σύστημα downstream—χωρίς την ανάγκη εγκατάστασης του Microsoft Project.

## Συχνές Ερωτήσεις

**Q: Μπορεί το Aspose.Tasks για Java να διαχειριστεί σύνθετα, πολυ‑φάση έργα;**  
A: Ναι, υποστηρίζει πλήρως εργασίες, πόρους, αναθέσεις, βάσεις και προσαρμοσμένα πεδία σε όλες τις εκδόσεις του Project έως το 2024.

**Q: Διατίθεται δοκιμαστική έκδοση;**  
A: Απόλυτα – κατεβάστε μια δωρεάν δοκιμή από [εδώ](https://releases.aspose.com/).

**Q: Πού μπορώ να λάβω βοήθεια αν αντιμετωπίσω προβλήματα;**  
A: Το επίσημο φόρουμ υποστήριξης είναι στο [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) όπου το προσωπικό και τα μέλη της κοινότητας απαντούν σε ερωτήσεις.

**Q: Μπορώ να αποκτήσω προσωρινή άδεια για βραχυπρόθεσμη αξιολόγηση;**  
A: Ναι, αγοράστε μια προσωρινή άδεια στο [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Το Aspose.Tasks λειτουργεί σε Linux και macOS;**  
A: Είναι πλήρως δια‑πλατφορμικό και λειτουργεί σε Windows, macOS και Linux με οποιοδήποτε runtime Java 8+.

---

**Τελευταία Ενημέρωση:** 2026-05-26  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java 24.12 (latest)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Αρχείο MPP – Δημιουργία & Αποθήκευση Κενής Έργου σε Μορφή MPP με Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Φόρτωση Αρχείου MPP Java - Διαχείριση Ιδιοτήτων Έργου με Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Πώς να Εξάγετε MPP σε Excel με Aspose.Tasks για Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}