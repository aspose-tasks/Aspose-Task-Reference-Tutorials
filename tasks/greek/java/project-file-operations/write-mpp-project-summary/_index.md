---
date: 2025-12-23
description: Μάθετε πώς να δημιουργείτε σύνοψη MPP και να ενημερώνετε τον συγγραφέα
  του έργου χρησιμοποιώντας το Aspose.Tasks για Java. Ορίστε και ανακτήστε τις πληροφορίες
  του έργου με ευκολία.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να δημιουργήσετε σύνοψη MPP και να ενημερώσετε τον συγγραφέα του έργου
  με το Aspose.Tasks
url: /el/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Γράψτε Περίληψη Έργου MPP στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial, θα **create MPP summary** πληροφορίες για ένα αρχείο Microsoft Project και θα μάθετε πώς να **update project author** λεπτομέρειες χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks για Java. Είτε δημιουργείτε ένα εργαλείο διαχείρισης έργων είτε αυτοματοποιείτε την αναφορά, ο προγραμματιστικός έλεγχος των ιδιοτήτων περίληψης εξοικονομεί χρόνο και εξασφαλίζει συνέπεια σε όλα τα έργα σας.

## Γρήγορες Απαντήσεις
- **What does “create MPP summary” mean?** Σημαίνει τον ορισμό των υψηλού επιπέδου ιδιοτήτων του έργου (author, revision, keywords, κ.λπ.) που εμφανίζονται στο παράθυρο Project Summary Information του Microsoft Project.  
- **Which library handles this?** Η Aspose.Tasks for Java παρέχει ένα fluent API για ανάγνωση και εγγραφή αυτών των ιδιοτήτων.  
- **Do I need a license?** Διατίθεται δωρεάν δοκιμαστική έκδοση, αλλά απαιτείται εμπορική άδεια για παραγωγική χρήση.  
- **Can I also change the author after the file is saved?** Ναι – μπορείτε να **update project author** καλώντας `project.set(Prj.AUTHOR, "New Author")` και στη συνέχεια να αποθηκεύσετε ξανά το αρχείο.  
- **What file formats are supported?** Υποστηρίζονται πλήρως τόσο τα MPP όσο και XML (SaveFileFormat.Xml).

## Τι είναι η δημιουργία περίληψης MPP;
Η δημιουργία μιας MPP summary περιλαμβάνει την πληρότητα των μεταδεδομένων του έργου—author, revision number, keywords, comments, creation date και printed date. Αυτά τα μεταδεδομένα αποθηκεύονται μέσα στην εγγραφή Project Summary Information και εμφανίζονται στην ενότητα **File → Info** του Microsoft Project.

## Γιατί να ενημερώσετε τον συγγραφέα του έργου;
Η διατήρηση ακριβούς πληροφορίας **project author** είναι κρίσιμη για τα αρχεία ελέγχου, τη συνεργασία και την αναφορά. Όταν πολλοί μέλη της ομάδας συμβάλλουν, ίσως χρειαστεί να **update project author** ώστε να αντικατοπτρίζει τις τελευταίες αλλαγές ή να αποδίδει σωστά τη δουλειά.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Java Development Kit (JDK) εγκατεστημένο στον υπολογιστή σας.  
2. Aspose.Tasks for Java – κατεβάστε το από [here](https://releases.aspose.com/tasks/java/).  
3. Ένα IDE όπως IntelliJ IDEA, Eclipse ή NetBeans.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τα απαραίτητα πακέτα στην κλάση Java σας:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Βήμα 1: Ρύθμιση Έργου και Ορισμός Πληροφοριών Περίληψης
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Στον παραπάνω κώδικα **create MPP summary** πεδία όπως author, revision και keywords. Μπορείτε επίσης να **update project author** αργότερα καλώντας `project.set(Prj.AUTHOR, "New Name")`.

## Βήμα 2: Αποθήκευση Πληροφοριών Περίληψης Έργου
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Η αποθήκευση του έργου διατηρεί όλα τα δεδομένα περίληψης που ορίσατε.

## Βήμα 3: Ανάγνωση Πληροφοριών Περίληψης Έργου
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Αυτό το απόσπασμα δείχνει πώς να **read back** τις πληροφορίες περίληψης, επιβεβαιώνοντας ότι η λειτουργία **create MPP summary** ολοκληρώθηκε επιτυχώς.

## Κοινά Προβλήματα και Λύσεις
- **Null values after reading:** Βεβαιωθείτε ότι το έργο αποθηκεύτηκε επιτυχώς πριν το ξαναφορτώσετε. Ελέγξτε τις διαδρομές αρχείων και τα δικαιώματα.  
- **Date formatting differences:** `project.get(Prj.CREATION_DATE)` επιστρέφει ένα `java.util.Date`. Χρησιμοποιήστε `SimpleDateFormat` αν χρειάζεστε προσαρμοσμένη μορφή εμφάνισης.  
- **License not set:** Χωρίς έγκυρη άδεια, η Aspose.Tasks λειτουργεί σε λειτουργία αξιολόγησης και μπορεί να ενσωματώνει υδατογράφημα. Καταχωρίστε την άδειά σας νωρίς στον κώδικα.

## Συχνές Ερωτήσεις
**Q: Μπορώ να χρησιμοποιήσω την Aspose.Tasks for Java με άλλες βιβλιοθήκες Java;**  
A: Ναι, η Aspose.Tasks for Java μπορεί να ενσωματωθεί άψογα με άλλες βιβλιοθήκες Java για να ενισχύσει τις δυνατότητες διαχείρισης έργων σας.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για την Aspose.Tasks for Java;**  
A: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση από [here](https://releases.aspose.com/).

**Q: Πόσο συχνά ενημερώνεται η Aspose.Tasks for Java;**  
A: Η Aspose.Tasks for Java ενημερώνεται τακτικά για να εξασφαλίσει συμβατότητα με τις τελευταίες εκδόσεις της Java και των αρχείων Microsoft Project.

**Q: Μπορώ να προσαρμόσω περαιτέρω τις πληροφορίες περίληψης του έργου;**  
A: Απόλυτα, η Aspose.Tasks for Java παρέχει εκτενείς επιλογές για προσαρμογή των πληροφοριών περίληψης του έργου σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

**Q: Πού μπορώ να λάβω υποστήριξη για την Aspose.Tasks for Java;**  
A: Μπορείτε να λάβετε υποστήριξη από το φόρουμ της κοινότητας Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Συμπέρασμα
Σε αυτό το tutorial σας δείξαμε πώς να **create MPP summary** δεδομένα, να **update project author**, και να επαληθεύσετε αυτές τις αλλαγές χρησιμοποιώντας την Aspose.Tasks for Java. Με την αυτοματοποίηση αυτών των βημάτων αποκτάτε πλήρη έλεγχο πάνω στα μεταδεδομένα του έργου, καθιστώντας τις εφαρμογές σας πιο ανθεκτικές και τις αναφορές έργου πιο ακριβείς.

---

**Τελευταία Ενημέρωση:** 2025-12-23  
**Δοκιμάστηκε Με:** Aspose.Tasks for Java 24.10  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}