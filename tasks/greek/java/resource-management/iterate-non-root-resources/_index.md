---
date: 2026-08-18
description: Μάθετε πώς να διατρέχετε μη‑ριζικούς πόρους σε αρχεία Microsoft Project
  χρησιμοποιώντας το Aspose.Tasks for Java.
keywords:
- how to iterate resources
- extract resource data
- list project resources
lastmod: 2026-08-18
linktitle: Πώς να διατρέξετε πόρους με το Aspose.Tasks for Java
og_description: Μάθετε πώς να διατρέχετε πόρους σε αρχεία Microsoft Project χρησιμοποιώντας
  το Aspose.Tasks for Java. Αυτός ο οδηγός καλύπτει το φιλτράρισμα μη‑ριζικών πόρων,
  παραδείγματα κώδικα και βέλτιστες πρακτικές.
og_image_alt: Developer guide showing Java code that iterates non‑root resources in
  a Microsoft Project file
og_title: Πώς να διατρέξετε πόρους με το Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to iterate non‑root resources in Microsoft Project files
    using Aspose.Tasks for Java.
  headline: How to iterate resources with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes. The API offers full CRUD (Create, Read, Update, Delete) capabilities
      for MPP, MPT, and XML formats.
    question: Can I use Aspose.Tasks for Java to create new project files?
  - answer: Absolutely. It handles Project 2003‑2019 files, including the latest MPP
      specifications.
    question: Does Aspose.Tasks support all versions of Microsoft Project files?
  - answer: Yes. You can inject the library into Spring beans or use it in any standard
      Java application.
    question: Is Aspose.Tasks compatible with Java frameworks like Spring?
  - answer: Definitely. The API lets you add, modify, or delete custom fields on tasks,
      resources, and assignments.
    question: Can I customize project data fields using Aspose.Tasks?
  - answer: The product includes comprehensive API docs, code samples, and a dedicated
      support forum for quick assistance.
    question: Does Aspose.Tasks provide support and documentation for developers?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java resource handling
- project management API
title: Πώς να διατρέξετε πόρους με το Aspose.Tasks for Java
url: /el/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να επαναλάβετε πόρους με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτόν τον οδηγό θα ανακαλύψετε **πώς να επαναλάβετε πόρους**—συγκεκριμένα μη‑ριζικούς πόρους—σε αρχεία Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Είτε δημιουργείτε έναν πίνακα ελέγχου αναφορών, είτε μεταφέρετε κληρονομικά δεδομένα έργου, είτε δημιουργείτε έναν προσαρμοσμένο προγραμματιστή, η δυνατότητα παράλειψης του ενσωματωμένου placeholder “Project” εξοικονομεί χρόνο και διατηρεί το αποτέλεσμα καθαρό. Το αντικειμενοστραφές API της βιβλιοθήκης κάνει την εργασία απλή, και τα πρότυπα που παρουσιάζονται εδώ λειτουργούν σε οποιοδήποτε περιβάλλον Java 8+.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “non‑root resource”;** Είναι οποιοσδήποτε πόρος εκτός του προεπιλεγμένου “Project” placeholder που βρίσκεται στην κορυφή του δέντρου πόρων.  
- **Γιατί να φιλτράρετε τον ριζικό πόρο;** Η ρίζα δεν έχει δεδομένα χρονοπρογραμματισμού, έτσι η αφαίρεσή της αποτρέπει κενές γραμμές στις αναφορές.  
- **Ποια κλάση του Aspose.Tasks παρέχει τη συλλογή πόρων;** `Project.getResources()`.  
- **Χρειάζομαι άδεια για αυτόν τον κώδικα;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να το χρησιμοποιήσω με Java 17;** Ναι – το Aspose.Tasks υποστηρίζει Java 8 και νεότερες εκδόσεις.

## Τι είναι η επανάληψη πόρων;
Η φράση **πώς να επαναλάβετε πόρους** περιγράφει τα βήματα προγραμματισμού που απαιτούνται για να περάσετε από κάθε αντικείμενο `Resource` σε μια παρουσία `Project` ενώ εφαρμόζετε προσαρμοσμένα φίλτρα όπως `isRoot()`. Αυτό το tutorial σας παρέχει ένα έτοιμο προς χρήση πρότυπο που μπορεί να προσαρμοστεί για αναφορές, μεταφορά δεδομένων ή προσαρμοστική λογική χρονοπρογραμματισμού.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για Java;
Το Aspose.Tasks για Java υποστηρίζει **50+ μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί έργα που περιέχουν **μέχρι 10.000 εργασίες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, χάρη στην αρχιτεκτονική ροής του. Το API παρέχει επίσης ενσωματωμένη επικύρωση, ώστε να λαμβάνετε αξιόπιστα αποτελέσματα σε αρχεία Project 2003‑2019.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι τα παρακάτω είναι εγκατεστημένα:

1. **Java Development Kit (JDK)** – Εγκαταστήστε το τελευταίο JDK από την [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java library** – Κατεβάστε το τελευταίο JAR από τη [download page](https://releases.aspose.com/tasks/java/).  

## Εισαγωγή πακέτων
`Project` αντιπροσωπεύει ένα αρχείο Microsoft Project, `Resource` μοντελοποιεί έναν μεμονωμένο πόρο, και `Rsc` παρέχει σταθερές πεδίων πόρων.  

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Βήμα 1: ρυθμίστε τον φάκελο δεδομένων
Δημιουργήστε μια συμβολοσειρά που δείχνει στο φάκελο που περιέχει τα `.mpp` αρχεία σας. Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή όπου βρίσκονται τα αρχεία του έργου σας.

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: φορτώστε το αρχείο έργου
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που φορτώνεται στη μνήμη. Η δημιουργία μιας στιγμής της διαβάζει τη δομή του αρχείου και προετοιμάζει το API για περαιτέρω ερωτήματα.

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Αυτό δημιουργεί μια παρουσία `Project` φορτώνοντας το **ResourceCosts.mpp** από το φάκελο που καθορίσατε.

## Βήμα 3: επαναλάβετε τους μη‑ριζικούς πόρους
`isRoot()` επιστρέφει true εάν ο πόρος είναι το ενσωματωμένο placeholder του έργου.  

```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Ο βρόχος περνάει από κάθε αντικείμενο `Resource` στο έργο. Ο έλεγχος `isRoot()` παραλείπει τον ενσωματωμένο ριζικό πόρο, και η δήλωση `System.out.println` εκτυπώνει το όνομα κάθε **μη‑ριζικού πόρου**.

## Πώς να επαναλάβετε μη‑ριζικούς πόρους
`getResources()` επιστρέφει τη συλλογή όλων των πόρων στο έργο. Φορτώστε τη πλήρη συλλογή με `prj.getResources()`, φιλτράρετε τη ρίζα χρησιμοποιώντας `isRoot()`, και στη συνέχεια διαβάστε οποιοδήποτε πεδίο χρειάζεστε (π.χ., `Rsc.NAME`, `Rsc.COST`). Αυτό το πρότυπο μπορεί να επεκταθεί σε:

- Άθροιση συνολικού κόστους πόρων.  
- Εξαγωγή ονομάτων και τιμών σε CSV.  
- Εφαρμογή προσαρμοσμένων επιχειρηματικών κανόνων όπως υπολογισμοί υπερωριών.

## Κοινά προβλήματα & συμβουλές
- **Έλεγχοι null** – Ορισμένα προαιρετικά πεδία μπορεί να είναι `null`; πάντα προστατεύετε τις κλήσεις με έλεγχο null για να αποφύγετε `NullPointerException`.  
- **Απόδοση** – Για έργα με χιλιάδες πόρους, χρησιμοποιήστε βρόχο με βάση το δείκτη (`for (int i = 0; i < resources.size(); i++)`) για να μειώσετε τη δημιουργία προσωρινών αντικειμένων.  
- **Άδεια** – Η εκτέλεση χωρίς έγκυρη άδεια προσθέτει υδατογράφημα στα εξαγόμενα αρχεία· ενεργοποιήστε την άδειά σας στην εκκίνηση της εφαρμογής για να το αποφύγετε.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java για να δημιουργήσω νέα αρχεία έργου;**  
A: Ναι. Το API προσφέρει πλήρη δυνατότητα CRUD (Create, Read, Update, Delete) για μορφές MPP, MPT και XML.

**Q: Υποστηρίζει το Aspose.Tasks όλες τις εκδόσεις αρχείων Microsoft Project;**  
A: Απόλυτα. Διαχειρίζεται αρχεία Project 2003‑2019, συμπεριλαμβανομένων των τελευταίων προδιαγραφών MPP.

**Q: Είναι το Aspose.Tasks συμβατό με πλαίσια Java όπως το Spring;**  
A: Ναι. Μπορείτε να ενσωματώσετε τη βιβλιοθήκη σε Spring beans ή να τη χρησιμοποιήσετε σε οποιαδήποτε τυπική εφαρμογή Java.

**Q: Μπορώ να προσαρμόσω τα πεδία δεδομένων του έργου χρησιμοποιώντας το Aspose.Tasks;**  
A: Βεβαίως. Το API σας επιτρέπει να προσθέτετε, να τροποποιείτε ή να διαγράφετε προσαρμοσμένα πεδία σε εργασίες, πόρους και εκχωρήσεις.

**Q: Παρέχει το Aspose.Tasks υποστήριξη και τεκμηρίωση για προγραμματιστές;**  
A: Το προϊόν περιλαμβάνει ολοκληρωμένη τεκμηρίωση API, παραδείγματα κώδικα και ένα αφιερωμένο φόρουμ υποστήριξης για γρήγορη βοήθεια.

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να επαναλάβετε πόρους**—συγκεκριμένα τους μη‑ριζικούς—χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η προσέγγιση σας επιτρέπει να εστιάσετε στα πραγματικά δεδομένα του έργου, να δημιουργήσετε καθαρές αναφορές και να χτίσετε ισχυρές λύσεις διαχείρισης έργων χωρίς το άσκοπο placeholder.

---

**Τελευταία ενημέρωση:** 2026-08-18  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Πώς να δημιουργήσετε πόρους – Διαχείριση πόρων με Aspose.Tasks για Java](/tasks/java/resource-management/)
- [Προσθήκη πόρου στο έργο με Aspose.Tasks για Java](/tasks/java/resource-management/create-resources/)
- [Διαχείριση κόστους πόρων MS Project με Aspose.Tasks για Java](/tasks/java/resource-management/resource-cost/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}