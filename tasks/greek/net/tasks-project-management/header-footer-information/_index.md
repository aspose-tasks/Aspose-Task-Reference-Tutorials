---
title: Εξαγωγή πληροφοριών κεφαλίδας και υποσέλιδου με το Aspose.Tasks
linktitle: Πληροφορίες κεφαλίδας και υποσέλιδου στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε να εξάγετε πληροφορίες κεφαλίδας και υποσέλιδου από αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Εύκολη, αποτελεσματική και φιλική προς τους προγραμματιστές λύση.
type: docs
weight: 29
url: /el/net/tasks-project-management/header-footer-information/
---
## Εισαγωγή
Το Aspose.Tasks για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να χειρίζονται εύκολα τα αρχεία του Microsoft Project. Σε αυτό το σεμινάριο, θα μάθουμε πώς να ανακτούμε πληροφορίες κεφαλίδας και υποσέλιδου από αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Visual Studio: Εγκαταστήστε το Visual Studio στο σύστημά σας.
2.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/tasks/net/).
3. Βασική γνώση C#: Εξοικείωση με τη γλώσσα προγραμματισμού C#.

## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας C#. Αυτό θα σας επιτρέψει να αποκτήσετε πρόσβαση στις κλάσεις και τις μεθόδους που παρέχονται από τη βιβλιοθήκη Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Βήμα 1: Αρχικοποίηση αντικειμένου έργου
 Για να ξεκινήσετε, πρέπει να αρχικοποιήσετε το a`Project` αντικείμενο με τη φόρτωση ενός υπάρχοντος αρχείου MS Project.
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Βήμα 2: Ανάκτηση πληροφοριών κεφαλίδας και υποσέλιδου
 Αφού φορτώσετε το αρχείο του έργου, μπορείτε να ανακτήσετε τις πληροφορίες κεφαλίδας και υποσέλιδου χρησιμοποιώντας το`PageInfo` ιδιοκτησία.
```csharp
var info = project.DefaultView.PageInfo;
// Πληροφορίες κεφαλίδας
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Πληροφορίες υποσέλιδου
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Ακολουθώντας αυτά τα απλά βήματα, μπορείτε εύκολα να ανακτήσετε πληροφορίες κεφαλίδας και υποσέλιδου από αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο εξαγωγής πληροφοριών κεφαλίδας και υποσέλιδου από αρχεία MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Αυτή η ισχυρή βιβλιοθήκη απλοποιεί την εργασία με αρχεία Project σε εφαρμογές C#, παρέχοντας στους προγραμματιστές ισχυρά εργαλεία χειρισμού.
### Συχνές ερωτήσεις
### Μπορώ να τροποποιήσω τις πληροφορίες κεφαλίδας και υποσέλιδου χρησιμοποιώντας το Aspose.Tasks;
Ναι, μπορείτε να τροποποιήσετε τις πληροφορίες κεφαλίδας και υποσέλιδου μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για .NET.
### Το Aspose.Tasks υποστηρίζει άλλες μορφές αρχείων έργου εκτός από το MS Project;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες μορφές αρχείων έργου, συμπεριλαμβανομένων των MPP, XML και MPX.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω τεκμηρίωση για το Aspose.Tasks;
 Μπορείτε να βρείτε την τεκμηρίωση για το Aspose.Tasks[εδώ](https://reference.aspose.com/tasks/net/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Tasks;
 Μπορείτε να λάβετε υποστήριξη για το Aspose.Tasks μεταβαίνοντας στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).