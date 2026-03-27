---
date: 2026-02-18
description: Μάθετε πώς να αποθηκεύσετε το έργο ως PDF και να διαβάσετε τη βάση δεδομένων
  του Microsoft Project με το Aspose.Tasks for Java, καθώς και να συνδεθείτε με το
  Project Server, να μετατρέψετε το έργο σε HTML και να εξάγετε το έργο σε XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Αποθήκευση του έργου ως PDF και ανάγνωση της βάσης δεδομένων του έργου με το
  Aspose.Tasks για Java
url: /el/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση έργου ως PDF και ανάγνωση βάσης δεδομένων Microsoft Project με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το tutorial θα ανακαλύψετε πώς να **διαβάσετε τη βάση δεδομένων Microsoft Project** απευθείας από έναν Microsoft Project Server και στη συνέχεια να **αποθηκεύσετε το έργο ως PDF** χρησιμοποιώντας το Aspose.Tasks Java API. Είτε χρειάζεστε να δημιουργήσετε αναφορές, να μεταφέρετε δεδομένα, είτε να ενσωματώσετε πληροφορίες έργου στις δικές σας εφαρμογές, αυτός ο οδηγός σας οδηγεί βήμα‑βήμα—from τη ρύθμιση της σύνδεσης με τη βάση δεδομένων μέχρι την εξαγωγή του έργου σε PDF, XML ή HTML. Στο τέλος, θα έχετε μια σταθερή, έτοιμη για παραγωγή λύση που λειτουργεί χωρίς την εγκατάσταση του Microsoft Project στον υπολογιστή φιλοξενίας.

## Γρήγορες Απαντήσεις
- **Τι κάνει το Aspose.Tasks;** Παρέχει ένα καθαρό Java API για ανάγνωση, εγγραφή και διαχείριση αρχείων και βάσεων δεδομένων Microsoft Project.  
- **Χρειάζεται να έχω εγκατεστημένο το Microsoft Project;** Όχι, το Aspose.Tasks λειτουργεί ανεξάρτητα από το Microsoft Project.  
- **Τι τύπο βάσης δεδομένων υποστηρίζεται;** Microsoft SQL Server (το backend του Project Server).  
- **Μπορώ να εξάγω σε άλλες μορφές;** Ναι, εκτός από PDF μπορείτε να αποθηκεύσετε σε XML, HTML, CSV και άλλα.  
- **Ποια είναι τα κύρια προαπαιτούμενα;** JDK, βιβλιοθήκη Aspose.Tasks for Java, ο οδηγός JDBC για SQL Server, και διαπιστευτήρια για **σύνδεση με τον Project Server**.

## Τι σημαίνει «ανάγνωση βάσης δεδομένων Microsoft Project»;
Η ανάγνωση μιας βάσης δεδομένων Microsoft Project σημαίνει σύνδεση στο αποθετήριο SQL Server του Project Server, εξαγωγή των αποθηκευμένων δεδομένων έργου και φόρτωση τους σε ένα αντικείμενο `Project` που το Aspose.Tasks μπορεί να διαχειριστεί. Αυτή η προσέγγιση είναι ιδανική για αυτοματοποιημένες αναφορές, μεταφορά δεδομένων ή προσαρμοσμένη ανάλυση.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για Java;
- **Χωρίς εξάρτηση από το Microsoft Project** – εκτελείται σε οποιονδήποτε διακομιστή ή περιβάλλον CI.  
- **Πλούσιο μοντέλο αντικειμένων** – πρόσβαση σε εργασίες, πόρους, εκχωρήσεις, ημερολόγια και προσαρμοσμένα πεδία προγραμματιστικά.  
- **Πολλαπλές επιλογές εξαγωγής** – PDF, XML, HTML, PNG κ.λπ., με μία κλήση API.  
- **Υψηλή απόδοση** – βελτιστοποιημένο για μεγάλα εταιρικά έργα.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. Ένα λειτουργικό περιβάλλον ανάπτυξης Java (JDK 8 ή νεότερο).  
2. Βιβλιοθήκη Aspose.Tasks for Java προστιθέμενη στο classpath του έργου σας.  
3. Διαπιστευτήρια πρόσβασης στη βάση δεδομένων SQL του Project Server (όνομα διακομιστή, θύρα, όνομα βάσης, όνομα χρήστη, κωδικός) **για σύνδεση με τον Project Server**.  
4. Τον Microsoft JDBC Driver για SQL Server (π.χ., `sqljdbc4.jar`).  

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Η λίστα περιλαμβάνει κεντρικές κλάσεις του Aspose.Tasks και τυπικές βοηθητικές κλάσεις Java.

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

## Πώς να συνδεθείτε στον Project Server
Η δημιουργία μιας αξιόπιστης σύνδεσης αποτελεί τη βάση για την ανάγνωση των δεδομένων του έργου. Βεβαιωθείτε ότι η παρουσία SQL Server είναι προσβάσιμη από το Java host σας και ότι ο λογαριασμός που χρησιμοποιείτε έχει δικαιώματα **SELECT** στο σχήμα του Project Server.

## Βήμα 1: Ρύθμιση Σύνδεσης Βάσης Δεδομένων
Δημιουργήστε μια παρουσία `MspDbSettings` που περιέχει τη συμβολοσειρά σύνδεσης JDBC. Αντικαταστήστε τις τιμές placeholder με τις πραγματικές λεπτομέρειες του διακομιστή σας.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Αποθηκεύστε τη συμβολοσειρά σύνδεσης σε ασφαλή αρχείο ρυθμίσεων ή μεταβλητή περιβάλλοντος αντί να την κωδικοποιήσετε σκληρά στο κώδικα.

## Βήμα 2: Προσθήκη Οδηγού JDBC
Φορτώστε τον οδηγό Microsoft SQL Server JDBC κατά την εκτέλεση ώστε η JVM να μπορεί να επικοινωνήσει με τη βάση δεδομένων.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Βεβαιωθείτε ότι η έκδοση του οδηγού ταιριάζει με την έκδοση του SQL Server σας. Η χρήση ασύμβατου οδηγού μπορεί να προκαλέσει αποτυχίες σύνδεσης.

## Βήμα 3: Ανάγνωση Δεδομένων Έργου
Δημιουργήστε ένα αντικείμενο `Project` περνώντας το `MspDbSettings`. Το Aspose.Tasks θα ανακτήσει αυτόματα τα δεδομένα του έργου από τη βάση.

```java
Project project = new Project(settings);
```

Σε αυτό το σημείο μπορείτε να εξερευνήσετε το αντικείμενο `project`—να απαριθμήσετε εργασίες, πόρους ή να τροποποιήσετε πεδία όπως χρειάζεται.

## Βήμα 4: Αποθήκευση έργου ως PDF
Εξάγετε το φορτωμένο έργο σε μορφή της επιλογής σας. Το παρακάτω παράδειγμα αποθηκεύει το έργο ως **PDF**, ιδανικό για εκτυπώσιμες αναφορές. Μπορείτε επίσης να **εξάγετε το έργο σε XML** ή **να μετατρέψετε το έργο σε HTML** αλλάζοντας το enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Αν προτιμάτε XML, απλώς αντικαταστήστε το `SaveFileFormat.Pdf` με `SaveFileFormat.Xml`. Για έξοδο HTML, χρησιμοποιήστε `SaveFileFormat.Html`.

## Συνηθισμένα Προβλήματα & Λύσεις
| Πρόβλημα | Τυπική Αιτία | Διόρθωση |
|----------|--------------|----------|
| **Timeout σύνδεσης** | Λάθος διακομιστής/θύρα ή τείχος προστασίας που μπλοκάρει | Επαληθεύστε τη διεύθυνση του διακομιστή, ανοίξτε τη θύρα 1433 και δοκιμάστε τη συνδεσιμότητα με ένα απλό πρόγραμμα JDBC. |
| **Σφάλμα πιστοποίησης** | Μη έγκυρο όνομα χρήστη/κωδικός ή ο SQL Server δεν είναι ρυθμισμένος για πιστοποίηση SQL | Χρησιμοποιήστε έγκυρο λογαριασμό SQL ή ενεργοποιήστε την ανάμειξη (mixed‑mode) πιστοποίησης στον διακομιστή. |
| **Οδηγός δεν βρέθηκε** | Το αρχείο JDBC jar δεν βρίσκεται στο classpath | Βεβαιωθείτε ότι το `addJDBCDriver` δείχνει στο σωστό αρχείο `.jar` και ότι η διαδρομή χρησιμοποιεί διπλά backslashes (`\\`). |
| **Κενό έργο μετά τη φόρτωση** | Ανεπαρκή δικαιώματα για ανάγνωση πινάκων του Project Server | Χορηγήστε στο λογαριασμό δικαιώματα SELECT στο σχήμα της βάσης δεδομένων Project Server. |

## Συχνές Ερωτήσεις

**Q:** Μπορεί το Aspose.Tasks να χρησιμοποιηθεί για ανάγνωση δεδομένων έργου από άλλες βάσεις δεδομένων εκτός του Microsoft Project;  
**A:** Ναι, το Aspose.Tasks υποστηρίζει ανάγνωση δεδομένων έργου από διάφορες πηγές, συμπεριλαμβανομένων αρχείων XML, Primavera και βάσεων δεδομένων Microsoft Project.

**Q:** Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις του Microsoft Project;  
**A:** Ναι, το Aspose.Tasks έχει σχεδιαστεί ώστε να λειτουργεί με πολλαπλές εκδόσεις του Microsoft Project, εξασφαλίζοντας απρόσκοπτη ενσωμάτωση.

**Q:** Μπορώ να τροποποιήσω τα δεδομένα του έργου πριν το αποθηκεύσω;  
**A:** Απόλυτα, το Aspose.Tasks παρέχει πλούσιο API για προσθήκη εργασιών, ενημέρωση πόρων και ορισμό ιδιοτήτων του έργου πριν από την εξαγωγή.

**Q:** Υποστηρίζει το Aspose.Tasks πολλαπλές μορφές εξόδου;  
**A:** Ναι, μπορείτε να αποθηκεύσετε έργα ως PDF, XML, HTML, CSV, PNG, JPEG και άλλα.

**Q:** Πού μπορώ να βρω περαιτέρω υποστήριξη ή βοήθεια με το Aspose.Tasks;  
**A:** Για επιπλέον βοήθεια, επισκεφθείτε το φόρουμ Aspose.Tasks ή εξερευνήστε την τεκμηρίωση που είναι διαθέσιμη στην ιστοσελίδα [εδώ](https://forum.aspose.com/c/tasks/15).

## Συμπέρασμα
Ακολουθώντας αυτόν τον βήμα‑βήμα οδηγό, τώρα γνωρίζετε πώς να **διαβάσετε τη βάση δεδομένων Microsoft Project**, **αποθηκεύσετε το έργο ως PDF** και να εξάγετε σε άλλες μορφές χρησιμοποιώντας το Aspose.Tasks for Java. Αυτή η προσέγγιση εξαλείφει την εξάρτηση από το Microsoft Project, απλοποιεί την αυτοματοποιημένη αναφορά και ανοίγει το δρόμο για ισχυρές προσαρμοσμένες ενσωματώσεις.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}