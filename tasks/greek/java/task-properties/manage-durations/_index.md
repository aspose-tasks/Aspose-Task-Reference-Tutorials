---
date: 2026-02-20
description: Εξερευνήστε πώς να προσθέσετε εργασία σε έργο και να διαχειριστείτε τις
  διάρκειες με το Aspose.Tasks για Java. Μάθετε πώς να ορίζετε τη διάρκεια και πώς
  να τη μετατρέπετε εύκολα.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Προσθήκη εργασίας στο έργο και διαχείριση διάρκειων με το Aspose.Tasks
url: /el/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Εργασίας σε Έργο και Διαχείριση Διάρκειας με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο θα μάθετε **πώς να προσθέσετε εργασία σε έργο** και να ελέγξετε τη διάρκεια της χρησιμοποιώντας το Aspose.Tasks για Java. Είτε δημιουργείτε ένα νέο εργαλείο προγραμματισμού έργων είτε επεκτείνετε μια υπάρχουσα λύση, η κατανόηση της διαχείρισης διάρκειας εργασιών είναι απαραίτητη για ακριβή χρονοπρογραμματισμό και αναφορές.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “add task to project”;** Δημιουργεί ένα νέο αντικείμενο εργασίας κάτω από τη ρίζα του έργου ή μια συγκεκριμένη συνοπτική εργασία.  
- **Ποια κλάση αντιπροσωπεύει μια διάρκεια;** `com.aspose.tasks.Duration`.  
- **Πώς να ορίσετε διάρκεια;** Χρησιμοποιήστε `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Μπορώ να μετατρέψω μια διάρκεια σε άλλη μονάδα;** Ναι, καλέστε `duration.convert(TimeUnitType.Hour)` ή οποιαδήποτε άλλη `TimeUnitType`.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται έγκυρη άδεια Aspose.Tasks για εμπορική χρήση.

## Τι είναι το “add task to project”;
Η προσθήκη μιας εργασίας σε ένα έργο σημαίνει τη δημιουργία ενός αντικειμένου `Task` και την προσάρτησή του στην ιεραρχία εργασιών του έργου. Αυτή η ενέργεια είναι το πρώτο βήμα πριν μπορέσετε να ορίσετε εργασία, πόρους ή διάρκεια για αυτήν την εργασία.

## Γιατί να διαχειριζόμαστε τις διάρκειες των εργασιών;
Ακριβείς διάρκειες οδηγούν σε ρεαλιστικά χρονοδιαγράμματα, κατανομή πόρων και ανάλυση κρίσιμης διαδρομής. Με το Aspose.Tasks μπορείτε να ορίσετε, διαβάσετε, μετατρέψετε και προσαρμόσετε διάρκειες προγραμματιστικά, παρέχοντάς σας πλήρη έλεγχο των χρονοδιαγραμμάτων του έργου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

- Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκατεστημένη τη Java στο σύστημά σας. Μπορείτε να το κατεβάσετε [εδώ](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Κατεβάστε και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη [εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Στο έργο Java, εισάγετε τα απαραίτητα πακέτα για εργασία με το Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Βήμα 1: Ρύθμιση του Έργου Σας
```java
// Create a new project
Project project = new Project();
```

## Βήμα 2: Προσθήκη Νέας Εργασίας (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Πώς να ορίσετε διάρκεια
Τώρα που η εργασία υπάρχει, μπορείτε να ορίσετε το μήκος της. Από προεπιλογή, οι διάρκειες εκφράζονται σε ημέρες.

## Βήμα 3: Λήψη και Μετατροπή Διάρκειας Εργασίας
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Πώς να μετατρέψετε διάρκεια
Η μέθοδος `convert` σας επιτρέπει να μετατρέψετε ένα `Duration` από έναν `TimeUnitType` σε έναν άλλο (π.χ., ημέρες → ώρες, εβδομάδες → ημέρες).

## Βήμα 4: Ενημέρωση Διάρκειας Εργασίας σε 1 Εβδομάδα
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Βήμα 5: Μείωση Διάρκειας Εργασίας
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Ακολουθώντας αυτά τα βήματα, έχετε προσθέσει με επιτυχία **μια εργασία σε ένα έργο** και διαχειριστεί τη διάρκεια της χρησιμοποιώντας το Aspose.Tasks για Java.

## Κοινά Πιθανά Σφάλματα & Συμβουλές
- **Πιθανό σφάλμα:** Η παράλειψη μετατροπής της διάρκειας πριν από αριθμητικές πράξεις μπορεί να οδηγήσει σε λανθασμένα αποτελέσματα. Πάντα επαληθεύστε τη μονάδα με `duration.getTimeUnit()`.
- **Συμβουλή:** Χρησιμοποιήστε `project.getDuration(value, TimeUnitType)` για να δημιουργήσετε διάρκειες στη ζητούμενη μονάδα αντί για μετατροπή αργότερα.
- **Πιθανό σφάλμα:** Ορισμός αρνητικής διάρκειας θα προκαλέσει εξαίρεση. Βεβαιωθείτε ότι επικυρώνετε τις τιμές εισόδου.

## Συμπέρασμα
Σε αυτόν τον οδηγό καλύψαμε πώς να **προσθέσετε εργασία σε έργο**, να διαβάσετε την προεπιλεγμένη της διάρκεια, **να ορίσετε διάρκεια**, και **να μετατρέψετε τη διάρκεια** σε διαφορετικές μονάδες χρόνου. Μπορείτε τώρα να ενσωματώσετε αυτές τις τεχνικές σε μεγαλύτερες εφαρμογές χρονοπρογραμματισμού για ακριβή προγραμματισμό έργων.

## Συχνές Ερωτήσεις
### Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις της Java;
Το Aspose.Tasks είναι συμβατό με τη Java 6 και μεταγενέστερες εκδόσεις.

### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για εμπορικά έργα;
Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.Tasks τόσο για προσωπικά όσο και για εμπορικά έργα. Επισκεφθείτε [εδώ](https://purchase.aspose.com/buy) για λεπτομέρειες άδειας.

### Πού μπορώ να βρω πρόσθετη υποστήριξη και πόρους;
Επισκεφθείτε το [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για υποστήριξη κοινότητας και συζητήσεις.

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμαστικούς σκοπούς;
Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/) για δοκιμή και αξιολόγηση.

### Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Tasks;
Ναι, μπορείτε να αποκτήσετε πρόσβαση στη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/) για να εξερευνήσετε το Aspose.Tasks πριν κάνετε αγορά.

## Συχνές Ερωτήσεις

**Q: Πώς μπορώ να αλλάξω τη διάρκεια μιας εργασίας μετά τον ορισμό της;**  
A: Ανακτήστε την τρέχουσα διάρκεια με `task.get(Tsk.DURATION)`, τροποποιήστε την (π.χ., `add`, `subtract`, ή `convert`), και στη συνέχεια ορίστε την ξανά χρησιμοποιώντας `task.set(Tsk.DURATION, newDuration)`.

**Q: Μπορώ να ορίσω διάρκεια σε λεπτά;**  
A: Ναι, χρησιμοποιήστε `TimeUnitType.Minute` όταν καλείτε `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Η αλλαγή της διάρκειας ενημερώνει αυτόματα τις ημερομηνίες έναρξης και λήξης της εργασίας;**  
A: Μόνο εάν η λειτουργία χρονοπρογραμματισμού του έργου είναι ορισμένη σε αυτόματη. Διαφορετικά, ίσως χρειαστεί να επαναϋπολογίσετε το χρονοδιάγραμμα με `project.calculateCriticalPath()`.

**Q: Μπορεί να ληφθεί η διάρκεια ως ακατέργαστος αριθμός;**  
A: Καλέστε `duration.getTimeSpan()` για να λάβετε την αριθμητική τιμή στη τρέχουσα μονάδα χρόνου.

**Q: Τι συμβαίνει αν αφαιρέσω περισσότερο από την τρέχουσα διάρκεια;**  
A: Το API θα ρίξει ένα `ArgumentOutOfRangeException`. Πάντα επικυρώστε ότι η προκύπτουσα διάρκεια παραμένει θετική.

---

**Τελευταία Ενημέρωση:** 2026-02-20  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java (latest)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}