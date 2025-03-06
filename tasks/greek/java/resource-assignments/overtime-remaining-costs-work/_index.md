---
title: Παρακολουθήστε τις υπερωρίες, το υπόλοιπο κόστος και την εργασία στο Aspose.Tasks
linktitle: Παρακολουθήστε τις υπερωρίες, το υπόλοιπο κόστος και την εργασία στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να παρακολουθείτε τις υπερωρίες, το υπόλοιπο κόστος και να εργάζεστε σε έργα Java χρησιμοποιώντας το Aspose.Tasks. Εύκολα βήματα για αποτελεσματική διαχείριση έργου.
weight: 18
url: /el/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Παρακολουθήστε τις υπερωρίες, το υπόλοιπο κόστος και την εργασία στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθουμε πώς να χρησιμοποιούμε το Aspose.Tasks για Java για την παρακολούθηση των υπερωριών, των υπολειπόμενων δαπανών και της εργασίας σε ένα έργο. Αυτό μπορεί να είναι ανεκτίμητο για τους διαχειριστές έργων και τους επικεφαλής της ομάδας για να διασφαλίσουν ότι τα έργα παραμένουν σε καλό δρόμο και εντός του προϋπολογισμού.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Java Development Kit (JDK): Το Aspose.Tasks για Java απαιτεί Java SE 6 ή νεότερη έκδοση.
2.  Aspose.Tasks for Java Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από[εδώ](https://releases.aspose.com/tasks/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Οποιοδήποτε Java IDE όπως το Eclipse, το IntelliJ IDEA ή το NetBeans.

## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο αρχείο Java σας:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Βήμα 1: Ρυθμίστε τον Κατάλογο δεδομένων
Καθορίστε τον κατάλογο όπου βρίσκεται το αρχείο του έργου σας:
```java
String dataDir = "Your Data Directory";
```
 Αντικαθιστώ`"Your Data Directory"` με τη διαδρομή προς το αρχείο του έργου σας.
## Βήμα 2: Φορτώστε το έργο
 Στιγμιότυπο α`Project` αντικείμενο και φορτώστε το αρχείο του έργου:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Αντικαθιστώ`"ResourceAssignmentOvertimes.mpp"` με το όνομα του αρχείου του έργου σας.
## Βήμα 3: Επανάληψη μέσω αναθέσεων πόρων
Περιηγηθείτε σε κάθε ανάθεση πόρων στο έργο:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Βήμα 4: Εκτύπωση κόστους υπερωριών και εργασίας
Ανακτήστε και εκτυπώστε το κόστος και την εργασία υπερωριών για κάθε ανάθεση πόρων:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Βήμα 5: Εκτύπωση υπολειπόμενων δαπανών και εργασίας
Ανακτήστε και εκτυπώστε το υπόλοιπο κόστος και εργαστείτε για κάθε ανάθεση πόρων:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Βήμα 6: Εκτυπώστε το υπόλοιπο κόστος υπερωριών και εργασία
Ανακτήστε και εκτυπώστε το υπόλοιπο κόστος υπερωρίας και εργασία για κάθε ανάθεση πόρων:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## συμπέρασμα
Η παρακολούθηση των υπερωριών, των υπολειπόμενων δαπανών και της εργασίας σε ένα έργο είναι ζωτικής σημασίας για την επιτυχή διαχείριση του έργου. Με το Aspose.Tasks για Java, μπορείτε εύκολα να έχετε πρόσβαση και να παρακολουθείτε αυτές τις πληροφορίες, διασφαλίζοντας ότι τα έργα σας παραμένουν εντός χρονοδιαγράμματος και εντός του προϋπολογισμού.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java με άλλες βιβλιοθήκες Java;
Ναι, το Aspose.Tasks για Java είναι συμβατό με άλλες βιβλιοθήκες και πλαίσια Java.
### Το Aspose.Tasks υποστηρίζει διαφορετικές μορφές αρχείων έργου;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων έργου, συμπεριλαμβανομένων MPP, XML και άλλων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω υποστήριξη εάν αντιμετωπίσω προβλήματα;
 Μπορείτε να επισκεφτείτε το φόρουμ Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15) για υποστήριξη.
### Πώς μπορώ να αγοράσω άδεια χρήσης για το Aspose.Tasks;
 Μπορείτε να αγοράσετε άδεια από[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
