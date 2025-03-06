---
title: Μείωση του χάσματος μεταξύ της λίστας εργασιών και του υποσέλιδου στο Aspose.Tasks
linktitle: Μείωση του χάσματος μεταξύ της λίστας εργασιών και του υποσέλιδου στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να μειώσετε το χάσμα μεταξύ των λιστών εργασιών του MS Project και των υποσέλιδων χρησιμοποιώντας το Aspose.Tasks για Java. Βελτιστοποιήστε τη διάταξη του εγγράφου έργου χωρίς κόπο.
weight: 10
url: /el/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μείωση του χάσματος μεταξύ της λίστας εργασιών και του υποσέλιδου στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη μείωση του χάσματος μεταξύ της λίστας εργασιών και του υποσέλιδου στα αρχεία του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, θα μπορείτε να βελτιστοποιήσετε τη διάταξη των εγγράφων του έργου σας χωρίς κόπο.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Tasks for Java Library: Κάντε λήψη και συμπεριλάβετε τη βιβλιοθήκη Aspose.Tasks for Java στο έργο σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).

## Εισαγωγή πακέτων
Πριν βουτήξουμε στο τμήμα κωδικοποίησης, ας εισάγουμε τα απαραίτητα πακέτα:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Βήμα 1: Παρέχετε τη διαδρομή προς τον Κατάλογο δεδομένων σας
```java
String dataDir = "Your Data Directory";
```
 Φροντίστε να αντικαταστήσετε`"Your Data Directory"` με τη διαδρομή προς τον πραγματικό κατάλογο δεδομένων όπου βρίσκεται το αρχείο Microsoft Project (`HomeMovePlan.mpp` σε αυτό το παράδειγμα) βρίσκεται.
## Βήμα 2: Διαβάστε το Αρχείο MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Αυτή η γραμμή κώδικα διαβάζει το αρχείο Microsoft Project με το όνομα`HomeMovePlan.mpp`.
## Βήμα 3: Ορίστε τις Επιλογές ImageSave
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Διαμορφώστε τις επιλογές αποθήκευσης εικόνας, ρύθμιση`ReduceFooterGap` προς την`true` για να μειώσετε το κενό μεταξύ της λίστας εργασιών και του υποσέλιδου.
## Βήμα 4: Αποθήκευση ως εικόνα
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Αποθηκεύστε το έργο ως εικόνα με τις διαμορφωμένες επιλογές.
## Βήμα 5: Ορίστε τις επιλογές PdfSave
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Καθορίστε τις επιλογές αποθήκευσης PDF, διασφαλίζοντας τη ρύθμιση`ReduceFooterGap` προς την`true`.
## Βήμα 6: Αποθήκευση ως PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Αποθηκεύστε το έργο ως PDF με τις διαμορφωμένες επιλογές.
## Βήμα 7: Ορίστε τις επιλογές HtmlSave
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // οριστεί σε αληθινό
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Καθορίστε επιλογές αποθήκευσης HTML, ρύθμιση`ReduceFooterGap` προς την`true`.
## Βήμα 8: Αποθήκευση ως HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Αποθηκεύστε το έργο ως αρχείο HTML με τις διαμορφωμένες επιλογές.

## συμπέρασμα
Συμπερασματικά, η μείωση του χάσματος μεταξύ της λίστας εργασιών και του υποσέλιδου στα αρχεία Microsoft Project είναι μια απλή διαδικασία με το Aspose.Tasks για Java. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να βελτιστοποιήσετε αποτελεσματικά τη διάταξη των εγγράφων του έργου σας.

## Συχνές ερωτήσεις

### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις του Microsoft Project;

Α: Το Aspose.Tasks υποστηρίζει μορφές Microsoft Project 2003-2019, διασφαλίζοντας τη συμβατότητα σε διάφορες εκδόσεις.

### Ε: Μπορώ να προσαρμόσω την εμφάνιση του υποσέλιδου στα έγγραφα του έργου μου;

Α: Ναι, το Aspose.Tasks παρέχει εκτενείς επιλογές για την προσαρμογή της εμφάνισης των υποσέλιδων, συμπεριλαμβανομένης της μείωσης των κενών και της προσαρμογής της τοποθέτησης περιεχομένου.

### Ε: Το Aspose.Tasks υποστηρίζει την αποθήκευση έργων σε μορφές άλλες από PNG, PDF και HTML;

Α: Ναι, το Aspose.Tasks υποστηρίζει ένα ευρύ φάσμα μορφών, συμπεριλαμβανομένων των XLSX, XML και MPP, μεταξύ άλλων.

### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;

 Α: Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του Aspose.Tasks από[εδώ](https://releases.aspose.com/).

### Ε: Πού μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα κατά τη χρήση του Aspose.Tasks;

 Α: Μπορείτε να λάβετε βοήθεια από το φόρουμ κοινότητας Aspose.Tasks[εδώ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
