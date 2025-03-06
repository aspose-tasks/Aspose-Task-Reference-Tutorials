---
title: Ανάγνωση δεδομένων έργου από τη βάση δεδομένων MS Project στο Aspose.Tasks
linktitle: Ανάγνωση δεδομένων έργου από τη βάση δεδομένων Microsoft Project στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να διαβάζετε δεδομένα έργου από τη βάση δεδομένων Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Οδηγός βήμα προς βήμα με παραδείγματα κώδικα.
weight: 12
url: /el/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάγνωση δεδομένων έργου από τη βάση δεδομένων MS Project στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε τον τρόπο ανάγνωσης δεδομένων έργου από μια βάση δεδομένων έργου Microsoft χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι ένα ισχυρό Java API που επιτρέπει στους προγραμματιστές να χειρίζονται έγγραφα του Microsoft Project χωρίς να χρειάζεται να εγκατασταθεί το Microsoft Project. Ακολουθώντας τα βήματα που περιγράφονται σε αυτόν τον οδηγό, θα μάθετε πώς να εξάγετε αποτελεσματικά δεδομένα έργου από μια βάση δεδομένων και να τα αποθηκεύετε στην επιθυμητή μορφή.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Βασικές γνώσεις προγραμματισμού Java.
2. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
3. Λήψη και διαμόρφωση της βιβλιοθήκης Aspose.Tasks για Java στο έργο σας.

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## Βήμα 1: Ρύθμιση σύνδεσης βάσης δεδομένων
Αρχικά, πρέπει να ρυθμίσετε τη σύνδεση με τη βάση δεδομένων του Microsoft Project. Αυτό περιλαμβάνει τον καθορισμό της διεύθυνσης URL της βάσης δεδομένων, του ονόματος διακομιστή, του αριθμού θύρας, του ονόματος βάσης δεδομένων, του ονόματος χρήστη και του κωδικού πρόσβασης.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Βήμα 2: Προσθήκη προγράμματος οδήγησης JDBC
Στη συνέχεια, πρέπει να προσθέσετε το πρόγραμμα οδήγησης JDBC στο έργο σας. Αυτό το πρόγραμμα οδήγησης διευκολύνει την επικοινωνία μεταξύ εφαρμογών Java και της βάσης δεδομένων του Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Βήμα 3: Διαβάστε τα δεδομένα έργου
 Τώρα, δημιουργήστε ένα`Project` αντικείμενο και φόρτωση δεδομένων έργου από τη βάση δεδομένων χρησιμοποιώντας τις προηγουμένως καθορισμένες ρυθμίσεις.
```java
Project project = new Project(settings);
```
## Βήμα 4: Αποθήκευση δεδομένων έργου
Τέλος, αποθηκεύστε τα δεδομένα του έργου στην επιθυμητή μορφή. Σε αυτό το παράδειγμα, το αποθηκεύουμε ως αρχείο XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Συγχαρητήρια! Έχετε διαβάσει με επιτυχία τα δεδομένα έργου από μια βάση δεδομένων Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java.

## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τη διαδικασία ανάγνωσης δεδομένων έργου από μια βάση δεδομένων έργου Microsoft χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας τα βήματα που περιγράφονται, μπορείτε να εξαγάγετε απρόσκοπτα πληροφορίες έργου και να τις χειρίζεστε σύμφωνα με τις απαιτήσεις σας. Το Aspose.Tasks απλοποιεί τον χειρισμό των εγγράφων του Microsoft Project, επιτρέποντας την αποτελεσματική εξαγωγή και χειρισμό δεδομένων.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks να χρησιμοποιηθεί για την ανάγνωση δεδομένων έργου από άλλες βάσεις δεδομένων εκτός από το Microsoft Project;
Α: Ναι, το Aspose.Tasks υποστηρίζει την ανάγνωση δεδομένων έργου από διάφορες πηγές, συμπεριλαμβανομένων των αρχείων XML, των βάσεων δεδομένων Primavera και Microsoft Project.
### Ε: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις του Microsoft Project;
Α: Ναι, το Aspose.Tasks έχει σχεδιαστεί για να λειτουργεί με διαφορετικές εκδόσεις του Microsoft Project, διασφαλίζοντας συμβατότητα και απρόσκοπτη ενσωμάτωση.
### Ε: Μπορώ να χειριστώ τα δεδομένα του έργου πριν τα αποθηκεύσω;
Α: Απολύτως, το Aspose.Tasks παρέχει ένα ευρύ φάσμα δυνατοτήτων για τον χειρισμό δεδομένων έργου, όπως προσθήκη εργασιών, ενημέρωση πόρων και ρύθμιση ιδιοτήτων έργου.
### Ε: Το Aspose.Tasks υποστηρίζει πολλαπλές μορφές εξόδου;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές εξόδου, όπως XML, PDF, HTML και μορφές εικόνας όπως PNG και JPEG.
### Ε: Πού μπορώ να βρω περαιτέρω υποστήριξη ή βοήθεια με το Aspose.Tasks;
 Α: Για πρόσθετη υποστήριξη ή βοήθεια, μπορείτε να επισκεφτείτε το φόρουμ Aspose.Tasks ή να εξερευνήσετε την τεκμηρίωση που είναι διαθέσιμη στον ιστότοπο[εδώ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
