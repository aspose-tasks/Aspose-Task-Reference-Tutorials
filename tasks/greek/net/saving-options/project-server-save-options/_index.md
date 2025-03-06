---
title: Αποθήκευση διακομιστή Επιλογές έργου MS για Aspose.Tasks
linktitle: Επιλογές αποθήκευσης διακομιστή έργου για Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να αποθηκεύετε τις επιλογές του Microsoft Project για το Aspose.Tasks χρησιμοποιώντας την ενοποίηση του Project Server. Βελτιώστε τις ροές εργασιών διαχείρισης του έργου σας.
type: docs
weight: 16
url: /el/net/saving-options/project-server-save-options/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα εμβαθύνουμε στην αποθήκευση των επιλογών του Microsoft Project για το Aspose.Tasks χρησιμοποιώντας το Project Server. Το Aspose.Tasks είναι ένα ισχυρό API .NET που επιτρέπει στους προγραμματιστές να εργάζονται με αρχεία Microsoft Project μέσω προγραμματισμού. Αξιοποιώντας τις δυνατότητες του Project Server, μπορούμε να ενσωματώσουμε απρόσκοπτα το Aspose.Tasks στις ροές εργασιών διαχείρισης έργων μας. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Tasks για .NET: Εγκαταστήστε το Aspose.Tasks για .NET από το[σύνδεσμος λήψης](https://releases.aspose.com/tasks/net/).
   
2. Πρόσβαση στον Διακομιστή Έργου: Θα χρειαστείτε τα διαπιστευτήρια πρόσβασης και τη διεύθυνση URL της παρουσίας του διακομιστή έργου σας. Εάν δεν έχετε, μπορείτε να αποκτήσετε δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).
3. Αρχείο Microsoft Project: Προετοιμάστε το αρχείο Microsoft Project (.mpp) που θέλετε να αποθηκεύσετε χρησιμοποιώντας το Aspose.Tasks.

## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Βήμα 1: Αρχικοποίηση έργου και διαπιστευτηρίων
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Βεβαιωθείτε ότι έχετε αντικαταστήσει`"Your Document Directory"`, `URL`, `Domain`, `UserName` , και`Password` με τις πραγματικές σας αξίες.
## Βήμα 2: Δημιουργήστε Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Βήμα 3: Καθορίστε τις επιλογές αποθήκευσης
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Ρυθμίστε το`ProjectGuid`, `ProjectName`, `Timeout` , και`PollingInterval` σύμφωνα με τις απαιτήσεις σας.
## Βήμα 4: Αποθήκευση έργου στον διακομιστή
```csharp
manager.CreateNewProject(project, options);
```
Αυτό θα αποθηκεύσει το έργο στον διακομιστή έργου με τις καθορισμένες επιλογές.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να αποθηκεύουμε τις επιλογές του Microsoft Project για το Aspose.Tasks χρησιμοποιώντας την ενοποίηση του Project Server. Ακολουθώντας αυτά τα βήματα, μπορείτε να ενσωματώσετε απρόσκοπτα το Aspose.Tasks στις ροές εργασιών διαχείρισης του έργου σας, βελτιώνοντας την αποτελεσματικότητα και την παραγωγικότητα.
## Συχνές ερωτήσεις
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Tasks με διαφορετικές εκδόσεις του Microsoft Project;
Α: Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις του Microsoft Project, διασφαλίζοντας τη συμβατότητα σε διαφορετικά περιβάλλοντα.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks;
 Α: Ναι, μπορείτε να αποκτήσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Tasks από[εδώ](https://releases.aspose.com/).
### Ε: Υποστηρίζει το Aspose.Tasks multi-threading;
Α: Ναι, το Aspose.Tasks έχει σχεδιαστεί για να είναι ασφαλές σε νήματα, επιτρέποντας την ταυτόχρονη πρόσβαση στα δεδομένα του έργου.
### Ε: Μπορώ να προσαρμόσω τις επιλογές αποθήκευσης όταν χρησιμοποιώ την ενοποίηση του Project Server;
Α: Ναι, μπορείτε να προσαρμόσετε τις επιλογές αποθήκευσης όπως το όνομα του έργου, το χρονικό όριο λήξης και το διάστημα ψηφοφορίας ανάλογα με τις απαιτήσεις σας.
### Ε: Πού μπορώ να βρω υποστήριξη για το Aspose.Tasks;
 Α: Μπορείτε να βρείτε υποστήριξη και βοήθεια στο[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15).