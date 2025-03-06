---
title: Γράψτε ενημερωμένα δεδομένα πόρων στο Aspose.Tasks
linktitle: Γράψτε ενημερωμένα δεδομένα πόρων στο Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Μάθετε πώς να ενημερώνετε αβίαστα τα δεδομένα πόρων σε αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για Java.
weight: 21
url: /el/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Γράψτε ενημερωμένα δεδομένα πόρων στο Aspose.Tasks

## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στην ενημέρωση των δεδομένων πόρων του Microsoft Project χρησιμοποιώντας το Aspose.Tasks για Java. Το Aspose.Tasks είναι ένα ισχυρό Java API που σας επιτρέπει να χειρίζεστε αρχεία Microsoft Project χωρίς να απαιτείται η εγκατάσταση του Microsoft Project στο σύστημά σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Aspose.Tasks για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/java/).
3. Βασικές γνώσεις προγραμματισμού Java.

## Εισαγωγή πακέτων

Αρχικά, πρέπει να εισαγάγετε τα απαραίτητα πακέτα για να εργαστείτε με το Aspose.Tasks στον κώδικα Java σας. Προσθέστε τις ακόλουθες δηλώσεις εισαγωγής στο αρχείο Java σας:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Βήμα 1: Ρύθμιση του καταλόγου δεδομένων σας

Καθορίστε τον κατάλογο όπου βρίσκονται τα αρχεία δεδομένων σας:

```java
String dataDir = "Your Data Directory";
```

## Βήμα 2: Καθορίστε τα αρχεία εισόδου και εξόδου

Καθορίστε τις διαδρομές για το αρχείο εισόδου MS Project και το ενημερωμένο αρχείο που προκύπτει:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Δοκιμή αρχείου με ένα rsc για ενημέρωση
String resultFile = dataDir + "OutputMPP.mpp"; // Αρχείο για τη σύνταξη δοκιμαστικής εργασίας
```

## Βήμα 3: Φορτώστε το έργο

 Φορτώστε το αρχείο MS Project στο a`Project` αντικείμενο:

```java
Project project = new Project(file);
```

## Βήμα 4: Προσθέστε έναν πόρο και ορίστε χαρακτηριστικά

Προσθέστε έναν νέο πόρο στο έργο και ορίστε τα χαρακτηριστικά του, όπως τυπικό ποσοστό, ποσοστό υπερωριών και ομάδα:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Βήμα 5: Αποθηκεύστε το έργο

Αποθηκεύστε το ενημερωμένο έργο με τα τροποποιημένα δεδομένα πόρων:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, δείξαμε πώς να ενημερώσετε τα δεδομένα πόρων του MS Project χρησιμοποιώντας το Aspose.Tasks για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειριστείτε αποτελεσματικά τις πληροφορίες πόρων στα αρχεία του MS Project μέσω προγραμματισμού.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να ενημερώσω πολλούς πόρους στο ίδιο έργο χρησιμοποιώντας το Aspose.Tasks για Java;

A1: Ναι, μπορείτε να ενημερώσετε πολλούς πόρους επαναλαμβάνοντας μέσα από αυτούς και ορίζοντας ανάλογα τα χαρακτηριστικά τους.

### Ε2: Το Aspose.Tasks υποστηρίζει άλλες μορφές αρχείων εκτός από το MS Project;

A2: Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων, όπως XML, MPP και άλλα.

### Ε3: Είναι το Aspose.Tasks συμβατό με διαφορετικές εκδόσεις Java;

A3: Το Aspose.Tasks είναι συμβατό με τις εκδόσεις Java 6 και νεότερες.

### Ε4: Μπορώ να εκτελέσω άλλες λειτουργίες σε αρχεία MS Project με το Aspose.Tasks;

A4: Ναι, μπορείτε να εκτελέσετε ένα ευρύ φάσμα λειτουργιών, όπως ανάγνωση, γραφή και χειρισμός εργασιών, πόρων και ημερολογίων.

### Ε5: Πού μπορώ να βρω πρόσθετη βοήθεια ή υποστήριξη για το Aspose.Tasks;

 A5: Μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15) για οποιαδήποτε βοήθεια ή απορία.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
