---
date: 2026-10-26
description: Πώς να διαβάσετε δεδομένα ορισμού ομάδας χρησιμοποιώντας το Aspose.Tasks
  για Java. Εξάγετε ομαδοποίηση εργασιών, κριτήρια και μορφοποίηση από αρχεία Microsoft
  Project για να αυτοματοποιήσετε την αναφορά και τη μεταφορά.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: Ανάγνωση δεδομένων ορισμού ομάδας στο Aspose.Tasks
og_description: Πώς να διαβάσετε δεδομένα ορισμού ομάδας χρησιμοποιώντας το Aspose.Tasks
  για Java. Εξάγετε ομαδοποίηση εργασιών, κριτήρια και μορφοποίηση από αρχεία Microsoft
  Project για να αυτοματοποιήσετε την αναφορά και τη μεταφορά.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: Πώς να διαβάσετε δεδομένα ορισμού ομάδας με το Aspose.Tasks για Java
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: Πώς να διαβάσετε δεδομένα ορισμού ομάδας με το Aspose.Tasks για Java
url: /el/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε δεδομένα ορισμού ομάδας στο Aspose.Tasks για Java

## Εισαγωγή
Aspose.Tasks for Java σάς επιτρέπει να έχετε προγραμματιστική πρόσβαση, τροποποίηση και ανάλυση αρχείων Microsoft Project. Σε αυτό το tutorial θα μάθετε **πώς να διαβάζετε δεδομένα ορισμού ομάδας** από ένα αρχείο `.mpp`, να εξάγετε το όνομα, τα κριτήρια και το οπτικό στυλ κάθε ομάδας, και στη συνέχεια να χρησιμοποιήσετε αυτές τις πληροφορίες για τη δημιουργία προσαρμοσμένων αναφορών ή τη μεταφορά ρυθμίσεων σε άλλα έργα. Η κατανόηση αυτής της δυνατότητας σας επιτρέπει να αυτοματοποιήσετε την αναφορά, να επικυρώσετε τις δομές έργου και να βελτιώσετε τις ροές εργασίας που βασίζονται σε δεδομένα.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “read group definition”;** Σημαίνει την εξαγωγή των κανόνων ομαδοποίησης (όνομα, κριτήρια, χρώματα, γραμματοσειρές) που χρησιμοποιεί το Microsoft Project για την οργάνωση των εργασιών.  
- **Ποια βιβλιοθήκη χρειάζομαι;** Aspose.Tasks for Java.  
- **Χρειάζεται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια IDE υποστηρίζονται;** Οποιοδήποτε Java IDE όπως IntelliJ IDEA ή Eclipse.  
- **Πόσο κώδικα απαιτείται;** Λιγότερο από 30 γραμμές Java κώδικα για τη φόρτωση ενός έργου και την εμφάνιση των λεπτομερειών ομάδας.

## Πώς να διαβάσετε δεδομένα ορισμού ομάδας
Φορτώστε το έργο, απαριθμήστε τις ομάδες του και εξετάστε τα κριτήρια κάθε ομάδας. Η άμεση απάντηση είναι: **Δημιουργήστε ένα αντικείμενο `Project`, καλέστε `project.getTaskGroups()` και επαναλάβετε τη συλλογή για να διαβάσετε ονόματα, κριτήρια, γραμματοσειρές και χρώματα.** Τα παρακάτω τμήματα χωρίζουν τη διαδικασία σε σαφή βήματα, το καθένα συνοδευόμενο από έναν σύντομο κώδικα placeholder που αντικαθιστάτε με το πραγματικό απόσπασμα από την τεκμηρίωση του Aspose.Tasks.

## Τι είναι το read group definition;
Το read group definition αναφέρεται στην εξαγωγή των κανόνων ομαδοποίησης (όνομα, κριτήρια, μορφοποίηση) που εφαρμόζει το Microsoft Project για την ταξινόμηση των εργασιών. Αυτοί οι κανόνες καθορίζουν πώς η εφαρμογή ομαδοποιεί εργασίες κατά κατάσταση, προτεραιότητα ή προσαρμοσμένα πεδία, και περιλαμβάνουν οπτικά χαρακτηριστικά όπως το στυλ γραμματοσειράς και το χρώμα κελιού.

## Γιατί να διαβάζετε δεδομένα ορισμού ομάδας;
Η ανάγνωση των δεδομένων ορισμού ομάδας σας επιτρέπει να **αυτοματοποιήσετε τη δημιουργία αναφορών**, **να μεταφέρετε τη λογική ομαδοποίησης** σε άλλα έργα, και **να επικυρώσετε ότι οι απαιτούμενες ομάδες υπάρχουν** πριν από μαζικές ενημερώσεις. Το Aspose.Tasks for Java μπορεί να επεξεργαστεί έργα με **πάνω από 10.000 εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, επιτρέποντας υψηλής απόδοσης παρτίδες λειτουργίες. Επιπλέον, μπορείτε να εξάγετε χρώματα γραμματοσειράς, μοτίβα και κατευθύνσεις ταξινόμησης για να αναδημιουργήσετε την ακριβή οπτική διάταξη σε προσαρμοσμένα dashboards.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK) 8+** – οποιαδήποτε πρόσφατη έκδοση λειτουργεί.  
2. **Aspose.Tasks for Java** – κατεβάστε το πιο πρόσφατο JAR από τη [σελίδα λήψης Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Ένα Java IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή προτιμάτε.  

> **Συμβουλή:** Χρησιμοποιήστε Maven ή Gradle για τη διαχείριση της εξάρτησης Aspose.Tasks· αυτό αποφεύγει την χειροκίνητη διαχείριση JAR.

## Εισαγωγή πακέτων
`Project` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο Microsoft Project στο Aspose.Tasks for Java.  

```java
import com.aspose.tasks.*;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: ρυθμίστε τον φάκελο δεδομένων σας
Ορίστε το φάκελο που περιέχει το αρχείο `.mpp` που θέλετε να εξετάσετε. Η χρήση του `java.nio.file.Paths` εγγυάται ανεξαρτησία πλατφόρμας στη διαχείριση διαδρομών.

```java
String dataDir = "Your Data Directory";
```

### Βήμα 2: φορτώστε το αρχείο έργου
Δημιουργήστε ένα αντικείμενο `Project` δείχνοντας στο αρχείο `.mpp`. Ο κατασκευαστής διαβάζει την κεφαλίδα του αρχείου και δημιουργεί ένα μοντέλο στη μνήμη.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Βήμα 3: ανακτήστε τον αριθμό ομάδων εργασιών
Εκτυπώστε το συνολικό αριθμό ομάδων εργασιών που ορίζονται στο έργο. Αυτός ο γρήγορος έλεγχος επιβεβαιώνει ότι το αρχείο περιέχει πραγματικά πληροφορίες ομαδοποίησης.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Βήμα 4: ανακτήστε πληροφορίες συγκεκριμένης ομάδας εργασιών
Πάρτε μια συγκεκριμένη ομάδα (δείκτη 1 σε αυτό το παράδειγμα) και εμφανίστε το όνομά της και τον αριθμό κριτηρίων που περιέχει. Κάθε ομάδα μπορεί να έχει πολλαπλά κριτήρια που ορίζουν πώς ομαδοποιούνται οι εργασίες.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Βήμα 5: ανακτήστε πληροφορίες κριτηρίου ομάδας
Κάθε ομάδα μπορεί να έχει ένα ή περισσότερα κριτήρια. Το παρακάτω απόσπασμα εξάγει λεπτομέρειες όπως το πεδίο ομαδοποίησης, τη λειτουργία ομαδοποίησης, το χρώμα κελιού και το μοτίβο.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Βήμα 6: ελέγξτε την γονική ομάδα
Μερικές φορές ένα κριτήριο ανήκει σε γονική ομάδα. Αυτός ο έλεγχος επιβεβαιώνει τη σχέση και αποτρέπει σφάλματα null‑pointer κατά την πλοήγηση στην ιεραρχία.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Βήμα 7: ανακτήστε πληροφορίες γραμματοσειράς κριτηρίου
Τα κριτήρια ομάδας μπορούν να έχουν προσαρμοσμένο στυλ γραμματοσειράς. Ο παρακάτω κώδικας εκτυπώνει την οικογένεια γραμματοσειράς, το μέγεθος, το στυλ και την κατεύθυνση ταξινόμησης, επιτρέποντάς σας να αναδημιουργήσετε την ακριβή εμφάνιση στη δική σας διεπαφή.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Συνηθισμένα προβλήματα και λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| **`NullPointerException` στο `criterion.getParentGroup()`** | Το κριτήριο μπορεί να μην έχει γονική ομάδα. | Προσθέστε έλεγχο null πριν προσπελάσετε το γονικό. |
| **Αρχείο δεν βρέθηκε** | Η διαδρομή `dataDir` είναι λανθασμένη ή το όνομα αρχείου είναι γραμμένο λανθασμένα. | Χρησιμοποιήστε `Paths.get(dataDir, "project.mpp").toAbsolutePath()` και βεβαιωθείτε ότι το αρχείο υπάρχει. |
| **Δεν έχει οριστεί άδεια** | Το Aspose λειτουργεί σε λειτουργία αξιολόγησης και μπορεί να περικόψει την έξοδο. | Καταχωρίστε την άδειά σας με `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` πριν φορτώσετε το έργο. |

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java για τροποποίηση αρχείων έργου;**  
Α: Ναι, η βιβλιοθήκη παρέχει πλήρη δυνατότητα ανάγνωσης/εγγραφής για μορφές Microsoft Project, επιτρέποντάς σας να προσθέτετε εργασίες, να αλλάζετε πόρους και να ενημερώνετε ορισμούς ομάδων προγραμματιστικά.

**Ε: Είναι το Aspose.Tasks for Java συμβατό με όλες τις εκδόσεις αρχείων Microsoft Project;**  
Α: Υποστηρίζει MPP, XML, CSV και άλλες κοινές μορφές Project από το Project 2000 έως την πιο πρόσφατη έκδοση 2024.

**Ε: Πώς πρέπει να διαχειρίζομαι σφάλματα κατά τη χρήση του Aspose.Tasks for Java;**  
Α: Τυλίξτε τις λειτουργίες αρχείου σε μπλοκ `try‑catch` και πιάστε `TasksException` για λεπτομερείς πληροφορίες σφάλματος· εξετάστε το `getMessage()` της εξαίρεσης για ενδείξεις.

**Ε: Προσφέρει το Aspose.Tasks for Java εξαγωγή σε άλλες μορφές;**  
Α: Απόλυτα – μπορείτε να εξάγετε σε PDF, XLSX, HTML και άλλα χρησιμοποιώντας τις ειδικές API εξαγωγής της βιβλιοθήκης.

**Ε: Πού μπορώ να βρω πρόσθετους πόρους και υποστήριξη;**  
Α: Επισκεφθείτε την [τεκμηρίωση Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/) για αναφορές API και το [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για βοήθεια από την κοινότητα.

## Συμπέρασμα
Σε αυτό το tutorial περάσαμε από **το πώς να διαβάζετε δεδομένα ορισμού ομάδας** από ένα αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks for Java. Φορτώνοντας ένα `Project`, απαριθμώντας το `TaskGroupCollection` του και εξετάζοντας τα κριτήρια, τις γραμματοσειρές και τα χρώματα κάθε ομάδας, μπορείτε να δημιουργήσετε αυτοματοποιημένες pipelines αναφοράς, να μεταφέρετε κανόνες ομαδοποίησης ή να επικυρώσετε δομές έργου με σιγουριά. Η ίδια προσέγγιση κλιμακώνεται σε μεγάλα έργα με χιλιάδες εργασίες, διατηρώντας χαμηλή χρήση μνήμης.

---

**Τελευταία ενημέρωση:** 2026-10-26  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά tutorials

- [How to Read Project Information from Microsoft Project with Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [How to get table fields and read table data in Aspose.Tasks](/tasks/java/project-data-reading/read-table-data/)
- [read gantt chart java – Extract Specific Gantt Data](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}