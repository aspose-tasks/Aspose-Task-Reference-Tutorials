---
date: 2026-03-29
description: Μάθετε πώς να ορίσετε λέξεις‑κλειδιά και ημερομηνία δημιουργίας σε ένα
  έργο MPP χρησιμοποιώντας το Aspose.Tasks for Java. Οδηγός βήμα‑βήμα με παραδείγματα
  κώδικα.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να ορίσετε λέξεις‑κλειδιά στην περίληψη έργου MPP με το Aspose.Tasks
url: /el/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε λέξεις‑κλειδιά στην περίληψη έργου MPP με το Aspose.Tasks

## Εισαγωγή
Σε αυτό το tutorial θα ανακαλύψετε **πώς να ορίσετε λέξεις‑κλειδιά** και άλλες πληροφορίες περίληψης για ένα αρχείο MPP χρησιμοποιώντας το Aspose.Tasks for Java. Είτε χρειάζεστε να ενσωματώσετε στοιχεία συγγραφέα, αριθμούς αναθεώρησης ή προσαρμοσμένη ημερομηνία δημιουργίας, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα, με έτοιμο κώδικα. Στο τέλος θα μπορείτε να ορίσετε λέξεις‑κλειδιά, να ορίσετε ημερομηνία δημιουργίας java και να ανακτήσετε τα δεδομένα από το αρχείο.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρησιμοποιείται;** Aspose.Tasks for Java  
- **Κύριος σκοπός;** Ορισμός λέξεων‑κλειδιών, πληροφοριών συγγραφέα και ημερομηνίας δημιουργίας σε αρχείο MPP  
- **Πόσα βήματα κώδικα;** Τρία απλά μπλοκ κώδικα (αρχικοποίηση, αποθήκευση, ανάγνωση)  
- **Χρειάζεται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή  
- **Υποστηριζόμενη έκδοση Java;** Java 8 και νεότερη  

## Τι είναι η «ορισμός λέξεων‑κλειδιών» σε αρχείο MPP;
Οι λέξεις‑κλειδιά είναι πεδία μεταδεδομένων που αποθηκεύονται μέσα σε ένα αρχείο Microsoft Project (MPP). Βοηθούν στην κατηγοριοποίηση των έργων, επιτρέπουν γρήγορη αναζήτηση και παρέχουν συμφραζόμενα για εργαλεία downstream. Το Aspose.Tasks εκθέτει την ιδιότητα `Prj.KEYWORDS`, καθιστώντας εύκολο τον προγραμματιστικό ορισμό ή την ενημέρωση αυτής της τιμής.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks for Java για τον ορισμό λέξεων‑κλειδιών και ημερομηνίας δημιουργίας;
* **Πλήρης συμβατότητα .MPP** – λειτουργεί με όλες τις μορφές Project 2007‑2023.  
* **Δεν απαιτείται εγκατάσταση COM ή Office** – καθαρή Java, ιδανική για περιβάλλοντα διακομιστή.  
* **Πλούσιο API** – εκτός από λέξεις‑κλειδιά μπορείτε να ορίσετε συγγραφέα, αναθεώρηση, σχόλια και ημερομηνίες με μία κλήση.  
* **Βελτιστοποιημένη απόδοση** – γρήγορη ανάγνωση/εγγραφή ακόμη και για μεγάλα αρχεία έργου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:
1. **Java Development Kit (JDK)** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Tasks for Java** – κατεβάστε το τελευταίο JAR από [εδώ](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans ή οποιονδήποτε επεξεργαστή προτιμάτε.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις κλάσεις που χρειάζεστε. Αυτές οι εισαγωγές σας δίνουν πρόσβαση στο αντικείμενο `Project`, στην απαρίθμηση `Prj` για πεδία περίληψης και στην απαρίθμηση `SaveFileFormat` για αποθήκευση.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Βήμα 1: Ρύθμιση Έργου και Ορισμός Πληροφοριών Περίληψης
Δημιουργήστε μια παρουσία `Project`, στη συνέχεια χρησιμοποιήστε τη μέθοδο `set` για να γράψετε τα επιθυμητά μεταδεδομένα. Παρατηρήστε πώς **ορίζουμε τις λέξεις‑κλειδιά** και **ορίζουμε ημερομηνία δημιουργίας java** χρησιμοποιώντας ένα αντικείμενο `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Βήμα 2: Αποθήκευση Πληροφοριών Περίληψης Έργου
Αφού συμπληρώσετε τα πεδία, αποθηκεύστε τις αλλαγές. Εδώ αποθηκεύουμε το έργο ως XML για εύκολη επιθεώρηση, αλλά μπορείτε επίσης να το αποθηκεύσετε ξανά ως MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Βήμα 3: Ανάγνωση Πληροφοριών Περίληψης Έργου
Για να επαληθεύσετε ότι τα μεταδεδομένα γράφτηκαν σωστά, φορτώστε ξανά το αρχείο και διαβάστε κάθε ιδιότητα. Αυτό το βήμα δείχνει ότι **η ορισμός λέξεων‑κλειδιών** λειτουργεί από άκρη σε άκρη.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| **NullPointerException στο `project.get(Prj.CREATION_DATE)`** | Το ημερολόγιο δεν είχε οριστεί ποτέ πριν από την αποθήκευση. | Βεβαιωθείτε ότι καλείτε `project.set(Prj.CREATION_DATE, cal.getTime())` πριν από το `save()`. |
| **Οι λέξεις‑κλειδιά δεν εμφανίζονται στη διεπαφή του Microsoft Project** | Το αρχείο αποθηκεύτηκε ως XML και ανοίχθηκε απευθείας στο Project. | Αποθηκεύστε ξανά ως MPP (`SaveFileFormat.MPP`) ή ανοίξτε το XML μέσω *Import* στο Project. |
| **Οι τιμές ημερομηνίας μετατοπίζονται λόγω ζώνης ώρας** | Η Java `Date` περιλαμβάνει πληροφορίες ζώνης ώρας. | Χρησιμοποιήστε `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` εάν χρειάζεστε ημερομηνίες UTC. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks for Java με άλλες βιβλιοθήκες Java;**  
Α: Ναι, το Aspose.Tasks for Java μπορεί να ενσωματωθεί άψογα με άλλες βιβλιοθήκες Java για να ενισχύσει τις δυνατότητες διαχείρισης έργων σας.

**Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks for Java;**  
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση από [εδώ](https://releases.aspose.com/).

**Ε: Πόσο συχνά ενημερώνεται το Aspose.Tasks for Java;**  
Α: Το Aspose.Tasks for Java ενημερώνεται τακτικά για να εξασφαλίζει συμβατότητα με τις τελευταίες εκδόσεις της Java και των αρχείων Microsoft Project.

**Ε: Μπορώ να προσαρμόσω περαιτέρω τις πληροφορίες περίληψης του έργου;**  
Α: Απόλυτα, το Aspose.Tasks for Java παρέχει εκτενείς επιλογές για την προσαρμογή των πληροφοριών περίληψης του έργου σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

**Ε: Πού μπορώ να λάβω υποστήριξη για το Aspose.Tasks for Java;**  
Α: Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας Aspose.Tasks [εδώ](https://forum.aspose.com/c/tasks/15).

---

**Τελευταία ενημέρωση:** 2026-03-29  
**Δοκιμάστηκε με:** Aspose.Tasks for Java 24.11 (τελευταία έκδοση κατά τη συγγραφή)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}