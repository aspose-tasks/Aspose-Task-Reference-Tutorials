---
title: Διαβάστε το MS Project από την Primavera με Aspose.Tasks για Java
linktitle: Διαβάστε το Project από την Primavera στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαβάζετε αρχεία MS Project από το Primavera XML απρόσκοπτα χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιώστε την αποτελεσματικότητα της διαχείρισης του έργου σας.
type: docs
weight: 20
url: /el/java/project-management/read-primavera/
---
## Εισαγωγή
Στη διαχείριση έργων, η διαλειτουργικότητα μεταξύ διαφορετικών πλατφορμών λογισμικού είναι ζωτικής σημασίας για την απρόσκοπτη ροή εργασίας. Το Aspose.Tasks για Java παρέχει ισχυρή λειτουργικότητα για την ανάγνωση αρχείων Microsoft Project από το Primavera XML. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία ανάγνωσης αρχείων MS Project από την Primavera χρησιμοποιώντας το Aspose.Tasks για Java, επιτρέποντάς σας να εξετάσετε αποτελεσματικά τις ιδιότητες των εργασιών που σχετίζονται με το Primavera.
## Προαπαιτούμενα
Πριν προχωρήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks για Java: Κατεβάστε και εγκαταστήστε το Aspose.Tasks για Java από[εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Βήμα 1: Ρύθμιση καταλόγου δεδομένων
```java
String dataDir = "Your Data Directory";
```
 Φροντίστε να αντικαταστήσετε`"Your Data Directory"` με την πραγματική διαδρομή προς τον κατάλογο δεδομένων σας.
## Βήμα 2: Διαβάστε το Project από την Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Φροντίστε να αντικαταστήσετε`"PrimaveraProject.xml"` με το πραγματικό όνομα του αρχείου σας Primavera XML.
## Βήμα 3: Επανάληψη μέσω εργασιών και ανάκτηση ειδικών ιδιοτήτων Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Αυτός ο κώδικας επαναλαμβάνεται σε κάθε εργασία στο έργο, εκτυπώνοντας σχετικές ιδιότητες που αφορούν συγκεκριμένα το Primavera.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να διαβάζετε αρχεία MS Project από το Primavera XML χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η λειτουργικότητα επιτρέπει την απρόσκοπτη ενσωμάτωση και ανάλυση των δεδομένων έργου σε διαφορετικές πλατφόρμες, βελτιώνοντας τη συνολική αποτελεσματικότητα διαχείρισης έργου.
## Συχνές ερωτήσεις
### Ε: Μπορώ να τροποποιήσω τις ιδιότητες των εργασιών που σχετίζονται με το Primavera χρησιμοποιώντας το Aspose.Tasks για Java;
Α: Ναι, το Aspose.Tasks για Java παρέχει API για την τροποποίηση των ιδιοτήτων των εργασιών που σχετίζονται με το Primavera, όπως απαιτείται.
### Ε: Το Aspose.Tasks για Java υποστηρίζει την ανάγνωση άλλων μορφών αρχείων έργου;
Α: Ναι, το Aspose.Tasks για Java υποστηρίζει την ανάγνωση διαφόρων μορφών αρχείων έργου, συμπεριλαμβανομένων MPP, XML και Primavera XML.
### Ε: Είναι το Aspose.Tasks για Java κατάλληλο για εφαρμογές διαχείρισης έργων σε εταιρικό επίπεδο;
Α: Απολύτως, το Aspose.Tasks για Java προσφέρει ισχυρές δυνατότητες και επεκτασιμότητα, καθιστώντας το κατάλληλο για εφαρμογές διαχείρισης έργων σε επίπεδο επιχείρησης.
### Ε: Μπορώ να εξαγάγω πληροφορίες πόρων από έργα Primavera χρησιμοποιώντας το Aspose.Tasks για Java;
Α: Ναι, το Aspose.Tasks για Java σάς επιτρέπει να εξάγετε πληροφορίες πόρων μαζί με λεπτομέρειες εργασιών από έργα Primavera.
### Ε: Πού μπορώ να βρω πρόσθετη υποστήριξη ή τεκμηρίωση για το Aspose.Tasks για Java;
 Α: Μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και πρόσβαση σε φόρουμ για υποστήριξη στο[Aspose.Tasks για τεκμηρίωση Java](https://reference.aspose.com/tasks/java/) σελίδα.