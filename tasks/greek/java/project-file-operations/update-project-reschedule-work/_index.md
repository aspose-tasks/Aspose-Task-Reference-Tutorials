---
date: 2026-03-29
description: Μάθετε πώς να επαναπρογραμματίζετε μη ολοκληρωμένη εργασία, να ενημερώνετε
  την εργασία του έργου και να αποθηκεύετε αρχεία MS Project ως XML χρησιμοποιώντας
  το Aspose.Tasks για Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Επαναπρογραμματισμός μη ολοκληρωμένης εργασίας και ενημέρωση αρχείων MS Project
  με το Aspose.Tasks
url: /el/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Επαναπρογραμματισμός Μη Ολοκληρωμένης Εργασίας και Ενημέρωση Αρχείων MS Project με Aspose.Tasks

## Εισαγωγή
Το Microsoft Project είναι ένα ευρέως χρησιμοποιούμενο εργαλείο διαχείρισης έργων που βοηθά τις ομάδες να προγραμματίζουν εργασίες, να κατανεμηούν πόρους και να παρακολουθούν χρονοδιαγράμματα. Το Aspose.Tasks for Java παρέχει στους προγραμματιστές ένα πλούσιο API για να χειρίζονται αρχεία Microsoft Project προγραμματιστικά. Σε αυτό το tutorial, θα μάθετε πώς να **ενημερώσετε την εργασία του έργου**, **επαναπρογραμματίσετε τη μη ολοκληρωμένη εργασία** και **αποθηκεύσετε το αρχείο MS Project** σε μορφή XML χρησιμοποιώντας το Aspose.Tasks for Java.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει το «επαναπρογραμματισμός μη ολοκληρωμένης εργασίας»;** Μετακινεί οποιαδήποτε εναπομείνασα εργασία σε μια ημερομηνία έναρξης μετά από μια επιλεγμένη ημερομηνία, διατηρώντας τα ολοκληρωμένα τμήματα αμετάβλητα.  
- **Ποια μέθοδος σηματοδοτεί την εργασία ως ολοκληρωμένη;** `project.updateProjectWorkAsComplete(date, false)`.  
- **Πώς διατηρώ τις αλλαγές;** Χρησιμοποιήστε `project.save(<path>, SaveFileFormat.Xml)`.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks για εμπορική χρήση.  
- **Ποια έκδοση της Java υποστηρίζεται;** Η Java 8 και μεταγενέστερες υποστηρίζονται πλήρως.

## Τι είναι ο «επαναπρογραμματισμός μη ολοκληρωμένης εργασίας»;
Ο επαναπρογραμματισμός μη ολοκληρωμένης εργασίας προσαρμόζει τις ημερομηνίες έναρξης όλων των εργασιών που δεν έχουν ολοκληρωθεί ακόμη, μετακινώντας τες ώστε να ξεκινήσουν μετά από μια καθορισμένη ημερομηνία αποκοπής. Αυτό είναι χρήσιμο όταν το χρονοδιάγραμμα του έργου μετατοπίζεται λόγω καθυστερήσεων ή αλλαγών στο πεδίο εφαρμογής.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για την ενημέρωση της εργασίας του έργου και τον επαναπρογραμματισμό των εργασιών;
- **Ακριβής έλεγχος:** Ορίστε απευθείας τα ποσοστά ολοκλήρωσης της εργασίας και τις ημερομηνίες.  
- **Δεν απαιτείται UI:** Αυτοματοποιήστε μαζικές ενημερώσεις σε πολλά αρχεία έργου.  
- **Διαπλατφορμικό:** Λειτουργεί σε οποιοδήποτε σύστημα εκτελεί Java.  
- **Διατηρεί την ακεραιότητα των δεδομένων:** Όλες οι εξαρτήσεις, περιορισμοί και πόροι παραμένουν συνεπείς.

## Προαπαιτούμενα
1. Java Development Kit (JDK) εγκατεστημένο στο σύστημά σας.  
2. Βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να τη κατεβάσετε από [here](https://releases.aspose.com/tasks/java/).  
3. Βασική κατανόηση της γλώσσας προγραμματισμού Java.

## Εισαγωγή Πακέτων
First, import the necessary packages in your Java code:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Βήμα 1: Ρύθμιση του Έργου
Initialize a new `Project` object, define tasks, set durations, and establish dependencies. This creates the baseline project that we will later update and reschedule.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Βήμα 2: Ενημέρωση Εργασίας Έργου
Mark work as complete up to a specific date. This step demonstrates the **update project work** operation, which is often the first action before rescheduling.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Βήμα 3: Επαναπρογραμματισμός Μη Ολοκληρωμένης Εργασίας
Now we shift any remaining (uncompleted) work so that it starts after the same cutoff date. This is the core **reschedule uncompleted work** functionality.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Συμπέρασμα
In this tutorial, we covered how to **update project work**, **reschedule uncompleted work**, and **save the MS Project file** as XML using Aspose.Tasks for Java. These capabilities are essential when project timelines need to be adjusted based on actual progress or changing business priorities.

## Συχνές Ερωτήσεις
### Q: Μπορεί το Aspose.Tasks for Java να διαχειριστεί σύνθετες δομές έργου;
A: Ναι, το Aspose.Tasks for Java παρέχει ισχυρά APIs για τη διαχείριση εργασιών, εξαρτήσεων, πόρων και άλλων στοιχείων του έργου αποδοτικά.  
### Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks for Java;
A: Ναι, μπορείτε να λάβετε δωρεάν δοκιμή από [here](https://releases.aspose.com/).  
### Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks for Java;
A: Μπορείτε να επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή ερωτήματα.  
### Q: Μπορώ να αγοράσω προσωρινή άδεια για το Aspose.Tasks for Java;
A: Ναι, προσωρινές άδειες είναι διαθέσιμες για αγορά [here](https://purchase.aspose.com/temporary-license/).  
### Q: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το Aspose.Tasks for Java;
A: Μπορείτε να ανατρέξετε στην τεκμηρίωση [here](https://reference.aspose.com/tasks/java/) για ολοκληρωμένους οδηγούς και αναφορές API.

## Πρόσθετες Συχνές Ερωτήσεις

**Q: Πώς μπορώ να εξασφαλίσω ότι το αποθηκευμένο αρχείο είναι συμβατό με παλαιότερες εκδόσεις του Microsoft Project;**  
A: Αποθηκεύστε το έργο χρησιμοποιώντας `SaveFileFormat.Xml`; το XML υποστηρίζεται ευρέως σε όλες τις εκδόσεις του Project.

**Q: Μπορώ να επαναπρογραμματίσω μόνο ένα υποσύνολο εργασιών αντί για ολόκληρο το έργο;**  
A: Ναι, μπορείτε να επαναλάβετε τις συγκεκριμένες εργασίες και να καλέσετε `task.setStart(date)` μετά τον υπολογισμό της νέας ημερομηνίας έναρξης.

**Q: Τι συμβαίνει με τις κατανομές πόρων όταν επαναπρογραμματίζω τη μη ολοκληρωμένη εργασία;**  
A: Οι αναθέσεις πόρων μετατοπίζονται αυτόματα ώστε να ταιριάζουν με τις νέες ημερομηνίες έναρξης των εργασιών, διατηρώντας τη λογική κατανομής.

**Q: Είναι δυνατόν να αναιρέσω προγραμματιστικά μια λειτουργία επαναπρογραμματισμού;**  
A: Μπορείτε να φορτώσετε ξανά το αρχικό αρχείο έργου (ή ένα αντίγραφο ασφαλείας) για να επαναφέρετε τις αλλαγές.

**Q: Υποστηρίζει το Aspose.Tasks αποθήκευση σε άλλες μορφές όπως .mpp;**  
A: Απόλυτα. Χρησιμοποιήστε `SaveFileFormat.MPP` για αποθήκευση στη φυσική μορφή Microsoft Project.

---

**Τελευταία Ενημέρωση:** 2026-03-29  
**Δοκιμή Με:** Aspose.Tasks for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}