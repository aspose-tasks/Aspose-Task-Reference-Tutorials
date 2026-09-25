---
date: 2026-09-25
description: Μάθετε πώς να ανακτήσετε κωδικούς νομίσματος από αρχεία MS Project χρησιμοποιώντας
  Aspose.Tasks για Java – ο γρήγορος τρόπος για να αποκτήσετε τον κωδικό νομίσματος
  που χρειάζονται οι προγραμματιστές Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Διαχείριση κωδικών νομίσματος στο Aspose.Tasks
og_description: Ανάκτηση κωδικού νομίσματος java από αρχεία MS Project χρησιμοποιώντας
  Aspose.Tasks. Αυτός ο οδηγός σας δείχνει πώς να διαβάσετε το έργο, να εξάγετε το
  αναγνωριστικό νομίσματος ISO και να το εφαρμόσετε σε εφαρμογές Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Ανάκτηση κωδικού νομίσματος java από το MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Ανάκτηση κωδικού νομίσματος java από το MS Project με Aspose.Tasks
url: /el/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάκτηση κωδικού νομίσματος java από το MS Project με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο θα μάθετε **πώς να ανακτήσετε τον κωδικό νομίσματος java** από ένα αρχείο MS Project χρησιμοποιώντας το Aspose.Tasks Java API. Είτε χρειάζεστε να δημιουργήσετε οικονομικές αναφορές πολλαπλών νομισμάτων, να ενοποιήσετε έργα από διαφορετικές περιοχές, είτε απλώς να εμφανίσετε το σωστό σύμβολο νομίσματος σε ένα σύστημα downstream, τα παρακάτω βήματα θα σας οδηγήσουν από τη ρύθμιση του περιβάλλοντος μέχρι την κλήση μιας γραμμής που επιστρέφει το αναγνωριστικό ISO του νομίσματος. Στο τέλος του οδηγού θα είστε άνετοι με τη φόρτωση οποιουδήποτε υποστηριζόμενου μορφότυπου αρχείου Project και την εξαγωγή του τριψήφιου κωδικού νομίσματος όπως `USD`, `EUR` ή `GBP`.

## Γρήγορες απαντήσεις
- **Τι κάνει το API;** Διαβάζει αρχεία MS Project και εκθέτει ιδιότητες όπως ο κωδικός νομίσματος.  
- **Ποια γλώσσα χρησιμοποιείται;** Java, μέσω της βιβλιοθήκης Aspose.Tasks for Java.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να ανακτήσω τον κωδικό σε μία γραμμή;** Ναι—`prj.get(Prj.CURRENCY_CODE)` επιστρέφει αμέσως τη συμβολοσειρά του κωδικού νομίσματος.  
- **Είναι συμβατό με όλες τις εκδόσεις του Project;** Το Aspose.Tasks υποστηρίζει περισσότερα από 20 μορφές εισόδου, συμπεριλαμβανομένων των παλαιών MPP, XML και XER αρχείων.

## Τι είναι η ανάγνωση αρχείου ms project;
Η ανάγνωση ενός αρχείου MS Project σημαίνει το προγραμματιστικό άνοιγμα ενός *.mpp* (ή οποιουδήποτε άλλου υποστηριζόμενου μορφότυπου όπως XML ή XER) και η πρόσβαση στις εσωτερικές δομές δεδομένων του. Αυτές οι δομές περιλαμβάνουν εργασίες, πόρους, ημερολόγια, πίνακες κόστους και οικονομικές ρυθμίσεις. Αναλύοντας το αρχείο μπορείτε να εξάγετε πληροφορίες χωρίς να εκκινήσετε το Microsoft Project, επιτρέποντας αυτοματοποιημένες αναφορές, μετανάστευση και ροές ενσωμάτωσης.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για την ανάγνωση αρχείων msproject;
Το Aspose.Tasks προσφέρει μια καθαρά‑Java λύση που αφαιρεί την ανάγκη για COM interop ή τοπική εγκατάσταση του Microsoft Project. Υποστηρίζει περισσότερα από 20 μορφές αρχείων, μπορεί να διαχειριστεί έργα με χιλιάδες εργασίες ενώ χρησιμοποιεί λιγότερο από 100 MB μνήμης, και παρέχει ένα πλούσιο μοντέλο αντικειμένων. Η άμεση πρόσβαση σε σταθερές όπως `Prj.CURRENCY_CODE` σας επιτρέπει να ανακτήσετε τις πληροφορίες νομίσματος άμεσα και αξιόπιστα.

## Προαπαιτούμενα
Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε τα εξής:

### Java Development Kit (JDK) εγκατεστημένο
Απαιτείται πρόσφατο JDK (11 ή νεότερο). Κατεβάστε το από την επίσημη ιστοσελίδα της Oracle: [εδώ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Βιβλιοθήκη Aspose.Tasks for Java
Αποκτήστε τα πιο πρόσφατα binaries του Aspose.Tasks for Java και προσθέστε τα στο classpath του έργου σας. Η πλήρης τεκμηρίωση και οι σύνδεσμοι λήψης είναι διαθέσιμοι [εδώ](https://reference.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Η κλάση `Project` και οι σταθερές `Prj` βρίσκονται στο namespace `com.aspose.tasks`. Εισάγετέ τα στην αρχή του αρχείου πηγαίου κώδικα Java:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: ρύθμιση καταλόγου δεδομένων
Ορίστε το φάκελο που περιέχει το αρχείο *.mpp* σας. Προσαρμόστε τη διαδρομή ώστε να ταιριάζει με το περιβάλλον σας ώστε το runtime να μπορεί να εντοπίσει το αρχείο έργου.

```java
String dataDir = "Your Data Directory";
```

### Βήμα 2: φόρτωση του αρχείου έργου
Η κλάση `Project` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Tasks που αντιπροσωπεύει ένα μοναδικό αρχείο MS Project στη μνήμη. Η δημιουργία μιας στιγμής διαβάζει το αρχείο και δημιουργεί ένα μοντέλο στη μνήμη που μπορείτε να ερωτήσετε.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Βήμα 3: ανάκτηση κωδικού νομίσματος
Η σταθερά `Prj.CURRENCY_CODE` προσδιορίζει την ιδιότητα που αποθηκεύει το αναγνωριστικό ISO του νομίσματος. Η κλήση `prj.get(Prj.CURRENCY_CODE)` επιστρέφει τον τριψήφιο κωδικό σε μία ενέργεια.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Η έξοδος θα είναι ο τριψήφιος κωδικός ISO του νομίσματος (π.χ., `USD`, `EUR`, `GBP`) που έχει ρυθμιστεί το έργο για χρήση.

### Βήμα 4: πώς να ανακτήσετε τον κωδικό νομίσματος σε Java (πρόσθετο πλαίσιο)
Φορτώστε το έργο σας, καλέστε `prj.get(Prj.CURRENCY_CODE)` και αποθηκεύστε το αποτέλεσμα σε μια `String`. Στη συνέχεια μπορείτε να περάσετε αυτήν την τιμή σε οποιαδήποτε χρηματοοικονομική υπηρεσία, μηχανή αναφορών ή στοιχείο UI που απαιτεί αναγνωριστικό νομίσματος.

### Βήμα 5: (προαιρετικό) χρήση του κωδικού νομίσματος
Τυπικά σενάρια downstream περιλαμβάνουν:

- **Δημιουργία αναφορών** – προσθέστε τον κωδικό στην αρχή των στηλών κόστους (`USD 1,200`).  
- **Ενσωμάτωση API** – στείλτε τον κωδικό ISO σε πύλες πληρωμών που απαιτούν παράμετρο νομίσματος.  
- **Συγκέντρωση δεδομένων** – ομαδοποιήστε πολλαπλά έργα ανά νόμισμα για ανάλυση σε επίπεδο χαρτοφυλακίου.

## Συχνά προβλήματα και λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Αδυναμία εξόδου** | Το αρχείο έργου δεν ορίζει νόμισμα (η προεπιλογή είναι κενή). | Ορίστε το νόμισμα στο Microsoft Project ή εκχωρήστε το μέσω `prj.set(Prj.CURRENCY_CODE, "USD");` πριν από την ανάγνωση. |
| **Αρχείο δεν βρέθηκε** | Λανθασμένη διαδρομή `dataDir`. | Επαληθεύστε τη διαδρομή και βεβαιωθείτε ότι το όνομα αρχείου ταιριάζει ακριβώς, συμπεριλαμβανομένης της ευαισθησίας σε πεζά/κεφαλαία. |
| **Μη υποστηριζόμενη έκδοση αρχείου** | Πολύ παλιό ή κατεστραμμένο αρχείο *.mpp*. | Αναβαθμίστε στην πιο πρόσφατη έκδοση του Aspose.Tasks ή μετατρέψτε το αρχείο σε νεότερο μορφότυπο στο Microsoft Project πρώτα. |

## Συχνές ερωτήσεις

**Q: Μπορεί το Aspose.Tasks να διαχειριστεί σύνθετες δομές έργου;**  
A: Ναι, το API διαβάζει ιεραρχίες εργασιών πολλαπλών επιπέδων, ομάδες πόρων, προσαρμοσμένα πεδία και ημερολόγια χωρίς περιορισμό.

**Q: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις αρχείων MS Project;**  
A: Απόλυτα. Υποστηρίζει MPP, XML, XER και άλλες μορφές από το Project 98 μέχρι τις πιο πρόσφατες εκδόσεις του Office.

**Q: Παρέχει το Aspose.Tasks τεκμηρίωση και υποστήριξη;**  
A: Πλήρης αναφορά API, παραδείγματα κώδικα και εξειδικευμένη τεχνική υποστήριξη είναι διαθέσιμα στην ιστοσελίδα της Aspose.

**Q: Μπορώ να δοκιμάσω το Aspose.Tasks πριν την αγορά;**  
A: Προσφέρεται δωρεάν δοκιμή ώστε να αξιολογήσετε όλα τα χαρακτηριστικά, συμπεριλαμβανομένης της εξαγωγής κωδικού νομίσματος.

**Q: Πού μπορώ να αποκτήσω προσωρινή άδεια για αξιολόγηση;**  
A: Προσωρινές άδειες διατίθενται από την [ιστοσελίδα](https://purchase.aspose.com/temporary-license/).

---

**Τελευταία ενημέρωση:** 2026-09-25  
**Δοκιμάστηκε με:** Aspose.Tasks for Java (latest version)  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Ιδιότητες Έργου Java – Ανάγνωση Μεταδεδομένων με Aspose.Tasks](/tasks/java/project-properties/)
- [Πώς να Διαβάσετε Πληροφορίες Έργου από το Microsoft Project με το Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Ανάκτηση Κωδικών Περιγράμματος MS Project στο Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}