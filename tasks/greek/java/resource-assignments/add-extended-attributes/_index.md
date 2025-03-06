---
title: Mastering Project Manipulation με Aspose.Tasks για Java
linktitle: Προσθέστε εκτεταμένα χαρακτηριστικά σε αναθέσεις πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να γράφετε αποτελεσματικά πληροφορίες MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Οδηγός βήμα προς βήμα για προγραμματιστές Java.
weight: 10
url: /el/java/resource-assignments/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Project Manipulation με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη χρήση του Aspose.Tasks για Java, μιας ισχυρής βιβλιοθήκης για τον προγραμματισμό των αρχείων του Microsoft Project. Θα εστιάσουμε σε μια βασική εργασία: τη σύνταξη πληροφοριών MS Project χρησιμοποιώντας το Aspose.Tasks. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε το ταξίδι σας στον προγραμματισμό Java, αυτός ο οδηγός θα σας καθοδηγήσει βήμα προς βήμα στη διαδικασία.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks for Java Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks for Java. Μπορείτε να το αποκτήσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Ολοκληρωμένο περιβάλλον ανάπτυξης (IDE): Επιλέξτε ένα IDE της προτίμησής σας. Προτείνουμε το IntelliJ IDEA ή το Eclipse.

## Εισαγωγή πακέτων
Πρώτα, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
#Ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα:
## Βήμα 1: Ρύθμιση καταλόγου δεδομένων
Καθορίστε τον κατάλογο όπου θα αποθηκευτούν τα δεδομένα του έργου σας.
```java
String dataDir = "Your Data Directory";
```
## Βήμα 2: Δημιουργία παρουσίας έργου
Αρχικοποιήστε ένα νέο παράδειγμα έργου.
```java
Project project = new Project();
```
## Βήμα 3: Ορισμός ιδιοτήτων πληροφοριών έργου
Ορίστε ιδιότητες για το έργο, όπως ημερομηνία έναρξης, χρονοδιάγραμμα από την έναρξη και ημερομηνία κατάστασης.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## Βήμα 4: Αποθήκευση έργου ως XML
Αποθηκεύστε το έργο με τις ενημερωμένες πληροφορίες ως αρχείο XML.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να γράφετε πληροφορίες MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Με αυτή τη νέα γνώση, μπορείτε να αυτοματοποιήσετε διάφορες εργασίες που σχετίζονται με αρχεία Microsoft Project, βελτιώνοντας την παραγωγικότητά σας ως προγραμματιστής Java.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για Java για την ανάγνωση αρχείων MS Project;
Α: Ναι, το Aspose.Tasks για Java παρέχει ισχυρές λειτουργίες τόσο για ανάγνωση όσο και για εγγραφή αρχείων MS Project.
### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικές εκδόσεις του MS Project;
Α: Οπωσδήποτε, το Aspose.Tasks για Java υποστηρίζει διάφορες εκδόσεις του MS Project, διασφαλίζοντας τη συμβατότητα μεταξύ διαφορετικών μορφών αρχείων.
### Ε: Υπάρχουν περιορισμοί στη δοκιμαστική έκδοση του Aspose.Tasks για Java;
Α: Ενώ η δοκιμαστική έκδοση σάς επιτρέπει να εξερευνήσετε τις δυνατότητες της βιβλιοθήκης, έχει ορισμένους περιορισμούς, όπως υδατογραφήματα σε αρχεία εξόδου.
### Ε: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks για Java;
 Α: Μπορείτε να ζητήσετε βοήθεια από το φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Tasks για Java;
 Α: Ναι, οι προσωρινές άδειες είναι διαθέσιμες για βραχυπρόθεσμη χρήση. Μπορείτε να αποκτήσετε ένα από[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
