---
title: Επανάληψη μέσω μη ριζικών πόρων στο Aspose.Tasks
linktitle: Επανάληψη μέσω μη ριζικών πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να κάνετε αποτελεσματική επανάληψη σε πόρους που δεν είναι ριζικοί σε αρχεία Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιώστε τη διαδικασία ανάπτυξής σας.
weight: 12
url: /el/java/resource-management/iterate-non-root-resources/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Επανάληψη μέσω μη ριζικών πόρων στο Aspose.Tasks

## Εισαγωγή
Το Aspose.Tasks για Java είναι μια ισχυρή βιβλιοθήκη που παρέχει στους προγραμματιστές τα εργαλεία που χρειάζονται για να χειριστούν αποτελεσματικά τα αρχεία του Microsoft Project. Με τη διαισθητική διεπαφή και την εκτεταμένη λειτουργικότητά του, το Aspose.Tasks απλοποιεί τη διαδικασία εργασίας με δεδομένα έργου, επιτρέποντας στους προγραμματιστές να επικεντρωθούν στη δημιουργία ισχυρών εφαρμογών.
## Προαπαιτούμενα
Πριν ξεκινήσετε τη χρήση του Aspose.Tasks για Java, βεβαιωθείτε ότι έχετε τα εξής:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το[Ιστοσελίδα Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για Java από το[σελίδα λήψης](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα για να ξεκινήσετε να εργάζεστε με το Aspose.Tasks:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Βήμα 1: Ρυθμίστε τον Κατάλογο δεδομένων
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με τη διαδρομή προς τον κατάλογο όπου είναι αποθηκευμένα τα αρχεία του έργου σας.
## Βήμα 2: Φορτώστε το Αρχείο Έργου
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
 Αυτή η γραμμή προετοιμάζει μια νέα`Project` αντικείμενο με τη φόρτωση του αρχείου έργου με το όνομα`"ResourceCosts.mpp"` από τον καθορισμένο κατάλογο δεδομένων.
## Βήμα 3: Επανάληψη μέσω μη ριζικών πόρων
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Αυτός ο βρόχος επαναλαμβάνεται σε κάθε πόρο του έργου (`prj.getResources()`). Εάν ο πόρος είναι πόρος ρίζας, μεταβαίνει στην επόμενη επανάληψη. Διαφορετικά, εκτυπώνει το όνομα του πόρου που δεν είναι ρίζας.

## συμπέρασμα
Σε αυτό το σεμινάριο, έχουμε εξερευνήσει τον τρόπο επανάληψης σε πόρους που δεν είναι root χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειριστείτε αποτελεσματικά τα δεδομένα του έργου και να εξορθολογίσετε τη διαδικασία ανάπτυξής σας.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java για τη δημιουργία νέων αρχείων έργου;
Ναι, το Aspose.Tasks παρέχει δυνατότητα δημιουργίας, τροποποίησης και αποθήκευσης αρχείων έργου σε διάφορες μορφές.
### Το Aspose.Tasks υποστηρίζει όλες τις εκδόσεις των αρχείων Microsoft Project;
Το Aspose.Tasks υποστηρίζει μορφές αρχείων Microsoft Project 2003-2019, συμπεριλαμβανομένων MPP, MPT και XML.
### Είναι το Aspose.Tasks συμβατό με πλαίσια Java όπως το Spring;
Ναι, το Aspose.Tasks μπορεί να ενσωματωθεί απρόσκοπτα σε πλαίσια Java όπως το Spring για εφαρμογές εταιρικού επιπέδου.
### Μπορώ να προσαρμόσω τα πεδία δεδομένων έργου χρησιμοποιώντας το Aspose.Tasks;
Οπωσδήποτε, το Aspose.Tasks προσφέρει εκτεταμένα API για την προσαρμογή των πεδίων δεδομένων έργου σύμφωνα με τις απαιτήσεις σας.
### Το Aspose.Tasks παρέχει υποστήριξη και τεκμηρίωση για προγραμματιστές;
Ναι, το Aspose.Tasks προσφέρει ολοκληρωμένη τεκμηρίωση και ένα αποκλειστικό φόρουμ υποστήριξης για να βοηθά τους προγραμματιστές με τυχόν απορίες ή προβλήματα που αντιμετωπίζουν.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
