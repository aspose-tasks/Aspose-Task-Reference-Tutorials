---
title: Mastering Table Field Collections στο Aspose.Tasks για .NET
linktitle: Συλλογή πεδίων πίνακα στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Εξερευνήστε τον δυναμικό κόσμο της διαχείρισης έργων με το Aspose.Tasks για .NET. Μάθετε πώς να χειρίζεστε συλλογές πεδίων πινάκων για μια προσαρμοσμένη εμπειρία έργου.
weight: 13
url: /el/net/task-table-management/table-field-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Table Field Collections στο Aspose.Tasks για .NET

## Εισαγωγή
Το Aspose.Tasks για .NET είναι μια ισχυρή βιβλιοθήκη που διευκολύνει τη διαχείριση έργων παρέχοντας εκτεταμένες λειτουργίες για εργασία με αρχεία Microsoft Project. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη συλλογή πεδίων πίνακα στο Aspose.Tasks, διερευνώντας πώς να τα χειριστείτε και να τα διαχειριστείτε αποτελεσματικά χρησιμοποιώντας το C#.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες ρυθμίσεις:
- Γνώση εργασίας γλώσσας προγραμματισμού C#.
-  Εγκαταστάθηκε το Aspose.Tasks για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/tasks/net/).
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Visual Studio.
## Εισαγωγή χώρων ονομάτων
Αρχικά, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στην αρχή του αρχείου C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα σε μια μορφή οδηγού βήμα προς βήμα.
## Βήμα 1: Ορίστε τον Κατάλογο εγγράφων
Ορίστε τη διαδρομή προς τον κατάλογο των εγγράφων σας όπου βρίσκεται το αρχείο Project.
```csharp
String DataDir = "Your Document Directory";
```
## Βήμα 2: Φορτώστε το Αρχείο Έργου
Φορτώστε το αρχείο του έργου χρησιμοποιώντας τη βιβλιοθήκη Aspose.Tasks.
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## Βήμα 3: Επαναλάβετε τα πεδία του πίνακα
Επαναλάβετε τα πεδία του πίνακα εντός του έργου.
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    //επανάληψη σε πεδία πίνακα
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## Βήμα 4: Προσθέστε ένα νέο πεδίο πίνακα
Προσθέστε ένα νέο πεδίο πίνακα στον υπάρχοντα πίνακα.
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## Βήμα 5: Εισαγάγετε ένα νέο πεδίο
Εισαγάγετε ένα νέο πεδίο σε μια συγκεκριμένη θέση μέσα στον πίνακα.
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## Βήμα 6: Επεξεργαστείτε το Πεδίο Νέου Πίνακα
Επεξεργαστείτε το πεδίο πίνακα που προστέθηκε πρόσφατα χρησιμοποιώντας την πρόσβαση ευρετηρίου.
```csharp
table.TableFields[idx].WrapHeader = true;
```
## Βήμα 7: Αφαιρέστε το πεδίο
Καταργήστε το πεδίο πίνακα είτε ένα προς ένα είτε διαγράψτε ολόκληρη τη συλλογή.
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// Αφαιρέστε το πεδίο
table.TableFields.RemoveAt(idx);
```
## Βήμα 8: Εκκαθαρίστε τη Συλλογή
Διαγράψτε τη συλλογή πεδίων πίνακα είτε ένα προς ένα είτε εντελώς.
```csharp
if (deleteOneByOne)
{
    // Αφαιρέστε ένα προς ένα
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // Διαγράψτε εντελώς τη συλλογή
    table.TableFields.Clear();
}
```
Τώρα έχετε εξερευνήσει με επιτυχία τη συλλογή πεδίων πίνακα στο Aspose.Tasks για .NET, επιτρέποντάς σας να τα διαχειρίζεστε και να τα χειρίζεστε σύμφωνα με τις απαιτήσεις του έργου σας.
## συμπέρασμα
Συμπερασματικά, η κατανόηση του τρόπου εργασίας με συλλογές πεδίων πινάκων στο Aspose.Tasks για .NET ανοίγει δυνατότητες για αποτελεσματική διαχείριση και προσαρμογή έργου. Με την ευελιξία που παρέχει το Aspose.Tasks, οι προγραμματιστές μπορούν να προσαρμόσουν τις εφαρμογές τους για να ανταποκρίνονται απρόσκοπτα σε συγκεκριμένες ανάγκες του έργου.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Tasks για .NET με οποιαδήποτε έκδοση των αρχείων Microsoft Project;
Ναι, το Aspose.Tasks υποστηρίζει διάφορες εκδόσεις αρχείων Microsoft Project, διασφαλίζοντας συμβατότητα και ευελιξία.
### Είναι δυνατή η δυναμική δημιουργία και τροποποίηση πεδίων πίνακα κατά τη διάρκεια του χρόνου εκτέλεσης;
Απολύτως! Όπως φαίνεται στο σεμινάριο, μπορείτε να προσθέσετε, να εισαγάγετε, να επεξεργαστείτε και να αφαιρέσετε πεδία πίνακα δυναμικά όπως απαιτείται.
### Υπάρχουν ζητήματα αδειοδότησης για τη χρήση του Aspose.Tasks για .NET σε ένα εμπορικό έργο;
 Ναι, χρειάζεστε έγκυρη άδεια χρήσης για να χρησιμοποιήσετε το Aspose.Tasks για .NET σε ένα εμπορικό έργο. Μπορείτε να αποκτήσετε άδεια[εδώ](https://purchase.aspose.com/buy).
### Πώς μπορώ να λάβω υποστήριξη ή να ζητήσω βοήθεια με το Aspose.Tasks για .NET;
 Επισκέψου το[Aspose.Tasks φόρουμ](https://forum.aspose.com/c/tasks/15)για να λάβετε υποστήριξη, να κάνετε ερωτήσεις και να συνεργαστείτε με την κοινότητα.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Tasks για .NET;
 Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Tasks για .NET με μια δωρεάν δοκιμή. Κατέβασέ το[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
