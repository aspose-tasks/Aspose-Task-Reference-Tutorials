---
date: 2026-01-05
description: Μάθετε πώς να ορίζετε την ημερομηνία έναρξης του έργου και να αποθηκεύετε
  το XML του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Οδηγός βήμα‑προς‑βήμα
  για προγραμματιστές Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ορισμός ημερομηνίας έναρξης του έργου με το Aspose.Tasks για Java
url: /el/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Ημερομηνίας Έναρξης Έργου με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε **πώς να ορίσετε την ημερομηνία έναρξης του έργου** σε ένα αρχείο Microsoft Project και στη συνέχεια **να αποθηκεύσετε το MS Project XML** χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε αυτοματοποιείτε μια αλυσίδα αναφορών είτε δημιουργείτε ένα προσαρμοσμένο εργαλείο διαχείρισης έργων, η κατανόηση αυτού του θέματος θα σας εξοικονομήσει χρόνο και θα αφαιρέσει τα χειροκίνητα σφάλματα.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια μέθοδος για ορισμό ημερομηνίας έναρξης;** Χρησιμοποιήστε `project.set(Prj.START_DATE, …)`.
- **Ποια μορφή πρέπει να χρησιμοποιήσω για εξαγωγή του αρχείου;** Αποθηκεύστε το ως XML με `SaveFileFormat.Xml`.
- **Χρειάζομαι άδεια για αυτή τη λειτουργία;** Μια δοκιμαστική έκδοση λειτουργεί, αλλά μια πλήρης άδεια αφαιρεί τα υδατογραφήματα.
- **Μπορώ να αλλάξω την ημερομηνία έναρξης μετά τη δημιουργία των εργασιών;** Ναι, ενημερώστε την ιδιότητα του έργου πριν προσθέσετε εργασίες.
- **Είναι συμβατό με όλες τις εκδόσεις του MS Project;** Το Aspose.Tasks υποστηρίζει XML, MPP και άλλα.

## Τι είναι το “Set Project Start Date”;
Ο ορισμός της ημερομηνίας έναρξης του έργου καθορίζει το βασικό ημερολόγιο από το οποίο ξεκινούν όλοι οι υπολογισμοί προγραμματισμού εργασιών. Είναι το πρώτο βήμα για την προγραμματιστική δημιουργία ενός αξιόπιστου χρονοδιαγράμματος έργου.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για Java;
Το Aspose.Tasks παρέχει ένα καθαρό API Java που λειτουργεί σε οποιαδήποτε πλατφόρμα χωρίς να απαιτείται εγκατάσταση του Microsoft Project. Σας επιτρέπει να δημιουργείτε, να τροποποιείτε και να εξάγετε δεδομένα έργου γρήγορα, καθιστώντας το ιδανικό για αυτοματοποίηση στο διακομιστή.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – οποιαδήποτε πρόσφατη έκδοση JDK.
2. **Aspose.Tasks for Java** – κατεβάστε το από [εδώ](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse ή το προτιμώμενο Java IDE σας.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαραίτητες κλάσεις:

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
Ορίστε πού θα αποθηκευτούν τα παραγόμενα αρχεία.

```java
String dataDir = "Your Data Directory";
```

### Βήμα 2: Δημιουργία Αντικειμένου Project
Δημιουργήστε ένα νέο, κενό έργο.

```java
Project project = new Project();
```

### Βήμα 3: Ορισμός Ιδιοτήτων Πληροφοριών Έργου
Εδώ **ορίζουμε την ημερομηνία έναρξης του έργου** και τις σχετικές ιδιότητες χρονοπρογραμματισμού.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Βήμα 4: Αποθήκευση MS Project XML
Εξάγετε το ρυθμισμένο έργο σε αρχείο XML.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Συχνά Προβλήματα και Λύσεις
- **Λανθασμένη μορφή ημερομηνίας:** Βεβαιωθείτε ότι χρησιμοποιείτε `java.util.Calendar` και καλείτε `getTime()` πριν την ανάθεση.
- **Το αρχείο δεν αποθηκεύεται:** Ελέγξτε ότι το `dataDir` δείχνει σε έναν υπάρχοντα, εγγράψιμο φάκελο.
- **Προειδοποιήσεις άδειας:** Η δοκιμαστική έκδοση προσθέτει υδατογραφήματα· εφαρμόστε μια έγκυρη άδεια για να τα αφαιρέσετε.

## Συχνές Ερωτήσεις

### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java για ανάγνωση αρχείων MS Project;  
**Α:** Ναι, το Aspose.Tasks για Java παρέχει ισχυρές λειτουργίες τόσο για ανάγνωση όσο και για εγγραφή αρχείων MS Project.

### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικές εκδόσεις του MS Project;  
**Α:** Απόλυτα, το Aspose.Tasks για Java υποστηρίζει διάφορες μορφές MS Project, εξασφαλίζοντας ευρεία συμβατότητα.

### Ε: Υπάρχουν περιορισμοί στη δοκιμαστική έκδοση του Aspose.Tasks για Java;  
**Α:** Η δοκιμαστική έκδοση σας επιτρέπει να εξερευνήσετε τη βιβλιοθήκη, αλλά προσθέτει υδατογραφήματα στα αρχεία εξόδου.

### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;  
**Α:** Μπορείτε να ζητήσετε βοήθεια από το φόρουμ κοινότητας Aspose.Tasks [εδώ](https://forum.aspose.com/c/tasks/15).

### Ε: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Tasks για Java;  
**Α:** Ναι, προσωρινές άδειες διατίθενται για βραχυπρόθεσμη χρήση. Αποκτήστε μία από [εδώ](https://purchase.aspose.com/temporary-license/).

### Ε: Η αποθήκευση ως XML διατηρεί τα προσαρμοσμένα πεδία;  
**Α:** Ναι, όταν αποθηκεύετε χρησιμοποιώντας `SaveFileFormat.Xml`, όλα τα προσαρμοσμένα χαρακτηριστικά και τα επεκταμένα πεδία διατηρούνται.

### Ε: Μπορώ να αλλάξω την ημερομηνία έναρξης μετά την προσθήκη εργασιών;  
**Α:** Μπορείτε να ενημερώσετε την ημερομηνία έναρξης οποτεδήποτε πριν από την αποθήκευση· απλώς καλέστε ξανά `project.set(Prj.START_DATE, …)`.

---

**Τελευταία Ενημέρωση:** 2026-01-05  
**Δοκιμασμένο Με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}