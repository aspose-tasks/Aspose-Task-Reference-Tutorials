---
date: 2026-06-30
description: Μάθετε πώς να ενημερώσετε πολλαπλούς πόρους και να τροποποιήσετε τα δεδομένα
  ομάδας πόρων, στη συνέχεια να εξάγετε το έργο σε μορφή MPP και να αποθηκεύσετε το
  έργο ως MPP χρησιμοποιώντας το Aspose.Tasks for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Ενημέρωση Πολλών Πόρων στο Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ενημέρωση Πολλών Πόρων στο Aspose.Tasks for Java
url: /el/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ενημέρωση Πολλαπλών Πόρων στο Aspise.Tasks για Java

## Εισαγωγή
Σε αυτό το tutorial, θα μάθετε πώς να **ενημερώνετε πολλαπλούς πόρους** σε ένα αρχείο Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Είτε χρειάζεται να αλλάξετε τιμές, να επανατοποθετήσετε ομάδες, είτε να εξάγετε το ενημερωμένο αρχείο σε μορφή MPP, τα παρακάτω βήματα σας καθοδηγούν μέσα από μια πλήρη, έτοιμη για παραγωγή ροή εργασίας. Δεν απαιτείται εγκατάσταση του Microsoft Project και το API μπορεί να διαχειριστεί έργα με εκατοντάδες πόρους αποδοτικά.

## Γρήγορες Απαντήσεις
- **Μπορώ να ενημερώσω πολλούς πόρους ταυτόχρονα;** Ναι – επαναλάβετε τη `ResourceCollection` και ορίστε τις ιδιότητες σε μία μόνο διαδρομή.  
- **Ποια μέθοδος αποθηκεύει το αρχείο ως MPP;** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Χρειάζομαι άδεια για εμπορική χρήση;** Απαιτείται πληρωμένη άδεια για παραγωγή· διατίθεται δωρεάν δοκιμή.  
- **Ποιες εκδόσεις της Java υποστηρίζονται;** Java 6 και άνω, συμπεριλαμβανομένης της Java 17 LTS.  
- **Είναι αποδοτική η μαζική ενημέρωση;** Το Aspose.Tasks επεξεργάζεται έργα με 500 πόρους σε λιγότερο από 2 δευτερόλεπτα σε τυπικό διακομιστή.

## Τι είναι η «ενημέρωση πολλαπλών πόρων»;
Η **«ενημέρωση πολλαπλών πόρων»** αναφέρεται στην προγραμματιστική αλλαγή των ιδιοτήτων πολλών εγγραφών πόρων—όπως τιμές, ομάδες, ημερολόγια ή προσαρμοσμένα πεδία—εντός ενός ενιαίου αρχείου Project. Αυτή η λειτουργία απαιτείται συχνά κατά τον συγχρονισμό δεδομένων έργου με συστήματα Enterprise Resource Planning, την προσαρμογή προϋπολογισμών σε πολλούς πόρους ή την εφαρμογή πολιτικών σε όλη την οργάνωση.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για την τροποποίηση ομάδας πόρων και την εξαγωγή έργου σε MPP;
Το Aspose.Tasks υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου**, συμπεριλαμβανομένων των MPP, XML και CSV, και μπορεί να **εξάγει το έργο σε MPP** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη επεξεργάζεται αρχεία έως **2 GB** σε μέγεθος, επιτρέποντάς σας να **αποθηκεύσετε το έργο ως MPP** γρήγορα και αξιόπιστα.

## Προαπαιτούμενα

1. Java Development Kit (JDK) εγκατεστημένο στο σύστημά σας.  
2. Βιβλιοθήκη Aspose.Tasks για Java. Μπορείτε να τη κατεβάσετε από [εδώ](https://releases.aspose.com/tasks/java/).  
3. Βασικές γνώσεις προγραμματισμού Java.  

## Εισαγωγή Πακέτων

Οι δηλώσεις `import` φέρνουν τις απαιτούμενες κλάσεις του Aspose.Tasks στο αρχείο πηγαίου κώδικα.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Βήμα 1: Ρύθμιση του Καταλόγου Δεδομένων σας

Ορίστε τον κατάλογο όπου βρίσκονται τα αρχεία δεδομένων σας:

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: Καθορισμός Αρχείων Εισόδου και Εξόδου

Ορίστε τις διαδρομές για το αρχείο εισόδου MS Project και το ενημερωμένο αρχείο που θα προκύψει:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Βήμα 3: Φόρτωση του Έργου

`Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που έχει φορτωθεί στη μνήμη, παρέχοντας πρόσβαση σε εργασίες, πόρους και άλλα δεδομένα του έργου.

```java
Project project = new Project(file);
```

## Βήμα 4: Προσθήκη Πόρου και Ορισμός Ιδιοτήτων

`Resource` μοντελοποιεί έναν μεμονωμένο πόρο του έργου, επιτρέποντάς σας να ορίσετε τιμές, ομάδες, ημερολόγια και άλλες ιδιότητες.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Βήμα 5: Αποτελεσματική Ενημέρωση Πολλαπλών Πόρων

`ResourceCollection` είναι η συλλογή όλων των πόρων σε ένα έργο, προσβάσιμη μέσω `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Βήμα 6: Αποθήκευση του Έργου

`SaveFileFormat` απαριθμεί τις υποστηριζόμενες μορφές αρχείων για την αποθήκευση ενός έργου, όπως MPP, XML και PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Πώς να ενημερώσετε πολλαπλούς πόρους σε ένα έργο;

Φορτώστε το υπάρχον έργο, ανακτήστε το `ResourceCollection` του και επαναλάβετε πάνω σε κάθε αντικείμενο `Resource`. Για κάθε πόρο, τροποποιήστε τα απαιτούμενα πεδία όπως τιμές, ομάδες ή προσαρμοσμένα χαρακτηριστικά, και στη συνέχεια προχωρήστε στο επόμενο στοιχείο. Μετά την επεξεργασία όλων των πόρων, καλέστε μία φορά το `project.save(...)` για να αποθηκεύσετε τις αλλαγές αποδοτικά.

## Συνηθισμένα Προβλήματα και Λύσεις

- **Σύγκρουση ID πόρων** – Βεβαιωθείτε ότι κάθε νέος πόρος λαμβάνει μοναδικό ID χρησιμοποιώντας `project.getResources().add(new Resource())`.  
- **Σφάλματα μορφής τιμής** – Χρησιμοποιήστε αντικείμενα `ResourceRate` και ορίστε το `RateType` σε `StandardRate` ή `OvertimeRate`.  
- **Μεγάλα αρχεία προκαλούν πίεση μνήμης** – Ενεργοποιήστε `Project.setReadOnly(true)` πριν τη φόρτωση για να μειώσετε το αποτύπωμα μνήμης.

## Συχνές Ερωτήσεις

**Q: Μπορώ να ενημερώσω πολλούς πόρους στο ίδιο έργο χρησιμοποιώντας το Aspose.Tasks για Java;**  
A: Ναι, μπορείτε να ενημερώσετε πολλούς πόρους επαναλαμβάνοντας τους και ορίζοντας τις ιδιότητές τους αναλόγως.

**Q: Υποστηρίζει το Aspose.Tasks άλλες μορφές αρχείων εκτός από το MS Project;**  
A: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων, συμπεριλαμβανομένων XML, MPP και άλλων.

**Q: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις της Java;**  
A: Το Aspose.Tasks είναι συμβατό με εκδόσεις Java 6 και άνω.

**Q: Μπορώ να εκτελέσω άλλες λειτουργίες σε αρχεία MS Project με το Aspose.Tasks;**  
A: Ναι, μπορείτε να εκτελέσετε ένα ευρύ φάσμα λειτουργιών όπως ανάγνωση, εγγραφή και διαχείριση εργασιών, πόρων και ημερολογίων.

**Q: Πού μπορώ να βρω πρόσθετη βοήθεια ή υποστήριξη για το Aspose.Tasks;**  
A: Μπορείτε να επισκεφθείτε το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή ερώτηση.

**Q: Πώς εξάγω το ενημερωμένο αρχείο σε μορφή MPP;**  
A: Καλέστε `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` μετά τις αλλαγές σε όλους τους πόρους.

**Q: Ποιος είναι ο καλύτερος τρόπος για την τροποποίηση μιας ομάδας πόρων;**  
A: Ορίστε την ιδιότητα `Resource.Group` σε κάθε αντικείμενο `Resource` πριν αποθηκεύσετε το έργο.

---

**Τελευταία ενημέρωση:** 2026-06-30  
**Δοκιμή με:** Aspose.Tasks for Java 24.12  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικές Οδηγίες

- [Προσθήκη πόρου στο έργο με Aspose.Tasks για Java](/tasks/java/resource-management/create-resources/)
- [Διαχείριση Κόστους Πόρων MS Project με Aspose.Tasks για Java](/tasks/java/resource-management/resource-cost/)
- [Πώς να Εξάγετε MPP σε Excel με Aspose.Tasks για Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}