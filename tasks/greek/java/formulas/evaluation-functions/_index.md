---
date: 2026-10-10
description: Μάθετε πώς να προσθέσετε επεκτατικό χαρακτηριστικό σε Aspose.Tasks, να
  χρησιμοποιήσετε evaluation functions και να δημιουργήσετε αναφορές έργου με αυτή
  τη βιβλιοθήκη διαχείρισης έργων Java.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Υποστήριξη evaluation functions σε τύπους Aspose.Tasks
og_description: Μάθετε πώς να προσθέσετε επεκτατικό χαρακτηριστικό σε Aspose.Tasks,
  να χρησιμοποιήσετε evaluation functions και να δημιουργήσετε αναφορές έργου με αυτή
  τη βιβλιοθήκη διαχείρισης έργων Java.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Πώς να προσθέσετε επεκτατικό χαρακτηριστικό σε τύπους Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Πώς να προσθέσετε επεκτατικό χαρακτηριστικό σε τύπους Aspose.Tasks
url: /el/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε εκτεταμένο χαρακτηριστικό σε τύπους Aspose.Tasks

## Εισαγωγή
Το Aspose.Tasks for Java είναι μια **βιβλιοθήκη διαχείρισης έργων Java** που σας επιτρέπει να δημιουργείτε αναφορές έργου δημιουργώντας ένα αντικείμενο `Project` σε Java και αξιολογώντας τις λειτουργίες του Microsoft Project απευθείας μέσα στον κώδικά σας. Ενσωματώνοντας αυτούς τους τύπους, μπορείτε να εκτελείτε σύνθετους υπολογισμούς, να δημιουργείτε προσαρμοσμένες αναφορές και να αυτοματοποιείτε την ανάλυση του έργου χωρίς να αφήνετε το περιβάλλον ανάπτυξης. Σε αυτό το σεμινάριο θα περάσουμε από τη δημιουργία ενός αντικειμένου έργου, την προσθήκη ενός εκτεταμένου χαρακτηριστικού και τη χρήση λειτουργιών αξιολόγησης για **προσθήκη προσαρμοσμένου πεδίου εργασίας** δεδομένων.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “create project object java”;** Δημιουργεί ένα στιγμιότυπο `Project` στη μνήμη που μπορείτε να χειριστείτε προγραμματιστικά.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (download from the official site).  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια Aspose.Tasks για χρήση σε παραγωγή· διατίθεται δωρεάν δοκιμή.  
- **Μπορώ να χρησιμοποιήσω προσαρμοσμένα πεδία;** Ναι – μπορείτε **προσθήκη εκτεταμένου χαρακτηριστικού** σε εργασίες και να τα αντιμετωπίσετε ως προσαρμοσμένα πεδία.  
- **Είναι συμβατό με όλες τις μορφές αρχείων Project;** Aspose.Tasks υποστηρίζει 3 κύριες μορφές (MPP, MPT, XML) και πάνω από 50 επιπλέον μορφές εισόδου/εξόδου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Environment** – JDK 8+ και ένα IDE όπως IntelliJ IDEA ή Eclipse.  
2. **Aspose.Tasks for Java Library** – Κατεβάστε και συμπεριλάβετε τη βιβλιοθήκη από τη [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Προσθέστε το namespace Aspose.Tasks στην κλάση Java ώστε να μπορείτε να εργάζεστε με έργα, εργασίες και εκτεταμένα χαρακτηριστικά:

```java
import com.aspose.tasks.*;
```

## Δημιουργία αναφοράς έργου – create project object java
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη, εκθέτοντας εργασίες, πόρους και προσαρμοσμένα δεδομένα. Η δημιουργία ενός αντικειμένου αυτής της κλάσης σας παρέχει ένα δοχείο για όλα τα στοιχεία του έργου που θα ορίσετε.

```java
Project project = new Project();
```

Η παραπάνω γραμμή **creates project object java** που ξεκινά κενή και έτοιμη για προσαρμογή.

## Πώς να προσθέσετε εκτεταμένο χαρακτηριστικό
Η κλάση `ExtendedAttributeDefinition` ορίζει ένα προσαρμοσμένο πεδίο που μπορεί να προσαρμοστεί σε εργασίες. Για να προσθέσετε ένα εκτεταμένο χαρακτηριστικό, δημιουργήστε ένα στιγμιότυπο αυτής της κλάσης με τύπο `Number`, ορίστε του ένα ψευδώνυμο όπως “Sine”, προσθέστε το στη συλλογή `ExtendedAttributes` του έργου και, στη συνέχεια, συνδέστε το με κάθε εργασία που απαιτεί το προσαρμοσμένο πεδίο.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Εδώ **add extended attribute** τύπου `Number` με όνομα “Sine” και το συσχετίζουμε με εργασίες.

## Προσθήκη του εκτεταμένου χαρακτηριστικού στο έργο
Καταχωρίστε τον ορισμό του χαρακτηριστικού στο έργο ώστε κάθε εργασία να μπορεί να το αναφέρει.

```java
project.getExtendedAttributes().add(attr);
```

## Δημιουργία νέας εργασίας
`Task` αντιπροσωπεύει ένα στοιχείο εργασίας στο έργο και μπορεί να περιέχει προσαρμοσμένα πεδία.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Προσθήκη προσαρμοσμένου πεδίου εργασίας στο έργο
Συνδέστε το προηγουμένως ορισμένο εκτεταμένο χαρακτηριστικό με τη νεοδημιουργημένη εργασία, δίνοντας στην εργασία ένα προσαρμοσμένο πεδίο “Sine” που μπορείτε να χρησιμοποιήσετε σε τύπους ή υπολογισμούς.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Τώρα η εργασία διαθέτει ένα προσαρμοσμένο πεδίο “Sine” που μπορείτε να χρησιμοποιήσετε σε τύπους ή υπολογισμούς. Αυτός είναι επίσης ο τρόπος με τον οποίο **add custom field task** δεδομένα προγραμματιστικά.

## Γιατί να χρησιμοποιήσετε λειτουργίες αξιολόγησης;
Οι λειτουργίες αξιολόγησης σας επιτρέπουν να ενσωματώσετε εγγενείς τύπους Microsoft Project (π.χ., `Sin([Start])`) απευθείας στο Aspose.Tasks, επιτρέποντας άμεσους υπολογισμούς χωρίς εξωτερική επεξεργασία. Αυτό διατηρεί όλη τη λογική του έργου σε ένα μέρος, μειώνει τα σφάλματα συγχρονισμού δεδομένων και επιταχύνει τη δημιουργία αναφορών. Το Aspose.Tasks υποστηρίζει αξιολόγηση πάνω από 100 λειτουργιών MS Project, παρέχοντας μια ολοκληρωμένη μηχανή υπολογισμών μέσα στη Java.

## Κοινά προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|-------|----------|
| **Formula returns `NaN`** | Επαληθεύστε ότι ο τύπος του προσαρμοσμένου πεδίου ταιριάζει με τον αναμενόμενο αριθμητικό τύπο. |
| **Extended attribute not visible** | Βεβαιωθείτε ότι ο ορισμός του χαρακτηριστικού έχει προστεθεί στο έργο **before** δημιουργίας εργασιών. |
| **License exception** | Εγκαταστήστε μια προσωρινή ή πλήρη **Aspose.Tasks license**· η λειτουργία δοκιμής μπορεί να περιορίζει ορισμένα χαρακτηριστικά. |
| **Missing temporary license** | Αποκτήστε μια **temporary Aspose license** από την ιστοσελίδα Aspose. |

## Συχνές ερωτήσεις

**Q: Μπορεί το Aspose.Tasks for Java να διαχειριστεί σύνθετους τύπους MS Project;**  
A: Ναι, το Aspose.Tasks for Java υποστηρίζει αξιολόγηση ευρείας γκάμας λειτουργιών MS Project, επιτρέποντας σύνθετους υπολογισμούς σε εφαρμογές Java.

**Q: Είναι το Aspose.Tasks for Java συμβατό με διαφορετικές εκδόσεις αρχείων Microsoft Project;**  
A: Ναι, το Aspose.Tasks for Java υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.

**Q: Μπορώ να δοκιμάσω το Aspose.Tasks for Java πριν από την αγορά;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks for Java από την ιστοσελίδα [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks for Java;**  
A: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Υπάρχει διαθέσιμη προσωρινή άδεια για το Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια για δοκιμαστικούς σκοπούς από την ιστοσελίδα Aspose [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα έχετε μάθει πώς να **create project object**, **add extended attribute**, και να αξιοποιήσετε τις λειτουργίες αξιολόγησης για **generate project report** αυτόματα. Μπορείτε τώρα να επεκτείνετε αυτή τη βάση για να δημιουργήσετε πιο πλούσια αναλυτικά στοιχεία έργου, προσαρμοσμένα dashboards ή αυτοματοποιημένα εργαλεία προγραμματισμού—όλα με τη δύναμη του Aspose.Tasks for Java.

---

**Τελευταία ενημέρωση:** 2026-10-10  
**Δοκιμή με:** Aspose.Tasks for Java 24.10  
**Συγγραφέας:** Aspose

## Σχετικά σεμινάρια

- [Προσαρμοσμένες στήλες και εκτεταμένα χαρακτηριστικά στη διαχείριση έργων Java](/tasks/java/project-management/extended-attributes/)
- [Ανάγνωση εκτεταμένων χαρακτηριστικών εργασιών με Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [Πώς να χρησιμοποιήσετε το Aspose.Tasks for Java – Προσθήκη εκτεταμένων χαρακτηριστικών σε αναθέσεις πόρων](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}