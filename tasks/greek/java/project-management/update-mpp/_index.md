---
date: 2025-12-28
description: Μάθετε πώς να προσθέτετε εργασίες και να ενημερώνετε αρχεία MPP χρησιμοποιώντας
  το Aspose.Tasks for Java, μια βιβλιοθήκη διαχείρισης έργων Java. Ακολουθήστε τον
  βήμα‑βήμα οδηγό μας για να δημιουργήσετε εργασία σε MPP και να αποθηκεύσετε το έργο
  ως MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να προσθέσετε εργασία και να ενημερώσετε το αρχείο MPP στο Aspose.Tasks
url: /el/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Εργασία και να Ενημερώσετε Αρχείο MPP στο Aspose.Tasks

## Introduction
Σε αυτό το tutorial θα σας δείξουμε **πώς να προσθέσετε εργασία** και να ενημερώσετε ένα αρχείο MPP χρησιμοποιώντας το Aspose.Tasks for Java, μια κορυφαία **βιβλιοθήκη διαχείρισης έργων java**. Είτε δημιουργείτε έναν προσαρμοσμένο χρονοπρογραμματιστή είτε χρειάζεστε να τροποποιήσετε υπάρχοντα σχέδια έργων προγραμματιστικά, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα—από τη φόρτωση του αρχείου μέχρι την αποθήκευση των αλλαγών ως νέο έγγραφο MPP.

## Quick Answers
- **Τι σημαίνει το “πώς να προσθέσετε εργασία” σε αυτό το πλαίσιο;** Αναφέρεται στη δημιουργία προγραμματιστικά μιας νέας εργασίας μέσα σε ένα υπάρχον αρχείο Microsoft Project (MPP).  
- **Ποια βιβλιοθήκη διαχειρίζεται τη λειτουργία;** Aspose.Tasks for Java, μια ισχυρή βιβλιοθήκη διαχείρισης έργων java.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να αποθηκεύσω το αποτέλεσμα ως MPP;** Ναι—χρησιμοποιήστε `project.save(..., SaveFileFormat.Mpp)` για **αποθήκευση έργου ως mpp**.  
- **Ποια έκδοση Java απαιτείται;** Java 8 ή νεότερη.

## What is “how to add task” in an MPP file?
Τι σημαίνει “πώς να προσθέσετε εργασία” σε ένα αρχείο MPP;
Η προσθήκη μιας εργασίας σημαίνει την εισαγωγή ενός νέου στοιχείου εργασίας στην ιεραρχία του έργου, τον ορισμό των ημερομηνιών έναρξης/λήξης, και την αποθήκευση της αλλαγής πίσω στο αρχείο MPP. Το Aspose.Tasks αφαιρεί τις λεπτομέρειες του χαμηλού επιπέδου μορφής αρχείου, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης.

## Why use Aspose.Tasks for Java?
- **Πλήρης συμβατότητα** με αρχεία Microsoft Project 2007‑2021.  
- **Δεν απαιτείται εγκατάσταση COM ή Office**—καθαρό Java API.  
- **Πλούσιο σύνολο λειτουργιών**: σύνδεση εργασιών, κατανομή πόρων, προσαρμοσμένα πεδία κ.ά.  
- **Υψηλή απόδοση** για μεγάλα αρχεία έργων, καθιστώντας το ιδανικό για αυτοματοποίηση στο διακομιστή.

## Prerequisites
1. **Περιβάλλον Ανάπτυξης Java** – JDK 8+ εγκατεστημένο και διαμορφωμένο.  
2. **Aspose.Tasks for Java** – Λήψη από τη [σελίδα λήψης](https://releases.aspose.com/tasks/java/).  
3. **Βασικές γνώσεις Java** – Εξοικείωση με κλάσεις, αντικείμενα και διαχείριση ημερομηνιών.  

## Import Packages
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Αυτό σας δίνει πρόσβαση στη διαχείριση έργου, ιδιότητες εργασιών και διαχείριση ημερομηνιών.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Define Data Directory
```java
String dataDir = "Your Data Directory";
```
Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή όπου βρίσκεται το αρχείο πηγής MPP.

## Step 2: Read Existing Project
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
Ο κατασκευαστής `Project` φορτώνει το **SampleMSP2010.mpp**, παρέχοντάς σας ένα διαχειρίσιμο μοντέλο αντικειμένων.

## Step 3: Create a New Task (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Αυτή η γραμμή **δημιουργεί εργασία στο mpp** προσθέτοντας ένα παιδί με όνομα *Task1* στην ριζική εργασία.

## Step 4: Set Start and Finish Dates
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Εδώ ορίζουμε το χρονοδιάγραμμα για τη νεοεισαχθείσα εργασία. Προσαρμόστε τις ημερομηνίες ώστε να ταιριάζουν με το χρονοδιάγραμμα του έργου σας.

## Step 5: Save the Project (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Το ενημερωμένο έργο, που τώρα περιέχει τη νέα εργασία, αποθηκεύεται ως **AfterLinking.mpp**.

## Common Issues and Solutions
| Πρόβλημα | Λύση |
|----------|------|
| **File not found** | Επαληθεύστε ότι το `dataDir` τελειώνει με διαχωριστικό διαδρομής (`/` ή `\\`) και ότι το όνομα αρχείου είναι σωστό. |
| **Incorrect dates** | Θυμηθείτε ότι οι μήνες του `Calendar` είναι μηδενικής βάσης· το `Calendar.JULY` είναι σωστό για τον Ιούλιο. |
| **License exception** | Εγκαταστήστε μια έγκυρη άδεια Aspose.Tasks πριν καλέσετε οποιοδήποτε API για να αποφύγετε υδατογραφήματα αξιολόγησης. |

## FAQ's
### Ε: Μπορεί το Aspose.Tasks for Java να διαχειριστεί σύνθετες δομές έργου;
Α: Ναι, το Aspose.Tasks for Java παρέχει ισχυρές δυνατότητες για αποτελεσματική διαχείριση σύνθετων δομών έργου.

### Ε: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Tasks for Java;
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμή από την [ιστοσελίδα](https://releases.aspose.com/).

### Ε: Υποστηρίζει το Aspose.Tasks for Java διαφορετικές εκδόσεις αρχείων Microsoft Project;
Α: Απόλυτα, το Aspose.Tasks for Java υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, συμπεριλαμβανομένων των μορφών MPP, MPT και XML.

### Ε: Μπορώ να αποκτήσω προσωρινές άδειες για το Aspose.Tasks for Java;
Α: Ναι, προσωρινές άδειες είναι διαθέσιμες για δοκιμαστικούς σκοπούς. Μπορείτε να τις αποκτήσετε από τη [σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).

### Ε: Πού μπορώ να ζητήσω βοήθεια ή υποστήριξη σχετικά με το Aspose.Tasks for Java;
Α: Μπορείτε να επισκεφθείτε το [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή ερωτήσεις.

## Frequently Asked Questions
**Ε: Πώς μπορώ να προσθέσω πολλές εργασίες ταυτόχρονα;**  
Α: Επανάληψη (loop) πάνω σε μια συλλογή ονομάτων εργασιών και επανάληψη του μπλοκ “create task” μέσα στο βρόχο.

**Ε: Μπορώ να ορίσω προσαρμοσμένα πεδία για τη νέα εργασία;**  
Α: Ναι—χρησιμοποιήστε `task.set(Tsk.CUSTOM_FIELD_x, value)` όπου *x* είναι ο δείκτης του πεδίου.

**Ε: Είναι δυνατόν να αντιγράψω μια υπάρχουσα εργασία ως πρότυπο;**  
Α: Κλωνοποιήστε την πηγαία εργασία (`Task cloned = sourceTask.clone();`) και στη συνέχεια προσθέστε την στον επιθυμητό γονέα.

**Ε: Τι κάνω αν χρειάζεται να ενημερώσω μια υπάρχουσα εργασία αντί να προσθέσω νέα;**  
Α: Ανακτήστε την εργασία με το ID (`Task existing = project.getRootTask().getChildren().getById(id);`) και τροποποιήστε τις ιδιότητές της.

**Ε: Υποστηρίζει το Aspose.Tasks αποθήκευση σε άλλες μορφές όπως PDF ή PNG;**  
Α: Ναι—χρησιμοποιήστε `project.save("output.pdf", SaveFileFormat.Pdf);` ή `SaveFileFormat.Png` για οπτικές αναπαραστάσεις.

---

**Τελευταία ενημέρωση:** 2025-12-28  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}