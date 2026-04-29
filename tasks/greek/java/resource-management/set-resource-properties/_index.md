---
date: 2026-01-18
description: Μάθετε πώς να ορίζετε το τυπικό κόστος και άλλες ιδιότητες πόρων στο
  MS Project χρησιμοποιώντας το Aspose.Tasks για Java, συμπεριλαμβανομένου του πώς
  να προσθέτετε πόρους στο MS Project και να διαχειρίζεστε τους πόρους αποδοτικά.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να ορίσετε το τυπικό ποσοστό για πόρους στο Aspose.Tasks
url: /el/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Τυπικής Τιμής για Πόρους στο Aspose.Tasks

## Εισαγωγή
Αν δημιουργείτε εφαρμογές Java που χρειάζεται να αλληλεπιδρούν με αρχεία Microsoft Project, η **ρύθμιση της τυπικής τιμής** για έναν πόρο είναι μία από τις πιο συνηθισμένες εργασίες. Σε αυτό το tutorial θα μάθετε πώς να **ορίζετε την τυπική τιμή** και άλλες ιδιότητες πόρων χρησιμοποιώντας το Aspose.Tasks για Java. Στο τέλος του οδηγού θα μπορείτε να δημιουργήσετε ένα αντικείμενο project, να προσθέσετε έναν πόρο σε ένα αρχείο MS Project και να διαχειρίζεστε τους πόρους του MS Project με σιγουριά.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για εργασία με αρχείο Project;** `Project`
- **Ποια μέθοδος προσθέτει νέο πόρο;** `project.getResources().add()`
- **Πώς ορίζετε την τυπική τιμή;** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks.
- **Ποια έκδοση Java υποστηρίζεται;** Java 8+ (συνιστάται η τελευταία έκδοση JDK).

## Τι είναι η «ρύθμιση τυπικής τιμής»;
Η λειτουργία *ρύθμιση τυπικής τιμής* εκχωρεί ένα προεπιλεγμένο ωριαίο κόστος σε έναν πόρο. Οι διαχειριστές έργων χρησιμοποιούν αυτήν την τιμή για να υπολογίζουν τα κόστη εργασίας, να δημιουργούν αναφορές κόστους και να προβλέπουν προϋπολογισμούς.

## Γιατί να ορίζετε τιμές με το Aspose.Tasks;
- **Δεν απαιτείται εγκατάσταση Microsoft Project** – διαχειριστείτε τα αρχεία απευθείας από Java.
- **Πλήρης πιστότητα** – όλα τα πεδία πόρων, συμπεριλαμβανομένων των υπερωριών και των τιμών κόστους, διατηρούνται.
- **Διαπλατφορμική** – λειτουργεί σε Windows, Linux και macOS.
- **Φιλικό προς τον αυτοματισμό** – ιδανικό για επεξεργασία παρτίδων ή ενσωμάτωση σε CI pipelines.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

### Ρύθμιση Περιβάλλοντος Ανάπτυξης Java
1. **Εγκατάσταση JDK:** Βεβαιωθείτε ότι έχετε εγκατεστημένο το Java Development Kit (JDK) στο σύστημά σας. Μπορείτε να το κατεβάσετε από την [ιστοσελίδα της Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **Ρύθμιση IDE:** Επιλέξτε ένα Integrated Development Environment (IDE) όπως IntelliJ IDEA, Eclipse ή NetBeans και εγκαταστήστε το στο μηχάνημά σας.

### Εγκατάσταση Aspose.Tasks για Java
1. **Λήψη Aspose.Tasks για Java:** Μεταβείτε στη [σελίδα λήψης](https://releases.aspose.com/tasks/java/) και αποκτήστε την τελευταία έκδοση του Aspose.Tasks για Java.
2. **Ενσωμάτωση στο Project:** Ενσωματώστε τη βιβλιοθήκη Aspose.Tasks για Java στο Java project σας προσθέτοντάς την ως εξάρτηση.

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, πρέπει να εισάγετε τα απαραίτητα πακέτα από το Aspose.Tasks για Java στο project σας. Αυτό το βήμα εξασφαλίζει ότι έχετε πρόσβαση στις απαιτούμενες λειτουργίες.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Βήμα 1: Δημιουργία Αντικειμένου Project
Η δημιουργία ενός **αντικειμένου project** είναι το πρώτο βήμα για οποιαδήποτε επεξεργασία MS Project. Αντιπροσωπεύει ολόκληρο το αρχείο project στη μνήμη.

```java
Project project = new Project();
```

## Βήμα 2: Προσθήκη Πόρου (add resource ms project)
Τώρα θα **προσθέσουμε πόρο MS Project** χρησιμοποιώντας τη συλλογή Resources. Το όνομα του πόρου μπορεί να είναι οτιδήποτε έχει νόημα για το χρονοδιάγραμμά σας.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Βήμα 3: Ορισμός Ιδιοτήτων Πόρου (how to set rates)
Εδώ **ορίζουμε την τυπική τιμή** και επίσης δείχνουμε πώς να ορίσουμε μια τιμή υπερωρίας. Αυτές οι τιμές αποθηκεύονται ως τιμές `BigDecimal` για να διατηρηθεί η ακρίβεια.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Κοινά Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| `NullPointerException` when calling `set` | Ο πόρος δεν προστέθηκε σωστά. | Βεβαιωθείτε ότι το `project.getResources().add()` επιστρέφει ένα μη‑null `Resource`. |
| Rates appear as 0 in the saved file | Χρήση `int` αντί για `BigDecimal`. | Πάντα χρησιμοποιείτε `BigDecimal.valueOf()` για χρηματικές τιμές. |
| License not found | Το αρχείο άδειας δεν φορτώθηκε πριν τη δημιουργία του `Project`. | Φορτώστε την άδεια (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) στην αρχή του προγράμματός σας. |

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα έχετε μάθει πώς να **δημιουργήσετε ένα αντικείμενο project**, **προσθέσετε έναν πόρο MS Project**, και **ορίσετε την τυπική τιμή** μαζί με άλλες ιδιότητες πόρων. Αυτό σας δίνει τη δυνατότητα να αυτοματοποιήσετε τους υπολογισμούς κόστους, να δημιουργήσετε προσαρμοσμένες αναφορές και να διαχειριστείτε πλήρως τους πόρους του MS Project από τη Java.

## Συχνές Ερωτήσεις
### Μπορεί το Aspose.Tasks για Java να διαχειριστεί σύνθετα αρχεία MS Project;
Ναι, το Aspose.Tasks για Java είναι ικανό να διαχειριστεί μια ευρεία γκάμα μορφών αρχείων MS Project, συμπεριλαμβανομένων των σύνθετων με εκτεταμένες ιεραρχίες εργασιών.

### Υπάρχει δωρεάν δοκιμαστική έκδοση του Aspose.Tasks για Java;
Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμαστική έκδοση του Aspose.Tasks για Java από [εδώ](https://releases.aspose.com/).

### Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks για Java;
Μπορείτε να ζητήσετε βοήθεια και να συμμετέχετε σε συζητήσεις σχετικά με το Aspose.Tasks για Java στο [φόρουμ υποστήριξης](https://forum.aspose.com/c/tasks/15).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks για Java;
Μπορείτε να αποκτήσετε προσωρινή άδεια από τη [σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/) για σκοπούς αξιολόγησης.

### Πού μπορώ να αγοράσω μια αδειοδοτημένη έκδοση του Aspose.Tasks για Java;
Μπορείτε να αγοράσετε μια αδειοδοτημένη έκδοση του Aspose.Tasks για Java από τη [σελίδα αγοράς](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία ενημέρωση:** 2026-01-18  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose