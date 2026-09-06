---
date: 2026-08-29
description: Μάθετε πώς να διαβάζετε δεδομένα γραμμής βάσης και να προγραμματίζετε
  εργασίες χρησιμοποιώντας το Aspose.Tasks για Java, ώστε να μπορείτε να συγκρίνετε
  αποτελεσματικά την προγραμματισμένη με την πραγματική πρόοδο.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Προγραμματισμός εργασιών γραμμής βάσης στο Aspose.Tasks
og_description: Μάθετε πώς να διαβάζετε δεδομένα γραμμής βάσης και να προγραμματίζετε
  εργασίες χρησιμοποιώντας το Aspose.Tasks για Java, επιτρέποντας ακριβή σύγκριση
  της προγραμματισμένης με την πραγματική πρόοδο.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Πώς να διαβάσετε τη γραμμή βάσης και να προγραμματίσετε εργασίες με το Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Πώς να διαβάσετε τη γραμμή βάσης και να προγραμματίσετε εργασίες με το Aspose.Tasks
url: /el/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε τη βάση αναφοράς και να προγραμματίσετε εργασίες με Aspose.Tasks

Σε αυτόν τον οδηγό θα ανακαλύψετε **πώς να διαβάσετε τη βάση αναφοράς** πληροφορίες και να προγραμματίσετε εργασίες προγραμματιστικά χρησιμοποιώντας το Aspose.Tasks για Java. Στο τέλος του σεμιναρίου, θα μπορείτε να καταγράψετε το αρχικό σχέδιο του έργου, να το συγκρίνετε με την πραγματική πρόοδο και να δημιουργήσετε αναφορές διακύμανσης — όλα χωρίς να χρειάζεται εγκατεστημένο το Microsoft Project.

## Εισαγωγή στη βάση αναφοράς διαχείρισης έργου
Η διαχείριση μιας **βάσης αναφοράς διαχείρισης έργου** είναι θεμέλιος λίθος της αποτελεσματικής διαχείρισης έργων. Σας επιτρέπει να καταγράψετε το αρχικό σχέδιο και αργότερα να συγκρίνετε **προγραμματισμένη vs πραγματική πρόοδο** ώστε να εντοπίζετε τις αποκλίσεις νωρίς. Σε αυτόν τον οδηγό, θα περάσουμε από το πώς να προγραμματίζετε βάσεις εργασιών χρησιμοποιώντας το Aspose.Tasks για Java, παρέχοντάς σας τα εργαλεία για **διαχείριση βάσεων έργου** με σιγουριά και να διατηρείτε τα έργα σας σε σωστή πορεία.

## Γρήγορες απαντήσεις
- **Τι αντιπροσωπεύει μια βάση αναφοράς διαχείρισης έργου;**  
  Καταγράφει το εγκεκριμένο χρονοδιάγραμμα, το κόστος και το πεδίο εφαρμογής στην έναρξη του έργου, παρέχοντας ένα σημείο αναφοράς για ανάλυση διακυμάνσεων.  
- **Ποια βιβλιοθήκη διαχειρίζεται τον προγραμματισμό βάσεων αναφοράς σε Java;**  
  Το Aspose.Tasks for Java προσφέρει ένα καθαρό‑Java API που υποστηρίζει 45+ μορφές εισόδου και εξόδου και έργα έως 100 000 εργασίες.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;**  
  Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Ποιες είναι οι κύριες προαπαιτήσεις;**  
  Java Development Kit (JDK) 11+ και η βιβλιοθήκη Aspose.Tasks for Java.  
- **Μπορώ να δω τις ημερομηνίες βάσης αναφοράς μετά τον ορισμό τους;**  
  Ναι—χρησιμοποιήστε το αντικείμενο `TaskBaseline` για να διαβάσετε τις τιμές έναρξης, λήξης και διάρκειας.

## Τι είναι μια βάση αναφοράς διαχείρισης έργου;
Μια βάση αναφοράς διαχείρισης έργου καταγράφει το εγκεκριμένο χρονοδιάγραμμα, τον προϋπολογισμό και το πεδίο εφαρμογής στην έναρξη της εκτέλεσης. Λειτουργεί ως σημείο αναφοράς για τη μέτρηση της απόδοσης και την ταυτοποίηση αποκλίσεων καθ' όλη τη διάρκεια του κύκλου ζωής του έργου. Περιλαμβάνει τις προγραμματισμένες ημερομηνίες έναρξης και λήξης, το συνολικό κόστος και τις λεπτομέρειες του πεδίου, παρέχοντας μια ολοκληρωμένη εικόνα για μελλοντική σύγκριση.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για προγραμματισμό βάσεων αναφοράς;
Το Aspose.Tasks παρέχει ένα καθαρό‑Java API που λειτουργεί χωρίς εγκατεστημένο το Microsoft Project. Υποστηρίζει **45+ μορφές εισόδου και εξόδου**, μπορεί να επεξεργαστεί έργα με **έως 100 000 εργασίες** σε λειτουργία αποδοτικής μνήμης, και προσφέρει ενσωματωμένες μεθόδους για ανάγνωση και εγγραφή δεδομένων βάσης αναφοράς — καθιστώντας την αυτοματοποιημένη αναφορά και ενσωμάτωση απλή.

## Προαπαιτήσεις
- **Java Development Kit (JDK)** – εγκαταστήστε το JDK 11 ή νεότερο. Μπορείτε να το κατεβάσετε από την [ιστοσελίδα](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – κατεβάστε την πιο πρόσφατη έκδοση από τη [σελίδα λήψης](https://releases.aspose.com/tasks/java/) και προσθέστε το JAR στο classpath του έργου σας.

## Εισαγωγή πακέτων
Οι κλάσεις `Project`, `Task` και `TaskBaseline` βρίσκονται στον χώρο ονομάτων `com.aspose.tasks`. Εισάγετέ τις στην αρχή του αρχείου πηγαίου κώδικα:

Η κλάση `Project` είναι το κορυφαίο αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα μόνο αρχείο έργου στη μνήμη. Παρέχει πρόσβαση σε εργασίες, πόρους και συλλογές βάσεων αναφοράς.

## Πώς να διαβάσετε τη βάση αναφοράς;
Φορτώστε το έργο, στη συνέχεια ερωτήστε τη συλλογή `TaskBaseline` για κάθε εργασία. Το αντικείμενο `TaskBaseline` επιστρέφει την έναρξη, λήξη και διάρκεια της βάσης αναφοράς που καταγράφηκαν όταν καλέσατε `setBaseline`. Αυτή η άμεση προσέγγιση σας επιτρέπει να διαβάσετε τις τιμές της βάσης αναφοράς χωρίς να αναλύετε αρχεία XML ή δυαδικά.

## Βήμα 1: δημιουργία νέου αντικειμένου έργου
Η κλάση `Project` αντιπροσωπεύει ολόκληρο το αρχείο έργου στη μνήμη.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Βήμα 2: ορισμός εργασίας και ορισμός βάσης αναφοράς
`Task` αντιπροσωπεύει ένα μεμονωμένο αντικείμενο εργασίας, και το `setBaseline` καταγράφει το τρέχον χρονοδιάγραμμα της ως βάση αναφοράς.
```java
Project project = new Project();
```

## Βήμα 3: πρόσβαση σε πληροφορίες βάσης αναφοράς
`TaskBaseline` περιέχει τις αποθηκευμένες τιμές έναρξης, λήξης και διάρκειας για μια βάση αναφοράς.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Βήμα 4: εμφάνιση διάρκειας βάσης αναφοράς
`Duration` αντιπροσωπεύει τη διάρκεια χρόνου για μια εργασία ή μια βάση αναφοράς.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Βήμα 5: εμφάνιση ημερομηνίας έναρξης βάσης αναφοράς
`Start` είναι η προγραμματισμένη ημερομηνία έναρξης της βάσης αναφοράς.
```java
System.out.println(baseline.getDuration().toString());
```

## Βήμα 6: εμφάνιση ημερομηνίας λήξης βάσης αναφοράς
`Finish` είναι η προγραμματισμένη ημερομηνία ολοκλήρωσης της βάσης αναφοράς.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Συνηθισμένα προβλήματα και λύσεις
- **Η βάση αναφοράς δεν έχει οριστεί:** Βεβαιωθείτε ότι καλείτε το `project.setBaseline(BaselineType.Baseline)` **μετά** την προσθήκη εργασιών· διαφορετικά η συλλογή βάσεων θα είναι κενή.  
- **Τιμές Null:** Εάν το `task.getBaselines()` επιστρέφει κενή λίστα, ελέγξτε ότι η εργασία προστέθηκε στην ιεραρχία του έργου πριν οριστεί η βάση αναφοράς.  
- **Μορφή ημερομηνίας:** Οι μέθοδοι `getStart()` και `getFinish()` επιστρέφουν αντικείμενα `java.util.Date`. Χρησιμοποιήστε `SimpleDateFormat` εάν χρειάζεστε προσαρμοσμένη μορφή εμφάνισης.

## Συχνές ερωτήσεις

**Ε: Πώς δημιουργώ ένα νέο αντικείμενο έργου στο Aspose.Tasks;**  
Α: Δημιουργήστε ένα στιγμιότυπο της κλάσης `Project` (`Project project = new Project();`). Αυτό δημιουργεί ένα νέο αρχείο έργου έτοιμο για εργασίες και βάσεις αναφοράς.

**Ε: Ποια είναι η διαφορά μεταξύ `BaselineType.Baseline` και άλλων τύπων βάσης;**  
Α: Το `BaselineType.Baseline` αναφέρεται στην κύρια βάση (Baseline 1). Το Aspose.Tasks υποστηρίζει επίσης Baseline 2‑10 για πρόσθετα στιγμιότυπα.

**Ε: Μπορώ να εξάγω τα δεδομένα της βάσης αναφοράς σε Excel ή CSV;**  
Α: Ναι, μπορείτε να επαναλάβετε τα αντικείμενα `TaskBaseline` και να γράψετε τις τιμές σε αρχείο CSV χρησιμοποιώντας το τυπικό Java I/O.

**Ε: Η ρύθμιση μιας βάσης αναφοράς επηρεάζει τις υπάρχουσες ημερομηνίες εργασίας;**  
Α: Η ρύθμιση μιας βάσης καταγράφει τις τρέχουσες ημερομηνίες αλλά δεν τροποποιεί το ενεργό χρονοδιάγραμμα της εργασίας. Μπορείτε ακόμη να προσαρμόσετε τις ημερομηνίες έναρξης/λήξης μετά τον ορισμό της βάσης.

**Ε: Είναι δυνατόν να συγκρίνετε πολλαπλές βάσεις προγραμματιστικά;**  
Α: Απόλυτα. Ανακτήστε κάθε βάση μέσω `task.getBaselines().get(index)` και συγκρίνετε τις ιδιότητες `Start`, `Finish` και `Duration`.

---

**Τελευταία ενημέρωση:** 2026-08-29  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Σχετικά Σεμινάρια

- [Δημιουργία λίστας εργασιών Java – Βάση MS Project χρησιμοποιώντας Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Πώς να ορίσετε τη διάρκεια βάσης στο Aspose.Tasks για Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Δημιουργία έργου MPP Java – Αλλαγή προόδου εργασίας με Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}