---
title: Κλίμακα ποσοστού ανάγνωσης και εγγραφής για αναθέσεις πόρων στο Aspose.Tasks
linktitle: Κλίμακα ποσοστού ανάγνωσης και εγγραφής για αναθέσεις πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαχειρίζεστε αποτελεσματικά την κλίμακα ποσοστού αναθέσεων πόρων στο Aspose.Tasks για Java με αυτό το ολοκληρωμένο σεμινάριο.
weight: 20
url: /el/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Κλίμακα ποσοστού ανάγνωσης και εγγραφής για αναθέσεις πόρων στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαχείριση της κλίμακας ρυθμού ανάθεσης πόρων χρησιμοποιώντας το Aspose.Tasks για Java, μια ισχυρή βιβλιοθήκη για εργασία με αρχεία Microsoft Project μέσω προγραμματισμού. Ακολουθώντας αυτά τα βήματα, θα μπορείτε να χειρίζεστε αποτελεσματικά τις ρυθμίσεις κλίμακας ρυθμού για αναθέσεις πόρων στις εφαρμογές σας Java.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε εγκατεστημένο το Java Development Kit (JDK) στο σύστημά σας.
2.  Aspose.Tasks for Java Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for Java από[εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Αρχικά, πρέπει να εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με τις λειτουργίες Aspose.Tasks. 
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
## Βήμα 1: Ρυθμίστε το έργο σας
Ξεκινήστε ρυθμίζοντας το έργο σας Java και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks στις εξαρτήσεις σας.
## Βήμα 2: Φορτώστε το Αρχείο Έργου
Φορτώστε το αρχείο Project με το οποίο θέλετε να εργαστείτε στην εφαρμογή Java.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Βήμα 3: Προσθέστε μια εργασία
Προσθέστε μια νέα εργασία στο έργο σας.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Βήμα 4: Καθορισμός πόρων
Ορίστε τους υλικούς και μη πόρους και προσδιορίστε τους τύπους τους.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Βήμα 5: Εκχώρηση πόρων στο Task
Αντιστοιχίστε τους προηγουμένως καθορισμένους πόρους στην εργασία μαζί με τους τύπους κλίμακας ποσοστού τους.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Βήμα 6: Αποθηκεύστε το έργο
Αποθηκεύστε το έργο με τις τροποποιημένες αναθέσεις πόρων.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Βήμα 7: Ανάκτηση αναθέσεων πόρων
Φορτώστε ξανά το αποθηκευμένο έργο και ανακτήστε αναθέσεις πόρων για να επαληθεύσετε τις ρυθμίσεις κλίμακας ρυθμού.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## συμπέρασμα
Η διαχείριση της κλίμακας ποσοστού αναθέσεων πόρων στο Aspose.Tasks για Java είναι ζωτικής σημασίας για την αποτελεσματική διαχείριση έργου. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα, μπορείτε να χειρίζεστε απρόσκοπτα τις ρυθμίσεις κλίμακας ρυθμού για αναθέσεις πόρων στις εφαρμογές σας Java.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java με οποιοδήποτε Java IDE;
Α: Ναι, το Aspose.Tasks για Java είναι συμβατό με όλα τα κύρια Java IDE, συμπεριλαμβανομένων των IntelliJ IDEA, Eclipse και NetBeans.
### Ε2: Το Aspose.Tasks υποστηρίζει άλλες μορφές αρχείων εκτός από το MPP;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων, συμπεριλαμβανομένων MPP, XML και HTML.
### Ε3: Είναι το Aspose.Tasks κατάλληλο για διαχείριση έργου σε επίπεδο επιχείρησης;
Α: Απολύτως, το Aspose.Tasks προσφέρει ολοκληρωμένες δυνατότητες για τη διαχείριση έργων οποιασδήποτε κλίμακας, καθιστώντας το κατάλληλο για διαχείριση έργων σε επίπεδο επιχείρησης.
### Ε4: Μπορώ να προσαρμόσω τις αναθέσεις πόρων πέρα από την κλίμακα τιμών;
Α: Ναι, το Aspose.Tasks παρέχει εκτεταμένες δυνατότητες για την προσαρμογή των αναθέσεων πόρων, συμπεριλαμβανομένων των προσαρμογών κόστους, εργασίας και διάρκειας.
### Ε5: Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη Aspose.Tasks;
 Α: Ναι, μπορείτε να βρείτε υποστήριξη και να αλληλεπιδράσετε με άλλους χρήστες στο φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
