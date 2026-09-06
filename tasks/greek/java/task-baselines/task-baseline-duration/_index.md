---
date: 2026-08-29
description: Μάθετε πώς να ορίσετε το baseline duration και να παρακολουθείτε την
  πρόοδο του έργου χρησιμοποιώντας το Aspose.Tasks for Java. Αυτός ο οδηγός βήμα‑βήμα
  σας βοηθά να διαχειρίζεστε τα task baselines αποδοτικά.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Πώς να ορίσετε το Baseline Duration στο Aspose.Tasks for Java
og_description: Μάθετε πώς να ορίσετε το baseline duration και να παρακολουθείτε την
  πρόοδο του έργου χρησιμοποιώντας το Aspose.Tasks for Java. Ακολουθήστε αυτόν τον
  λεπτομερή οδηγό για να διαχειριστείτε τα task baselines αποδοτικά.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Πώς να ορίσετε το baseline duration για την παρακολούθηση της προόδου του
  έργου
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Πώς να ορίσετε το baseline duration για την παρακολούθηση της προόδου του έργου
url: /el/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε τη διάρκεια της βάσης για την παρακολούθηση της προόδου του έργου

## Εισαγωγή
Η παρακολούθηση της προόδου του έργου ξεκινά με μια ισχυρή βάση. Σε αυτό το σεμινάριο θα ανακαλύψετε **πώς να ορίσετε τη διάρκεια της βάσης** για εργασίες σε αρχεία Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java, και θα κατανοήσετε γιατί η εγκατάσταση μιας βάσης νωρίς σας βοηθά να παρακολουθείτε την απόκλιση του χρονοδιαγράμματος, την απόκλιση κόστους και την υπερκατανομή πόρων καθ' όλη τη διάρκεια του έργου.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “set baseline”;** Καταγράφει την αρχική ημερομηνία έναρξης, λήξης και διάρκεια μιας εργασίας ώστε να μπορείτε να συγκρίνετε μελλοντικές αλλαγές.  
- **Ποια κλάση Aspose.Tasks δημιουργεί ένα έργο;** Η κλάση `Project` – θα μάθετε επίσης πώς να **δημιουργήσετε μια παρουσία έργου** σωστά.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια δωρεάν άδεια αξιολόγησης λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να ανακτήσω ενδιάμεσες βάσεις;** Ναι, το Aspose.Tasks σας επιτρέπει να ερωτήσετε ενδιάμεσες βάσεις και τα σταθερά τους κόστη.  
- **Ποια έκδοση Java απαιτείται;** Συνιστάται η Java 8 ή νεότερη.  
- **Πώς αυτό με βοηθά να παρακολουθώ την πρόοδο του έργου;** Μόλις οριστεί η βάση, μπορείτε άμεσα να συγκρίνετε τις πραγματικές ημερομηνίες με το αρχικό σχέδιο χρησιμοποιώντας ενσωματωμένες λειτουργίες αναφοράς.

## Τι είναι μια βάση εργασίας και γιατί να την ορίσετε;
Μια βάση εργασίας καταγράφει το προγραμματισμένο χρονοδιάγραμμα (ημερομηνία έναρξης, λήξης και διάρκεια) σε ένα συγκεκριμένο χρονικό σημείο. Ορίζοντας μια βάση δημιουργείτε ένα σημείο αναφοράς που καθιστά εύκολο να εντοπίζετε αποκλίσεις χρονοδιαγράμματος, υπερβάσεις κόστους και υπερκατανομή πόρων καθώς το έργο εξελίσσεται.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για διαχείριση βάσεων;
Το Aspose.Tasks παρέχει **πλήρη συμβατότητα .mpp** – μπορείτε να διαβάζετε και να γράφετε εγγενή αρχεία Microsoft Project χωρίς να χρειάζεται εγκατεστημένο το Microsoft Office. Το API σας δίνει προγραμματιστική πρόσβαση σε **πάνω από 50 μορφές εισόδου και εξόδου**, υποστηρίζει **ενδιάμεσες βάσεις 1‑10**, και μπορεί να διαχειριστεί **πολύπλοκα έργα εκατοντάδων σελίδων** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, κάτι που είναι απαραίτητο για υψηλής απόδοσης επεξεργασία παρτίδων.

## Προαπαιτούμενα
1. **Περιβάλλον Ανάπτυξης Java** – εγκατεστημένο και ρυθμισμένο JDK 8+.  
2. **Aspose.Tasks for Java** – κατεβάστε τη βιβλιοθήκη από τη [σελίδα λήψης Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **IDE ή εργαλείο κατασκευής** – Maven, Gradle ή οποιοδήποτε IDE προτιμάτε.

## Εισαγωγή πακέτων
Οι παρακάτω εισαγωγές φέρνουν τις βασικές κλάσεις του Aspose.Tasks που χρειάζονται για εργασία με έργα, εργασίες, βάσεις και δεδομένα χρονικής φάσης.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Βήμα 1: δημιουργία μιας παρουσίας έργου
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη και αποτελεί το σημείο εισόδου για όλες τις λειτουργίες.

```java
Project project = new Project();
```

## Βήμα 2: δημιουργία βάσης εργασίας
Η `TaskBaseline` αποθηκεύει την προγραμματισμένη έναρξη, λήξη και διάρκεια για μια συγκεκριμένη εργασία.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Βήμα 3: εμφάνιση πληροφοριών βάσης εργασίας
Η μέθοδος `getBaselines()` επιστρέφει τη συλλογή των βάσεων που σχετίζονται με μια εργασία.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Βήμα 4: έλεγχος ενδιάμεσης βάσης και σταθερού κόστους
Η `BaselineType` απαριθμεί τις κύριες και ενδιάμεσες βάσεις (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Βήμα 5: εκτύπωση δεδομένων χρονικής φάσης
Η `TimephasedData` αντιπροσωπεύει ένα κομμάτι πληροφοριών χρονοδιαγράμματος για ένα συγκεκριμένο χρονικό διάστημα.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Ακολουθώντας αυτά τα βήματα, μπορείτε να **ορίσετε τη διάρκεια της βάσης** για οποιαδήποτε εργασία και να ανακτήσετε λεπτομερείς πληροφορίες βάσης χρησιμοποιώντας το Aspose.Tasks for Java, παρέχοντάς σας έναν αξιόπιστο τρόπο για **να παρακολουθείτε την πρόοδο του έργου** καθ' όλη τη διάρκεια του κύκλου ζωής του έργου.

## Συνηθισμένα προβλήματα και λύσεις
- **Η βάση δεν εμφανίζεται στο MS Project:** Βεβαιωθείτε ότι κάλεσατε `project.setBaseline(BaselineType.Baseline)` **μετά** την προσθήκη της εργασίας.  
- **NullPointerException στο `getBaselines()`:** Επαληθεύστε ότι η εργασία προστέθηκε στο έργο πριν οριστεί η βάση.  
- **Ασυμφωνία μονάδας χρόνου:** Χρησιμοποιήστε `TimeUnitType` για να μορφοποιήσετε τη διάρκεια σωστά, ειδικά όταν εργάζεστε με προσαρμοσμένα ημερολόγια.

## Συχνές ερωτήσεις
### Τι είναι μια βάση εργασίας στο MS Project;
Μια βάση εργασίας στο MS Project είναι ένα στιγμιότυπο του αρχικού προγραμματισμένου χρονοδιαγράμματος για μια εργασία, συμπεριλαμβανομένης της ημερομηνίας έναρξης, λήξης και διάρκειας.

### Γιατί είναι σημαντική η διαχείριση των βάσεων εργασίας;
Η διαχείριση των βάσεων εργασίας βοηθά στη σύγκριση του προγραμματισμένου χρονοδιαγράμματος με την πραγματική πρόοδο του έργου, διευκολύνοντας καλύτερη παρακολούθηση και λήψη αποφάσεων.

### Μπορώ να τροποποιήσω μια βάση εργασίας αφού οριστεί;
Ναι, μπορείτε να τροποποιήσετε τις βάσεις εργασίας στο MS Project για να αντανακλούν αλλαγές στο σχέδιο του έργου. Ωστόσο, είναι σημαντικό να τεκμηριώσετε τυχόν αποκλίσεις από την αρχική βάση.

### Υποστηρίζει το Aspose.Tasks άλλες λειτουργίες διαχείρισης έργων;
Ναι, το Aspose.Tasks προσφέρει ένα ευρύ φάσμα λειτουργιών για τη διαχείριση έργων, συμπεριλαμβανομένου του προγραμματισμού εργασιών, της κατανομής πόρων και της δημιουργίας διαγραμμάτων Gantt.

### Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;
Μπορείτε να βρείτε υποστήριξη για το Aspose.Tasks στο [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15), όπου μπορείτε να κάνετε ερωτήσεις και να αλληλεπιδράσετε με άλλους χρήστες.

## Επιπλέον συχνές ερωτήσεις
**Ε: Πρέπει να καλέσω `setBaseline` για κάθε εργασία ξεχωριστά;**  
Α: Όχι. Καλώντας `project.setBaseline(BaselineType.Baseline)` καταγράφει τη βάση για όλες τις εργασίες του έργου ταυτόχρονα.  

**Ε: Πώς μπορώ να ορίσω ενδιάμεση βάση για μια συγκεκριμένη εργασία;**  
Α: Χρησιμοποιήστε `project.setBaseline(BaselineType.Baseline1)` (ή Baseline2‑Baseline10) μετά την ενημέρωση του χρονοδιαγράμματος της εργασίας.  

**Ε: Είναι δυνατόν να εξάγω τα δεδομένα της βάσης σε CSV;**  
Α: Ναι. Επανάληψη πάνω από `task.getBaselines()` και εγγραφή των επιθυμητών πεδίων σε αρχείο CSV χρησιμοποιώντας την τυπική Java I/O.  

**Ε: Μπορώ να διαβάσω ένα υπάρχον αρχείο .mpp που ήδη περιέχει βάσεις;**  
Α: Απόλυτα. Φορτώστε το αρχείο με `new Project("myproject.mpp")` και στη συνέχεια προσπελάστε τις βάσεις κάθε εργασίας όπως φαίνεται παραπάνω.  

**Ε: Διαχειρίζεται το Aspose.Tasks αρχεία πολλαπλών έργων;**  
Α: Το Aspose.Tasks λειτουργεί με αρχεία .mpp ενός μόνο έργου. Για σενάρια πολλαπλών έργων, συνδυάστε τα έργα προγραμματιστικά.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Σχετικά Σεμινάρια

- [Δημιουργία λίστας εργασιών Java – Βάση MS Project χρησιμοποιώντας Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Δημιουργία έργου MPP Java – Αλλαγή προόδου εργασίας με Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Βάση διαχείρισης έργου – Προγραμματισμός εργασιών με Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}