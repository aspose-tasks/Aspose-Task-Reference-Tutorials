---
date: 2025-12-23
description: Μάθετε πώς να χρησιμοποιείτε το aspose tasks java για να ενημερώνετε
  το χρονοδιάγραμμα του έργου, να ορίζετε την ημέρα έναρξης της εβδομάδας, να αλλάζετε
  τις ημέρες ανά μήνα και να προσαρμόζετε αποδοτικά το ημερολόγιο του έργου.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Διαχείριση Ιδιοτήτων Ημέρας Εβδομάδας
url: /el/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Διαχείριση Ιδιοτήτων Ημερών Εργασίας

## Εισαγωγή
Aspose.Tasks for Java (aspose tasks java) είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές Java να εργάζονται με αρχεία Microsoft Project χωρίς να χρειάζεται εγκατεστημένο το Microsoft Project. Σε αυτό το tutorial θα μάθετε πώς να **φορτώνετε ένα αρχείο MPP**, **ορίζετε την ημέρα έναρξης της εβδομάδας**, **αλλάζετε τις ημέρες ανά μήνα**, και γενικά **προσαρμόζετε το ημερολόγιο του έργου** — όλα τα απαραίτητα βήματα για την ενημέρωση του χρονοδιαγράμματος ενός έργου. Στο τέλος, θα μπορείτε να ρυθμίζετε τις ιδιότητες των ημερών εργασίας προγραμματιστικά και να αποθηκεύετε τις αλλαγές στη μορφή που χρειάζεστε.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για τη διαχείριση έργων;** `Project` from the Aspose.Tasks library.  
- **Πώς αλλάζω την ημέρα έναρξης της εβδομάδας;** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Μπορώ να φορτώσω ένα υπάρχον αρχείο .mpp;** Yes—instantiate `Project` with the file path.  
- **Ποια μέθοδος αποθηκεύει το έργο ως XML;** `project.save(path, SaveFileFormat.Xml)`.  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for evaluation; a license is required for production.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα παρακάτω:

- **Java Development Kit (JDK)** – εγκατεστημένη η πιο πρόσφατη έκδοση.  
- **Aspose.Tasks for Java library** – download it [here](https://releases.aspose.com/tasks/java/).  
- **An IDE** όπως IntelliJ IDEA, Eclipse, ή NetBeans.  

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, εισάγετε τις απαραίτητες κλάσεις του Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Τώρα ας περάσουμε από κάθε βήμα της διαχείρισης των ιδιοτήτων των ημερών εργασίας.

## Βήμα 1: Φόρτωση Αρχείου MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Εδώ **φορτώνουμε ένα υπάρχον αρχείο .mpp** (`load mpp file`) ώστε να μπορούμε να ελέγξουμε και να τροποποιήσουμε τις ρυθμίσεις του ημερολογίου του.*

## Βήμα 2: Εμφάνιση Τρεχουσών Ιδιοτήτων Ημερών Εργασίας
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Αυτός ο κώδικας εκτυπώνει την τρέχουσα **ημέρα έναρξης της εβδομάδας**, **ημέρες ανά μήνα**, **λεπτά ανά ημέρα**, και **λεπτά ανά εβδομάδα** — τα βασικά στοιχεία που συχνά χρειάζεστε για να **προσαρμόσετε το ημερολόγιο του έργου**.

## Βήμα 3: Ορισμός Νέων Ιδιοτήτων Ημερών Εργασίας
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Σε αυτό το βήμα **ορίζουμε την ημέρα έναρξης της εβδομάδας** σε Δευτέρα, **αλλάζουμε τις ημέρες ανά μήνα** σε 24, και προσαρμόζουμε τις ημερήσιες και εβδομαδιαίες μετρήσεις λεπτών. Αυτές οι ρυθμίσεις είναι τυπικές όταν χρειάζεται να **ενημερώσετε το χρονοδιάγραμμα του έργου** ώστε να ταιριάζει με ένα μη‑τυπικό ημερολόγιο εργασίας.

## Βήμα 4: Αποθήκευση του Ενημερωμένου Έργου
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Το τροποποιημένο έργο αποθηκεύεται ως αρχείο XML, καθιστώντας το εύκολο για κοινή χρήση ή εισαγωγή σε άλλα εργαλεία.

## Βήμα 5: Επιβεβαίωση της Λειτουργίας
```java
System.out.println("Process completed Successfully");
```
Ένα απλό μήνυμα στην κονσόλα σας ενημερώνει ότι η διαδικασία ολοκληρώθηκε χωρίς σφάλματα.

## Συχνά Προβλήματα & Συμβουλές
- **Λανθασμένη διαδρομή αρχείου** – Επαληθεύστε ότι το `dataDir` τελειώνει με κάθετο ή χρησιμοποιήστε `Paths.get(...)` για διαδρομές ανεξάρτητες από την πλατφόρμα.  
- **Η άδεια δεν έχει οριστεί** – Σε περιβάλλον παραγωγής, καλέστε `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` πριν δημιουργήσετε το `Project`.  
- **Απροσδόκητη ημέρα έναρξης εβδομάδας** – Βεβαιωθείτε ότι χρησιμοποιείτε τη σωστή τιμή του enum `DayType` (π.χ., `DayType.Sunday`).  

## Συχνές Ερωτήσεις

**Q: Μπορεί το Aspose.Tasks for Java να διαχειριστεί σύνθετες δομές έργου;**  
A: Ναι, το Aspose.Tasks for Java παρέχει ολοκληρωμένη υποστήριξη για τη διαχείριση σύνθετων δομών έργου με ευκολία.

**Q: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;**  
A: Απόλυτα, το Aspose.Tasks for Java υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, εξασφαλίζοντας συμβατότητα σε όλες τις πλατφόρμες.

**Q: Μπορώ να ενσωματώσω το Aspose.Tasks for Java στις υπάρχουσες εφαρμογές Java μου;**  
A: Ναι, το Aspose.Tasks for Java προσφέρει απρόσκοπτες δυνατότητες ενσωμάτωσης, επιτρέποντάς σας να ενισχύσετε τις εφαρμογές Java με ισχυρές λειτουργίες διαχείρισης έργων.

**Q: Παρέχει το Aspose.Tasks for Java τεκμηρίωση και υποστήριξη;**  
A: Ναι, μπορείτε να έχετε πρόσβαση σε εκτενή τεκμηρίωση και υποστήριξη κοινότητας για το Aspose.Tasks for Java στην [ιστοσελίδα τους](https://releases.aspose.com/).

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks for Java από την [ιστοσελίδα τους](https://reference.aspose.com/tasks/java/) για να εξερευνήσετε τις δυνατότητές του πριν κάνετε αγορά.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}