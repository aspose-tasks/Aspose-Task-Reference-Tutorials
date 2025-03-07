---
title: Διαβάστε τα δεδομένα χρονικής φάσης για πόρους στο Aspose.Tasks
linktitle: Διαβάστε τα δεδομένα χρονικής φάσης για πόρους στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να εξάγετε δεδομένα χρονικής φάσης από πόρους του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Βήμα προς βήμα φροντιστήριο.
weight: 15
url: /el/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε τα δεδομένα χρονικής φάσης για πόρους στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία ανάγνωσης δεδομένων χρονικής φάσης για πόρους του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η βιβλιοθήκη παρέχει ισχυρές λειτουργίες για τη διαχείριση αρχείων Microsoft Project μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) και ακολουθήστε τις οδηγίες εγκατάστασης.
2.  Aspose.Tasks for Java Library: Κάντε λήψη της βιβλιοθήκης Aspose.Tasks for Java από το[σελίδα λήψης](https://releases.aspose.com/tasks/java/) και ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση.

## Εισαγωγή πακέτων
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Βήμα 1: Ρύθμιση καταλόγου δεδομένων
Αρχικά, ορίστε τον κατάλογο όπου βρίσκεται το αρχείο MS Project.
```java
String dataDir = "Your Data Directory";
```
## Βήμα 2: Διαβάστε το αρχείο προτύπου έργου MS
Καθορίστε το όνομα του αρχείου προτύπου MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Βήμα 3: Διαβάστε το αρχείο εισόδου ως έργο
Διαβάστε το αρχείο εισόδου χρησιμοποιώντας το Aspose.Tasks και φορτώστε το ως αντικείμενο Project.
```java
Project project = new Project(dataDir + fileName);
```
## Βήμα 4: Λήψη πόρων με αναγνωριστικό
Ανακτήστε τον επιθυμητό πόρο από το έργο με το μοναδικό του αναγνωριστικό (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Βήμα 5: Εκτύπωση δεδομένων χρονικής φάσης για εργασία πόρων
Εκτυπώστε τα δεδομένα χρονικής φάσης για εργασία πόρων.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Βήμα 6: Εκτύπωση δεδομένων χρονικής φάσης για το κόστος πόρων
Εκτυπώστε τα δεδομένα χρονικής φάσης για το κόστος πόρων.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να διαβάζουμε δεδομένα χρονικής φάσης για πόρους του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να εξαγάγετε αποτελεσματικά πολύτιμες πληροφορίες από τα αρχεία του έργου σας μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Μπορεί το Aspose.Tasks να χειριστεί άλλους τύπους αρχείων έργου εκτός από το Microsoft Project;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων, όπως MPP, XML και CSV.
### Είναι το Aspose.Tasks συμβατό με διαφορετικά περιβάλλοντα ανάπτυξης Java;
Ναι, το Aspose.Tasks είναι συμβατό με όλα τα κύρια Java IDE και πλαίσια.
### Μπορώ να χειριστώ τα δεδομένα του έργου χρησιμοποιώντας το Aspose.Tasks;
Οπωσδήποτε, το Aspose.Tasks παρέχει εκτεταμένα API για τη δημιουργία, την τροποποίηση και την ανάλυση δεδομένων έργου.
### Είναι το Aspose.Tasks κατάλληλο για έργα σε επίπεδο επιχείρησης;
Ναι, το Aspose.Tasks χρησιμοποιείται ευρέως σε εταιρικά περιβάλλοντα λόγω της αξιοπιστίας και της επεκτασιμότητας του.
### Πού μπορώ να βρω υποστήριξη εάν αντιμετωπίσω προβλήματα κατά τη χρήση του Aspose.Tasks;
 Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για βοήθεια από την κοινότητα και την ομάδα υποστήριξης.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
