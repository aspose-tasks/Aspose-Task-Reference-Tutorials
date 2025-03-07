---
title: Δημιουργήστε δεδομένα χρονικής φάσης στο Aspose.Tasks
linktitle: Δημιουργήστε δεδομένα χρονικής φάσης για αναθέσεις πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να δημιουργείτε δεδομένα χρονικής φάσης για αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιώστε την αποτελεσματικότητα της διαχείρισης έργου με αυτόν τον περιεκτικό οδηγό.
weight: 24
url: /el/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργήστε δεδομένα χρονικής φάσης στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία δημιουργίας δεδομένων χρονικής φάσης για αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks για Java. Τα δεδομένα χρονικής φάσης παρέχουν πολύτιμες πληροφορίες για τον τρόπο κατανομής των πόρων με την πάροδο του χρόνου σε ένα έργο, βοηθώντας τους διαχειριστές του έργου να λαμβάνουν τεκμηριωμένες αποφάσεις.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να κατεβάσετε και να εγκαταστήσετε το JDK από[εδώ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java Library: Πρέπει να έχετε τη βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα για να δουλέψουμε με το Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Βήμα 1: Διαβάστε το αρχείο προέλευσης MPP
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Data Directory";
// Διαβάστε το αρχείο MPP προέλευσης
Project project = new Project(dataDir + "project.mpp");
```
## Βήμα 2: Λάβετε ανάθεση εργασιών και πόρων
```java
// Αποκτήστε την πρώτη εργασία του Έργου
Task task = project.getRootTask().getChildren().getById(1);
// Λάβετε την πρώτη ανάθεση πόρων του έργου
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Βήμα 3: Δημιουργήστε δεδομένα χρονικής φάσης με επίπεδο περίγραμμα
```java
// Το επίπεδο περίγραμμα είναι το προεπιλεγμένο περίγραμμα
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 4: Αλλάξτε το περίγραμμα σε Χελώνα
```java
// Αλλάξτε το περίγραμμα σε Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 5: Αλλάξτε το περίγραμμα σε Backloaded
```java
// Αλλάξτε το περίγραμμα σε Backloaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 6: Αλλάξτε το Contour σε FrontLoaded
```java
// Αλλάξτε το περίγραμμα σε FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 7: Αλλάξτε το περίγραμμα σε Bell
```java
// Αλλάξτε το περίγραμμα σε Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 8: Αλλάξτε το περίγραμμα σε EarlyPeak
```java
// Αλλάξτε το περίγραμμα σε EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 9: Αλλάξτε το Contour σε LatePeak
```java
// Αλλαγή περιγράμματος σε LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Βήμα 10: Αλλάξτε το περίγραμμα σε DoublePeak
```java
// Αλλάξτε το περίγραμμα σε DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε καλύψει τον τρόπο δημιουργίας δεδομένων χρονικής φάσης για αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks για Java. Η κατανόηση διαφορετικών περιγραμμάτων εργασίας μπορεί να βοηθήσει τους διαχειριστές έργων να διαχειριστούν αποτελεσματικά την κατανομή πόρων και τον προγραμματισμό στα έργα τους.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks με άλλες βιβλιοθήκες Java;
Ναι, το Aspose.Tasks μπορεί να ενσωματωθεί με άλλες βιβλιοθήκες Java για τη βελτίωση των δυνατοτήτων διαχείρισης έργου.
### Είναι το Aspose.Tasks κατάλληλο για μεγάλης κλίμακας εταιρικά έργα;
Οπωσδήποτε, το Aspose.Tasks έχει σχεδιαστεί για να χειρίζεται έργα όλων των μεγεθών, συμπεριλαμβανομένων μεγάλων επιχειρηματικών έργων.
### Το Aspose.Tasks παρέχει υποστήριξη για διαφορετικές μορφές αρχείων έργου;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων έργου, συμπεριλαμβανομένων των MPP, XML και MPX.
### Μπορώ να προσαρμόσω τα περιγράμματα εργασίας σύμφωνα με τις απαιτήσεις του έργου μου;
Ναι, το Aspose.Tasks επιτρέπει στους χρήστες να ορίζουν προσαρμοσμένα περιγράμματα εργασίας για να ταιριάζουν στις συγκεκριμένες ανάγκες του έργου τους.
### Υπάρχει κάποιο φόρουμ κοινότητας όπου μπορώ να λάβω βοήθεια με το Aspose.Tasks;
 Ναι, μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για υποστήριξη και συζητήσεις.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
