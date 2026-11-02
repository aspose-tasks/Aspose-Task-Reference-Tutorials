---
date: 2026-10-31
description: Μάθετε πώς να αποθηκεύετε έργο ως PDF και να διαβάζετε τη βάση δεδομένων
  Microsoft Project με το Aspose.Tasks for Java, καθώς και πώς να συνδέεστε με το
  Project Server, να μετατρέπετε το έργο σε HTML και να εξάγετε το έργο σε XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Ανάγνωση δεδομένων έργου από τη βάση δεδομένων Microsoft Project στο Aspose.Tasks
og_description: Αποθήκευση έργου ως PDF και ανάγνωση βάσης δεδομένων Microsoft Project
  χρησιμοποιώντας το Aspose.Tasks for Java. Μάθετε πώς να συνδέεστε με το Project
  Server, να εξάγετε σε HTML, XML και CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Αποθήκευση έργου ως PDF και ανάγνωση βάσης δεδομένων Microsoft Project με
  το Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Αποθήκευση έργου ως PDF και ανάγνωση βάσης δεδομένων Microsoft Project με το
  Aspose.Tasks for Java
url: /el/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση έργου ως PDF και ανάγνωση βάσης δεδομένων Microsoft Project με Aspose.Tasks για Java

## Εισαγωγή
Σε αυτό το σεμινάριο θα ανακαλύψετε πώς να **read Microsoft Project database** απευθείας από έναν Microsoft Project Server και στη συνέχεια να **save the project as PDF** χρησιμοποιώντας το Aspose.Tasks Java API. Είτε χρειάζεστε τη δημιουργία εκτυπώσιμων αναφορών, τη μετεγκατάσταση παλαιών δεδομένων, είτε την ενσωμάτωση πληροφοριών έργου σε μια προσαρμοσμένη πύλη, αυτός ο οδηγός σας καθοδηγεί βήμα προς βήμα—από τη ρύθμιση της σύνδεσης JDBC μέχρι την εξαγωγή του έργου σε PDF, XML ή HTML. Στο τέλος, θα έχετε μια λύση έτοιμη για παραγωγή που εκτελείται σε οποιονδήποτε διακομιστή Java χωρίς εγκατάσταση του Microsoft Project.

## Γρήγορες απαντήσεις
- **Τι κάνει το Aspose.Tasks;** Παρέχει ένα καθαρό‑Java API για ανάγνωση, εγγραφή και διαχείριση αρχείων και βάσεων δεδομένων Microsoft Project.  
- **Χρειάζεται να είναι εγκατεστημένο το Microsoft Project;** Όχι, το Aspose.Tasks λειτουργεί ανεξάρτητα από το Microsoft Project.  
- **Ποιος τύπος βάσης δεδομένων υποστηρίζεται;** Microsoft SQL Server, το backend του Project Server.  
- **Μπορώ να εξάγω σε άλλες μορφές;** Ναι—PDF, XML, HTML, CSV, PNG, JPEG, και άλλα.  
- **Ποια είναι τα κύρια προαπαιτούμενα;** JDK 8 ή νεότερο, η βιβλιοθήκη Aspose.Tasks for Java, ο οδηγός JDBC για SQL Server, και έγκυρα διαπιστευτήρια Project Server.

## Τι σημαίνει “read Microsoft Project database”;
Η ανάγνωση μιας βάσης δεδομένων Microsoft Project σημαίνει σύνδεση στο αποθετήριο SQL Server του Project Server, εξαγωγή των αποθηκευμένων δεδομένων έργου και φόρτωση τους σε ένα αντικείμενο `Project` που μπορεί να διαχειριστεί το Aspose.Tasks. Αυτή η προσέγγιση είναι ιδανική για αυτοματοποιημένες αναφορές, μετεγκατάσταση δεδομένων ή προσαρμοσμένη ανάλυση.

## Γιατί να χρησιμοποιήσετε το Aspose.Tasks για Java;
Το Aspose.Tasks for Java σας επιτρέπει να εργάζεστε με δεδομένα Microsoft Project χωρίς την ανάγκη της επιτραπέζιας εφαρμογής, προσφέροντας μια καθαρή‑Java λύση που εκτελείται σε οποιαδήποτε πλατφόρμα. Παρέχει ένα ολοκληρωμένο μοντέλο αντικειμένων για εργασίες, πόρους, ημερολόγια και προσαρμοσμένα πεδία, και μπορεί να διαχειριστεί μεγάλα επιχειρησιακά έργα αποδοτικά, καθιστώντας το ιδανικό για αυτοματοποιημένες αναφορές, μετεγκατάσταση και σενάρια ενσωμάτωσης.

- **Χωρίς εξάρτηση από το Microsoft Project** – εκτελείται σε οποιονδήποτε διακομιστή ή περιβάλλον CI.  
- **Πλούσιο μοντέλο αντικειμένων** – πρόσβαση σε εργασίες, πόρους, αναθέσεις, ημερολόγια και προσαρμοσμένα πεδία προγραμματιστικά.  
- **Πολλαπλές επιλογές εξαγωγής** – το Aspose.Tasks υποστηρίζει εξαγωγή σε **πάνω από 20 μορφές αρχείων**, συμπεριλαμβανομένων PDF, XML, HTML, CSV, PNG και JPEG, με μία κλήση API.  
- **Υψηλή απόδοση** – η βιβλιοθήκη μπορεί να επεξεργαστεί έργα που περιέχουν **έως 10.000 εργασίες** σε λιγότερο από ένα λεπτό, και μεταδίδει δεδομένα για να αποφεύγει τη φόρτωση ολόκληρου του αρχείου στη μνήμη.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. Ένα λειτουργικό περιβάλλον ανάπτυξης Java (JDK 8 ή νεότερο).  
2. Τη βιβλιοθήκη Aspose.Tasks for Java προστεθειμένη στο classpath του έργου σας.  
3. Διαπιστευτήρια πρόσβασης για τη βάση δεδομένων SQL του Project Server (όνομα διακομιστή, θύρα, όνομα βάσης, όνομα χρήστη, κωδικός) για σύνδεση με το Project Server.  
4. Τον Microsoft JDBC Driver για SQL Server (π.χ., `sqljdbc4.jar`).  

## Εισαγωγή πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Η λίστα περιλαμβάνει τις βασικές κλάσεις του Aspose.Tasks και τις τυπικές βοηθητικές κλάσεις Java.

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

## Πώς να συνδεθείτε στο Project Server
Η δημιουργία μιας αξιόπιστης σύνδεσης είναι το θεμέλιο για την ανάγνωση δεδομένων έργου. Βεβαιωθείτε ότι η παρουσία SQL Server είναι προσβάσιμη από το Java host σας και ότι ο λογαριασμός που χρησιμοποιείτε έχει δικαιώματα **SELECT** στο σχήμα του Project Server. Πρέπει επίσης να ελέγξετε την καθυστέρηση δικτύου και να διαμορφώσετε τυχόν απαιτούμενες ρυθμίσεις SSL για να εξασφαλίσετε ασφαλή επικοινωνία.

## Βήμα 1: ρύθμιση σύνδεσης βάσης δεδομένων
Η κλάση `MspDbSettings` περιλαμβάνει τις λεπτομέρειες σύνδεσης JDBC που απαιτούνται για πρόσβαση σε μια βάση δεδομένων Microsoft Project Server. Δημιουργήστε μια παρουσία `MspDbSettings` που περιέχει τη συμβολοσειρά σύνδεσης JDBC. Αντικαταστήστε τις τιμές placeholder με τις πραγματικές λεπτομέρειες του διακομιστή σας.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Αποθηκεύστε τη συμβολοσειρά σύνδεσης σε ένα ασφαλές αρχείο ρυθμίσεων ή μεταβλητή περιβάλλοντος αντί να κωδικοποιείτε σκληρά τα διαπιστευτήρια.

## Βήμα 2: προσθήκη οδηγού JDBC
Φορτώστε τον οδηγό Microsoft SQL Server JDBC κατά την εκτέλεση ώστε η JVM να μπορεί να επικοινωνεί με τη βάση δεδομένων.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Βεβαιωθείτε ότι η έκδοση του οδηγού ταιριάζει με την έκδοση του SQL Server σας. Η χρήση μη συμβατής έκδοσης οδηγού μπορεί να προκαλέσει αποτυχίες σύνδεσης.

## Βήμα 3: ανάγνωση δεδομένων έργου
Η κλάση `Project` αντιπροσωπεύει ένα αρχείο Microsoft Project που έχει φορτωθεί στη μνήμη, εκθέτοντας εργασίες, πόρους και αναθέσεις. Δημιουργήστε ένα αντικείμενο `Project` περνώντας το `MspDbSettings`. Το Aspose.Tasks θα ανακτήσει αυτόματα τα δεδομένα του έργου από τη βάση δεδομένων.

```java
Project project = new Project(settings);
```

Σε αυτό το σημείο μπορείτε να εξερευνήσετε το αντικείμενο `project`—να παραθέσετε εργασίες, πόρους ή να τροποποιήσετε πεδία όπως απαιτείται.

## Βήμα 4: αποθήκευση έργου ως PDF
Η απαρίθμηση `SaveFileFormat` ορίζει τη μορφή εξόδου για τη μέθοδο `Project.save`, όπως PDF, XML ή HTML. Εξάγετε το φορτωμένο έργο σε μορφή αρχείου της επιλογής σας. Το παρακάτω παράδειγμα αποθηκεύει το έργο ως **PDF**, που είναι ιδανικό για εκτυπώσιμες αναφορές. Μπορείτε επίσης να **εξάγετε το έργο σε XML** ή να **μετατρέψετε το έργο σε HTML** αλλάζοντας την απαρίθμηση `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Αν προτιμάτε XML, απλώς αντικαταστήστε το `SaveFileFormat.Pdf` με `SaveFileFormat.Xml`. Για έξοδο HTML, χρησιμοποιήστε το `SaveFileFormat.Html`.

## Συχνά προβλήματα & λύσεις
| Πρόβλημα | Τυπική αιτία | Διόρθωση |
|----------|--------------|----------|
| **Χρονικό όριο σύνδεσης** | Λάθος διακομιστής/θύρα ή αποκλεισμός από τείχος προστασίας | Επαληθεύστε τη διεύθυνση του διακομιστή, ανοίξτε τη θύρα 1433 και δοκιμάστε τη συνδεσιμότητα με ένα απλό πρόγραμμα δοκιμής JDBC. |
| **Σφάλμα πιστοποίησης** | Μη έγκυρο όνομα χρήστη/κωδικός ή ο SQL Server δεν είναι ρυθμισμένος για πιστοποίηση SQL | Χρησιμοποιήστε έγκυρο λογαριασμό SQL ή ενεργοποιήστε την ανάμειξη λειτουργίας πιστοποίησης (mixed‑mode) στον διακομιστή. |
| **Οδηγός δεν βρέθηκε** | Το αρχείο JDBC jar δεν βρίσκεται στο classpath | Βεβαιωθείτε ότι το `addJDBCDriver` δείχνει στο σωστό αρχείο `.jar` και ότι η διαδρομή χρησιμοποιεί διπλές ανάστροφες καθέτους (`\\`). |
| **Κενό έργο μετά τη φόρτωση** | Ανεπαρκή δικαιώματα για ανάγνωση πινάκων του Project Server | Παραχωρήστε στο λογαριασμό δικαιώματα SELECT στο σχήμα της βάσης δεδομένων του Project Server. |

## Συχνές ερωτήσεις

**Q: Μπορεί το Aspose.Tasks να χρησιμοποιηθεί για ανάγνωση δεδομένων έργου από άλλες βάσεις δεδομένων εκτός του Microsoft Project;**  
A: Ναι, το Aspose.Tasks υποστηρίζει την ανάγνωση δεδομένων έργου από αρχεία XML, βάσεις δεδομένων Primavera και άλλες τυπικές μορφές έργου.

**Q: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις του Microsoft Project;**  
A: Ναι, η βιβλιοθήκη λειτουργεί με το Microsoft Project 2007 έως τις πιο πρόσφατες εκδόσεις του 2024, εξασφαλίζοντας απρόσκοπτη ενσωμάτωση μεταξύ εκδόσεων.

**Q: Μπορώ να τροποποιήσω τα δεδομένα του έργου πριν το αποθηκεύσω;**  
A: Απόλυτα, μπορείτε να προσθέσετε, ενημερώσετε ή διαγράψετε εργασίες, πόρους και προσαρμοσμένα πεδία χρησιμοποιώντας το πλούσιο API πριν από την εξαγωγή.

**Q: Το Aspose.Tasks υποστηρίζει πολλαπλές μορφές εξόδου;**  
A: Ναι, μπορείτε να αποθηκεύσετε έργα ως PDF, XML, HTML, CSV, PNG, JPEG και άλλα—πάνω από 20 μορφές συνολικά.

**Q: Πού μπορώ να βρω περαιτέρω υποστήριξη ή βοήθεια για το Aspose.Tasks;**  
A: Για πρόσθετη βοήθεια, επισκεφθείτε το φόρουμ Aspose.Tasks ή εξερευνήστε την τεκμηρίωση που είναι διαθέσιμη στην ιστοσελίδα [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό βήμα‑βήμα, τώρα γνωρίζετε πώς να **read Microsoft Project database**, **save the project as PDF**, και να εξάγετε σε άλλες μορφές χρησιμοποιώντας το Aspose.Tasks for Java. Αυτή η προσέγγιση εξαλείφει την εξάρτηση από το Microsoft Project, απλοποιεί τις αυτοματοποιημένες αναφορές και ανοίγει το δρόμο για ισχυρές προσαρμοσμένες ενσωματώσεις.

---

**Τελευταία ενημέρωση:** 2026-10-31  
**Δοκιμή με:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Πώς να αποθηκεύσετε το έργο ως PDF με Aspose.Tasks – Οδηγός εξαγωγής](/tasks/java/project-file-operations/save-as-pdf/)
- [Αποθήκευση έργου ως PDF – Απόδοση φύλλου εργασιών με Aspose.Tasks for Java](/tasks/java/task-properties/render-task-sheet/)
- [Εξαγωγή έργου σε PDF και μείωση του κενά μεταξύ λίστας εργασιών και υποσέλιδου στο Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}