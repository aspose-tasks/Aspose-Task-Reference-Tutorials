---
title: Εργασία με το Ημερολόγιο στο Aspose.Tasks
linktitle: Εργασία με το Ημερολόγιο στο Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Διαχειριστείτε τα ημερολόγια έργων, υπολογίστε τις διάρκειες, χειριστείτε τις εξαιρέσεις με ευκολία χρησιμοποιώντας το Aspose.Tasks για .NET.
type: docs
weight: 10
url: /el/net/calendar-scheduling/working-with-calendar/
---
## Εισαγωγή

Το Aspose.Tasks για .NET παρέχει ισχυρές δυνατότητες για εργασία με ημερολόγια, επιτρέποντας στους προγραμματιστές να διαχειρίζονται αποτελεσματικά τα χρονοδιαγράμματα έργων και τις κατανομές πόρων. Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να χρησιμοποιήσετε το Aspose.Tasks για αλληλεπίδραση με ημερολόγια, καλύπτοντας βασικές λειτουργίες όπως η ανάκτηση πληροφοριών ημερολογίου, ο καθορισμός εβδομάδων εργασίας, ο υπολογισμός των ωρών εργασίας και πολλά άλλα.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:

- Βασική κατανόηση της γλώσσας προγραμματισμού C#.
-  Εγκατάσταση του Aspose.Tasks για .NET. Εάν δεν είναι εγκατεστημένο, κατεβάστε το από[εδώ](https://releases.aspose.com/tasks/net/).
- Εξοικείωση με το Visual Studio ή οποιοδήποτε άλλο προτιμώμενο περιβάλλον ανάπτυξης .NET.

## Εισαγωγή χώρων ονομάτων

Πριν ξεκινήσετε την κωδικοποίηση, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα σε μια μορφή οδηγού βήμα προς βήμα:

## Βήμα 1: Ανάκτηση πληροφοριών ημερολογίου

Για να ανακτήσετε πληροφορίες ημερολογίου από ένα έργο, ακολουθήστε τα εξής βήματα:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Ανάκτηση πληροφοριών ημερολογίων
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Επαναλάβετε σε κάθε ημερολόγιο του έργου.
- Εκτυπώστε το UID και το όνομα κάθε ημερολογίου.

## Βήμα 2: Διαβάστε τις Πληροφορίες Εβδομάδων Εργασίας

Για να διαβάσετε πληροφορίες εργάσιμων εβδομάδων από ένα ημερολόγιο, ακολουθήστε τα εξής βήματα:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λήψη του ημερολογίου κατά UID.
- Επαναλάβετε κάθε εργάσιμη εβδομάδα στο ημερολόγιο.
- Εκτυπώστε το όνομα, την ημερομηνία έναρξης και την ημερομηνία λήξης κάθε εργάσιμης εβδομάδας.
- Διασχίστε εργάσιμες ημέρες και ώρες εργασίας μέσα σε κάθε εβδομάδα.

## Βήμα 3: Διαβάστε τις ιδιότητες ημερολογίου

Για να διαβάσετε τις ιδιότητες των ημερολογίων έργων, ακολουθήστε τα εξής βήματα:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Επαναλάβετε σε κάθε ημερολόγιο του έργου.
- Εκτυπώστε το UID, το όνομα και εάν πρόκειται για βασικό ημερολόγιο.
- Εκτύπωση ωρών εργασίας για κάθε τύπο ημέρας.

## Βήμα 4: Υπολογίστε τις ώρες εργασίας

Για να υπολογίσετε τις ώρες εργασίας για μια εργασία, ακολουθήστε τα εξής βήματα:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λάβετε λεπτομέρειες εργασίας όπως ημερολόγιο, ημερομηνία έναρξης και ημερομηνία λήξης.
- Υπολογίστε τις ώρες εργασίας επαναλαμβάνοντας κάθε μέρα και ελέγχοντας αν είναι εργάσιμη.
- Αθροίστε τη συνολική διάρκεια σε λεπτά.

## Βήμα 5: Καθορίστε τις εργάσιμες ημέρες για το ημερολόγιο

Για να ορίσετε τις καθημερινές για ένα ημερολόγιο, ακολουθήστε τα εξής βήματα:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Εξήγηση:
- Δημιουργήστε ένα νέο έργο και ημερολόγιο.
- Προσθέστε προεπιλεγμένες εργάσιμες ημέρες (Δευτέρα έως Πέμπτη) και προσαρμοσμένες ώρες εργασίας για την Παρασκευή.
- Ορίστε το Σάββατο και την Κυριακή ως μη εργάσιμες ημέρες.

## Βήμα 6: Γράψτε τα ενημερωμένα δεδομένα ημερολογίου στο MPP

Για να γράψετε ενημερωμένα δεδομένα ημερολογίου σε ένα αρχείο MPP, ακολουθήστε τα εξής βήματα:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/.");
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου και ανακτήστε το τυπικό ημερολόγιο.
- Τροποποιήστε τα δεδομένα ημερολογίου, όπως εξαιρέσεις και χρόνους εργασίας.
- Αποθηκεύστε το ενημερωμένο έργο με τα τροποποιημένα δεδομένα ημερολογίου.

## Βήμα 7: Υπολογίστε την Ημερομηνία λήξης της διαίρεσης εργασίας

Για να υπολογίσετε την ημερομηνία λήξης μιας διαίρεσης εργασίας, ακολουθήστε τα εξής βήματα:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου και ανακτήστε την εργασία διαχωρισμού.
- Λάβετε το ημερολόγιο του έργου.
- Υπολογίστε την ημερομηνία λήξης με βάση μια προσαρμοσμένη διάρκεια.

## Βήμα 8: Ανάκτηση εξαιρέσεων ημερολογίου

Για να ανακτήσετε πληροφορίες σχετικά με τις εξαιρέσεις ημερολογίου, ακολουθήστε τα εξής βήματα:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Επαναλάβετε κάθε ημερολόγιο και τις εξαιρέσεις του.
- Εκτυπώστε τις ημερομηνίες έναρξης και λήξης κάθε εξαίρεσης.

## Βήμα 9: Λήψη ημερολογίου πόρων βάσης

Για να εργαστείτε με το βασικό ημερολόγιο του ημερολογίου ενός πόρου, ακολουθήστε τα εξής βήματα:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Προσθέστε έναν πόρο και το ημερολόγιό του.
- Εκτυπώστε το βασικό όνομα ημερολογίου για όλους τους πόρους.

## Βήμα 10: Διαγραφή Ημερολογίου

Για να διαγράψετε ένα ημερολόγιο από ένα έργο, ακολουθήστε τα εξής βήματα:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λάβετε το ημερολόγιο με το όνομα.
- Διαγράψτε το ημερολόγιο.

## Βήμα 11: Λάβετε την ημερομηνία λήξης με την έναρξη και την εργασία

Για να υπολογίσετε μια ημερομηνία λήξης με βάση την ημερομηνία έναρξης και την εργασία, ακολουθήστε τα εξής βήματα:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Αποκτήστε το τυπικό ημερολόγιο.
- Καθορίστε ημερομηνία έναρξης και διάρκεια εργασίας.
- Υπολογίστε την ημερομηνία λήξης με βάση την ημερομηνία έναρξης και την εργασία.

## Βήμα 12: Ξεκινήστε την επόμενη εργάσιμη ημέρα

Για να ξεκινήσετε την επόμενη εργάσιμη ημέρα χρησιμοποιώντας ένα ημερολόγιο, ακολουθήστε τα εξής βήματα:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λήψη του ημερολογίου κατά UID.
- Λάβετε ώρα έναρξης την επόμενη εργάσιμη ημέρα.

## Βήμα 13: Λάβετε το τέλος της προηγούμενης εργάσιμης ημέρας

Για να λάβετε το τέλος της προηγούμενης εργάσιμης ημέρας χρησιμοποιώντας ένα ημερολόγιο, ακολουθήστε τα εξής βήματα:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λήψη του ημερολογίου κατά UID.
- Λάβετε την ώρα λήξης της προηγούμενης εργάσιμης ημέρας.

## Βήμα 14: Λήψη ημερομηνίας έναρξης από το τέλος και τη διάρκεια

Για να λάβετε μια ημερομηνία έναρξης κατά ημερομηνία λήξης και διάρκεια, ακολουθήστε τα εξής βήματα:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λήψη του ημερολογίου κατά UID.
- Υπολογίστε την ημερομηνία έναρξης από την ημερομηνία λήξης και τη διάρκεια.

## Βήμα 15: Λήψη ωραρίου εργασίας

Για να λάβετε ώρες εργασίας για μια συγκεκριμένη ημερομηνία, ακολουθήστε τα εξής βήματα:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λήψη του ημερολογίου κατά UID.
- Λάβετε τις ώρες εργασίας για την καθορισμένη ημερομηνία.

## Βήμα 16: Λήψη ωρών εργασίας

Για να λάβετε ώρες εργασίας για μια συγκεκριμένη ημερομηνία, ακολουθήστε τα εξής βήματα:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Εξήγηση:
- Φορτώστε το αρχείο του έργου.
- Λήψη του ημερολογίου κατά UID.
- Λάβετε τις ώρες εργασίας για την καθορισμένη ημερομηνία.

## συμπέρασμα

Η εργασία με ημερολόγια στο Aspose.Tasks για .NET είναι ζωτικής σημασίας για την αποτελεσματική διαχείριση των χρονοδιαγραμμάτων έργων. Με τα παρεχόμενα παραδείγματα και τους οδηγούς βήμα προς βήμα, μπορείτε εύκολα να χειριστείτε δεδομένα ημερολογίου, να υπολογίσετε τη διάρκεια εργασιών και να χειριστείτε αποτελεσματικά τις εξαιρέσεις. Ενσωματώνοντας αυτές τις λειτουργίες στις εφαρμογές σας, μπορείτε να απλοποιήσετε τις διαδικασίες διαχείρισης έργων και να εξασφαλίσετε ακριβή προγραμματισμό.

## Συχνές ερωτήσεις

### Ε1: Χρειάζομαι άδεια χρήσης για να χρησιμοποιήσω το Aspose.Tasks για .NET;

 A1: Ναι, χρειάζεστε έγκυρη άδεια χρήσης για να χρησιμοποιήσετε το Aspose.Tasks για .NET στις εφαρμογές σας. Μπορείτε να αγοράσετε μια πλήρη άδεια χρήσης ή να αποκτήσετε μια προσωρινή άδεια 30 ημερών από[εδώ](https://purchase.aspose.com/temporary-license/).

### Ε2: Μπορώ να τροποποιήσω τις εξαιρέσεις ημερολογίου μέσω προγραμματισμού;

A2: Ναι, μπορείτε να προσθέσετε, να ενημερώσετε ή να διαγράψετε εξαιρέσεις ημερολογίου μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Tasks για API .NET.

### Ε3: Πώς μπορώ να υπολογίσω τις ημερομηνίες λήξης εργασιών με προσαρμοσμένες διάρκειες;

 A3: Το Aspose.Tasks για .NET παρέχει μεθόδους όπως`GetTaskFinishDateFromDuration()` για τον υπολογισμό των ημερομηνιών λήξης εργασιών με βάση προσαρμοσμένες διάρκειες.

### Ε4: Είναι δυνατή η δημιουργία προσαρμοσμένων ημερολογίων, όπως ημερολόγια νυχτερινής βάρδιας;

A4: Ναι, μπορείτε να δημιουργήσετε προσαρμοσμένα ημερολόγια όπως ημερολόγια νυχτερινής βάρδιας χρησιμοποιώντας το Aspose.Tasks για API .NET.

### Ε5: Μπορώ να ανακτήσω πληροφορίες σχετικά με εξαιρέσεις ημερολογίου από αρχεία έργου;

A5: Ναι, μπορείτε εύκολα να ανακτήσετε πληροφορίες σχετικά με εξαιρέσεις ημερολογίου από αρχεία έργου χρησιμοποιώντας το Aspose.Tasks για .NET.