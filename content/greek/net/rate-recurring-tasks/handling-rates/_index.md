---
title: Χειρισμός ποσοστών έργων MS με το Aspose.Tasks για .NET
linktitle: Χειρισμός τιμών στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Πλοίαρχος διαχείρισης των ποσοστών έργων MS με ευκολία χρησιμοποιώντας το Aspose.Tasks για .NET. Αυτοματοποιήστε τις εργασίες αποτελεσματικά για ομαλότερη ροή εργασιών έργου.
type: docs
weight: 10
url: /el/net/rate-recurring-tasks/handling-rates/
---
## Εισαγωγή
Καλώς ήρθατε στο σεμινάριο μας σχετικά με τον χειρισμό των ποσοστών έργων MS χρησιμοποιώντας το Aspose.Tasks για .NET! Σε αυτόν τον οδηγό, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα, διασφαλίζοντας ότι μπορείτε να διαχειριστείτε αποτελεσματικά τις τιμές στα έγγραφα του MS Project. Το Aspose.Tasks για .NET παρέχει ισχυρές δυνατότητες για τον χειρισμό αρχείων MS Project μέσω προγραμματισμού, επιτρέποντάς σας να βελτιστοποιήσετε τις εργασίες διαχείρισης του έργου σας χωρίς κόπο.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Εγκατεστημένο Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Tasks για .NET. Μπορείτε να βρείτε τον σύνδεσμο λήψης[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική κατανόηση της C#: Εξοικειωθείτε με τις βασικές αρχές της γλώσσας προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας C#. Αυτοί οι χώροι ονομάτων θα παρέχουν πρόσβαση στις κλάσεις και τις μεθόδους που απαιτούνται για το χειρισμό των ποσοστών έργων MS.
## Βήμα 1: Εισαγωγή χώρου ονομάτων Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Τώρα, ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα και ας κατανοήσουμε διεξοδικά κάθε βήμα.
## Βήμα 1: Φόρτωση αρχείου έργου
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Σε αυτό το βήμα, φορτώνουμε ένα υπάρχον αρχείο MS Project με το όνομα "Project1.mpp" χρησιμοποιώντας το`Project` τάξη που παρέχεται από το Aspose.Tasks.
## Βήμα 2: Προσθήκη πόρων και ορισμός εργασίας
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Εδώ, προσθέτουμε έναν νέο πόρο με το όνομα "Resource 1" στο έργο και ορίζουμε τον τύπο του ως "Work". Ορίζουμε επίσης τη διάρκεια εργασίας για αυτόν τον πόρο.
## Βήμα 3: Ορίστε την τυπική τιμή
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Σε αυτό το βήμα, ορίσαμε την τυπική τιμή για τον πόρο σε 20 $ ανά ώρα.
## Βήμα 4: Καθορίστε τις περιόδους τιμών
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Εδώ, ορίζουμε τις περιόδους τιμών για τον πόρο. Το Rate1 ορίζεται από την 1η Ιανουαρίου 2019 έως τις 11 Νοεμβρίου 2019, με καθορισμένες τιμές τυπικών και υπερωριών.
## Βήμα 5: Προσθήκη άλλης περιόδου τιμής
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Σε αυτό το τελευταίο βήμα, προσθέτουμε μια άλλη περίοδο τιμών από τις 12 Νοεμβρίου 2019 έως τις 31 Δεκεμβρίου 2019, με διαφορετική τυπική τιμή και κόστος ανά χρήση που ορίζεται.
Συγχαρητήρια! Έχετε χειριστεί με επιτυχία τα ποσοστά έργου MS χρησιμοποιώντας το Aspose.Tasks για .NET.
## συμπέρασμα
Η διαχείριση των ποσοστών έργων MS μέσω προγραμματισμού μπορεί να βελτιώσει σημαντικά τη ροή εργασιών διαχείρισης του έργου σας. Με το Aspose.Tasks για .NET, έχετε τη δύναμη να αυτοματοποιήσετε αποτελεσματικά τις εργασίες διαχείρισης ρυθμών, εξοικονομώντας χρόνο και πόρους.
## Συχνές ερωτήσεις
### Ε: Μπορεί το Aspose.Tasks να χειριστεί πολύπλοκες δομές έργου;
Α: Ναι, το Aspose.Tasks παρέχει ισχυρές δυνατότητες για να χειριστείτε πολύπλοκες δομές έργου με ευκολία.
### Ε: Είναι το Aspose.Tasks συμβατό με όλες τις εκδόσεις των αρχείων MS Project;
Α: Το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων MS Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικές πλατφόρμες.
### Ε: Μπορώ να τροποποιήσω τις υπάρχουσες τιμές σε ένα αρχείο MS Project χρησιμοποιώντας το Aspose.Tasks;
Α: Απολύτως! Το Aspose.Tasks σάς επιτρέπει να τροποποιείτε τις υπάρχουσες τιμές, να προσθέτετε νέες τιμές και να τις διαχειρίζεστε δυναμικά.
### Ε: Το Aspose.Tasks προσφέρει υποστήριξη για υπολογισμούς προσαρμοσμένων τιμών;
Α: Ναι, μπορείτε να εφαρμόσετε υπολογισμούς προσαρμοσμένου ποσοστού χρησιμοποιώντας το Aspose.Tasks για να ικανοποιήσετε συγκεκριμένες απαιτήσεις έργου.
### Ε: Υπάρχει διαθέσιμο φόρουμ κοινότητας ή υποστήριξη για τους χρήστες του Aspose.Tasks;
 Α: Ναι, μπορείτε να επισκεφθείτε το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15)για να αναζητήσετε βοήθεια και να αλληλεπιδράσετε με άλλους χρήστες.