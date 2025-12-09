---
date: 2025-12-09
description: Μάθετε πώς να ορίσετε τον φάκελο δεδομένων και να διαμορφώσετε την προβολή
  διαγράμματος Gantt στο Aspose.Tasks χρησιμοποιώντας Java. Αυτός ο οδηγός δείχνει
  επίσης πώς να προσαρμόσετε τα πεδία του πίνακα και να διαμορφώσετε τα έργα Java
  με διάγραμμα Gantt βήμα‑βήμα.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ορισμός καταλόγου δεδομένων για την προβολή διαγράμματος Gantt στο Aspose.Tasks
url: /el/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Καταλόγου Δεδομένων για την Προβολή Gantt Chart στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial, θα μάθετε **πώς να ορίσετε τον κατάλογο δεδομένων** και να διαμορφώσετε την Προβολή Gantt MS Project Chart σε έργα Aspose.Tasks χρησιμοποιώντας Java. Το Aspose.Tasks είναι ένα ισχυρό Java API που σας επιτρέπει να χειρίζεστε αρχεία Microsoft Project προγραμματιστικά. Στο τέλος αυτού του οδηγού θα μπορείτε να **προσαρμόσετε τα πεδία πίνακα**, να ρυθμίσετε τον κατάλογο δεδομένων και να οπτικοποιήσετε το έργο σας ακριβώς όπως το χρειάζεστε.

## Γρήγορες Απαντήσεις
- **Ποιο είναι το πρώτο βήμα;** Ορίστε τη διαδρομή του καταλόγου δεδομένων όπου βρίσκονται τα αρχεία του έργου σας.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks για Java (διαθέσιμη για λήψη από την επίσημη ιστοσελίδα).  
- **Μπορώ να προσθέσω προσαρμοσμένα χαρακτηριστικά;** Ναι – μπορείτε να ορίσετε εκτεταμένα χαρακτηριστικά και να τα εμφανίσετε στο διάγραμμα Gantt.  
- **Χρειάζομαι άδεια για δοκιμές;** Διατίθεται προσωρινή άδεια για σκοπούς αξιολόγησης.  
- **Ποιο IDE είναι το καλύτερο;** Οποιοδήποτε Java IDE (IntelliJ IDEA, Eclipse, NetBeans) λειτουργεί.

## Τι είναι το “set data directory” και γιατί είναι σημαντικό;
Ορίζοντας τον κατάλογο δεδομένων λέτε στο Aspose.Tasks πού να διαβάζει και να γράφει τα αρχεία του έργου. Χωρίς σωστή διαδρομή το API δεν μπορεί να εντοπίσει τα `.mpp` αρχεία σας, οδηγώντας σε σφάλματα FileNotFound. Ορίζοντας αυτόν τον κατάλογο στην αρχή του κώδικά σας, το υπόλοιπο workflow γίνεται καθαρό και επαναλήψιμο.

## Γιατί να προσαρμόσετε τα πεδία πίνακα σε ένα διάγραμμα Gantt;
Τα προσαρμοσμένα πεδία πίνακα σας επιτρέπουν να εμφανίζετε πρόσθετες πληροφορίες—όπως προσαρμοσμένα χαρακτηριστικά, δεδομένα πόρων ή σημειώσεις ειδικές για το έργο—απευθείας στην προβολή Gantt. Αυτό κάνει το διάγραμμα πιο ενημερωτικό για τα ενδιαφερόμενα μέρη και μειώνει την ανάγκη εναλλαγής μεταξύ πολλαπλών αναφορών.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – οποιαδήποτε πρόσφατη έκδοση (8+).  
2. **Aspose.Tasks Library** – κατεβάστε το από [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε Java‑συμβατό επεξεργαστή προτιμάτε.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε το namespace του Aspose.Tasks ώστε να μπορείτε να εργάζεστε με τις κλάσεις του:

```java
import com.aspose.tasks.*;
```

## Οδηγός Βήμα‑Βήμα

### Βήμα 1: Ρύθμιση Καταλόγου Δεδομένων
Ορίστε το φάκελο που περιέχει τα αρχεία του έργου σας. Αυτό είναι το βήμα **set data directory** στο οποίο εστιάζει το tutorial.

```java
String dataDir = "Your Data Directory";
```

Αντικαταστήστε το `"Your Data Directory"` με την απόλυτη διαδρομή του φακέλου όπου αποθηκεύεται το `project.mpp`.

### Βήμα 2: Φόρτωση Αρχείου Έργου
Δημιουργήστε μια παρουσία `Project` φορτώνοντας ένα υπάρχον αρχείο Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Βήμα 3: Προσθήκη Νέας Δραστηριότητας
Εισάγετε μια νέα εργασία (δραστηριότητα) στη ρίζα του έργου.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Βήμα 4: Ορισμός Προσαρμοσμένου Χαρακτηριστικού
Δημιουργήστε έναν ορισμό προσαρμοσμένου χαρακτηριστικού που μπορείτε αργότερα να συνδέσετε με εργασίες.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Βήμα 5: Προσθήκη Προσαρμοσμένου Χαρακτηριστικού σε Εργασία
Αναθέστε το νεοδημιουργημένο χαρακτηριστικό στην εργασία που δημιουργήσατε.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Βήμα 6: Προσαρμογή Πίνακα – **customize table fields**
Προσθέστε το προσαρμοσμένο χαρακτηριστικό ως στήλη στον πίνακα του διαγράμματος Gantt, καθορίζοντας πλάτος, τίτλο και στοίχιση.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Βήμα 7: Αποθήκευση Έργου
Αποθηκεύστε τις αλλαγές σε ένα νέο αρχείο που μπορεί να ανοιχθεί στο Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| **FileNotFoundException** κατά τη φόρτωση του έργου | Η διαδρομή **set data directory** είναι λανθασμένη ή λείπει το τελικό slash. | Επαληθεύστε ότι το `dataDir` δείχνει στον ακριβή φάκελο και συμπεριλάβετε το κατάλληλο διαχωριστικό αρχείων (`/` ή `\\`). |
| Το προσαρμοσμένο χαρακτηριστικό δεν εμφανίζεται στην προβολή Gantt | Το πεδίο του πίνακα προστέθηκε σε λάθος δείκτη ή το πλάτος της στήλης είναι πολύ μικρό. | Βεβαιωθείτε ότι το `table.getTableFields().add(3, attrField);` χρησιμοποιεί έγκυρο δείκτη και προσαρμόστε το `setWidth` όπως χρειάζεται. |
| LicenseException κατά την αποθήκευση | Δεν εφαρμόστηκε έγκυρη άδεια για παραγωγική χρήση. | Εφαρμόστε προσωρινή ή μόνιμη άδεια πριν καλέσετε το `project.save()`. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;**  
A: Ναι, το Aspose.Tasks είναι διαθέσιμο για πολλαπλές γλώσσες προγραμματισμού, συμπεριλαμβανομένων .NET, Java και C++.

**Q: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Tasks;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμή από [here](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;**  
A: Μπορείτε να βρείτε υποστήριξη και να θέσετε ερωτήσεις στο [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Πώς μπορώ να αγοράσω άδεια για το Aspose.Tasks;**  
A: Μπορείτε να αγοράσετε άδεια από [here](https://purchase.aspose.com/buy).

**Q: Χρειάζομαι προσωρινή άδεια για δοκιμαστικούς σκοπούς;**  
A: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια από [here](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
Τώρα έχετε μάθει πώς να **ορίσετε τον κατάλογο δεδομένων**, να προσθέσετε μια νέα δραστηριότητα, να ορίσετε και να συνδέσετε ένα προσαρμοσμένο χαρακτηριστικό, και να **προσαρμόσετε τα πεδία πίνακα** σε μια προβολή Gantt χρησιμοποιώντας το Aspose.Tasks για Java. Αυτά τα βήματα σας δίνουν πλήρη έλεγχο πάνω στο πώς εμφανίζονται τα δεδομένα του έργου, καθιστώντας τα διαγράμματα Gantt πιο ενημερωτικά και προσαρμοσμένα στις ανάγκες των ενδιαφερόμενων μερών.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}