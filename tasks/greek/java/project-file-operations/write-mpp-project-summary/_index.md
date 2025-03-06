---
title: Γράψτε τη σύνοψη έργου MPP στο Aspose.Tasks
linktitle: Γράψτε τη σύνοψη έργου MPP στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να γράφετε περιλήψεις έργων MPP σε Java χρησιμοποιώντας το Aspose.Tasks. Ρυθμίστε και ανακτήστε πληροφορίες έργου χωρίς κόπο.
type: docs
weight: 27
url: /el/java/project-file-operations/write-mpp-project-summary/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθουμε πώς να χρησιμοποιούμε το Aspose.Tasks για την Java για τη σύνταξη περιλήψεων έργων MPP. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java για εργασία με αρχεία Microsoft Project. Ακολουθώντας τα βήματα που περιγράφονται παρακάτω, θα μπορείτε να ορίσετε και να ανακτήσετε διάφορες συνοπτικές πληροφορίες σχετικά με ένα έργο χρησιμοποιώντας αυτήν τη βιβλιοθήκη.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks για Java: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Επιλέξτε το IDE που προτιμάτε για ανάπτυξη Java, όπως το IntelliJ IDEA, το Eclipse ή το NetBeans.

## Εισαγωγή πακέτων
Πρώτα, εισαγάγετε τα απαραίτητα πακέτα στην τάξη Java σας:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Βήμα 1: Ρύθμιση έργου και ορισμός πληροφοριών σύνοψης
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
//Αρχικοποιήστε ένα νέο αντικείμενο Project με τη διαδρομή προς το αρχείο του έργου σας
Project project = new Project(dataDir + "project.mpp");
// Ορίστε συνοπτικές πληροφορίες για το έργο
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Ορίστε την ημερομηνία δημιουργίας του έργου
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Ορίστε λέξεις-κλειδιά για το έργο
project.set(Prj.KEYWORDS, "MPP Aspose");
// Ορίστε την τελευταία ημερομηνία εκτύπωσης του έργου
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Βήμα 2: Αποθήκευση πληροφοριών περίληψης έργου
```java
// Αποθηκεύστε το έργο ξανά σε μορφή MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Εμφάνιση μηνύματος επιτυχίας
System.out.println("Process completed Successfully");
```
## Βήμα 3: Διαβάστε τις πληροφορίες περίληψης έργου
```java
// Ανάγνωση πληροφοριών περίληψης έργου
project = new Project(dataDir + "MppAspose.xml");
// Εκτύπωση συγγραφέας του έργου
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Εκτύπωση τελευταίου συγγραφέα του έργου
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Εκτύπωση του αριθμού αναθεώρησης του έργου
System.out.println("Revision: " + project.get(Prj.REVISION));
// Εκτύπωση λέξεων-κλειδιών του έργου
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Εκτύπωση σχολίων του έργου
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Εκτύπωση ημερομηνίας δημιουργίας του έργου
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Εκτύπωση λέξεων-κλειδιών του έργου (ξανά)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Εκτύπωση τελευταίας ημερομηνίας εκτύπωσης του έργου
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε καλύψει πώς να γράφουμε περιλήψεις έργων MPP χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να ορίσετε και να ανακτήσετε αποτελεσματικά διάφορες συνοπτικές πληροφορίες σχετικά με τα αρχεία του έργου σας. Το Aspose.Tasks απλοποιεί τη διαδικασία εργασίας με αρχεία Microsoft Project σε εφαρμογές Java, προσφέροντας ισχυρή λειτουργικότητα και ευκολία στη χρήση.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java με άλλες βιβλιοθήκες Java;
Α: Ναι, το Aspose.Tasks για Java μπορεί να ενσωματωθεί απρόσκοπτα με άλλες βιβλιοθήκες Java για να βελτιώσει τις δυνατότητες διαχείρισης του έργου σας.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης από[εδώ](https://releases.aspose.com/).
### Ε: Πόσο συχνά ενημερώνεται το Aspose.Tasks για Java;
Α: Το Aspose.Tasks για Java ενημερώνεται τακτικά για να διασφαλίζεται η συμβατότητα με τις πιο πρόσφατες εκδόσεις των αρχείων Java και Microsoft Project.
### Ε: Μπορώ να προσαρμόσω περαιτέρω τις πληροφορίες περίληψης του έργου;
Α: Απολύτως, το Aspose.Tasks για Java παρέχει εκτενείς επιλογές για την προσαρμογή των πληροφοριών περίληψης έργου σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.
### Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).