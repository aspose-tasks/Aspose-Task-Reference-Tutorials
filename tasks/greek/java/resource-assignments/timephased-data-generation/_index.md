---
date: 2026-01-10
description: Μάθετε πώς να αλλάζετε το περίγραμμα και να δημιουργείτε δεδομένα χρονικής
  φάσης για τις αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks for Java, βελτιώνοντας
  την αποδοτικότητα της διαχείρισης έργων.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Πώς να αλλάξετε το περίγραμμα στο Aspose.Tasks για δεδομένα χρονικής φάσης
url: /el/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Αλλάξετε το Contour στο Aspose.Tasks για Δεδομένα Χρονικής Φάσης

## Εισαγωγή
Σε αυτό το tutorial, θα ανακαλύψετε **πώς να αλλάξετε το contour** για μια ανάθεση πόρου και να δημιουργήσετε δεδομένα χρονικής φάσης χρησιμοποιώντας το Aspose.Tasks for Java. Τα δεδομένα χρονικής φάσης αποκαλύπτουν την κατανομή της εργασίας κατά τη διάρκεια του χρονοδιαγράμματος του έργου, επιτρέποντάς σας να βελτιστοποιήσετε τα προγράμματα, να εξισορροπήσετε τα φορτία εργασίας και να λαμβάνετε αποφάσεις βάσει δεδομένων.

## Γρήγορες Απαντήσεις
- **Τι είναι ένα contour;** Ένα contour εργασίας ορίζει πώς κατανέμεται η προσπάθεια κατά τη διάρκεια μιας εργασίας (π.χ., Flat, Turtle, Bell).  
- **Γιατί να αλλάξω ένα contour;** Για να αντικατοπτρίσει ρεαλιστικά πρότυπα εργασίας όπως η προ-φόρτωση ή η μετα-φόρτωση της προσπάθειας.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for Java (οποιαδήποτε πρόσφατη έκδοση).  
- **Χρειάζομαι άδεια;** Ναι, απαιτείται έγκυρη άδεια Aspose.Tasks για χρήση σε παραγωγή.  
- **Μπορώ να δω τα αποτελέσματα στην κονσόλα;** Το παράδειγμα εκτυπώνει τις ημερομηνίες έναρξης και τις τιμές για κάθε τμήμα χρονικής φάσης.

## Τι σημαίνει «πώς να αλλάξετε το contour»;
Η αλλαγή ενός contour σημαίνει την ενημέρωση της ιδιότητας `WORK_CONTOUR` ενός `ResourceAssignment`. Το Aspose.Tasks υποστηρίζει αρκετά προ‑ορισμένα contours (Flat, Turtle, Bell κ.λπ.) που επηρεάζουν τον τρόπο κατανομής της εργασίας στο χρόνο.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για τη δημιουργία δεδομένων χρονικής φάσης;
- **Ακριβής αναφορά:** Εξαγωγή ακριβούς κατανομής εργασίας για εργαλεία αναφοράς.  
- **Σχεδιασμός σεναρίων:** Δοκιμή διαφορετικών contours χωρίς αλλαγή του αρχικού χρονοδιαγράμματος.  
- **Αυτοματοποίηση:** Ενσωμάτωση σε CI pipelines για αυτόματη επαλήθευση της υγείας του έργου.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι διαθέτετε τα παρακάτω προαπαιτούμενα:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε και να το εγκαταστήσετε από [εδώ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks for Java Library: Πρέπει να έχετε τη βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να την κατεβάσετε από την [ιστοσελίδα](https://releases.aspose.com/tasks/java/).

## Εισαγωγή Πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα για εργασία με το Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Βήμα 1: Ανάγνωση του Πηγαίου Αρχείου MPP
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Βήμα 2: Λήψη Εργασίας και Ανάθεσης Πόρου
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Πώς να Αλλάξετε το Contour – Flat (Προεπιλογή)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Πώς να Αλλάξετε το Contour – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Συχνά Προβλήματα & Συμβουλές
- **Το contour δεν ενημερώνεται;** Βεβαιωθείτε ότι καλείτε `firstRA.set(Asn.WORK_CONTOUR, …)` *πριν* την ανάκτηση των δεδομένων χρονικής φάσης.  
- **Απρόσμενες τιμές;** Επαληθεύστε ότι οι ημερομηνίες έναρξης και λήξης της εργασίας έχουν οριστεί σωστά στο πηγαίο MPP.  
- **Συμβουλή απόδοσης:** Επαναχρησιμοποιήστε την ίδια παρουσία `Project` όταν επαναλαμβάνετε πολλαπλά contours για να αποφύγετε περιττές ενέργειες I/O αρχείων.

## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες βιβλιοθήκες Java;
Ναι, το Aspose.Tasks μπορεί να ενσωματωθεί με άλλες βιβλιοθήκες Java για ενίσχυση των δυνατοτήτων διαχείρισης έργων.

### Είναι το Aspose.Tasks κατάλληλο για μεγάλης κλίμακας εταιρικά έργα;
Απολύτως, το Aspose.Tasks έχει σχεδιαστεί για να χειρίζεται έργα κάθε μεγέθους, συμπεριλαμβανομένων μεγάλων εταιρικών πρωτοβουλιών.

### Παρέχει το Aspose.Tasks υποστήριξη για διαφορετικές μορφές αρχείων έργου;
Ναι, το Aspose.Tasks υποστηρίζει μια ποικιλία μορφών, όπως MPP, XML και MPX.

### Μπορώ να προσαρμόσω τα contours εργασίας σύμφωνα με τις απαιτήσεις του έργου μου;
Ναι, μπορείτε να ορίσετε προσαρμοσμένα contours εργασίας ώστε να ταιριάζουν σε συγκεκριμένες ανάγκες χρονοπρογραμματισμού.

### Υπάρχει φόρουμ κοινότητας όπου μπορώ να λάβω βοήθεια για το Aspose.Tasks;
Ναι, μπορείτε να επισκεφθείτε το [φόρουμ Aspose.Tasks](https://forum.aspose.com/c/tasks/15) για υποστήριξη και συζητήσεις.

---

**Τελευταία Ενημέρωση:** 2026-01-10  
**Δοκιμασμένο Με:** Aspose.Tasks for Java (τελευταία έκδοση)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}