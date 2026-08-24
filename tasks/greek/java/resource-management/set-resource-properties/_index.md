---
date: 2026-08-24
description: Μάθετε πώς να προσθέσετε resource ms project, να ορίσετε standard rate
  και άλλες resource properties στο MS Project χρησιμοποιώντας Aspose.Tasks for Java,
  και να διαχειρίζεστε resources αποδοτικά.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Ορίστε Resource Properties στο Aspose.Tasks
og_description: Προσθέστε resource ms project και ορίστε standard rate χρησιμοποιώντας
  Aspose.Tasks for Java. Μάθετε prerequisites, step‑by‑step code, και troubleshooting
  σε αυτόν τον σύντομο οδηγό.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Προσθέστε resource ms project και ορίστε rate με Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Πώς να προσθέσετε resource ms project με Aspose.Tasks
url: /el/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη πόρου ms project και ορισμός τιμής στο Aspose.Tasks

## Εισαγωγή
Αν αναπτύσσετε εφαρμογές Java που χρειάζεται να διαβάζουν ή να γράφουν αρχεία Microsoft Project, **προσθήκη πόρου ms project** και η διαμόρφωση της τυπικής τιμής του είναι μια συνηθισμένη αλλά απαραίτητη εργασία. Σε αυτόν τον οδηγό θα δείτε πώς να δημιουργήσετε ένα αντικείμενο `Project`, να προσθέσετε έναν πόρο και να ορίσετε τόσο τις τυπικές όσο και τις υπερωριακές τιμές χρησιμοποιώντας το Aspose.Tasks για Java. Στο τέλος θα μπορείτε να αυτοματοποιήσετε τους υπολογισμούς κόστους και να διατηρείτε τα χρονοδιαγράμματα του έργου ενημερωμένα χωρίς να απαιτείται η εγκατάσταση του Microsoft Project.

## Γρήγορες απαντήσεις
- **Ποια κλάση αντιπροσωπεύει ένα αρχείο Project;** `Project`
- **Ποια κλήση προσθέτει έναν νέο πόρο;** `project.getResources().add()`
- **Πώς ορίζετε την τυπική τιμή;** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Απαιτείται άδεια για παραγωγική χρήση;** Ναι, πρέπει να φορτώσετε μια έγκυρη άδεια Aspose.Tasks.
- **Ποιες εκδόσεις Java υποστηρίζονται;** Java 8 και νεότερες (συνιστάται Java 17+).

## Τι είναι το «ορισμός τυπικής τιμής»?
Η λειτουργία *ορισμός τυπικής τιμής* αναθέτει ένα προεπιλεγμένο ωριαίο κόστος σε έναν πόρο. Αυτή η τιμή χρησιμοποιείται από τους διαχειριστές έργων για τον υπολογισμό των εξόδων εργασίας, τη δημιουργία αναφορών κόστους και την πρόβλεψη προϋπολογισμών, εξασφαλίζοντας ότι οι υπολογισμοί κόστους αντικατοπτρίζουν την αναμενόμενη τιμή της εργασίας που εκτελείται από κάθε πόρο καθ' όλη τη διάρκεια του κύκλου ζωής του έργου.

## Γιατί να ορίζετε τιμές με το Aspose.Tasks;
Το Aspose.Tasks μπορεί να επεξεργαστεί **πάνω από 50 μορφές εισόδου και εξόδου**, συμπεριλαμβανομένων των αρχείων MPP, MPX, XML και Primavera, και διαχειρίζεται έργα με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Αυτό επιτρέπει επεξεργασία παρτίδων υψηλής απόδοσης σε διακομιστές Windows, Linux ή macOS, μειώνοντας την χειροκίνητη εργασία έως και 90 % σε τυπικά σενάρια αυτοματοποίησης.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι τα παρακάτω στοιχεία είναι έτοιμα:

### Ρύθμιση περιβάλλοντος ανάπτυξης Java
1. Εγκαταστήστε το JDK 8 ή νεότερο. Μπορείτε να το κατεβάσετε από την [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Επιλέξτε ένα IDE όπως IntelliJ IDEA, Eclipse ή NetBeans και ρυθμίστε το για ανάπτυξη Java.

### Εγκατάσταση Aspose.Tasks για Java
1. Κατεβάστε το πιο πρόσφατο πακέτο Aspose.Tasks για Java από τη [download page](https://releases.aspose.com/tasks/java/).  
2. Προσθέστε τα αρχεία JAR στην classpath του έργου σας ή δηλώστε την εξάρτηση Maven/Gradle όπως φαίνεται στην τεκμηρίωση του προϊόντος.

## Εισαγωγή πακέτων
Εισάγετε τις βασικές κλάσεις Aspose.Tasks που θα χρειαστείτε. Αυτό το βήμα σας δίνει πρόσβαση στους τύπους `Project`, `Resource` και `Rsc` που χρησιμοποιούνται αργότερα.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Βήμα 1: δημιουργία αντικειμένου project
Η κλάση `Project` είναι το αντικείμενο υψηλότερου επιπέδου που αντιπροσωπεύει ολόκληρο το αρχείο MS Project στη μνήμη. Η δημιουργία ενός στιγμιότυπου της δημιουργεί ένα κενό έργο που μπορείτε να γεμίσετε με εργασίες, πόρους και άλλα δεδομένα.

```java
Project project = new Project();
```

## Βήμα 2: προσθήκη πόρου (add resource ms project)
Η κλάση `Resource` μοντελοποιεί έναν μοναδικό πόρο του έργου, όπως ένα άτομο, εξοπλισμό ή υλικό. Η προσθήκη ενός πόρου μέσω του `project.getResources().add()` επιστρέφει ένα μη‑null αντικείμενο `Resource` έτοιμο για διαμόρφωση ιδιοτήτων.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Βήμα 3: ορισμός ιδιοτήτων πόρου (how to set rates)
Η απαρίθμηση `Rsc` περιέχει σταθερές για πεδία πόρων όπως `STANDARD_RATE` και `OVERTIME_RATE`.  
Ορίζετε τις τυπικές και υπερωριακές τιμές καλώντας τη μέθοδο `set` στο αντικείμενο `Resource` με τις κατάλληλες τιμές της απαρίθμησης `Rsc`. Οι τιμές αποθηκεύονται ως `BigDecimal` για να διατηρείται η χρηματική ακρίβεια.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Συχνά προβλήματα και λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| `NullPointerException` κατά την κλήση του `set` | Ο πόρος δεν προστέθηκε σωστά. | Βεβαιωθείτε ότι το `project.getResources().add()` επιστρέφει ένα μη‑null `Resource`. |
| Οι τιμές εμφανίζονται ως 0 στο αποθηκευμένο αρχείο | Χρήση `int` αντί για `BigDecimal`. | Πάντα χρησιμοποιείτε `BigDecimal.valueOf()` για χρηματικές τιμές. |
| Δεν βρέθηκε άδεια | Το αρχείο άδειας δεν φορτώθηκε πριν τη δημιουργία του `Project`. | Φορτώστε την άδεια (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) στην εκκίνηση του προγράμματος. |

## Συμπέρασμα
Τώρα ξέρετε πώς να **προσθέσετε πόρο ms project**, να δημιουργήσετε ένα αντικείμενο `Project` και να **ορίσετε τυπικές και υπερωριακές τιμές** χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η δυνατότητα σας επιτρέπει να αυτοματοποιήσετε τους υπολογισμούς κόστους, να δημιουργήσετε προσαρμοσμένες αναφορές και να διαχειριστείτε πλήρως τους πόρους του MS Project από οποιαδήποτε εφαρμογή Java.

## Συχνές ερωτήσεις
**Q: Μπορεί το Aspose.Tasks για Java να χειριστεί σύνθετα αρχεία MS Project;**  
A: Ναι, υποστηρίζει όλες τις κύριες μορφές Project, συμπεριλαμβανομένων μεγάλων αρχείων με χιλιάδες εργασίες και πόρους, διατηρώντας κάθε πεδίο χωρίς απώλεια δεδομένων.

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Tasks για Java από τη [Aspose.Tasks free trial page](https://releases.aspose.com/).

**Q: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;**  
A: Μπορείτε να ζητήσετε βοήθεια στο [support forum](https://forum.aspose.com/c/tasks/15).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για αξιολόγηση;**  
A: Μια προσωρινή άδεια είναι διαθέσιμη από τη [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να αγοράσω μια άδεια έκδοσης;**  
A: Αγοράστε πλήρη άδεια από τη [purchase page](https://purchase.aspose.com/buy).

---

**Τελευταία ενημέρωση:** 2026-08-24  
**Δοκιμή με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Πώς να δημιουργήσετε πόρους – Διαχείριση πόρων με Aspose.Tasks για Java](/tasks/java/resource-management/)
- [Προσθήκη πόρου στο έργο με Aspose.Tasks για Java](/tasks/java/resource-management/create-resources/)
- [Πώς να προσθέσετε πόρο στο έργο και να διαχειριστείτε τις ιδιότητες καθυστέρησης εξισορρόπησης στο Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}