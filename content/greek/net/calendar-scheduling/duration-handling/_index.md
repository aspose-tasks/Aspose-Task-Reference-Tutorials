---
title: Duration Handling στο Aspose.Tasks
linktitle: Duration Handling στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Μάθετε πώς να χειρίζεστε αποτελεσματικά τις διάρκειες στο Aspose.Tasks για .NET με οδηγίες βήμα προς βήμα.
type: docs
weight: 30
url: /el/net/calendar-scheduling/duration-handling/
---
## Εισαγωγή

Ο αποτελεσματικός χειρισμός της διάρκειας είναι ζωτικής σημασίας στις εφαρμογές διαχείρισης έργων. Το Aspose.Tasks για .NET παρέχει ισχυρή λειτουργικότητα για την αποτελεσματική διαχείριση των διάρκειων. Σε αυτό το σεμινάριο, θα εξερευνήσουμε διάφορες πτυχές του χειρισμού διάρκειας χρησιμοποιώντας το Aspose.Tasks για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# είναι απαραίτητη για την κατανόηση και την υλοποίηση των παραδειγμάτων.
2. Visual Studio: Εγκαταστήστε το Visual Studio IDE για να δημιουργήσετε και να εκτελέσετε εφαρμογές .NET.
3.  Aspose.Tasks για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Tasks για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/tasks/net/).

## Εισαγωγή χώρων ονομάτων

Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσουμε τις λειτουργίες Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα σε μια μορφή οδηγού βήμα προς βήμα:

## Ενημέρωση Διάρκειας εργασιών

### Βήμα 1: Φόρτωση αρχείου έργου

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Βήμα 2: Λήψη Εργασίας και Διάρκειας

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Βήμα 3: Διάρκεια ενημέρωσης

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Βήμα 4: Εμφάνιση ενημερωμένης διάρκειας

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Αφαίρεση Διάρκειας Εργασιών

### Βήμα 1: Φόρτωση αρχείου έργου

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Βήμα 2: Λήψη Εργασίας και Διάρκειας

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Βήμα 3: Αφαίρεση διάρκειας

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Βήμα 4: Εμφάνιση ενημερωμένης διάρκειας

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Μετατροπή Διάρκειας σε Χρονικό Διάστημα

### Βήμα 1: Φόρτωση αρχείου έργου

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Βήμα 2: Λήψη Εργασίας και Διάρκειας

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Βήμα 3: Μετατροπή Διάρκειας σε Χρονικό Διάστημα

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Μετατροπή διάρκειας σε συμβολοσειρά

### Βήμα 1: Φόρτωση αρχείου έργου

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Βήμα 2: Λήψη Εργασίας και Διάρκειας

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Βήμα 3: Μετατρέψτε τη διάρκεια σε συμβολοσειρά

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## συμπέρασμα

Σε αυτό το σεμινάριο, καλύψαμε διάφορες πτυχές του χειρισμού διάρκειας στο Aspose.Tasks για .NET. Η κατανόηση και η αποτελεσματική διαχείριση των διάρκειων είναι ζωτικής σημασίας για την επιτυχημένη διαχείριση έργου. Το Aspose.Tasks παρέχει ολοκληρωμένες λειτουργίες για την απλοποίηση των εργασιών διαχείρισης διάρκειας στις εφαρμογές σας .NET.

## Συχνές ερωτήσεις

### Ε1: Τι είναι το Aspose.Tasks για .NET;

A1: Το Aspose.Tasks για .NET είναι μια ισχυρή βιβλιοθήκη για εργασία με αρχεία Microsoft Project σε εφαρμογές .NET.

### Ε2: Μπορεί το Aspose.Tasks να χειριστεί περίπλοκες δομές έργου;

A2: Ναι, το Aspose.Tasks μπορεί να χειριστεί πολύπλοκες δομές έργου με ευκολία, παρέχοντας εκτεταμένα API για χειρισμό.

### Ε3: Είναι το Aspose.Tasks για .NET συμβατό με .NET Core;

A3: Ναι, το Aspose.Tasks για .NET είναι συμβατό με το .NET Core, επιτρέποντάς το να το χρησιμοποιείτε σε εφαρμογές πολλαπλών πλατφορμών.

### Ε4: Το Aspose.Tasks υποστηρίζει την ανάγνωση και τη σύνταξη αρχείων Microsoft Project;

A4: Ναι, το Aspose.Tasks υποστηρίζει την ανάγνωση και εγγραφή αρχείων Microsoft Project σε διάφορες μορφές, συμπεριλαμβανομένων MPP, XML και MPX.

### Ε5: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Tasks για .NET;

 A5: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Tasks για .NET από[εδώ](https://releases.aspose.com/).