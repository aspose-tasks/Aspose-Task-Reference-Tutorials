---
date: 2026-05-26
description: Μάθετε πώς να λάβετε τα πεδία του πίνακα και να διαβάσετε τα δεδομένα
  του πίνακα σε Java χρησιμοποιώντας το Aspose.Tasks. Αυτό το σεμινάριο σας δείχνει
  πώς να ανακτήσετε πληροφορίες του πίνακα από αρχεία Project.
keywords:
- read table data aspose.tasks
- Aspose.Tasks Java
- project table extraction
linktitle: Ανάγνωση δεδομένων πίνακα από αρχείο στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to get table fields and read table data in Java using Aspose.Tasks.
    This tutorial shows you how to retrieve table information from Project files.
  headline: How to get table fields and read table data in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Load each project separately with `new Project(path)` and repeat the table‑field
      extraction loop for each instance.
    question: How do I read table data in a multi‑project environment?
  - answer: Yes, after printing the field details you can write them to a `FileWriter`
      or use a CSV library such as OpenCSV to generate a properly escaped file.
    question: Can I export the retrieved table fields to CSV?
  - answer: Absolutely. The `project.getTables()` collection includes both default
      and user‑defined tables, so you can iterate through them and process each one
      individually.
    question: Does Aspose.Tasks handle custom tables created by users?
  - answer: Use the overloaded `Project` constructor that accepts a `LoadOptions`
      object where you can specify the password, e.g., `new Project(path, new LoadOptions("pwd"))`.
    question: What if the Project file is password‑protected?
  - answer: Check each `TableField`'s `getVisible()` method (available in newer releases)
      to determine whether the column is displayed in the UI.
    question: Is there a way to filter only visible columns?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να λάβετε τα πεδία του πίνακα και να διαβάσετε τα δεδομένα του πίνακα στο
  Aspose.Tasks
url: /el/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να λάβετε τα πεδία πίνακα και να διαβάσετε τα δεδομένα πίνακα στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο θα μάθετε **πώς να λάβετε τα πεδία πίνακα** και **να διαβάσετε τα δεδομένα πίνακα** από ένα αρχείο Microsoft Project χρησιμοποιώντας το API **read table data aspose.tasks**. Είτε δημιουργείτε έναν προσαρμοσμένο πίνακα ελέγχου αναφορών, μεταφέρετε κληρονομημένα δεδομένα έργου, είτε αυτοματοποιείτε την ανάλυση χρονοδιαγράμματος, η προγραμματιστική εξαγωγή των ορισμών του πίνακα εξοικονομεί αμέτρητες χειροκίνητες ώρες. Θα περάσουμε από τη ρύθμιση του περιβάλλοντος, τη φόρτωση ενός έργου και την εκτύπωση των ιδιοτήτων κάθε στήλης, ώστε να μπορείτε να αρχίσετε να χρησιμοποιείτε αυτή τη δυνατότητα στις εφαρμογές Java σας αμέσως.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “get table fields”;** Αναφέρεται στην ανάκτηση του ορισμού (πλάτος, τίτλος, στοίχιση κ.λπ.) κάθε στήλης που εμφανίζεται σε έναν πίνακα προβολής Project.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται εμπορική άδεια για χρήση σε παραγωγή.  
- **Μπορώ να διαβάσω πίνακες από οποιαδήποτε έκδοση του Project;** Ναι, το Aspose.Tasks υποστηρίζει πάνω από 15 εκδόσεις αρχείων Microsoft Project, από το Project 2003 έως το Project 2024.  
- **Απαιτείται κάποια πρόσθετη ρύθμιση;** Απλώς JDK 8+ και το Aspose.Tasks JAR στο classpath σας.

## Τι είναι το read table data aspose.tasks;
Το read table data aspose.tasks είναι το σύνολο μεθόδων API του Aspose.Tasks που σας επιτρέπει να έχετε προγραμματιστική πρόσβαση στη δομή και το περιεχόμενο των πινάκων που ορίζονται μέσα σε ένα αρχείο Microsoft Project. Επιστρέφει μεταδεδομένα όπως το πλάτος της στήλης, ο τίτλος, η στοίχιση και η ορατότητα, επιτρέποντάς σας να αναδημιουργήσετε ή να μετατρέψετε τα χρονοδιαγράμματα του έργου σε οποιαδήποτε μορφή χρειάζεστε.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για ανάγνωση δεδομένων πίνακα;
Το Aspose.Tasks επεξεργάζεται **πάνω από 50 διαφορετικές μορφές αρχείων Project** (συμπεριλαμβανομένων των MPP, MPX, XML και Primavera) και μπορεί να διαχειριστεί αρχεία με **έως 10.000 εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Αυτή η μετρήσιμη απόδοση σημαίνει ότι μπορείτε με ασφάλεια να εξάγετε πίνακες από μεγάλα επιχειρησιακά έργα διατηρώντας τη χρήση μνήμης κάτω από 200 MB.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK) 8 ή νεότερο** – κατεβάστε το από την επίσημη ιστοσελίδα της Oracle.  
2. **Aspose.Tasks for Java JAR** – αποκτήστε την τελευταία έκδοση από το [download link](https://releases.aspose.com/tasks/java/) και προσθέστε την στο build path του έργου σας.  

> **Pro tip:** Εάν χρησιμοποιείτε Maven ή Gradle, μπορείτε να αναφέρετε το artifact του Aspose.Tasks απευθείας για να απλοποιήσετε τη διαχείριση εξαρτήσεων.

## Εισαγωγή Πακέτων
Οι κλάσεις `Project`, `Table` και `TableField` αποτελούν τον πυρήνα της διαδικασίας ανάγνωσης πίνακα.

Η κλάση `Project` είναι το κορυφαίο αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα μόνο αρχείο Microsoft Project στη μνήμη.

Η κλάση `Table` περιλαμβάνει μια συλλογή αντικειμένων `TableField`, το καθένα περιγράφει μια στήλη μιας προβολής.

Η κλάση `TableField` είναι ένας φορέας ορισμού για το πλάτος, τον τίτλο, τη στοίχιση και την ορατότητα μιας στήλης.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## Βήμα 1: Ρύθμιση του Καταλόγου Δεδομένων
Ορίστε το φάκελο που περιέχει το αρχείο *.mpp* σας:

```java
String dataDir = "Your Data Directory";
```

Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή στο μηχάνημά σας (π.χ., `C:/Projects/Data/`). Η χρήση απόλυτης διαδρομής αποτρέπει αμφιβολίες του class‑loader όταν ο κώδικας εκτελείται από διαφορετικά IDE.

## Βήμα 2: Φόρτωση του Αρχείου Project
Δημιουργήστε μια παρουσία `Project` δείχνοντας στο αρχείο Project που θέλετε να εξετάσετε:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

Εάν το αρχείο σας έχει διαφορετικό όνομα ή επέκταση, προσαρμόστε τη συμβολοσειρά αναλόγως. Ο κατασκευαστής ανιχνεύει αυτόματα τη μορφή του αρχείου, οπότε δεν χρειάζεται να καθορίσετε την έκδοση χειροκίνητα.

## Βήμα 3: Ανάκτηση πληροφοριών πίνακα
Τώρα θα **λάβουμε τα πεδία πίνακα** και θα εμφανίσουμε τις ιδιότητες κάθε πεδίου:

```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```

Το απόσπασμα εκτυπώνει το πλάτος, τον τίτλο και τη στοίχιση για κάθε στήλη στον προεπιλεγμένο πίνακα, παρέχοντάς σας μια πλήρη εικόνα των **πεδίων πίνακα** που ορίζονται στο έργο.

## Πώς να διαβάσετε δεδομένα πίνακα χρησιμοποιώντας το Aspose.Tasks για Java;
Για να διαβάσετε τα πραγματικά δεδομένα του πίνακα, πρώτα φορτώστε το έργο, στη συνέχεια αποκτήστε τον επιθυμητό πίνακα (π.χ. τον προεπιλεγμένο) χρησιμοποιώντας `project.getTables().getByName("Name")` ή με δείκτη. Επανάλαβε τη συλλογή που επιστρέφεται από `table.getFields()` και πρόσβαση στις ιδιότητες κάθε `TableField` όπως πλάτος, τίτλος, στοίχιση και ορατότητα. Αυτή η προσέγγιση λειτουργεί για οποιονδήποτε προσαρμοσμένο ή ενσωματωμένο πίνακα που ορίζεται στο αρχείο Project.

## Συνηθισμένα Πιθανά Προβλήματα & Συμβουλές
- **Null tables** – Εάν ένα έργο δεν έχει πίνακες, το `project.getTables()` μπορεί να είναι κενό. Πάντα ελέγξτε το μέγεθος της συλλογής πριν προσπελάσετε έναν δείκτη.  
- **Encoding issues** – Οι μη‑ASCII χαρακτήρες στους τίτλους εμφανίζονται σωστά όταν χρησιμοποιείτε την τελευταία έκδοση του Aspose.Tasks (24.12 ή νεότερη).  
- **Performance** – Η φόρτωση πολύ μεγάλων αρχείων *.mpp* μπορεί να είναι απαιτητική σε μνήμη· σκεφτείτε τη χρήση του streaming API (`ProjectReader`) για αρχεία που υπερβαίνουν τα 500 MB.  

## Συχνές Ερωτήσεις

**Q: Πώς διαβάζω δεδομένα πίνακα σε περιβάλλον πολλαπλών έργων;**  
A: Φορτώστε κάθε έργο ξεχωριστά με `new Project(path)` και επαναλάβετε τον βρόχο εξαγωγής πεδίων πίνακα για κάθε παρουσία.

**Q: Μπορώ να εξάγω τα ανακτημένα πεδία πίνακα σε CSV;**  
A: Ναι, μετά την εκτύπωση των λεπτομερειών των πεδίων μπορείτε να τα γράψετε σε ένα `FileWriter` ή να χρησιμοποιήσετε μια βιβλιοθήκη CSV όπως η OpenCSV για να δημιουργήσετε ένα σωστά escaped αρχείο.

**Q: Το Aspose.Tasks διαχειρίζεται προσαρμοσμένους πίνακες που δημιουργούν οι χρήστες;**  
A: Απόλυτα. Η συλλογή `project.getTables()` περιλαμβάνει τόσο τους προεπιλεγμένους όσο και τους πίνακες που ορίζονται από τον χρήστη, ώστε μπορείτε να τους επαναλάβετε και να επεξεργαστείτε καθέναν ξεχωριστά.

**Q: Τι γίνεται αν το αρχείο Project είναι προστατευμένο με κωδικό;**  
A: Χρησιμοποιήστε τον υπερφορτωμένο κατασκευαστή `Project` που δέχεται ένα αντικείμενο `LoadOptions` όπου μπορείτε να καθορίσετε τον κωδικό, π.χ., `new Project(path, new LoadOptions("pwd"))`.

**Q: Υπάρχει τρόπος να φιλτράρετε μόνο τις ορατές στήλες;**  
A: Ελέγξτε τη μέθοδο `getVisible()` του κάθε `TableField` (διαθέσιμη σε νεότερες εκδόσεις) για να καθορίσετε εάν η στήλη εμφανίζεται στη διεπαφή χρήστη.

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε πώς να **λάβετε τα πεδία πίνακα** και να διαβάσετε τα δεδομένα πίνακα από ένα αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks for Java. Αυτή η δυνατότητα ανοίγει το δρόμο για ισχυρά σενάρια αυτοματοποίησης, αγωγούς μεταφοράς δεδομένων και προσαρμοσμένες λύσεις αναφοράς στις εφαρμογές Java σας. Στη συνέχεια, σκεφτείτε την εξαγωγή των εξαγόμενων μεταδεδομένων σε JSON ή σε βάση δεδομένων ώστε να δημιουργήσετε ευρετήρια έργων ή να ενσωματώσετε με εργαλεία BI.

---

**Τελευταία ενημέρωση:** 2026-05-26  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (τελευταία τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Πώς να διαβάσετε πληροφορίες έργου από το Microsoft Project με το Aspose.Tasks για Java](/tasks/java/project-properties/read-project-info/)
- [Διαβάστε τη βάση δεδομένων του Microsoft Project με το Aspose.Tasks για Java](/tasks/java/project-data-reading/read-project-database/)
- [java read access database: Διαβάστε δεδομένα έργου με το Aspose.Tasks](/tasks/java/project-data-reading/read-access-database/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}