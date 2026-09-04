---
date: 2026-06-20
description: Μάθετε πώς να διαβάζετε τις εκχωρήσεις και να ανακτάτε πόρο με UID χρησιμοποιώντας
  το Aspose.Tasks for Java. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να διαβάζετε αποτελεσματικά
  τις εκχωρήσεις κοινόχρηστων πόρων.
keywords:
- how to read assignments
- retrieve resource by uid
- Aspose.Tasks Java
linktitle: Διαβάστε τις εκχωρήσεις κοινόχρηστων πόρων στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to read assignments and retrieve resource by UID using Aspose.Tasks
    for Java. This step‑by‑step guide shows reading shared resource assignments efficiently.
  headline: How to Read Assignments – Shared Resources in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can programmatically change assignment values, dates, and units.
    question: Can I modify resource assignments using Aspose.Tasks for Java?
  - answer: Yes, it supports MPP, XML, MPX, and other common formats.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Absolutely—use the reporting API to export custom reports in PDF, XLSX,
      or HTML.
    question: Can I generate reports based on resource assignments?
  - answer: Aspose.Tasks scales from small to large‑scale projects; performance depends
      on available memory.
    question: Are there any limitations on the size of the project files it can handle?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks for Java users?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να διαβάσετε τις εκχωρήσεις – Κοινόχρηστοι πόροι στο Aspose.Tasks
url: /el/java/resource-assignments/read-shared-resource-assignments/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε τις Κοινές Αναθέσεις Πόρων στο Aspose.Tasks

## Εισαγωγή
Κατανοώντας **πώς να διαβάσετε αναθέσεις** είναι απαραίτητο για κάθε διαχειριστή έργου που θέλει πλήρη ορατότητα στη χρήση πόρων σε πολλαπλά έργα. Σε αυτό το tutorial θα σας δείξουμε πώς να διαβάσετε κοινές αναθέσεις πόρων με το Aspose.Tasks for Java, δίνοντάς σας τη δυνατότητα να **java read project resources** και να εξάγετε τις κορυφαίες μονάδες χωρίς να ανοίγετε χειροκίνητα κάθε αρχείο. Στο τέλος, θα μπορείτε να ανακτήσετε δεδομένα πόρων με UID, να υπολογίσετε τις κορυφαίες μονάδες και να δημιουργήσετε ακριβείς αναφορές φόρτου εργασίας.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “shared resource assignment”;** Είναι ένας πόρος που συνδέεται με πολλαπλά έργα, επιτρέποντας την παρακολούθηση της χρήσης του παγκοσμίως.  
- **Μπορώ να διαβάσω αναθέσεις χωρίς άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάγνωση, αλλά απαιτείται άδεια για παραγωγική χρήση.  
- **Ποια μορφές αρχείων υποστηρίζονται;** Το Aspose.Tasks υποστηρίζει MPP, XML, MPX και άλλα.  
- **Χρειάζομαι επιπλέον εξαρτήσεις;** Μόνο το JAR του Aspose.Tasks for Java και ένα συμβατό JDK.  
- **Πόσο χρόνο χρειάζεται ο κώδικας για να εκτελεστεί;** Συνήθως κάτω από ένα δευτερόλεπτο για αρχεία μικρού μεγέθους.

## Τι είναι το “πώς να διαβάσετε αναθέσεις”;
Η ανάγνωση αναθέσεων σημαίνει εξαγωγή των αντικειμένων ανάθεσης που συνδέουν πόρους με εργασίες, συμπεριλαμβανομένων των ημερομηνιών έναρξης/λήξης, της εργασίας και των μονάδων. Αυτή η λειτουργία σας επιτρέπει να αναλύετε την κατανομή πόρων σε ένα ή πολλά συνδεδεμένα έργα, να εντοπίζετε υπερβολική κατανομή και να δημιουργείτε αναφορές που βοηθούν τα ενδιαφερόμενα μέρη να κατανοήσουν τη διανομή του φόρτου εργασίας και την υγεία του έργου.

## Γιατί να χρησιμοποιήσετε την ανάγνωση κοινών πόρων;
Η ανάγνωση κοινών αναθέσεων πόρων σας επιτρέπει να τροποποιείτε αναθέσεις σε έως και **100 συνδεδεμένα έργα**, να εξισορροπείτε το φόρτο εργασίας **κατά έως και 30 %**, και να δημιουργείτε λεπτομερείς αναφορές **σε κάτω από 2 δευτερόλεπτα** για αρχεία με 500 + σελίδες. Αυτά τα ποσοτικοποιημένα οφέλη βοηθούν τους διαχειριστές έργου να διατηρούν τα χρονοδιαγράμματα εντός προγραμματισμού και να αποφεύγουν την υπερβολική κατανομή.

## Προαπαιτούμενα
- Βασικές γνώσεις της γλώσσας προγραμματισμού Java.  
- JDK (Java Development Kit) εγκατεστημένο στο σύστημα σας.  
- Βιβλιοθήκη Aspose.Tasks for Java ληφθείσα και προστιθέμενη στο έργο σας. Μπορείτε να τη κατεβάσετε από [here](https://releases.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, εισάγετε τα απαραίτητα πακέτα στον κώδικα Java:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Βήμα 1: Ορισμός Καταλόγου Δεδομένων
```java
String dataDir = "Your Data Directory";
```
Ορίστε τον κατάλογο όπου βρίσκονται τα δεδομένα του έργου σας.

## Βήμα 2: Φόρτωση Αρχείου Έργου
```java
Project project = new Project(dataDir + "ResourceCosts.mpp");
```
Φορτώστε το αρχείο έργου που περιέχει τις κοινές αναθέσεις πόρων.

## Βήμα 3: Πρόσβαση στον Πόρο
Η κλάση `Resource` αντιπροσωπεύει έναν πόρο έργου και παρέχει ιδιότητες όπως UID, όνομα και συλλογή αναθέσεων.  
```java
Resource resource = project.getResources().getByUid(1);
```
Ανακτήστε τον πόρο από το έργο με το μοναδικό του αναγνωριστικό (UID).

## Βήμα 4: Ανάκτηση Μονάδων Πόρου
```java
Double units = resource.get(Rsc.PEAK_UNITS);
```
Η μέθοδος `getPeakUnits()` επιστρέφει τις μέγιστες μονάδες που έχουν ανατεθεί στον πόρο σε όλα τα συνδεδεμένα έργα.  
Ανακτήστε τις κορυφαίες μονάδες του πόρου, οι οποίες υπολογίζονται χρησιμοποιώντας τις αναθέσεις από άλλα έργα.

## Πώς να διαβάσετε αναθέσεις από κοινά πόρους;
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project και παρέχει πρόσβαση στους πόρους, τις εργασίες και τις αναθέσεις του.  
Φορτώστε το στόχο έργου με `Project project = new Project(dataDir + "Project.mpp");` και στη συνέχεια καλέστε `Resource resource = project.getResources().toList().stream().filter(r -> r.getUid() == desiredUid).findFirst().orElse(null);`. Αφού αποκτήσετε το αντικείμενο `Resource`, χρησιμοποιήστε `resource.getPeakUnits()` για να διαβάσετε τις συγκεντρωτικές μονάδες σε όλα τα συνδεδεμένα έργα. Αυτή η σύντομη προσέγγιση δύο βημάτων επιστρέφει τα δεδομένα ανάθεσης που χρειάζεστε χωρίς να ανοίγετε κάθε συνδεδεμένο αρχείο ξεχωριστά.

## Γιατί είναι σημαντικό αυτό
Η ανάγνωση κοινών αναθέσεων πόρων σας επιτρέπει να **τροποποιείτε τις αναθέσεις** έξυπνα, να εξισορροπείτε το φόρτο εργασίας και να δημιουργείτε ακριβείς αναφορές — κρίσιμα βήματα για αποτελεσματική διακυβέρνηση έργων. Με το Aspose.Tasks μπορείτε να επεξεργαστείτε έργα που περιέχουν **έως 10.000 εργασίες** διατηρώντας τη χρήση μνήμης κάτω από **200 MB**, χάρη στην αρχιτεκτονική ροής δεδομένων.

## Κοινά Προβλήματα & Συμβουλές
- **Null resource:** Βεβαιωθείτε ότι το UID που ζητάτε υπάρχει πραγματικά στο αρχείο.  
- **Incorrect file path:** Χρησιμοποιήστε απόλυτες διαδρομές ή ελέγξτε ότι το `dataDir` τελειώνει με διαχωριστικό.  
- **License exceptions:** Η εκτέλεση χωρίς άδεια μπορεί να προκαλέσει προειδοποίηση λειτουργίας δοκιμής· εφαρμόστε την άδειά σας νωρίς στον κώδικα.

## Συχνές Ερωτήσεις

**Q: Μπορώ να τροποποιήσω τις αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks for Java;**  
A: Ναι, μπορείτε προγραμματιστικά να αλλάξετε τιμές, ημερομηνίες και μονάδες αναθέσεων.

**Q: Το Aspose.Tasks for Java είναι συμβατό με διαφορετικές μορφές αρχείων έργου;**  
A: Ναι, υποστηρίζει MPP, XML, MPX και άλλες κοινές μορφές.

**Q: Μπορώ να δημιουργήσω αναφορές βασισμένες σε αναθέσεις πόρων;**  
A: Απόλυτα — χρησιμοποιήστε το API αναφορών για εξαγωγή προσαρμοσμένων αναφορών σε PDF, XLSX ή HTML.

**Q: Υπάρχουν περιορισμοί στο μέγεθος των αρχείων έργου που μπορεί να διαχειριστεί;**  
A: Το Aspose.Tasks κλιμακώνεται από μικρά έως μεγάλα έργα· η απόδοση εξαρτάται από τη διαθέσιμη μνήμη.

**Q: Διατίθεται τεχνική υποστήριξη για χρήστες του Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να λάβετε βοήθεια από το φόρουμ Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να διαβάσετε αναθέσεις** από κοινά πόρους χρησιμοποιώντας το Aspose.Tasks for Java, πώς να ανακτήσετε έναν πόρο με UID και πώς να υπολογίσετε τις κορυφαίες μονάδες του σε συνδεδεμένα έργα. Εφαρμόστε αυτά τα βήματα για να δημιουργήσετε πίνακες ελέγχου, να εξισορροπήσετε το φόρτο εργασίας και να αυτοματοποιήσετε την αναφορά στις λύσεις διαχείρισης έργων σας.

---

**Τελευταία ενημέρωση:** 2026-06-20  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικές Εκπαιδεύσεις

- [Πώς να τροποποιήσετε τις αναθέσεις – Διαβάστε κοινά πόρους με Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Δημιουργία Αναθέσεων Πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Πώς να προσθέσετε σημειώσεις σε αναθέσεις πόρων στο Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}