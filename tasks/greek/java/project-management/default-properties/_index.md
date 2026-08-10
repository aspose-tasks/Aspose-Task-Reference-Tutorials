---
date: 2026-05-31
description: Μάθετε πώς να φορτώσετε ένα αρχείο MPP σε Java και να διαχειριστείτε
  τις ιδιότητες του έργου με το Aspose.Tasks, συμπεριλαμβανομένου του καθορισμού προεπιλεγμένων
  ιδιοτήτων και της μετατροπής μορφών.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Διαχείριση προεπιλεγμένων ιδιοτήτων έργου στο Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Φόρτωση αρχείου MPP Java – Διαχείριση ιδιοτήτων έργου με Aspose.Tasks
url: /el/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Φόρτωση αρχείου MPP Java – Διαχείριση ιδιοτήτων έργου με Aspose.Tasks

## Εισαγωγή
Αν χρειάζεστε να **load MPP file Java** έργα και να διαχειριστείτε προγραμματιστικά τις προεπιλεγμένες ιδιότητες του έργου, το Aspose.Tasks for Java το καθιστά εύκολο. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία—από τη φόρτωση ενός υπάρχοντος αρχείου Microsoft Project μέχρι την προσαρμογή των προεπιλεγμένων ρυθμίσεων εργασιών και πόρων, και τέλος την αποθήκευση του ενημερωμένου έργου. Στο τέλος θα έχετε ένα σαφές, επαναχρησιμοποιήσιμο μοτίβο που μπορείτε να ενσωματώσετε σε οποιαδήποτε λύση διαχείρισης έργων βασισμένη σε Java.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “load MPP file Java”;** Σημαίνει ανάγνωση ενός αρχείου Microsoft Project (.mpp) χρησιμοποιώντας κώδικα Java μέσω Aspose.Tasks.  
- **Ποια βιβλιοθήκη το διαχειρίζεται;** Το Aspose.Tasks for Java παρέχει ένα πλήρες API για τη διαχείριση έργων.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για χρήση σε παραγωγή.  
- **Μπορώ να αλλάξω τις προεπιλεγμένες ημερομηνίες έναρξης εργασιών;** Ναι—χρησιμοποιήστε το `Prj.DEFAULT_START_TIME` και σχετικές ιδιότητες για να ορίσετε τις προεπιλογές.  
- **Ποια μορφές εξόδου υποστηρίζονται;** Εκτός από το εγγενές MPP, μπορείτε να αποθηκεύσετε σε XML, PDF, HTML και πάνω από 20 άλλες μορφές.

## Τι είναι το “load MPP file Java”;
Η φόρτωση ενός αρχείου MPP σε Java σημαίνει χρήση μιας βιβλιοθήκης για την ανάλυση της δυαδικής μορφής Microsoft Project, εκθέτοντας τα αντικείμενά του (εργασίες, πόροι, ημερολόγια) ως κλάσεις Java. Αυτό σας επιτρέπει να διαβάζετε, να τροποποιείτε και να αποθηκεύετε δεδομένα έργου χωρίς ποτέ να ανοίξετε το Microsoft Project.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks for Java;
Το Aspose.Tasks σας επιτρέπει να διαχειρίζεστε τις ιδιότητες του έργου χωρίς εγκατάσταση του Microsoft Project, υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου**, και μπορεί να επεξεργαστεί έργα με **μέχρι 10.000 εργασίες** διατηρώντας τη χρήση μνήμης κάτω από 200 MB. Εκτελείται σε οποιοδήποτε λειτουργικό σύστημα που υποστηρίζει JDK, καθιστώντας το ιδανικό για αυτοματοποίηση στο διακομιστή.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

### 1. Java Development Kit (JDK)
- Εγκαταστήστε το JDK 11 ή νεότερο.  
- Μπορείτε να το κατεβάσετε από [εδώ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### 2. Aspose.Tasks for Java Library
- Κατεβάστε το πιο πρόσφατο Aspose.Tasks JAR και προσθέστε το στο classpath του έργου σας.  
- Λάβετε το από την [ιστοσελίδα](https://releases.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Οι δηλώσεις import φέρνουν τις απαραίτητες κλάσεις του Aspose.Tasks στο αρχείο πηγαίου κώδικα Java.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Πώς να φορτώσετε MPP file Java και να ορίσετε προεπιλεγμένες ιδιότητες;
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project και παρέχει πρόσβαση στις εργασίες, τους πόρους και τις ρυθμίσεις του. Φορτώστε το έργο, ελέγξτε τις προεπιλογές του, τροποποιήστε τις και αποθηκεύστε το αποτέλεσμα—όλα σε λίγες απλές γραμμές. Αυτή η προσέγγιση σας δίνει πλήρη έλεγχο πάνω στις προεπιλεγμένες ρυθμίσεις χρονοδιαγράμματος, ρυθμίσεις ημερολογίου και κανόνες συσσωμάτωσης κόστους, επιτρέποντας την επιβολή συνεπών προτύπων έργου σε όλα τα παραγόμενα αρχεία.

### Βήμα 1: Φόρτωση Αρχείου Έργου
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Βήμα 2: Εμφάνιση Προεπιλεγμένων Ιδιοτήτων
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Βήμα 3: Ορισμός Προεπιλεγμένων Ιδιοτήτων
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Βήμα 4: Αποθήκευση Έργου σε Μορφή XML
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Βήμα 5: Εμφάνιση Αποτελέσματος
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Ακολουθώντας αυτά τα βήματα έχετε επιτυχώς **φορτώσει ένα αρχείο MPP σε Java**, ελέγξει τις προεπιλεγμένες ρυθμίσεις του, τις προσαρμόσει και αποθηκεύσει το ενημερωμένο έργο.

## Συχνά Προβλήματα & Συμβουλές
- **Αρχείο δεν βρέθηκε** – Επαληθεύστε ότι το `dataDir` τελειώνει με διαχωριστικό διαδρομής (`/` ή `\\`).  
- **Άδεια δεν εφαρμόστηκε** – Αν δείτε υδατογράφημα δοκιμής, προσθέστε το αρχείο άδειας πριν φορτώσετε το έργο: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Διαχείριση ημερομηνίας** – Χρησιμοποιήστε το `java.util.Calendar` ή το νεότερο API `java.time` (μετατρέψτε σε `java.util.Date` πριν την ανάθεση).

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;**  
Ναι, το Aspose.Tasks είναι επίσης διαθέσιμο για .NET, Python και άλλες πλατφόρμες.

**Ε: Είναι το Aspose.Tasks κατάλληλο για προσωπική και επιχειρηματική χρήση;**  
Απολύτως! Κλιμακώνεται από μικρά προσωπικά έργα μέχρι μεγάλης κλίμακας επιχειρηματικά χαρτοφυλάκια.

**Ε: Παρέχει το Aspose.Tasks υποστήριξη πελατών;**  
Ναι, μπορείτε να βρείτε βοήθεια και υποστήριξη κοινότητας στο [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Ε: Μπορώ να δοκιμάσω το Aspose.Tasks πριν την αγορά;**  
Φυσικά! Μπορείτε να εκμεταλλευτείτε μια δωρεάν δοκιμή από την [ιστοσελίδα](https://releases.aspose.com/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Tasks;**  
Μπορείτε να λάβετε μια προσωρινή άδεια από τη [σελίδα αγοράς](https://purchase.aspose.com/temporary-license/) για δοκιμή και αξιολόγηση.

## Συμπέρασμα
Σε αυτό το tutorial καλύψαμε πώς να **load MPP file Java** έργα, να διαβάσετε και να τροποποιήσετε τις προεπιλεγμένες ιδιότητές τους, και να αποθηκεύσετε τις αλλαγές χρησιμοποιώντας το Aspose.Tasks for Java. Η ενσωμάτωση αυτών των τεχνικών στις εφαρμογές σας θα σας βοηθήσει να αυτοματοποιήσετε εργασίες διαχείρισης έργων, να επιβάλετε συνεπείς προεπιλογές και να μειώσετε την χειροκίνητη προσπάθεια.

---

**Τελευταία ενημέρωση:** 2026-05-31  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [How to Set Project Calendar with Aspose.Tasks for Java](/tasks/java/calendars/properties/)
- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}