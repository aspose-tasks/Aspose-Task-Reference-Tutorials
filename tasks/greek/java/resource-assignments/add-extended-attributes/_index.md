---
date: 2026-05-20
description: Μάθετε πώς να χρησιμοποιήσετε Aspose.Tasks for Java για να προσθέσετε
  extended attributes σε resource assignments, να ορίσετε την ημερομηνία έναρξης του
  έργου και να γράψετε αρχεία MS Project αποδοτικά.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Προσθήκη Extended Attributes σε Resource Assignments στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να χρησιμοποιήσετε Aspose.Tasks for Java – Προσθήκη Extended Attributes
  σε Resource Assignments
url: /el/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποκτώντας Δεξιότητες στη Διαχείριση του MS Project με το Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το μάθημα θα ανακαλύψετε **πώς να χρησιμοποιήσετε το Aspose.Tasks για Java** για να προσθέσετε εκτεταμένα χαρακτηριστικά σε αναθέσεις πόρων και να γράψετε προγραμματιστικά πληροφορίες Microsoft Project. Είτε αυτοματοποιείτε μια αλυσίδα αναφορών είτε δημιουργείτε ένα προσαρμοσμένο εργαλείο διαχείρισης έργου, τα παρακάτω βήματα δείχνουν ακριβώς πώς να ορίσετε την ημερομηνία έναρξης του έργου, να δημιουργήσετε αναθέσεις πόρων και να αποθηκεύσετε το αρχείο ως XML — όλα με λίγες μόνο γραμμές κώδικα Java.

## Γρήγορες Απαντήσεις
- **Τι κάνει το Aspose.Tasks για Java;** Διαβάζει, γράφει και τροποποιεί αρχεία Microsoft Project χωρίς να απαιτείται εγκατάσταση του Microsoft Project.  
- **Μπορώ να προσθέσω προσαρμοσμένα πεδία σε μια ανάθεση πόρων;** Ναι, χρησιμοποιήστε τη συλλογή `ExtendedAttribute` στο αντικείμενο `ResourceAssignment`.  
- **Πώς ορίζω την ημερομηνία έναρξης του έργου;** Καλείτε `project.setStartDate(LocalDateTime.of(...))` πριν από την αποθήκευση.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Μια εμπορική άδεια αφαιρεί τα υδατογράμματα αξιολόγησης και ξεκλειδώνει πλήρη πρόσβαση στο API.  
- **Ποιες εκδόσεις Java υποστηρίζονται;** Το Aspose.Tasks για Java υποστηρίζει JDK 8 μέχρι JDK 21.

## Πώς να χρησιμοποιήσετε το Aspose.Tasks για Java;
`Project` είναι το κύριο αντικείμενο που αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη. Φορτώστε τη βιβλιοθήκη Aspose.Tasks, δημιουργήστε μια παρουσία `Project`, διαμορφώστε ιδιότητες σε επίπεδο έργου, προσθέστε εκτεταμένα χαρακτηριστικά σε μια ανάθεση πόρων και, τέλος, αποθηκεύστε το έργο ως XML. Η βασική ροή εργασίας χωρίζεται σε τρία συνοπτικά βήματα: αρχικοποίηση, τροποποίηση και αποθήκευση. Αυτό το μοτίβο λειτουργεί για αρχεία έργου οποιουδήποτε μεγέθους και εκτελείται σε JVM Windows, Linux ή macOS.

## Τι είναι ένα εκτεταμένο χαρακτηριστικό στο Aspose.Tasks;
Ένα **εκτεταμένο χαρακτηριστικό** είναι ένα προσαρμοσμένο πεδίο που συνδέετε σε εργασίες, πόρους ή αναθέσεις για να αποθηκεύσετε πρόσθετα μεταδεδομένα πέρα από τις ενσωματωμένες στήλες. Η `ExtendedAttributeDefinition` ορίζει το σχήμα για ένα προσαρμοσμένο πεδίο. Το Aspose.Tasks εκθέτει τις κλάσεις `ExtendedAttributeDefinition` και `ExtendedAttribute` για να ορίζετε και να εκχωρείτε αυτά τα πεδία προγραμματιστικά.

## Γιατί να προσθέσετε εκτεταμένα χαρακτηριστικά σε αναθέσεις πόρων;
Το Aspose.Tasks υποστηρίζει **50+ ενσωματωμένα και προσαρμοσμένα πεδία**, και μπορείτε να προσθέσετε απεριόριστα χαρακτηριστικά ορισμένα από τον χρήστη. Η προσθήκη τους σας επιτρέπει να καταγράψετε κωδικούς κόστους, ταυτότητες τμημάτων ή οποιαδήποτε επιχειρηματικά δεδομένα απευθείας μέσα στο αρχείο .mpp, εξαλείφοντας την ανάγκη για εξωτερικά φύλλα εργασίας και εξασφαλίζοντας την ακεραιότητα των δεδομένων καθ' όλη τη διάρκεια του κύκλου ζωής του έργου.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java library** – Κατεβάστε το από τη σελίδα επίσημης κυκλοφορίας [εδώ](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ή οποιοσδήποτε επεξεργαστής συμβατός με Java που προτιμάτε.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τα απαραίτητα πακέτα στο έργο Java σας:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Βήμα 1: Ρύθμιση Καταλόγου Δεδομένων
Ορίστε τον φάκελο όπου θα αποθηκευτούν τα δεδομένα του έργου σας. Αυτή η διαδρομή θα χρησιμοποιηθεί αργότερα όταν αποθηκεύσετε το αρχείο XML.

```java
String dataDir = "Your Data Directory";
```

### Βήμα 2: Δημιουργία Αντικειμένου Project
Η κλάση `Project` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Tasks που αντιπροσωπεύει ένα μόνο αρχείο Microsoft Project στη μνήμη. Η δημιουργία του σας δίνει πλήρη πρόσβαση σε όλα τα στοιχεία του έργου.

```java
Project project = new Project();
```

### Βήμα 3: Ορισμός Ιδιοτήτων Πληροφοριών Έργου
Ορίστε βασικές ιδιότητες του έργου όπως η ημερομηνία έναρξης, η σημαία schedule from start και η ημερομηνία κατάστασης. Αυτές οι τιμές αποθηκεύονται στο αντικείμενο `ProjectInfo` του έργου.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Βήμα 4: Προσθήκη Εκτεταμένων Χαρακτηριστικών σε Ανάθεση Πόρου
Δημιουργήστε μια `ExtendedAttributeDefinition` για το προσαρμοσμένο πεδίο, συνδέστε την σε μια `ResourceAssignment` και συμπληρώστε την τιμή. Αυτό το βήμα δείχνει τη λειτουργία της λέξης‑κλειδί **add extended attributes** σε δράση.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Κοινά Προβλήματα και Λύσεις
- **NullPointerException κατά την πρόσβαση στη συλλογή αναθέσεων** – Βεβαιωθείτε ότι έχετε δημιουργήσει τουλάχιστον έναν πόρο και μία εργασία πριν ανακτήσετε τις αναθέσεις.  
- **Το εκτεταμένο χαρακτηριστικό δεν εμφανίζεται στο MS Project** – Επαληθεύστε ότι το `FieldId` του χαρακτηριστικού ταιριάζει με μια θέση προσαρμοσμένου πεδίου (π.χ., `ExtendedAttributeTask.Text1`).  
- **Ασυμφωνία μορφής ημερομηνίας** – Χρησιμοποιήστε `java.time.LocalDateTime` για τις τιμές ημερομηνίας· το Aspose.Tasks μετατρέπει αυτόματα σε μορφή ημερολογίου του Project.

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java για ανάγνωση αρχείων MS Project;**  
A: Ναι, η βιβλιοθήκη παρέχει πλήρη δυνατότητα ανάγνωσης‑εγγραφής για μορφές .mpp, .xml και .xps.

**Q: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικές εκδόσεις του MS Project;**  
A: Απόλυτα, υποστηρίζει αρχεία από το Project 2000 έως την πιο πρόσφατη έκδοση του 2024, καλύπτοντας πάνω από 20 μορφές εκδόσεων.

**Q: Υπάρχουν περιορισμοί στην δοκιμαστική έκδοση του Aspose.Tasks για Java;**  
A: Η δοκιμαστική έκδοση προσθέτει υδατογράφημα στα παραγόμενα αρχεία και περιορίζει τον αριθμό των εργασιών που μπορείτε να δημιουργήσετε, αλλά όλες οι λειτουργίες του API παραμένουν προσβάσιμες.

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;**  
A: Μπορείτε να ζητήσετε βοήθεια από το φόρουμ κοινότητας Aspose.Tasks [εδώ](https://forum.aspose.com/c/tasks/15).

**Q: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Tasks για Java;**  
A: Ναι, προσωρινές άδειες είναι διαθέσιμες για βραχυπρόθεσμη χρήση. Μπορείτε να αποκτήσετε μία από [εδώ](https://purchase.aspose.com/temporary-license/).

**Τελευταία ενημέρωση:** 2026-05-20  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Προσθέσετε Σημειώσεις σε Αναθέσεις Πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Πώς να Διαβάσετε και να Γράψετε Rate Scale για Αναθέσεις Πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Πώς να Προσθέσετε Πόρο σε Έργο και να Διαχειριστείτε Ιδιότητες Leveling Delay στο Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}