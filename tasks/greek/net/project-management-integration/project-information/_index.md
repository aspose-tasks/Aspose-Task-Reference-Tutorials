---
title: Εξαγωγή πληροφοριών έργου MS στο Aspose.Tasks
linktitle: Εξαγωγή πληροφοριών έργου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να εξάγετε πληροφορίες MS Project χωρίς κόπο χρησιμοποιώντας το Aspose.Tasks για .NET. Βουτήξτε στο περιεκτικό μας σεμινάριο.
weight: 20
url: /el/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εξαγωγή πληροφοριών έργου MS στο Aspose.Tasks

## Εισαγωγή
Ψάχνετε να εξαγάγετε αποτελεσματικά πληροφορίες από αρχεία Microsoft Project χρησιμοποιώντας το Aspose.Tasks για .NET; Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα. Αλλά προτού βουτήξουμε στις λεπτομέρειες υλοποίησης, ας βεβαιωθούμε πρώτα ότι έχετε όλα όσα χρειάζεστε.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:
### 1. Aspose.Tasks για .NET
 Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Tasks για .NET. Εάν δεν το έχετε κάνει ήδη, μπορείτε να το κατεβάσετε από το[Aspose.Tasks για τον ιστότοπο .NET](https://releases.aspose.com/tasks/net/).
### 2. Διαπιστευτήρια για το SharePoint
Θα χρειαστείτε τα διαπιστευτήρια για να αποκτήσετε πρόσβαση στο SharePoint όπου είναι αποθηκευμένα τα αρχεία του MS Project. Βεβαιωθείτε ότι έχετε τις ακόλουθες πληροφορίες:
- Διεύθυνση τομέα SharePoint
- Ονομα χρήστη
- Κωδικός πρόσβασης
## Εισαγωγή χώρων ονομάτων
Αφού τακτοποιήσετε τις προϋποθέσεις, ήρθε η ώρα να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Τώρα ας αναλύσουμε τη διαδικασία εξαγωγής πληροφοριών MS Project σε πολλαπλά βήματα.
## Βήμα 1: Παρέχετε διαπιστευτήρια
Πρώτα, πρέπει να δώσετε τα διαπιστευτήριά σας στο SharePoint για πρόσβαση στον διακομιστή έργου.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Βήμα 2: Αρχικοποίηση του Project Server Manager
 Στη συνέχεια, αρχικοποιήστε a`ProjectServerManager` παράδειγμα με τα παρεχόμενα διαπιστευτήρια.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Βήμα 3: Ανακτήστε τη λίστα έργων
Τώρα, μπορείτε να ανακτήσετε τη λίστα των έργων από τον διακομιστή έργου.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Βήμα 4: Εκτύπωση πληροφοριών έργου
Τέλος, επαναλάβετε τη λίστα των έργων και εκτυπώστε τις πληροφορίες τους.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## συμπέρασμα
Συγχαρητήρια! Μάθατε με επιτυχία πώς να εξάγετε πληροφορίες MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Με αυτή τη γνώση, μπορείτε πλέον να ενσωματώσετε αυτή τη λειτουργία στις εφαρμογές σας .NET απρόσκοπτα.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με οποιαδήποτε έκδοση του Microsoft Project;
Α: Ναι, το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις του Microsoft Project, συμπεριλαμβανομένων των 2003, 2007, 2010, 2013, 2016 και 2019.
### Ε2: Είναι το Aspose.Tasks για .NET συμβατό με πλατφόρμες Windows και Linux;
Α: Ναι, το Aspose.Tasks για .NET είναι συμβατό με πλατφόρμες Windows και Linux, καθιστώντας το ευέλικτο για διαφορετικά περιβάλλοντα ανάπτυξης.
### Ε3: Μπορώ να εξαγάγω εξαρτήσεις εργασιών χρησιμοποιώντας το Aspose.Tasks για .NET;
Α: Απολύτως! Το Aspose.Tasks για .NET παρέχει ισχυρή λειτουργικότητα για την εξαγωγή όχι μόνο βασικών πληροφοριών έργου αλλά και εξαρτήσεων εργασιών και άλλων περίπλοκων λεπτομερειών.
### Ε4: Το Aspose.Tasks για .NET προσφέρει τεχνική υποστήριξη;
 Α: Ναι, μπορείτε να λάβετε τεχνική υποστήριξη για το Aspose.Tasks για .NET μέσω του[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15), όπου μπορείτε να κάνετε ερωτήσεις και να ζητήσετε βοήθεια από ειδικούς.
### Ε5: Μπορώ να δοκιμάσω το Aspose.Tasks για .NET πριν το αγοράσω;
 Α: Σίγουρα! Μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή του Aspose.Tasks για .NET από το[σελίδα εκδόσεων](https://releases.aspose.com/), επιτρέποντάς σας να εξερευνήσετε τις δυνατότητές του πριν πάρετε μια απόφαση αγοράς.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
