---
title: Ορισμοί χειρισμού κώδικα περίληψης έργου MS στο Aspose.Tasks
linktitle: Χειρισμός ορισμών κώδικα περίγραμμα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε τους ορισμούς του κώδικα περίληψης του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET, ενδυναμώνοντας τις εφαρμογές διαχείρισης έργων σας.
weight: 12
url: /el/net/outline-code-page-settings/outline-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμοί χειρισμού κώδικα περίληψης έργου MS στο Aspose.Tasks

## Εισαγωγή
Το Microsoft Project είναι ένα ισχυρό εργαλείο για τη διαχείριση έργων και το Aspose.Tasks για .NET παρέχει ολοκληρωμένη υποστήριξη για το χειρισμό αρχείων έργου μέσω προγραμματισμού. Μια βασική πτυχή της διαχείρισης έργου είναι η οργάνωση εργασιών χρησιμοποιώντας κώδικες περιγράμματος. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να χειριστούμε τους ορισμούς του κώδικα περίγραμμα του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET.
## Προαπαιτούμενα
Πριν προχωρήσουμε στην υλοποίηση, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκατάσταση του Aspose.Tasks για .NET
 Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Tasks για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).
### 2. Βασική κατανόηση της C# και του .NET Framework
Εξοικειωθείτε με τη γλώσσα προγραμματισμού C# και το πλαίσιο .NET καθώς αυτό το σεμινάριο απαιτεί μεσαίου επιπέδου γνώση C#.
### 3. Ολοκληρωμένο Αναπτυξιακό Περιβάλλον (IDE)
Έχετε ένα IDE όπως το Visual Studio εγκατεστημένο στο σύστημά σας για κωδικοποίηση και εντοπισμό σφαλμάτων.
## Εισαγωγή χώρων ονομάτων
Πριν ξεκινήσουμε την κωδικοποίηση, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για να δουλέψουμε με το Aspose.Tasks για .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα για μια σαφή κατανόηση.
## Βήμα 1: Φορτώστε το Αρχείο Έργου
Αρχικά, πρέπει να φορτώσουμε το αρχείο MS Project στην εφαρμογή μας.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Βήμα 2: Δημιουργήστε ορισμό κώδικα περίγραμμα
Τώρα, ας δημιουργήσουμε έναν νέο ορισμό κώδικα περίγραμμα.
```csharp
var outline = new OutlineCodeDefinition();
```
## Βήμα 3: Ορίστε τον αριθμό και το όνομα πεδίου
Ορίστε τον αριθμό πεδίου και το όνομα για τον κωδικό περίγραμμα.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Βήμα 4: Ορίστε το GUID και άλλες ιδιότητες
Ορίστε το GUID και άλλες ιδιότητες του κώδικα περίγραμμα.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Βήμα 5: Προσθέστε μάσκα περιγράμματος
Προσθέστε μια μάσκα περιγράμματος στον κώδικα περιγράμματος.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Βήμα 6: Ορίστε άλλες ιδιότητες
Ορίστε πρόσθετες ιδιότητες του κώδικα περίγραμμα.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Βήμα 7: Προσθήκη τιμής περίγραμμα
Τέλος, ας προσθέσουμε μια τιμή περίγραμμα στον κώδικα περίγραμμα.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να χειριζόμαστε τους ορισμούς του κώδικα περίγραμμα του MS Project χρησιμοποιώντας το Aspose.Tasks για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να χειριστείτε αποτελεσματικά τους κωδικούς περιγράμματος στα αρχεία του έργου σας μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με διαφορετικές εκδόσεις αρχείων MS Project;
Α: Ναι, το Aspose.Tasks για .NET υποστηρίζει διάφορες εκδόσεις αρχείων MS Project, συμπεριλαμβανομένων των μορφών MPP και XML.
### Ε2: Είναι το Aspose.Tasks για .NET συμβατό με .NET Core;
Α: Ναι, το Aspose.Tasks για .NET είναι συμβατό με το .NET Core, επιτρέποντάς σας να αναπτύσσετε εφαρμογές πολλαπλών πλατφορμών.
### Ε3: Μπορώ να χειριστώ τις αναθέσεις πόρων χρησιμοποιώντας το Aspose.Tasks για .NET;
Α: Ναι, το Aspose.Tasks για .NET παρέχει εκτεταμένες δυνατότητες για τον χειρισμό αναθέσεων πόρων, συμπεριλαμβανομένης της προσθήκης, της ενημέρωσης και της αφαίρεσης αναθέσεων.
### Ε4: Το Aspose.Tasks για .NET υποστηρίζει την ανάγνωση προσαρμοσμένων πεδίων από αρχεία MS Project;
Α: Απολύτως, το Aspose.Tasks για .NET υποστηρίζει την ανάγνωση και εγγραφή προσαρμοσμένων πεδίων, συμπεριλαμβανομένων των κωδικών περίγραμμα, από αρχεία MS Project.
### Ε5: Υπάρχει ένα φόρουμ κοινότητας για το Aspose.Tasks για .NET;
 Α: Ναι, μπορείτε να εγγραφείτε στο φόρουμ κοινότητας για το Aspose.Tasks για .NET[εδώ](https://forum.aspose.com/c/tasks/15) για να κάνετε ερωτήσεις, να μοιραστείτε γνώσεις και να συνεργαστείτε με άλλους προγραμματιστές.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
