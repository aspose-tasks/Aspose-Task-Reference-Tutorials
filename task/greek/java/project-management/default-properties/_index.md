---
title: Διαχειριστείτε αποτελεσματικά τις ιδιότητες του έργου MS στο Aspose.Tasks
linktitle: Διαχείριση προεπιλεγμένων ιδιοτήτων έργου στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαχειρίζεστε τις προεπιλεγμένες ιδιότητες του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιώστε τη ροή εργασιών διαχείρισης του έργου σας χωρίς κόπο.
type: docs
weight: 11
url: /el/java/project-management/default-properties/
---
## Εισαγωγή
Ψάχνετε να απλοποιήσετε τη διαδικασία διαχείρισης του έργου σας με το Aspose.Tasks για Java; Η διαχείριση προεπιλεγμένων ιδιοτήτων στα αρχεία του Microsoft Project μπορεί να βελτιώσει σημαντικά την αποτελεσματικότητα. Σε αυτό το σεμινάριο, θα ακολουθήσουμε οδηγίες βήμα προς βήμα σχετικά με τον τρόπο διαχείρισης των προεπιλεγμένων ιδιοτήτων MS Project χρησιμοποιώντας το Aspose.Tasks.
## Προαπαιτούμενα
Πριν εμβαθύνουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Java Development Kit (JDK)
   - Βεβαιωθείτε ότι το JDK είναι εγκατεστημένο στο σύστημά σας.
   -  Μπορείτε να το κατεβάσετε από[εδώ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks για Java Library
   - Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks για Java στο έργο σας.
   -  Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Αρχικά, εισαγάγετε τα απαραίτητα πακέτα στο αρχείο Java σας:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Ας αναλύσουμε τη διαδικασία σε διαχειρίσιμα βήματα:
## Βήμα 1: Φόρτωση αρχείου έργου
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Βήμα 2: Εμφάνιση προεπιλεγμένων ιδιοτήτων
```java
// Εμφάνιση προεπιλεγμένων ιδιοτήτων
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Βήμα 3: Ορίστε τις προεπιλεγμένες ιδιότητες
```java
// Ορισμός προεπιλεγμένων ιδιοτήτων
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
## Βήμα 4: Αποθήκευση έργου σε μορφή XML
```java
// Αποθηκεύστε το έργο σε μορφή XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Βήμα 5: Εμφάνιση αποτελεσμάτων
```java
// Εμφάνιση του αποτελέσματος της μετατροπής.
System.out.println("Process completed Successfully");
```
Ακολουθώντας αυτά τα βήματα, μπορείτε να διαχειριστείτε αποτελεσματικά τις προεπιλεγμένες ιδιότητες του MS Project χρησιμοποιώντας το Aspose.Tasks για Java.
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να διαχειριζόμαστε τις προεπιλεγμένες ιδιότητες του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Χρησιμοποιώντας αυτές τις τεχνικές, μπορείτε να βελτιστοποιήσετε τη ροή εργασιών διαχείρισης του έργου σας, βελτιώνοντας την παραγωγικότητα και την οργάνωση.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες γλώσσες προγραμματισμού;
A1: Ναι, το Aspose.Tasks υποστηρίζει διάφορες γλώσσες προγραμματισμού όπως .NET, Python και Java.
### Ε2: Είναι το Aspose.Tasks κατάλληλο τόσο για προσωπική όσο και για εταιρική χρήση;
Α2: Απολύτως! Είτε διαχειρίζεστε μικρά προσωπικά έργα είτε επιχειρηματικές πρωτοβουλίες μεγάλης κλίμακας, το Aspose.Tasks απευθύνεται σε όλους.
### Ε3: Το Aspose.Tasks προσφέρει υποστήριξη πελατών;
A3: Ναι, μπορείτε να βρείτε βοήθεια και υποστήριξη της κοινότητας στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
### Ε4: Μπορώ να δοκιμάσω το Aspose.Tasks πριν από την αγορά;
 Α4: Φυσικά! Μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή από το[δικτυακός τόπος](https://releases.aspose.com/).
### Ε5: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Tasks;
 A5: Μπορείτε να λάβετε μια προσωρινή άδεια από το[σελίδα αγοράς](https://purchase.aspose.com/temporary-license/) για σκοπούς δοκιμών και αξιολόγησης.