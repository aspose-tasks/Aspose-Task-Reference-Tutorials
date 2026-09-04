---
date: 2026-06-25
description: Μάθετε πώς να προσθέσετε εργασία και να ενημερώσετε αρχεία MPP χρησιμοποιώντας
  το Aspose.Tasks for Java, μια βιβλιοθήκη διαχείρισης έργων Java που σας επιτρέπει
  να δημιουργείτε αρχεία εργασίας Microsoft Project και να αποθηκεύετε το έργο ως
  MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Πώς να προσθέσετε εργασία και να ενημερώσετε αρχείο MPP στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Πώς να προσθέσετε εργασία και να ενημερώσετε αρχείο MPP στο Aspose.Tasks
url: /el/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Εργασία και να Ενημερώσετε το Αρχείο MPP στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε **πώς να προσθέσετε εργασία** σε ένα υπάρχον αρχείο Microsoft Project (MPP) και στη συνέχεια να αποθηκεύσετε το ενημερωμένο χρονοδιάγραμμα χρησιμοποιώντας το Aspose.Tasks for Java, μια κορυφαία **java project management library**. Είτε δημιουργείτε έναν προσαρμοσμένο προγραμματιστή, αυτοματοποιείτε μαζικές ενημερώσεις, είτε ενσωματώνετε δεδομένα έργου σε ένα μεγαλύτερο σύστημα, ο οδηγός βήμα‑βήμα παρακάτω δείχνει ακριβώς πώς να φορτώσετε ένα έργο, να εισάγετε μια νέα εργασία, να ορίσετε τις ημερομηνίες της και να αποθηκεύσετε το αποτέλεσμα ως νέο έγγραφο MPP.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “πώς να προσθέσετε εργασία” σε αυτό το πλαίσιο;** Σημαίνει τη δημιουργία προγραμματιστικά ενός νέου αντικειμένου εργασίας μέσα σε ένα υπάρχον αρχείο MPP.  
- **Ποια βιβλιοθήκη διαχειρίζεται τη λειτουργία;** Aspose.Tasks for Java, μια ισχυρή java project management library.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να αποθηκεύσω το αποτέλεσμα ως MPP;** Ναι—χρησιμοποιήστε `project.save(..., SaveFileFormat.Mpp)` για **save project as mpp**.  
- **Ποια έκδοση Java απαιτείται;** Java 8 ή νεότερη.

## Τι είναι το “πώς να προσθέσετε εργασία” σε αρχείο MPP;
Η προσθήκη εργασίας σημαίνει την εισαγωγή ενός νέου αντικειμένου εργασίας στην ιεραρχία του έργου, τον ορισμό των ημερομηνιών έναρξης/λήξης και την αποθήκευση της αλλαγής πίσω στο αρχείο MPP. Το Aspose.Tasks αφαιρεί τις λεπτομέρειες του χαμηλού επιπέδου μορφής αρχείου, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης ενώ διαχειρίζεται αυτόματα τις αναθέσεις πόρων, τα ημερολόγια και τους υπολογισμούς εξαρτήσεων. Επίσης ενημερώνει τυχόν σχετικές αναθέσεις και επαναϋπολογίζει το χρονοδιάγραμμα του έργου για να διατηρήσει τη συνοχή μεταξύ των εξαρτημένων εργασιών.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks for Java;
- **Πλήρης συμβατότητα**: Υποστηρίζει το 100 % των λειτουργιών του Microsoft Project 2007‑2021 (πάνω από 150 τύπους εργασιών και 200 πεδία πόρων).  
- **Χωρίς εξαρτήσεις**: Δεν απαιτείται COM, Office ή εγγενείς βιβλιοθήκες—καθαρό Java API που τρέχει οπουδήποτε υπάρχει JRE.  
- **Πλούσιο σύνολο λειτουργιών**: Περιλαμβάνει σύνδεση εργασιών, κατανομή πόρων, προσαρμοσμένα πεδία και ενσωματωμένη αναφορά.  
- **Υψηλή απόδοση**: Επεξεργάζεται έργα με έως και 10 000 εργασίες χρησιμοποιώντας λιγότερα από 200 MB RAM, καθιστώντας το ιδανικό για αυτοματισμούς διακομιστή.

## Προαπαιτούμενα
1. **Περιβάλλον Ανάπτυξης Java** – Εγκατεστημένο και ρυθμισμένο JDK 8+.  
2. **Aspose.Tasks for Java** – Λήψη από τη [σελίδα λήψης](https://releases.aspose.com/tasks/java/).  
3. **Βασικές γνώσεις Java** – Εξοικείωση με κλάσεις, αντικείμενα και διαχείριση ημερομηνιών.  

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Αυτό σας δίνει πρόσβαση στη διαχείριση έργου, στις ιδιότητες εργασιών και στη διαχείριση ημερομηνιών.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που φορτώνεται στη μνήμη. `SaveFileFormat` απαριθμεί τις μορφές στις οποίες μπορείτε να αποθηκεύσετε, όπως MPP ή PDF. `Task` μοντελοποιεί ένα μεμονωμένο αντικείμενο εργασίας μέσα στην ιεραρχία του έργου. `Tsk` παρέχει σταθερές για πεδία εργασίας που χρησιμοποιούνται κατά τον ορισμό ή την ανάκτηση τιμών. `Calendar` προσφέρει βοηθητικά εργαλεία ημερομηνίας‑ώρας για τον ορισμό χρονοδιαγραμμάτων.

## Βήμα 1: Ορισμός Καταλόγου Δεδομένων
```java
String dataDir = "Your Data Directory";
```  
Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή όπου βρίσκεται το πηγαίο αρχείο MPP σας.

## Βήμα 2: Ανάγνωση Υπάρχοντος Έργου
Η κλάση `Project` είναι το κεντρικό αντικείμενο του Aspose.Tasks που αντιπροσωπεύει ένα αρχείο Microsoft Project στη μνήμη.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Ο κατασκευαστής φορτώνει το **SampleMSP2010.mpp**, παρέχοντάς σας ένα πλήρως διαχειρίσιμο μοντέλο αντικειμένων.

## Βήμα 3: Δημιουργία Νέας Εργασίας (πώς να προσθέσετε εργασία)
Η κλάση `Task` αντιπροσωπεύει ένα μεμονωμένο αντικείμενο εργασίας μέσα στην ιεραρχία του έργου.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Αυτή η γραμμή **creates task in mpp** προσθέτοντας ένα παιδί με όνομα *Task1* στην ριζική εργασία.

## Βήμα 4: Ορισμός Ημερομηνιών Έναρξης και Λήξης
Η κλάση `Calendar` παρέχει βοηθητικά εργαλεία ημερομηνίας‑ώρας· οι μήνες είναι μηδενικής βάσης (π.χ., `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Εδώ ορίζουμε το χρονοδιάγραμμα για τη νεοεισαχθείσα εργασία. Προσαρμόστε τις ημερομηνίες ώστε να ταιριάζουν με το χρονοδιάγραμμα του έργου σας.

## Βήμα 5: Αποθήκευση του Έργου (save project as mpp)
`SaveFileFormat.Mpp` λέει στο Aspose.Tasks να γράψει το αρχείο πίσω στη φυσική μορφή Microsoft Project.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Το ενημερωμένο έργο, που τώρα περιέχει τη νέα εργασία, αποθηκεύεται ως **AfterLinking.mpp**.

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **File not found** | Επαληθεύστε ότι το `dataDir` τελειώνει με διαχωριστικό διαδρομής (`/` ή `\\`) και ότι το όνομα αρχείου είναι σωστό. |
| **Incorrect dates** | Θυμηθείτε ότι οι μήνες του `Calendar` είναι μηδενικής βάσης· το `Calendar.JULY` είναι σωστό για τον Ιούλιο. |
| **License exception** | Εγκαταστήστε μια έγκυρη άδεια Aspose.Tasks πριν καλέσετε οποιοδήποτε API για να αποφύγετε υδατογραφήματα αξιολόγησης. |

## Συχνές Ερωτήσεις
**Ε: Πώς μπορώ να προσθέσω πολλές εργασίες ταυτόχρονα;**  
Α: Επαναλάβετε τη δημιουργία εργασίας μέσα σε βρόχο που διατρέχει μια συλλογή ονομάτων εργασιών.

**Ε: Μπορώ να ορίσω προσαρμοσμένα πεδία για τη νέα εργασία;**  
Α: Ναι—χρησιμοποιήστε `task.set(Tsk.CUSTOM_FIELD_x, value)` όπου *x* είναι ο δείκτης του πεδίου.

**Ε: Είναι δυνατόν να αντιγράψω μια υπάρχουσα εργασία ως πρότυπο;**  
Α: Κλωνοποιήστε την πηγαία εργασία (`Task cloned = sourceTask.clone();`) και στη συνέχεια προσθέστε την στον επιθυμητό γονέα.

**Ε: Τι γίνεται αν χρειαστεί να ενημερώσω μια υπάρχουσα εργασία αντί να προσθέσω νέα;**  
Α: Ανακτήστε την εργασία με το ID (`Task existing = project.getRootTask().getChildren().getById(id);`) και τροποποιήστε τις ιδιότητές της.

**Ε: Υποστηρίζει το Aspose.Tasks αποθήκευση σε άλλες μορφές όπως PDF ή PNG;**  
Α: Ναι—χρησιμοποιήστε `project.save("output.pdf", SaveFileFormat.Pdf);` ή `SaveFileFormat.Png` για οπτικές αναπαραστάσεις.

**Τελευταία Ενημέρωση:** 2026-06-25  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά Tutorials

- [Πώς να Δημιουργήσετε Αρχείο MPP – Δημιουργία & Αποθήκευση Κεντρικού Έργου σε Μορφή MPP με Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Πώς να Δημιουργήσετε Έργο – Ορισμός Νέων Ιδιοτήτων Εργασίας με Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Δημιουργία Λίστας Εργασιών Java – Βάση MS Project χρησιμοποιώντας Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}