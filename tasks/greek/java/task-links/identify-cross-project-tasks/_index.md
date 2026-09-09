---
date: 2026-09-09
description: Μάθετε πώς να αναγνωρίζετε cross project tasks χρησιμοποιώντας το Aspose.Tasks
  για Java. Εξερευνήστε την αδιάκοπη ενσωμάτωση, την αποδοτική διαχείριση και παραδείγματα
  από την πραγματική ζωή.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Αναγνώριση cross project tasks στο Aspose.Tasks
og_description: Αναγνωρίστε cross project tasks στο Aspose.Tasks για Java. Μάθετε
  πώς να ορίσετε τον φάκελο εγγράφων, να ανακτήσετε τα IDs εργασιών και να διαχειριστείτε
  αποτελεσματικά τα συνδεδεμένα έργα.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Αναγνώριση cross project tasks στο Aspose.Tasks – Οδηγός Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Αναγνώριση cross project tasks στο Aspose.Tasks
url: /el/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αναγνώριση εργασιών μεταξύ έργων στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το μάθημα θα μάθετε **πώς να αναγνωρίζετε εργασίες μεταξύ έργων** με το Aspose.Tasks για Java. Είτε διαχειρίζεστε ένα χαρτοφυλάκιο αλληλοεξαρτώμενων χρονοδιαγραμμάτων είτε χρειάζεται να ελέγξετε εξωτερικές εξαρτήσεις, τα παρακάτω βήματα σας δείχνουν πώς να εντοπίσετε εργασίες που αναφέρονται σε άλλα αρχεία έργου, να ανακτήσετε τα αναγνωριστικά τους και να εργαστείτε με αυτές προγραμματιστικά.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “αναγνώριση εργασιών μεταξύ έργων”;** Σημαίνει τον εντοπισμό εργασιών που αναφέρονται ή εξαρτώνται από εργασίες σε άλλο αρχείο έργου.  
- **Ποια μέθοδος εκτυπώνει το ID της εργασίας;** Χρησιμοποιήστε `externalTask.get(Tsk.ID)` για να εκτυπώσετε το ID της εργασίας.  
- **Πώς ορίζω τον φάκελο εγγράφων;** Αναθέστε τη διαδρομή του φακέλου σε μια μεταβλητή τύπου `String` (π.χ., `dataDir`).  
- **Ποια ιδιότητα ανακτά μια εργασία με UID;** Καλέστε `getChildren().getByUid(yourUid)`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks για εμπορικές αναπτύξεις.

## Τι είναι η “αναγνώριση εργασιών μεταξύ έργων”;
Η αναγνώριση εργασιών μεταξύ έργων σας επιτρέπει να εντοπίσετε σχέσεις μεταξύ εργασιών που διασπείρονται σε πολλά αρχεία Microsoft Project. Εντοπίζοντας εργασίες που αναφέρονται ή εξαρτώνται από εξωτερικά χρονοδιαγράμματα, μπορείτε να κατανοήσετε πώς τα στοιχεία εργασίας αλληλεπιδρούν πέρα από τα όρια των έργων, να αποτρέψετε διπλή προσπάθεια και να διατηρήσετε ακριβείς χρονοδιαγράμματα. Αυτή η δυνατότητα είναι ουσιώδης για μεγάλα χαρτοφυλάκια όπου οι εργασίες μοιράζονται ή εξαρτώνται από εξωτερικά χρονοδιαγράμματα.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για Java;
Το Aspose.Tasks για Java υποστηρίζει **50+ μορφές εισόδου και εξόδου** (συμπεριλαμβανομένων των MPP, MPX, XML και CSV) και μπορεί να επεξεργαστεί έργα με **έως 10.000 εργασίες** χωρίς να φορτώσει ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη λειτουργεί σε οποιαδήποτε πλατφόρμα συμβατή με JVM, δεν απαιτεί εγκατάσταση του Microsoft Project και προσφέρει πλήρη πρόσβαση API σε IDs, UIDs, εξωτερικά IDs και μεταδεδομένα σύνδεσης.

## Προαπαιτούμενα
- Ένα λειτουργικό περιβάλλον ανάπτυξης Java (JDK 8 ή νεότερο).  
- Το Aspose.Tasks για Java εγκατεστημένο. Μπορείτε να το κατεβάσετε **[εδώ](https://releases.aspose.com/tasks/java/)**.  
- Ένα έγκυρο αρχείο άδειας Aspose.Tasks εάν σκοπεύετε να εκτελέσετε τον κώδικα σε παραγωγή.

## Εισαγωγή πακέτων
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project, η `Task` αντιπροσωπεύει μια μεμονωμένη εργασία, και η `Tsk` παρέχει σταθερές πεδίων εργασίας.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Βήμα 1: ορισμός φακέλου εγγράφων
Η συμβολοσειρά `dataDir` περιέχει τη διαδρομή προς το φάκελο που περιέχει τα αρχεία `.mpp` σας.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Βήμα 2: φόρτωση εξωτερικού έργου
`Project externalProject` φορτώνει το καθορισμένο εξωτερικό αρχείο έργου για επιθεώρηση.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Βήμα 3: ανάκτηση εξωτερικής εργασίας με uid
`externalProject.getChildren().getByUid(uid)` ανακτά μια εργασία από τη συλλογή εργασιών του εξωτερικού έργου χρησιμοποιώντας το μοναδικό της αναγνωριστικό.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Βήμα 4: εκτύπωση ID εργασίας (κύρια περίπτωση χρήσης)
`externalTask.get(Tsk.ID)` επιστρέφει το εσωτερικό ID που έχει εκχωρήσει το Aspose.Tasks για τη συγκεκριμένη εργασία.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Βήμα 5: εκτύπωση αρχικού (εξωτερικού) ID εργασίας
`externalTask.get(Tsk.ExternalID)` ανακτά το αρχικό ID της εργασίας όπως ορίζεται στο αρχικό αρχείο έργου.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Επαναλάβετε τα παραπάνω βήματα για τυχόν πρόσθετες εργασίες που χρειάζεται να παρακολουθήσετε μεταξύ έργων.

## Συχνά προβλήματα & συμβουλές
- **Σφάλματα διαδρομής** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με το κατάλληλο διαχωριστικό αρχείων (`/` ή `\\`).  
- **UID δεν βρέθηκε** – Επαληθεύστε ότι το UID υπάρχει στο εξωτερικό έργο· χρησιμοποιήστε `externalProject.getRootTask().getChildren().size()` για να εμφανίσετε τα διαθέσιμα UID.  
- **Εξαιρέσεις άδειας** – Μια ελλιπής ή μη έγκυρη άδεια θα προκαλέσει εξαίρεση άδειας κατά την εκτέλεση.  
- **Μεγάλα έργα** – Για έργα μεγαλύτερα από 5.000 εργασίες, σκεφτείτε τη χρήση του `ProjectReader` με τη σημαία `LoadOptions` για ροή δεδομένων και μείωση της κατανάλωσης μνήμης.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;**  
A: Ναι, το Aspose.Tasks υποστηρίζει πολλαπλές γλώσσες, συμπεριλαμβανομένων των Java, .NET και άλλων.

**Q: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks για Java;**  
A: Ανατρέξτε στην τεκμηρίωση **[εδώ](https://reference.aspose.com/tasks/java/)**.

**Q: Υπάρχει δωρεάν δοκιμή για το Aspose.Tasks για Java;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή **[εδώ](https://releases.aspose.com/)**.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks;**  
A: Αποκτήστε μια προσωρινή άδεια **[εδώ](https://purchase.aspose.com/temporary-license/)**.

**Q: Χρειάζεστε βοήθεια ή έχετε συγκεκριμένες ερωτήσεις;**  
A: Επισκεφθείτε το φόρουμ υποστήριξης του Aspose.Tasks **[εδώ](https://forum.aspose.com/c/tasks/15)**.

---

**Τελευταία ενημέρωση:** 2026-09-09  
**Δοκιμασμένο με:** Aspose.Tasks for Java 24.11 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose

## Σχετικές Οδηγίες

- [Δημιουργία εξαρτήσεων εργασιών διαχείρισης έργου στο Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Ορισμός ημερομηνίας έναρξης έργου και διαχείριση γονικών και θυγατρικών εργασιών στο Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Δημιουργία έργου MPP Java – Αλλαγή προόδου εργασίας με Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}