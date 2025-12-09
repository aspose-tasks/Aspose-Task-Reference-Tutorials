---
date: 2025-12-05
description: Μάθετε πώς να εξάγετε το σύμβολο νομίσματος mpp και να αλλάξετε το σύμβολο
  νομίσματος java με το Aspose.Tasks for Java. Ανακτήστε γρήγορα το σύμβολο νομίσματος
  java για τη διαχείριση έργων.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Εξαγωγή συμβόλου νομίσματος mpp με χρήση Aspose.Tasks για Java
url: /el/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εξαγωγή συμβόλου νομίσματος mpp χρησιμοποιώντας το Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το tutorial θα **εξάγετε το σύμβολο νομίσματος mpp** από ένα αρχείο Microsoft Project και θα ανακαλύψετε πώς να **αλλάξετε το σύμβολο νομίσματος java** ή **ανακτήσετε το σύμβολο νομίσματος java** χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks. Είτε δημιουργείτε ένα εργαλείο αναφορών, ενσωματώνετε δεδομένα Project σε σύστημα χρηματοοικονομίας, είτε απλώς χρειάζεστε να εμφανίσετε το σωστό σύμβολο νομίσματος στη διεπαφή χρήστη, η κατάκτηση αυτού του μικρού αλλά ουσιώδους έργου θα κάνει τις εφαρμογές Java σας πιο ανθεκτικές και φιλικές προς το χρήστη.

## Γρήγορες Απαντήσεις
- **What does “extract currency symbol mpp” mean?** Σημαίνει την ανάγνωση του συμβόλου νομίσματος που αποθηκεύεται σε ένα αρχείο MPP (Microsoft Project).  
- **Which library handles this?** Το Aspose.Tasks for Java παρέχει ένα απλό API για αυτή τη δουλειά.  
- **Do I need a license?** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **How long does it take?** Με τον παρακάτω κώδικα, μπορείτε να λάβετε το σύμβολο σε λιγότερο από ένα λεπτό.  
- **Can I also change the symbol?** Ναι – μπορείτε να ορίσετε μια νέα τιμή χρησιμοποιώντας την ίδια ιδιότητα `Prj.CURRENCY_SYMBOL`.

## Τι είναι το “extract currency symbol mpp”;
Το Microsoft Project αποθηκεύει το σύμβολο νομίσματος (π.χ., $, €, £) στην κεφαλίδα του αρχείου έργου. Η λειτουργία **extract currency symbol mpp** διαβάζει αυτήν την τιμή ώστε να μπορείτε να την εμφανίσετε ή να την επεξεργαστείτε προγραμματιστικά.

## Γιατί να αλλάξετε το σύμβολο νομίσματος java;
Τα έργα συχνά καλύπτουν πολλές περιοχές. Η δυνατότητα **change currency symbol java** σε χρόνο εκτέλεσης σας επιτρέπει να προσαρμόζετε αναφορές, τιμολόγια ή πίνακες ελέγχου στην τοπική αγορά χωρίς να χρειάζεται να δημιουργήσετε ξανά ολόκληρο το αρχείο έργου.

## Προαπαιτούμενα
1. **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη.  
2. **Aspose.Tasks for Java** – κατεβάστε το πιο πρόσφατο JAR από τη [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Ένα έγκυρο αρχείο **project.mpp** τοποθετημένο σε φάκελο που μπορείτε να αναφέρετε από τον κώδικά σας.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε για να εργαστείτε με αρχεία Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Βήμα 1: Ορισμός του Καταλόγου Δεδομένων
Ενημερώστε την εφαρμογή πού βρίσκεται το αρχείο *.mpp* σας.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Χρησιμοποιήστε `System.getProperty("user.dir")` για να δημιουργήσετε μια απόλυτη διαδρομή που λειτουργεί σε οποιονδήποτε υπολογιστή.

## Βήμα 2: Φόρτωση του Αρχείου MS Project
Δημιουργήστε ένα αντικείμενο `Project` που αντιπροσωπεύει το αρχείο MPP στη μνήμη.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Βήμα 3: Ανάκτηση (και προαιρετικά αλλαγή) του Συμβόλου Νομίσματος
Τώρα **retrieve currency symbol java** διαβάζοντας την ιδιότητα `Prj.CURRENCY_SYMBOL`. Μπορείτε επίσης να **change currency symbol java** αναθέτοντας μια νέα συμβολοσειρά στην ίδια ιδιότητα.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Η κλήση `System.out.println` εκτυπώνει το σύμβολο (π.χ., `$`) στην κονσόλα, επιβεβαιώνοντας ότι η εξαγωγή ήταν επιτυχής.

## Συχνά Προβλήματα & Πώς να Τα Διορθώσετε
| Συμπτωμα | Πιθανή Αιτία | Λύση |
|----------|--------------|------|
| `NullPointerException` on `project.get(...)` | Λάθος διαδρομή αρχείου ή αρχείο δεν βρέθηκε | Επαληθεύστε το `dataDir` και το όνομα αρχείου· χρησιμοποιήστε `new File(dataDir).exists()` για εντοπισμό σφαλμάτων |
| Unexpected symbol (e.g., `?`) | Το έργο δημιουργήθηκε με μη‑τυπική τοπική ρύθμιση | Βεβαιωθείτε ότι το αρχείο MPP ορίζει πραγματικά σύμβολο νομίσματος· μπορείτε να ορίσετε ένα προγραμματιστικά όπως φαίνεται παραπάνω |
| License error | Χρήση της δοκιμής χωρίς έγκυρο αρχείο άδειας | Φορτώστε την άδειά σας με `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` πριν δημιουργήσετε το αντικείμενο `Project` |

## Συχνές Ερωτήσεις

**Q: Μπορώ να χειριστώ άλλα χαρακτηριστικά του έργου εκτός από τα σύμβολα νομισμάτων χρησιμοποιώντας το Aspose.Tasks;**  
A: Ναι, το Aspose.Tasks σας επιτρέπει να επεξεργάζεστε εργασίες, πόρους, αναθέσεις, ημερολόγια και πολλά άλλα χαρακτηριστικά του έργου.

**Q: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων MS Project;**  
A: Απόλυτα. Υποστηρίζει μορφές MPP, MPT και XML από το Project 98 έως τις πιο πρόσφατες εκδόσεις.

**Q: Παρέχει το Aspose.Tasks τεκμηρίωση και υποστήριξη για προγραμματιστές;**  
A: Πλήρη τεκμηρίωση API, παραδείγματα κώδικα και ειδικό φόρουμ υποστήριξης διατίθενται στην ιστοσελίδα του Aspose.Tasks.

**Q: Μπορώ να δοκιμάσω το Aspose.Tasks πριν το αγοράσω;**  
A: Ναι – μπορείτε να κατεβάσετε μια πλήρως λειτουργική δωρεάν δοκιμή από την [Aspose website](https://purchase.aspose.com/buy).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks;**  
A: Προσωρινές άδειες παρέχονται στη [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) για σκοπούς αξιολόγησης.

---

**Τελευταία Ενημέρωση:** 2025-12-05  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}