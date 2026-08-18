---
date: 2026-02-23
description: Εξερευνήστε το Aspose.Tasks για Java για να απλοποιήσετε τη διαχείριση
  έργων Java και μάθετε πώς να υπολογίζετε το ποσοστό ολοκλήρωσης των εργασιών και
  να παρακολουθείτε την πρόοδο αποδοτικά.
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Διαχείριση Έργου Java: Ποσοστό % Ολοκλήρωσης Εργασίας με το Aspose.Tasks'
url: /el/java/task-properties/percentage-complete-calculations/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαχείριση Έργων Java: Υπολογισμός Ποσοστού Ολοκλήρωσης Εργασίας με το Aspose.Tasks

## Introduction
Καλώς ήρθατε στον ολοκληρωμένο μας οδηγό για **project management java** χρησιμοποιώντας το Aspose.Tasks for Java. Σε αυτό το σεμινάριο θα μάθετε πώς να διαβάζετε ένα αρχείο Microsoft Project, να υπολογίζετε την ολοκληρωμένη εργασία και να λαμβάνετε ακριβή ποσοστά προόδου για κάθε εργασία. Η κατανόηση αυτών των υπολογισμών σας βοηθά να κρατάτε ενημερωμένους τους ενδιαφερόμενους και εξασφαλίζει ότι το έργο σας παραμένει εντός χρονοδιαγράμματος.

## Quick Answers
- **Ποια βιβλιοθήκη διαχειρίζεται αρχεία Microsoft Project σε Java?** Aspose.Tasks for Java.  
- **Ποια ιδιότητα δείχνει τη συνολική πρόοδο;** `Tsk.PERCENT_COMPLETE`.  
- **Πώς διαβάζω ένα αρχείο .mpp;** Load it with `new Project(filePath)`.  
- **Μπορώ να υπολογίσω την ολοκληρωμένη εργασία;** Yes, use `Tsk.PERCENT_WORK_COMPLETE`.  
- **Χρειάζομαι άδεια για παραγωγή;** A valid Aspose.Tasks license is required.

## What is Project Management Java?
Η διαχείριση έργων java αναφέρεται στη χρήση εργαλείων και βιβλιοθηκών βασισμένων σε Java—όπως το Aspose.Tasks—για τη δημιουργία, ανάγνωση και διαχείριση προγραμματισμών έργων προγραμματιστικά. Αυτή η προσέγγιση επιτρέπει αυτοματοποιημένες αναφορές, προσαρμοσμένα ταμπλό και απρόσκοπτη ενσωμάτωση με υπάρχουσες εφαρμογές Java.

## Why Use Aspose.Tasks for Calculating Task Percentage?
- **Accurate progress tracking** – retrieve native Project fields without manual parsing.  
  → Ακριβής παρακολούθηση προόδου – ανάκτηση εγγενών πεδίων Project χωρίς χειροκίνητη ανάλυση.  
- **Full .mpp support** – read, edit, and save Microsoft Project files directly.  
  → Πλήρης υποστήριξη .mpp – ανάγνωση, επεξεργασία και αποθήκευση αρχείων Microsoft Project απευθείας.  
- **Scalable automation** – process thousands of tasks in seconds, ideal for large portfolios.  
  → Κλιμακώσιμη αυτοματοποίηση – επεξεργασία χιλιάδων εργασιών σε δευτερόλεπτα, ιδανική για μεγάλα χαρτοφυλάκια.  
- **Cross‑platform** – works on any Java runtime, from desktop to cloud services.  
  → Διαπλατφορμική – λειτουργεί σε οποιοδήποτε περιβάλλον εκτέλεσης Java, από επιτραπέζιους υπολογιστές έως υπηρεσίες cloud.

## Prerequisites
Προαπαιτούμενα
Before you begin, make sure you have:

- **Java Development Kit (JDK)** εγκατεστημένο (Java 8 ή νεότερο).  
- **Aspose.Tasks for Java** βιβλιοθήκη – κατεβάστε την από [this link](https://releases.aspose.com/tasks/java/).  
- Ένα δείγμα αρχείου Microsoft Project (π.χ., *Software Development.mpp*) τοποθετημένο σε γνωστό φάκελο.

## Import Packages
Εισαγωγή Πακέτων
First, import the classes you’ll need. This snippet should be added to any Java class that works with Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```

### Step 1: Set the Document Directory
Βήμα 1: Ορισμός του Καταλόγου Εγγράφου
Define the folder that contains your *.mpp* file. Replace the placeholder with the actual path on your machine.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Load the Project File
Βήμα 2: Φόρτωση του Αρχείου Project
Create a `Project` instance and load the Microsoft Project file. This step **reads the Microsoft Project file** so you can access its tasks.

```java
Project project = new Project(dataDir + "Software Development.mpp");
```

### Step 3: Retrieve the Task Collection
Βήμα 3: Ανάκτηση της Συλλογής Εργασιών
Grab the root task and then its child tasks. This collection represents all top‑level tasks in the project.

```java
TaskCollection alTasks = project.getRootTask().getChildren();
```

### Step 4: Print Percentage Complete Values
Βήμα 4: Εκτύπωση Τιμών Ποσοστού Ολοκλήρωσης
Iterate through each task and display three key progress metrics:

- **Percentage Complete** – overall task progress.  
  → **Percentage Complete** – συνολική πρόοδος εργασίας.  
- **Percentage Work Complete** – work‑based progress.  
  → **Percentage Work Complete** – πρόοδος βάσει εργασίας.  
- **Physical Percentage Complete** – physical progress (if set).  
  → **Physical Percentage Complete** – φυσική πρόοδος (αν έχει οριστεί).

```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```

Run this loop for every task you need to monitor. The output gives you a clear snapshot of **how to get progress** for each work item.

## Common Use Cases
Κοινές Περιπτώσεις Χρήσης
- **Dashboard reporting:** Ανάκτηση ποσοστών και ενσωμάτωσή τους σε εργαλεία BI.  
- **Automated alerts:** Ενεργοποίηση ειδοποιήσεων όταν το `PERCENT_COMPLETE` μιας εργασίας πέσει κάτω από ένα όριο.  
- **Resource leveling:** Προσαρμογή αναθέσεων βάσει του `PERCENT_WORK_COMPLETE` για να διατηρηθεί το χρονοδιάγραμμα ρεαλιστικό.

## Troubleshooting & Tips
Αντιμετώπιση Προβλημάτων & Συμβουλές
- **Null values:** Βεβαιωθείτε ότι το αρχείο project περιέχει πραγματικά τα πεδία που ερωτάτε· ορισμένα παλαιότερα αρχεία .mpp μπορεί να μην έχουν το `PHYSICAL_PERCENT_COMPLETE`.  
- **Performance:** Για πολύ μεγάλα έργα, εξετάστε τη σελιδοποίηση μέσω `TaskCollection` ή το φιλτράρισμα ανά ID εργασίας για μείωση της χρήσης μνήμης.  
- **License errors:** Εάν βλέπετε προειδοποιήσεις άδειας, επαληθεύστε ότι ένα έγκυρο αρχείο άδειας Aspose.Tasks έχει φορτωθεί πριν δημιουργήσετε το αντικείμενο `Project`.

## Frequently Asked Questions
Συχνές Ερωτήσεις

**Q: Πού μπορώ να βρω την τεκμηρίωση του Aspose.Tasks;**  
A: The documentation is available [here](https://reference.aspose.com/tasks/java/).

**Q: Πώς μπορώ να κατεβάσω τη βιβλιοθήκη Aspose.Tasks για Java;**  
A: You can download it [here](https://releases.aspose.com/tasks/java/).

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
A: Yes, you can access a free trial [here](https://releases.aspose.com/).

**Q: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks;**  
A: Visit the support forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια;**  
A: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Additional Q&A**

**Q: Μπορώ να υπολογίσω το ποσοστό εργασίας χωρίς το Aspose.Tasks;**  
A: You could parse the .mpp binary yourself, but Aspose.Tasks provides a reliable, fully‑supported API that handles all edge cases.

**Q: Το Aspose.Tasks υποστηρίζει την ανάγνωση αρχείων Project Online;**  
A: Yes, you can load files exported from Project Online as long as they are saved in the .mpp format.

---

**Τελευταία ενημέρωση:** 2026-02-23  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.11 (latest)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}