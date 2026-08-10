---
date: 2026-05-31
description: Μάθετε πώς να εξάγετε MPP σε Excel και να μετατρέψετε το αρχείο έργου
  σε Excel χρησιμοποιώντας το Aspose.Tasks για Java. Απλά βήματα για προγραμματιστές
  Java.
keywords:
- export mpp to excel
- convert mpp to xlsx
- write excel workbook java
- project file to spreadsheet
- export project schedule excel
linktitle: Αποθήκευση δεδομένων σε Excel στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  headline: How to Export MPP to Excel with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  name: How to Export MPP to Excel with Aspose.Tasks for Java
  steps:
  - name: Define the Data Directory Path
    text: Set the folder where your `.mpp` file resides. Replace the placeholder with
      your actual path. The `dataDir` string tells the API where to locate the source
      file and where to write the resulting Excel workbook. java String dataDir =
      "Your Data Directory";
  - name: Load the Project File
    text: Create a `Project` instance by loading the `.mpp` file you want to convert.
      The `Project` class represents a Microsoft Project file in memory, allowing
      further manipulation or direct export. java Project project = new Project(dataDir
      + "project5.mpp");
  - name: Save the Project as XLSX
    text: 'Finally, export the loaded project to an Excel workbook. The `SaveFileFormat`
      enum specifies the output file format; `SaveFileFormat.Xlsx` tells Aspose.Tasks
      to generate a modern `.xlsx` file, effectively **convert MPP file to XLSX**.
      You can also specify `SaveOptions` to fine‑tune column widths or '
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides extensive APIs to read, write, and
      modify project files, including tasks, resources, calendars, and custom fields.
    question: Can I use Aspose.Tasks for Java to manipulate project data programmatically?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: The official documentation is available [here](https://reference.aspose.com/tasks/java/).
    question: Where can I find documentation for Aspose.Tasks for Java?
  - answer: Support is provided through the Aspose.Tasks forum, reachable [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for issues or queries related to Aspose.Tasks
      for Java?
  - answer: Yes, a temporary license can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να εξάγετε MPP σε Excel με το Aspose.Tasks για Java
url: /el/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να εξάγετε MPP σε Excel με Aspose.Tasks για Java

## Εισαγωγή
Το Aspose.Tasks for Java είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να **εξάγετε MPP σε Excel** γρήγορα και αξιόπιστα. Σε αυτό το tutorial θα σας καθοδηγήσουμε βήμα-βήμα στις ακριβείς ενέργειες που απαιτούνται για τη μετατροπή ενός αρχείου Microsoft Project (.mpp) σε ένα βιβλίο εργασίας Excel (.xlsx). Στο τέλος θα καταλάβετε πώς να **μετατρέψετε το αρχείο έργου σε Excel**, γιατί αυτή η μετατροπή είναι χρήσιμη, και πώς να ενσωματώσετε τη διαδικασία σε οποιαδήποτε εφαρμογή Java.

## Γρήγορες Απαντήσεις
- **Τι κάνει το API;** Διαβάζει αρχεία Project και τα αποθηκεύει απευθείας ως βιβλία εργασίας XLSX.  
- **Ποια μορφή παράγεται;** Ένα αρχείο Excel χρησιμοποιώντας την επιλογή `SaveFileFormat.Xlsx`.  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική έκδοση λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια είναι τα προαπαιτούμενα;** Εγκατεστημένο JDK και η βιβλιοθήκη Aspose.Tasks for Java προστιθέμενη στο έργο σας.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Συνήθως κάτω από 10 λεπτά για μια βασική εξαγωγή.

## Τι σημαίνει «πώς να εξάγετε MPP σε Excel»;
Η εξαγωγή MPP σε Excel σημαίνει ότι λαμβάνετε το χρονοδιάγραμμα, τους πόρους και τα δεδομένα εργασιών που αποθηκεύονται σε ένα αρχείο Microsoft Project και τα γράφετε σε ένα δομημένο φύλλο Excel. Αυτό καθιστά εύκολη τη διαμοίραση των δεδομένων του έργου με ενδιαφερόμενους που ενδέχεται να μην έχουν εγκατεστημένο το Project.

## Γιατί να μετατρέψετε το αρχείο MPP σε XLSX;
Η εξαγωγή MPP σε Excel σας επιτρέπει να μοιράζεστε πληροφορίες έργου σε μια καθολικά διαθέσιμη μορφή. **Άμεση απάντηση:** Η μετατροπή MPP σε XLSX δίνει σε κάθε επιχειρηματικό χρήστη τη δυνατότητα να ανοίξει, να επεξεργαστεί και να αναλύσει τα δεδομένα του έργου με τα ενσωματωμένα εργαλεία του Excel — πίνακες pivot, γραφήματα και τύπους — χωρίς να χρειάζεται εγκατεστημένο το Microsoft Project. Αυτό αυξάνει τη διαθεσιμότητα, επιταχύνει την αναφορά και επιτρέπει αυτοματοποιημένες διαδικασίες που καταναλώνουν απλά αρχεία Excel.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. **Java Development Kit (JDK)** – εγκατεστημένο και προστιθέμενο στο σύστημα PATH.  
2. **Aspose.Tasks for Java library** – κατεβάστε το από το [download link](https://releases.aspose.com/tasks/java/) και προσθέστε το JAR στο classpath του έργου σας.

## Εισαγωγή Πακέτων
`com.aspose.tasks` παρέχει το βασικό API για τη διαχείριση αρχείων Project, ενώ το `java.io` παρέχει βοηθητικά εργαλεία συστήματος αρχείων.  
Η κλάση `Project` είναι το κορυφαίο αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα μόνο αρχείο Microsoft Project στη μνήμη. Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project φορτωμένο στη μνήμη. Εισάγετε τους απαιτούμενους χώρους ονομάτων πριν αρχίσετε να εργάζεστε με το API.

```text
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
```

## Οδηγός Βήμα‑βήμα

### Πώς να εξάγω MPP σε Excel χρησιμοποιώντας το Aspose.Tasks;
Φορτώστε το αρχείο `.mpp` σας με `new Project("yourfile.mpp")` και καλέστε αμέσως `project.save("output.xlsx", SaveFileFormat.Xlsx)`. Αυτό το μοτίβο δύο γραμμών εκτελεί πλήρη μετατροπή, διατηρώντας τις εργασίες, τους πόρους και τα προσαρμοσμένα πεδία. Η λειτουργία εκτελείται σε λιγότερο από ένα δευτερόλεπτο για τυπικά έργα 100 εργασιών σε ένα τυπικό μηχάνημα ανάπτυξης.

#### Βήμα 1: Ορισμός Διαδρομής Καταλόγου Δεδομένων
Ορίστε το φάκελο όπου βρίσκεται το αρχείο `.mpp` σας. Αντικαταστήστε το σύμβολο κράτησης θέσης με την πραγματική σας διαδρομή. Η συμβολοσειρά `dataDir` λέει στο API πού να βρει το αρχείο προέλευσης και πού να γράψει το προκύπτον βιβλίο εργασίας Excel.

```text
```java
String dataDir = "Your Data Directory";
```
```

#### Βήμα 2: Φόρτωση Αρχείου Project
Δημιουργήστε ένα αντικείμενο `Project` φορτώνοντας το αρχείο `.mpp` που θέλετε να μετατρέψετε. Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη, επιτρέποντας περαιτέρω επεξεργασία ή άμεση εξαγωγή.

```text
```java
Project project = new Project(dataDir + "project5.mpp");
```
```

#### Βήμα 3: Αποθήκευση του Project ως XLSX
Τέλος, εξάγετε το φορτωμένο project σε ένα βιβλίο εργασίας Excel. Η απαρίθμηση `SaveFileFormat` καθορίζει τη μορφή του αρχείου εξόδου· `SaveFileFormat.Xlsx` λέει στο Aspose.Tasks να δημιουργήσει ένα σύγχρονο αρχείο `.xlsx`, ουσιαστικά **μετατρέποντας το αρχείο MPP σε XLSX**. Μπορείτε επίσης να καθορίσετε `SaveOptions` για να ρυθμίσετε λεπτομερώς το πλάτος των στηλών ή να συμπεριλάβετε μόνο επιλεγμένους πίνακες.

```text
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
```

## Συνηθισμένες Περιπτώσεις Χρήσης
- **Executive reporting:** Παρέχετε υψηλού επιπέδου στιγμιότυπα έργου σε Excel για τη ανώτερη διοίκηση.  
- **Data analysis:** Εισάγετε δεδομένα εργασιών και πόρων στο Power Query του Excel για πιο βαθιές αναλύσεις.  
- **Integration:** Μεταβιβάστε το εξαγόμενο αρχείο Excel σε downstream συστήματα που δέχονται μόνο εισόδους CSV/Excel.

## Πρόσθετες Συμβουλές & Καλές Πρακτικές
- **Performance tip:** Για έργα μεγαλύτερα από 500 εργασίες, ενεργοποιήστε `project.setReadWriteMode(ReadWriteMode.MemoryOptimized)` για μείωση της κατανάλωσης μνήμης. `ReadWriteMode.MemoryOptimized` ελαχιστοποιεί τη χρήση RAM κατά την επεξεργασία μεγάλων έργων.  
- **Formatting tip:** Χρησιμοποιήστε `project.save("output.xlsx", SaveFileFormat.Xlsx, new XlsxSaveOptions { ExportAllFields = true })` για να συμπεριλάβετε προσαρμοσμένα πεδία στην εξαγωγή. `XlsxSaveOptions` σας επιτρέπει να προσαρμόσετε την εξαγωγή Excel, όπως η εξαγωγή όλων των πεδίων.  
- **Error handling:** Τυλίξτε τις κλήσεις φόρτωσης και αποθήκευσης σε μπλοκ try‑catch για να εντοπίσετε `FileNotFoundException` ή `LicenseException` και να παρέχετε σαφή ανατροφοδότηση στον χρήστη.

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java για να χειριστώ τα δεδομένα του έργου προγραμματιστικά;**  
A: Ναι, το Aspose.Tasks for Java παρέχει εκτενείς APIs για ανάγνωση, εγγραφή και τροποποίηση αρχείων έργου, συμπεριλαμβανομένων των εργασιών, των πόρων, των ημερολογίων και των προσαρμοσμένων πεδίων.

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμαστική έκδοση για το Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks for Java από [here](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks for Java;**  
A: Η επίσημη τεκμηρίωση είναι διαθέσιμη [here](https://reference.aspose.com/tasks/java/).

**Q: Πώς μπορώ να λάβω υποστήριξη για προβλήματα ή ερωτήματα σχετικά με το Aspose.Tasks for Java;**  
A: Η υποστήριξη παρέχεται μέσω του φόρουμ Aspose.Tasks, προσβάσιμο [here](https://forum.aspose.com/c/tasks/15).

**Q: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Tasks for Java;**  
A: Ναι, μια προσωρινή άδεια μπορεί να αποκτηθεί από [here](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
Σε αυτόν τον οδηγό δείξαμε **πώς να εξάγετε MPP σε Excel** χρησιμοποιώντας το Aspose.Tasks for Java. Ακολουθώντας τα τρία απλά βήματα — ορισμός του καταλόγου δεδομένων, φόρτωση του αρχείου Project και αποθήκευση ως XLSX — μπορείτε εύκολα να **εξάγετε δεδομένα έργου σε Excel** και να ενδυναμώσετε την ομάδα σας με ευέλικτες, διαμοιράσιμες αναφορές. Η δυνατότητα της βιβλιοθήκης να **γράψει κώδικα Java για βιβλία εργασίας Excel** καθιστά την ενσωμάτωση αδιάλειπτη για οποιαδήποτε ροή εργασίας βασισμένη σε Java.

---

**Τελευταία Ενημέρωση:** 2026-05-31  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε αρχείο MPP – Δημιουργία & αποθήκευση κενής εργασίας σε μορφή MPP με Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Αποθήκευση Project ως Πρότυπο, CSV και Κείμενο με Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Ορισμός Ημερομηνίας Έναρξης Project στο MS Project χρησιμοποιώντας Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}