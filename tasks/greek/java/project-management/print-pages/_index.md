---
title: Εκτύπωση σελίδων για ξεχωριστή εικόνα στο Aspose.Tasks
linktitle: Εκτύπωση σελίδων για ξεχωριστή εικόνα στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να εκτυπώνετε σελίδες για να διαχωρίζετε εικόνες στο Aspose.Tasks για Java. Βελτιώστε την οπτικοποίηση του έργου με αυτόν τον οδηγό βήμα προς βήμα.
weight: 22
url: /el/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εκτύπωση σελίδων για ξεχωριστή εικόνα στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία εκτύπωσης σελίδων για διαχωρισμό εικόνων χρησιμοποιώντας το Aspose.Tasks για Java. Αυτή η λειτουργία μπορεί να είναι ιδιαίτερα χρήσιμη όταν χρειάζεται να οπτικοποιήσετε τις διατάξεις του έργου ή τις κρίσιμες εργασίες ξεχωριστά.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από[εδώ](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks for Java στο έργο σας. Μπορείτε να το πάρετε από[εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Φροντίστε να εισαγάγετε τα απαραίτητα πακέτα στην αρχή του αρχείου Java:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Βήμα 1: Φόρτωση δεδομένων έργου
Αρχικά, φορτώστε τα δεδομένα του έργου από το αρχείο MPP:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Βήμα 2: Ορίστε τις επιλογές αποθήκευσης εικόνας
Καθορίστε τις επιλογές για την αποθήκευση της εικόνας, συμπεριλαμβανομένων της ημερομηνίας έναρξης, της ημερομηνίας λήξης, των κρίσιμων εργασιών, του υπόμνημα και των γραμμών πλέγματος:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Βήμα 3: Προσαρμογή Γραμμών Πλέγματος
Προσαρμόστε τις γραμμές πλέγματος για την εικόνα, προσδιορίζοντας τον τύπο, το χρώμα και το μοτίβο:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Βήμα 4: Αποθήκευση εικόνων
Αποθηκεύστε τη διάταξη του έργου ως εικόνες, τόσο ως ένα μόνο αρχείο όσο και ως ξεχωριστά αρχεία:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, δείξαμε πώς να εκτυπώνετε σελίδες σε ξεχωριστές εικόνες χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας τα βήματα που περιγράφονται παραπάνω, μπορείτε να απεικονίσετε αποτελεσματικά τις διατάξεις του έργου και τις κρίσιμες εργασίες σύμφωνα με τις απαιτήσεις σας.
## Συχνές ερωτήσεις
### Ε: Μπορώ να προσαρμόσω τη μορφή εικόνας κατά την αποθήκευση των διατάξεων του έργου;
 Α: Ναι, το Aspose.Tasks για Java υποστηρίζει διάφορες μορφές εικόνας όπως PNG, JPEG, BMP κ.λπ. Μπορείτε να καθορίσετε την επιθυμητή μορφή στο`ImageSaveOptions` τάξη.
### Ε: Είναι το Aspose.Tasks για Java συμβατό με διαφορετικά περιβάλλοντα ανάπτυξης Java;
Α: Ναι, το Aspose.Tasks για Java είναι συμβατό με τα περισσότερα περιβάλλοντα ανάπτυξης Java, συμπεριλαμβανομένων των Eclipse, IntelliJ IDEA και NetBeans.
### Ε: Μπορώ να ενσωματώσω το Aspose.Tasks για Java στο έργο μου Maven ή Gradle;
Α: Ναι, μπορείτε εύκολα να ενσωματώσετε το Aspose.Tasks για Java στο έργο Maven ή Gradle προσθέτοντας την κατάλληλη εξάρτηση στο`pom.xml` ή`build.gradle` αρχείο.
### Ε: Το Aspose.Tasks για Java υποστηρίζει την εξαγωγή δεδομένων έργου σε άλλες μορφές εκτός από εικόνες;
Α: Ναι, το Aspose.Tasks για Java υποστηρίζει την εξαγωγή δεδομένων έργου σε διάφορες μορφές όπως PDF, HTML, XLSX κ.λπ., παρέχοντας ευελιξία στην οπτικοποίηση και την αναφορά δεδομένων.
### Ε: Υπάρχει διαθέσιμη υποστήριξη κοινότητας για το Aspose.Tasks για Java;
 Α: Ναι, μπορείτε να βρείτε υποστήριξη κοινότητας, να κάνετε ερωτήσεις και να αλληλεπιδράσετε με άλλους χρήστες στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
