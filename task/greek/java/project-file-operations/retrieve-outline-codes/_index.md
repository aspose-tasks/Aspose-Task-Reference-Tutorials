---
title: Ανάκτηση Κωδικών Περίληψης Έργου MS στο Aspose.Tasks
linktitle: Ανάκτηση κωδικών περίγραμμα στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ανακτάτε κωδικούς περίληψης του Microsoft Project μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιώστε τις δυνατότητες διαχείρισης του έργου σας.
type: docs
weight: 15
url: /el/java/project-file-operations/retrieve-outline-codes/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθουμε πώς να ανακτούμε κωδικούς περίληψης του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Οι κωδικοί περιλήψεων στο MS Project παρέχουν έναν δομημένο τρόπο κατηγοριοποίησης και οργάνωσης εργασιών, πόρων και αναθέσεων έργου. Το Aspose.Tasks είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να χειρίζονται και να διαχειρίζονται αρχεία Microsoft Project μέσω προγραμματισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
### 1. Περιβάλλον Ανάπτυξης Java
Βεβαιωθείτε ότι έχετε εγκαταστήσει το Java Development Kit (JDK) στο σύστημά σας. Μπορείτε να κάνετε λήψη και εγκατάσταση του JDK από τον ιστότοπο της Oracle.
### 2. Aspose.Tasks Library
 Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks στο έργο σας Java. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από το[Σελίδα λήψης Aspose.Tasks για Java](https://releases.aspose.com/tasks/java/).
## Εισαγωγή πακέτων
Πρώτα, εισαγάγετε τα απαραίτητα πακέτα από το Aspose.Tasks στον κώδικα Java σας:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Τώρα ας αναλύσουμε το παρεχόμενο παράδειγμα κώδικα σε πολλά βήματα:
## Βήμα 1: Φορτώστε το έργο
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Σε αυτό το βήμα, φορτώνουμε το αρχείο Microsoft Project σε ένα`Project` αντικείμενο χρησιμοποιώντας το παρεχόμενο όνομα αρχείου.
## Βήμα 2: Ανάκτηση κωδικών περίγραμμα
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Επαναλαμβάνουμε κάθε ορισμό κώδικα περίγραμμα στο έργο.
## Βήμα 3: Πρόσβαση στις Ιδιότητες Κώδικα Περιγράμματος
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Ανακτούμε και εκτυπώνουμε διάφορες ιδιότητες του ορισμού του κώδικα περίγραμμα, όπως το ψευδώνυμο, το αναγνωριστικό πεδίου και το όνομα πεδίου.
## Βήμα 4: Ελέγξτε τον προσαρμοσμένο κωδικό επιχείρησης
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Ελέγχουμε αν ο κωδικός περιγράμματος είναι προσαρμοσμένος κωδικός επιχείρησης και εκτυπώνουμε το αποτέλεσμα ανάλογα.
## Βήμα 5: Εμφάνιση μάσκες κώδικα περιγράμματος
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Επαναλαμβάνουμε κάθε μάσκα που σχετίζεται με τον κώδικα περίγραμμα και εκτυπώνουμε το επίπεδο και την τιμή της μάσκας.
## Βήμα 6: Εμφάνιση τιμών κώδικα περίγραμμα
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Επαναλαμβάνουμε κάθε τιμή κωδικού περιγράμματος και εκτυπώνουμε την περιγραφή, το αναγνωριστικό τιμής, την τιμή και τον τύπο του.
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να ανακτούμε κώδικες περίληψης του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας τα παρεχόμενα βήματα, μπορείτε να αποκτήσετε αποτελεσματική πρόσβαση και να χειριστείτε τους κώδικες περιγράμματος στις εφαρμογές σας Java, επιτρέποντας προηγμένες δυνατότητες διαχείρισης έργου.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java για να τροποποιήσω τους κωδικούς περιγράμματος σε ένα αρχείο Project;
Α: Ναι, το Aspose.Tasks για Java παρέχει API για την τροποποίηση κωδικών περιλήψεων σε αρχεία MS Project μέσω προγραμματισμού.
### Ε2: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.Tasks για Java από το[Ιστότοπος Aspose.Tasks](https://releases.aspose.com/).
### Ε3: Πώς μπορώ να λάβω τεχνική υποστήριξη για το Aspose.Tasks για Java;
 Α: Μπορείτε να λάβετε τεχνική υποστήριξη επισκεπτόμενοι το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) και δημοσιεύστε τις απορίες σας εκεί.
### Ε4: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java από το[σελίδα αγοράς](https://purchase.aspose.com/temporary-license/).
### Ε5: Πού μπορώ να βρω την πλήρη τεκμηρίωση για το Aspose.Tasks για Java;
 Α: Μπορείτε να ανατρέξετε στο[τεκμηρίωση](https://reference.aspose.com/tasks/java/) για λεπτομερείς πληροφορίες σχετικά με τη χρήση του Aspose.Tasks για Java.