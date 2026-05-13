---
date: 2026-01-10
description: Μάθετε πώς να διαβάζετε την κλίμακα τιμών και να διαχειρίζεστε τις αναθέσεις
  πόρων στο Aspose.Tasks for Java. Ορίστε υλικό πόρο, πώς να ορίσετε την κλίμακα και
  να αναθέσετε πόρους σε εργασία.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να διαβάσετε και να γράψετε την κλίμακα τιμής για τις αναθέσεις πόρων στο
  Aspose.Tasks
url: /el/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Διαβάσετε και να Γράψετε το Rate Scale για Αναθέσεις Πόρων στο Aspose.Tasks

Σε αυτό το tutorial θα ανακαλύψετε **πώς να διαβάζετε** τις ρυθμίσεις του rate scale και να τις προσαρμόζετε για αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks for Java. Είτε χτίζετε έναν χρονοπρογραμματιστή, ένα εργαλείο αναφορών, είτε απλώς χρειάζεστε αυτοματοποίηση ενημερώσεων έργου, η εξοικείωση με τη διαχείριση του rate scale σας δίνει ακριβή έλεγχο πάνω σε υλικά και εργασιακούς πόρους.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για τη διαχείριση του rate;** `ResourceAssignment` με την ιδιότητα `Asn.RATE_SCALE`.  
- **Ποιο enum ορίζει τις επιλογές του scale;** `RateScaleType` (Day, Week, Month, κ.λπ.).  
- **Χρειάζεται άδεια για την εκτέλεση του δείγματος;** Μια δωρεάν δοκιμαστική άδεια λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να αλλάξω το scale μετά την αποθήκευση;** Ναι – φορτώστε ξανά το έργο και τροποποιήστε το `Asn.RATE_SCALE` όπως φαίνεται.  
- **Υποστηριζόμενα IDE;** Οποιοδήποτε Java IDE (IntelliJ IDEA, Eclipse, NetBeans) μπορεί να μεταγλωττίσει τον κώδικα.

## Τι είναι το Rate Scale;
Το rate scale καθορίζει τη μονάδα χρόνου (ημέρα, εβδομάδα, μήνας, κ.λπ.) στην οποία εφαρμόζεται το κόστος ανά μονάδα ενός πόρου. Η προσαρμογή του scale σας επιτρέπει να μοντελοποιήσετε με ακρίβεια την κατανάλωση υλικού ή την εργασία.

## Γιατί να διαβάζετε και να γράφετε το rate scale;
Η ανάγνωση του τρέχοντος scale σας βοηθά να ελέγξετε υπάρχοντα χρονοδιαγράμματα, ενώ η εγγραφή ενός νέου scale σας επιτρέπει να ευθυγραμμίσετε τους πόρους με τις πολιτικές χρέωσης ή κατανάλωσης του έργου. Αυτό είναι ιδιαίτερα χρήσιμο όταν **ορίζετε κόστη υλικών πόρων** ή όταν χρειάζεται να **ρυθμίσετε το scale** για μη‑τυπικά ημερολόγια εργασίας.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι διαθέτετε τα παρακάτω:
1. **Περιβάλλον Ανάπτυξης Java** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java Library** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από [εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαραίτητες κλάσεις του Aspose.Tasks.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Βήμα 1: Ρύθμιση του Java Project σας
Δημιουργήστε ένα έργο Maven ή Gradle και προσθέστε το JAR του Aspose.Tasks στο classpath. Αυτό το βήμα διασφαλίζει ότι ο μεταγλωττιστής μπορεί να εντοπίσει τις εισαγόμενες κλάσεις.

## Βήμα 2: Φόρτωση του Αρχείου Έργου
Φορτώστε το υπάρχον αρχείο Microsoft Project με το οποίο θέλετε να εργαστείτε.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Βήμα 3: Προσθήκη Εργασίας
Δημιουργήστε μια νέα εργασία που θα λάβει αργότερα αναθέσεις πόρων.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Βήμα 4: Ορισμός Πόρων
Εδώ **ορίζουμε υλικό πόρο** και έναν κανονικό εργασιακό πόρο. Παρατηρήστε τη χρήση του `ResourceType.Material` για τον πόρο τύπου υλικού.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Βήμα 5: Ανάθεση Πόρων στην Εργασία
Τώρα **αναθέτουμε πόρους στην εργασία** και καθορίζουμε **πώς να ορίσουμε το scale** χρησιμοποιώντας `RateScaleType.Week`. Αυτό δείχνει τόσο την ανάγνωση όσο και τη γραφή του rate scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Βήμα 6: Αποθήκευση του Έργου
Αποθηκεύστε τις αλλαγές σε ένα νέο αρχείο ώστε να μπορούμε αργότερα να επαληθεύσουμε το αποθηκευμένο rate scale.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Βήμα 7: Ανάκτηση Αναθέσεων Πόρων
Φορτώστε ξανά το αποθηκευμένο έργο και **διαβάστε το rate** scale για να επιβεβαιώσετε ότι γράφτηκε σωστά.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Συνηθισμένα Πόνα και Συμβουλές
- **Ασυμφωνία UID** – Κατά την ανάκτηση αναθέσεων με UID, βεβαιωθείτε ότι οι τιμές UID ταιριάζουν με αυτές που εκχωρήθηκαν κατά τη δημιουργία.  
- **Λανθασμένος Τύπος Πόρου** – Η χρήση του `ResourceType.Material` για έναν εργασιακό πόρο θα προκαλέσει ανεπιθύμητη συμπεριφορά στους υπολογισμούς του rate.  
- **Μορφή Αποθήκευσης** – Πάντα αποθηκεύετε χρησιμοποιώντας `SaveFileFormat.Mpp` (ή άλλη υποστηριζόμενη μορφή) για να διατηρήσετε προσαρμοσμένα πεδία όπως το rate scale.

## Συμπέρασμα
Η διαχείριση και η επιθεώρηση του rate scale για αναθέσεις πόρων στο Aspose.Tasks for Java είναι απλή μόλις γνωρίζετε τις σχετικές κλάσεις και ιδιότητες. Ακολουθώντας αυτόν τον οδηγό μπορείτε να **διαβάσετε πληροφορίες rate**, να **ορίσετε αντικείμενα υλικού πόρου**, να **ρυθμίσετε το scale**, και να **αναθέσετε πόρους σε εργασία** με σιγουριά.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java με οποιοδήποτε Java IDE;**  
Α: Ναι, το Aspose.Tasks for Java είναι συμβατό με όλα τα κύρια Java IDE, συμπεριλαμβανομένων των IntelliJ IDEA, Eclipse και NetBeans.

**Ε: Υποστηρίζει το Aspose.Tasks άλλες μορφές αρχείων εκτός του MPP;**  
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων, όπως MPP, XML και HTML.

**Ε: Είναι το Aspose.Tasks κατάλληλο για διαχείριση έργων σε επιχειρησιακό επίπεδο;**  
Α: Απόλυτα, το Aspose.Tasks προσφέρει ολοκληρωμένες δυνατότητες για τη διαχείριση έργων οποιουδήποτε μεγέθους, καθιστώντας το κατάλληλο για επιχειρησιακό επίπεδο.

**Ε: Μπορώ να προσαρμόσω περαιτέρω τις αναθέσεις πόρων πέρα από το rate scale;**  
Α: Ναι, το Aspose.Tasks παρέχει εκτενείς δυνατότητες προσαρμογής των αναθέσεων πόρων, συμπεριλαμβανομένων των ρυθμίσεων κόστους, εργασίας και διάρκειας.

**Ε: Υπάρχει φόρουμ κοινότητας για υποστήριξη του Aspose.Tasks;**  
Α: Ναι, μπορείτε να βρείτε υποστήριξη και να αλληλεπιδράσετε με άλλους χρήστες στο φόρουμ Aspose.Tasks [εδώ](https://forum.aspose.com/c/tasks/15).

---

**Τελευταία Ενημέρωση:** 2026-01-10  
**Δοκιμή Με:** Aspose.Tasks for Java 24.12 (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}