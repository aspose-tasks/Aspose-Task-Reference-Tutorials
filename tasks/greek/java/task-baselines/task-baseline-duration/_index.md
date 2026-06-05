---
date: 2026-01-23
description: Μάθετε πώς να ορίζετε τη διάρκεια της βάσης και να δημιουργείτε ένα αντίτυπο
  έργου χρησιμοποιώντας το Aspose.Tasks για Java. Αυτός ο οδηγός βήμα‑προς‑βήμα σας
  βοηθά να διαχειρίζεστε τις βάσεις εργασιών αποδοτικά.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Πώς να ορίσετε τη διάρκεια βάσης στο Aspose.Tasks για Java
url: /el/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε τη διάρκεια baseline στο Aspose.Tasks για Java

## Εισαγωγή
Η δημιουργία ενός baseline είναι ένα θεμελιώδες βήμα για την παρακολούθηση της προόδου του έργου σε σχέση με το αρχικό σχέδιο. Σε αυτό το tutorial θα μάθετε **πώς να ορίσετε baseline** διάρκειας για εργασίες στο Microsoft Project χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java, και θα δείτε γιατί η εγκατάσταση ενός baseline νωρίς μπορεί να σας εξοικονομήσει χρόνο και προβλήματα αργότερα.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “set baseline”;** Καταγράφει την αρχική ημερομηνία έναρξης, λήξης και διάρκεια μιας εργασίας ώστε να μπορείτε να συγκρίνετε μελλοντικές αλλαγές.  
- **Ποια κλάση Aspose.Tasks δημιουργεί ένα έργο;** Η κλάση `Project` – θα μάθετε επίσης πώς να **create project instance** σωστά.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια δωρεάν άδεια αξιολόγησης λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να ανακτήσω ενδιάμεσα baselines;** Ναι, το Aspose.Tasks σας επιτρέπει να ερωτήσετε ενδιάμεσα baselines και τα σταθερά κόστη τους.  
- **Ποια έκδοση Java απαιτείται;** Συνιστάται Java 8 ή νεότερη.

## Τι είναι ένα baseline εργασίας και γιατί να το ορίσετε;
Ένα baseline εργασίας καταγράφει το προγραμματισμένο χρονοδιάγραμμα (ημερομηνία έναρξης, λήξης και διάρκεια) σε μια συγκεκριμένη χρονική στιγμή. Ορίζοντας ένα baseline δημιουργείτε ένα σημείο αναφοράς που κάνει εύκολο να εντοπιστούν αποκλίσεις χρονοδιαγράμματος, υπερβάσεις κόστους και υπερβολική κατανομή πόρων καθώς το έργο εξελίσσεται.

## Γιατί να χρησιμοποιήσετε Aspose.Tasks για τη διαχείριση baselines;
- **Πλήρης συμβατότητα .mpp** – ανάγνωση και εγγραφή εγγενών αρχείων Microsoft Project χωρίς εγκατεστημένο Office.  
- **Πλούσιο API** – πρόσβαση σε δεδομένα baseline, ενδιάμεσα baselines και πληροφορίες time‑phased προγραμματιστικά.  
- **Διασυστημικό** – λειτουργεί σε Windows, Linux και macOS με οποιοδήποτε τυπικό JDK.

## Προαπαιτούμενα
1. **Περιβάλλον Ανάπτυξης Java** – εγκατεστημένο και ρυθμισμένο JDK 8+.  
2. **Aspose.Tasks for Java** – κατεβάστε τη βιβλιοθήκη από [here](https://releases.aspose.com/tasks/java/).  
3. **IDE ή εργαλείο κατασκευής** – Maven, Gradle ή οποιοδήποτε IDE προτιμάτε.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαραίτητες κλάσεις στο έργο Java σας:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Βήμα 1: Δημιουργία Project Instance
Η δημιουργία ενός project instance είναι το θεμέλιο για οποιαδήποτε περαιτέρω επεξεργασία. Αυτό το βήμα δείχνει πώς να **create project instance** χρησιμοποιώντας το Aspose.Tasks:

```java
Project project = new Project();
```

## Βήμα 2: Δημιουργία Baseline Εργασίας
Προσθέστε μια νέα εργασία στη ρίζα του έργου και ορίστε το baseline της. Αυτό καταγράφει το αρχικό χρονοδιάγραμμα για την εργασία:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Βήμα 3: Εμφάνιση Πληροφοριών Baseline Εργασίας
Ανακτήστε το baseline που μόλις δημιουργήσατε και εκτυπώστε τις κύριες ιδιότητές του. Αυτό σας βοηθά να επαληθεύσετε ότι το baseline ορίστηκε σωστά:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Βήμα 4: Έλεγχος Ενδιάμεσου Baseline και Σταθερού Κόστους
Αν εργάζεστε με ενδιάμεσα baselines, μπορείτε να ερωτήσετε αν το τρέχον baseline είναι ενδιάμεσο και τυχόν συνδεδεμένο σταθερό κόστος:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Βήμα 5: Εκτύπωση Δεδομένων Timephased
Τα δεδομένα time‑phased δείχνουν πώς το baseline κατανέμεται στο χρόνο. Επανάληψη μέσω της συλλογής για να εξετάσετε κάθε καταχώρηση:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Ακολουθώντας αυτά τα βήματα, μπορείτε **how to set baseline** διάρκεια για οποιαδήποτε εργασία και να ανακτήσετε λεπτομερείς πληροφορίες baseline χρησιμοποιώντας το Aspose.Tasks για Java.

## Συχνά Προβλήματα και Λύσεις
- **Baseline δεν εμφανίζεται στο MS Project:** Βεβαιωθείτε ότι κάλεσατε `project.setBaseline(BaselineType.Baseline)` **μετά** την προσθήκη της εργασίας.  
- **NullPointerException στο `getBaselines()`:** Επαληθεύστε ότι η εργασία προστέθηκε στο έργο πριν οριστεί το baseline.  
- **Ασυμφωνία μονάδας χρόνου:** Χρησιμοποιήστε `TimeUnitType` για να μορφοποιήσετε τη διάρκεια σωστά, ειδικά όταν εργάζεστε με προσαρμοσμένα ημερολόγια.

## Συχνές Ερωτήσεις
### Τι είναι ένα baseline εργασίας στο MS Project;
Ένα baseline εργασίας στο MS Project είναι μια λήψη στιγμιότυπου του αρχικού προγραμματισμένου χρονοδιαγράμματος για μια εργασία, συμπεριλαμβανομένων της ημερομηνίας έναρξης, λήξης και διάρκειας.

### Γιατί είναι σημαντική η διαχείριση των baselines εργασίας;
Η διαχείριση των baselines εργασίας βοηθά στη σύγκριση του προγραμματισμένου χρονοδιαγράμματος με την πραγματική πρόοδο του έργου, διευκολύνοντας την καλύτερη παρακολούθηση και λήψη αποφάσεων.

### Μπορώ να τροποποιήσω ένα baseline εργασίας αφού το ορίσω;
Ναι, μπορείτε να τροποποιήσετε τα baselines εργασίας στο MS Project για να αντανακλούν αλλαγές στο σχέδιο του έργου. Ωστόσο, είναι σημαντικό να τεκμηριώσετε τυχόν αποκλίσεις από το αρχικό baseline.

### Υποστηρίζει το Aspose.Tasks άλλες λειτουργίες διαχείρισης έργου;
Ναι, το Aspose.Tasks προσφέρει μια ευρεία γκάμα λειτουργιών για τη διαχείριση έργων, συμπεριλαμβανομένου του προγραμματισμού εργασιών, της κατανομής πόρων και της δημιουργίας διαγραμμάτων Gantt.

### Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;
Μπορείτε να βρείτε υποστήριξη για το Aspose.Tasks στο [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), όπου μπορείτε να κάνετε ερωτήσεις και να αλληλεπιδράσετε με άλλους χρήστες.

## Επιπλέον Συχνές Ερωτήσεις
**Ε: Πρέπει να καλέσω `setBaseline` για κάθε εργασία ξεχωριστά;**  
Α: Όχι. Καλώντας `project.setBaseline(BaselineType.Baseline)` καταγράφει το baseline για όλες τις εργασίες του έργου ταυτόχρονα.

**Ε: Πώς μπορώ να ορίσω ενδιάμεσο baseline για συγκεκριμένη εργασία;**  
Α: Χρησιμοποιήστε `project.setBaseline(BaselineType.Baseline1)` (ή Baseline2‑Baseline10) μετά την ενημέρωση του χρονοδιαγράμματος της εργασίας.

**Ε: Είναι δυνατόν να εξάγω τα δεδομένα baseline σε CSV;**  
Α: Ναι. Επανάληψη μέσω `task.getBaselines()` και εγγραφή των επιθυμητών πεδίων σε αρχείο CSV χρησιμοποιώντας το τυπικό Java I/O.

**Ε: Μπορώ να διαβάσω υπάρχον αρχείο .mpp που ήδη περιέχει baselines;**  
Α: Απόλυτα. Φορτώστε το αρχείο με `new Project("myproject.mpp")` και στη συνέχεια προσπελάστε τα baselines κάθε εργασίας όπως φαίνεται παραπάνω.

**Ε: Διαχειρίζεται το Aspose.Tasks αρχεία multi‑project;**  
Α: Το Aspose.Tasks λειτουργεί με αρχεία .mpp ενός μόνο έργου. Για σενάρια multi‑project, συνδυάστε τα έργα προγραμματιστικά.

---

**Τελευταία ενημέρωση:** 2026-01-23  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}