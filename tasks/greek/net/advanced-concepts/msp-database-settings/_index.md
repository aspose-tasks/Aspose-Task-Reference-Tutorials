---
date: 2026-03-14
description: Μάθετε πώς να καθορίζετε το σχήμα βάσης δεδομένων για μια βάση δεδομένων
  Microsoft Project χρησιμοποιώντας το Aspose.Tasks και πώς να εισάγετε δεδομένα έργου
  σε εφαρμογές .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Καθορίστε το σχήμα της βάσης δεδομένων για το Project DB με το Aspose.Tasks
url: /el/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ρυθμίσεις για τη Βάση Δεδομένων Microsoft Project στο Aspose.Tasks

## Εισαγωγή

Αν εργάζεστε με βάσεις δεδομένων Microsoft Project στις .NET εφαρμογές σας χρησιμοποιώντας Aspose.Tasks, θα χρειαστεί να **καθορίσετε το σχήμα της βάσης δεδομένων** και να διαμορφώσετε τις απαραίτητες ρυθμίσεις για να **εισάγετε δεδομένα project** απρόσκοπτα. Αυτό το tutorial θα σας καθοδηγήσει βήμα‑βήμα, δείχνοντάς σας **πώς να διαμορφώσετε τις λεπτομέρειες σύνδεσης**, **να δημιουργήσετε .NET connection string**, και τελικά **να αποθηκεύσετε το project ως MPP**.

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος στόχος;** Να καθορίσετε το σχήμα της βάσης δεδομένων και να εισάγετε μια βάση δεδομένων Project σε μια .NET εφαρμογή.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Tasks for .NET.  
- **Πώς συνδέομαι με το Project Server;** Δημιουργώντας ένα σωστό SQL connection string και χρησιμοποιώντας το `MspDbSettings`.  
- **Τι μορφή αρχείου παράγεται;** Ένα αρχείο MPP που αποθηκεύεται με `SaveFileFormat.Mpp`.  
- **Μπορώ να αλλάξω το όνομα του σχήματος;** Ναι, ορίστε την ιδιότητα `Schema` στο `MspDbSettings`.

## Πώς να καθορίσετε το σχήμα της βάσης δεδομένων για το Project DB

Η κατανόηση του γιατί μπορεί να χρειαστεί να **καθορίσετε το σχήμα της βάσης δεδομένων** είναι ουσιώδης. Σε πολλά εταιρικά περιβάλλοντα η βάση δεδομένων Project Server βρίσκεται κάτω από προσαρμοσμένο σχήμα (π.χ., `dbo`, `psdata`). Ορίζοντας ρητά το σχήμα, διασφαλίζετε ότι το Aspose.Tasks ερωτά τους σωστούς πίνακες, αποτρέποντας σφάλματα χρόνου εκτέλεσης και εγγυώμενοι ακριβή εισαγωγή δεδομένων.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι διαθέτετε τα εξής:

1. Aspose.Tasks for .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks από [here](https://releases.aspose.com/tasks/net/).  
2. Πρόσβαση σε μια Microsoft Project Database: Πρέπει να έχετε πρόσβαση σε μια βάση δεδομένων Microsoft Project για να εισάγετε δεδομένα από αυτήν.  

## Εισαγωγή Namespaces

Πρώτα, βεβαιωθείτε ότι εισάγετε τα απαραίτητα namespaces στο έργο σας:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Βήμα 1: Δημιουργία Connection String

Δημιουργήστε το connection string για τη Microsoft Project database σας. Εδώ **δημιουργείτε .NET connection string** και επίσης ορίζετε πώς να **συνδεθείτε με το Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Pro tip:** Ελέγξτε ξανά τις τιμές `DataSource` και `InitialCatalog`; πρέπει να ταιριάζουν με τη διεύθυνση του διακομιστή σας και το όνομα της δημοσιευμένης βάσης δεδομένων.

## Βήμα 2: Διαμόρφωση MspDbSettings

Δημιουργήστε ένα αντικείμενο `MspDbSettings`, περάστε το connection string και **καθορίστε το σχήμα της βάσης δεδομένων** ορίζοντας την ιδιότητα `Schema`. Αυτό ενημερώνει το Aspose.Tasks ποιο σχήμα να ερωτήσει.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Εδώ παρέχουμε επίσης το GUID του project που αναγνωρίζει το συγκεκριμένο project που θέλετε να φορτώσετε.

## Βήμα 3: Φόρτωση Δεδομένων Project

Δημιουργήστε ένα αντικείμενο `Project` χρησιμοποιώντας τις διαμορφωμένες ρυθμίσεις. Αυτό το βήμα ουσιαστικά **πώς να εισάγετε δεδομένα project** από τη βάση δεδομένων σε ένα .NET αντικείμενο.

```csharp
var project = new Project(settings);
```

## Βήμα 4: Αποθήκευση Δεδομένων Project

Τέλος, αποθηκεύστε το φορτωμένο project σε αρχείο MPP στον δίσκο. Αυτό δείχνει **πώς να αποθηκεύσετε το project ως MPP** χρησιμοποιώντας το API του Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Μετά την εκτέλεση του κώδικα, θα βρείτε το αρχείο `ImportProjectDataFromDatabase_out.mpp` στον φάκελο εξόδου, έτοιμο να ανοιχθεί στο Microsoft Project.

## Συμπέρασμα

Σε αυτό το tutorial, μάθατε πώς να **καθορίσετε το σχήμα της βάσης δεδομένων** για μια Microsoft Project database, **διαμορφώσετε τη σύνδεση**, **εισάγετε δεδομένα project**, και **αποθηκεύσετε το project ως MPP** χρησιμοποιώντας Aspose.Tasks for .NET. Αυτά τα βήματα επιτρέπουν αδιάσπαστη ενσωμάτωση των δεδομένων Project Server στις προσαρμοσμένες εφαρμογές σας, βοηθώντας σας να δημιουργήσετε ισχυρές λύσεις διαχείρισης έργων.

## Συχνές Ερωτήσεις

### Q1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με διαφορετικές εκδόσεις βάσεων δεδομένων Microsoft Project;
A1: Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις βάσεων δεδομένων Microsoft Project, προσφέροντας ευελιξία στην ενσωμάτωση.

### Q2: Πώς μπορώ να αντιμετωπίσω προβλήματα σύνδεσης με τη βάση δεδομένων;
A2: Βεβαιωθείτε ότι το connection string είναι σωστά διαμορφωμένο με τα κατάλληλα διαπιστευτήρια και λεπτομέρειες της βάσης δεδομένων. Μπορείτε επίσης να ανατρέξετε στην τεκμηρίωση ή να ζητήσετε υποστήριξη από το [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q3: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;
A3: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμαστική έκδοση από [here](https://releases.aspose.com/).

### Q4: Μπορώ να προσαρμόσω το σχήμα για την αλληλεπίδραση με τη βάση δεδομένων;
A4: Ναι, μπορείτε να καθορίσετε το σχήμα για το αντικείμενο `MspDbSettings` σύμφωνα με τη δομή της βάσης δεδομένων σας.

### Q5: Πού μπορώ να βρω πιο λεπτομερή τεκμηρίωση για τη χρήση του Aspose.Tasks;
A5: Μπορείτε να εξερευνήσετε την ολοκληρωμένη τεκμηρίωση [here](https://reference.aspose.com/tasks/net/) για λεπτομερείς πληροφορίες σχετικά με τις λειτουργίες του Aspose.Tasks.

**Ε: Λειτουργεί αυτή η προσέγγιση με βάσεις δεδομένων Azure SQL;**  
Α: Απόλυτα. Απλώς προσαρμόστε το `DataSource` στο όνομα του Azure διακομιστή σας και βεβαιωθείτε ότι οι ρυθμίσεις TLS/SSL είναι ενεργοποιημένες.

**Ε: Πώς διαχειρίζομαι μεγάλες βάσεις δεδομένων Project χωρίς να λήγει η σύνδεση;**  
Α: Αυξήστε την τιμή `ConnectTimeout` στο connection string και εξετάστε το ενδεχόμενο φόρτωσης των projects σε παρτίδες εάν χρειάζεται.

---

**Τελευταία ενημέρωση:** 2026-03-14  
**Δοκιμάστηκε με:** Aspose.Tasks 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}