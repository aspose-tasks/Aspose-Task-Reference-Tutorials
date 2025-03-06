---
title: Διαβάστε τις ιδιότητες νομίσματος στα έργα Aspose.Tasks
linktitle: Διαβάστε τις ιδιότητες νομίσματος στα έργα Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να εξάγετε πληροφορίες νομισμάτων από αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Παρέχεται οδηγός βήμα προς βήμα.
weight: 10
url: /el/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαβάστε τις ιδιότητες νομίσματος στα έργα Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθουμε πώς να χρησιμοποιούμε το Aspose.Tasks για Java για την ανάγνωση ιδιοτήτων νομίσματος από αρχεία Microsoft Project. Το Aspose.Tasks είναι ένα ισχυρό Java API που επιτρέπει στους προγραμματιστές να χειρίζονται έγγραφα του Microsoft Project χωρίς να απαιτείται η εγκατάσταση του Microsoft Project. Ακολουθώντας τα βήματα που περιγράφονται παρακάτω, θα μπορείτε να εξάγετε πληροφορίες που σχετίζονται με το νόμισμα χωρίς κόπο.
## Προαπαιτούμενα
Πριν προχωρήσετε σε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks για Java JAR: Κάντε λήψη της βιβλιοθήκης Aspose.Tasks για Java από[εδώ](https://releases.aspose.com/tasks/java/) και να το συμπεριλάβετε στο έργο σας Java.
## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στην τάξη Java:
```java
import com.aspose.tasks.*;
```
## Βήμα 1: Ρυθμίστε τον κατάλογο του έργου σας
Αρχικά, ρυθμίστε τον κατάλογο του έργου σας όπου βρίσκεται το αρχείο Microsoft Project. Μπορείτε να ορίσετε αυτήν τη διαδρομή καταλόγου ως εξής:
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με την πραγματική διαδρομή προς τον κατάλογο του έργου σας.
## Βήμα 2: Δημιουργήστε μια παρουσία προγράμματος ανάγνωσης έργου
 Στιγμιότυπο α`Project` αντικείμενο παρέχοντας τη διαδρομή προς το αρχείο Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Φροντίστε να αντικαταστήσετε`"project.mpp"` με το όνομα του αρχείου MS Project.
## Βήμα 3: Εμφάνιση ιδιοτήτων νομίσματος
Ανάκτηση και εμφάνιση ιδιοτήτων νομίσματος από το αρχείο του έργου:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Αυτό το τμήμα κώδικα ανακτά πληροφορίες όπως κωδικό νομίσματος, ψηφία, σύμβολο και θέση συμβόλου από το αρχείο MS Project και τις εκτυπώνει στην κονσόλα.
## Βήμα 4: Ολοκλήρωση διαδικασίας
Τέλος, εκτυπώστε ένα μήνυμα που υποδεικνύει την επιτυχή ολοκλήρωση της διαδικασίας:
```java
System.out.println("Process completed Successfully");
```
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο ανάγνωσης ιδιοτήτων νομίσματος από αρχεία Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας τα βήματα που περιγράφονται, μπορείτε να εξαγάγετε αβίαστα πληροφορίες που σχετίζονται με το νόμισμα από τα αρχεία του έργου σας μέσω προγραμματισμού, επιτρέποντας την απρόσκοπτη ενσωμάτωση στις εφαρμογές σας Java.
## Συχνές ερωτήσεις
### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;
Α: Το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις του Microsoft Project, συμπεριλαμβανομένων των αρχείων MPP που δημιουργούνται από το MS Project 2003-2021.
### Ε: Μπορώ να τροποποιήσω τις ιδιότητες νομίσματος χρησιμοποιώντας το Aspose.Tasks;
Α: Ναι, το Aspose.Tasks σάς επιτρέπει να διαβάζετε και να τροποποιείτε τις ιδιότητες νομίσματος σε αρχεία MS Project μέσω προγραμματισμού.
### Ε: Είναι το Aspose.Tasks κατάλληλο για εμπορική χρήση;
 Α: Ναι, το Aspose.Tasks είναι μια εμπορική βιβλιοθήκη σχεδιασμένη για επαγγελματική χρήση. Μπορείτε να αγοράσετε μια άδεια[εδώ](https://purchase.aspose.com/buy).
### Ε: Το Aspose.Tasks προσφέρει δωρεάν δοκιμή;
 Α: Ναι, μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να αναζητήσω βοήθεια ή υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να επισκεφτείτε το φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή απορία.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
