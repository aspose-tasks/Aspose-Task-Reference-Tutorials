---
title: Bekerja dengan Kalender di Aspose.Tasks
linktitle: Bekerja dengan Kalender di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Kelola kalender proyek, hitung durasi, tangani pengecualian dengan mudah menggunakan Aspose.Tasks untuk .NET.
type: docs
weight: 10
url: /id/net/calendar-scheduling/working-with-calendar/
---
## Perkenalan

Aspose.Tasks untuk .NET menyediakan fitur canggih untuk bekerja dengan kalender, memungkinkan pengembang mengelola jadwal proyek dan alokasi sumber daya secara efisien. Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks untuk berinteraksi dengan kalender, mencakup operasi penting seperti mengambil informasi kalender, menentukan minggu kerja, menghitung jam kerja, dan banyak lagi.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan prasyarat berikut:

- Pemahaman dasar bahasa pemrograman C#.
-  Pemasangan Aspose.Tasks untuk .NET. Jika belum diinstal, unduh dari[Di Sini](https://releases.aspose.com/tasks/net/).
- Keakraban dengan Visual Studio atau lingkungan pengembangan .NET pilihan lainnya.

## Impor Namespace

Sebelum Anda memulai coding, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah:

## Langkah 1: Ambil Informasi Kalender

Untuk mengambil informasi kalender dari suatu proyek, ikuti langkah-langkah berikut:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Ambil Informasi Kalender
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

Penjelasan:
- Muat file proyek.
- Ulangi setiap kalender dalam proyek.
- Cetak UID dan nama setiap kalender.

## Langkah 2: Baca Informasi Minggu Kerja

Untuk membaca informasi minggu kerja dari kalender, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Dapatkan kalender dengan UID.
- Ulangi setiap minggu kerja di kalender.
- Cetak nama, tanggal mulai, dan tanggal akhir setiap minggu kerja.
- Lewati hari kerja dan waktu kerja dalam setiap minggunya.

## Langkah 3: Baca Properti Kalender

Untuk membaca properti kalender proyek, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Ulangi setiap kalender dalam proyek.
- Cetak UID, nama, dan apakah itu kalender dasar.
- Cetak jam kerja untuk setiap jenis hari.

## Langkah 4: Hitung Jam Kerja

Untuk menghitung jam kerja suatu tugas, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Dapatkan detail tugas seperti kalender, tanggal mulai, dan tanggal akhir.
- Hitung jam kerja dengan mengulangi setiap hari dan memeriksa apakah itu hari kerja.
- Jumlahkan total durasi dalam menit.

## Langkah 5: Tentukan Hari Kerja untuk Kalender

Untuk menentukan hari kerja pada kalender, ikuti langkah-langkah berikut:

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

Penjelasan:
- Buat proyek dan kalender baru.
- Tambahkan hari kerja default (Senin hingga Kamis) dan waktu kerja khusus untuk hari Jumat.
- Tetapkan hari Sabtu dan Minggu sebagai hari tidak bekerja.

## Langkah 6: Tulis Data Kalender yang Diperbarui ke MPP

Untuk menulis data kalender yang diperbarui ke file MPP, ikuti langkah-langkah berikut:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://pembelian.aspose.com/temporary-license/).");
    }
}
```

Penjelasan:
- Muat file proyek dan ambil kalender standar.
- Ubah data kalender seperti pengecualian dan waktu kerja.
- Simpan proyek yang diperbarui dengan data kalender yang dimodifikasi.

## Langkah 7: Hitung Tanggal Selesai Tugas Terpisah

Untuk menghitung tanggal selesainya tugas terpisah, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek dan ambil tugas terpisah.
- Dapatkan kalender proyek.
- Hitung tanggal selesai berdasarkan durasi khusus.

## Langkah 8: Ambil Pengecualian Kalender

Untuk mengambil informasi tentang pengecualian kalender, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Ulangi setiap kalender dan pengecualiannya.
- Cetak tanggal mulai dan akhir setiap pengecualian.

## Langkah 9: Dapatkan Kalender Sumber Daya Dasar

Untuk bekerja dengan kalender dasar kalender sumber daya, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Tambahkan sumber daya dan kalendernya.
- Cetak nama kalender dasar untuk semua sumber daya.

## Langkah 10: Hapus Kalender

Untuk menghapus kalender dari proyek, ikuti langkah-langkah berikut:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Penjelasan:
- Muat file proyek.
- Dapatkan kalender berdasarkan nama.
- Hapus kalender.

## Langkah 11: Dapatkan Tanggal Selesai Berdasarkan Mulai dan Bekerja

Untuk menghitung tanggal selesai berdasarkan tanggal mulai dan pekerjaan, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Dapatkan kalender standar.
- Tentukan tanggal mulai dan durasi kerja.
- Hitung tanggal selesai berdasarkan tanggal mulai dan pekerjaan.

## Langkah 12: Mulailah Hari Kerja Berikutnya

Untuk memulai hari kerja berikutnya dengan menggunakan kalender, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Dapatkan kalender dengan UID.
- Dapatkan waktu mulai hari kerja berikutnya.

## Langkah 13: Dapatkan Akhir Hari Kerja Sebelumnya

Untuk mengakhiri hari kerja sebelumnya dengan menggunakan kalender, ikuti langkah-langkah berikut:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Penjelasan:
- Muat file proyek.
- Dapatkan kalender dengan UID.
- Dapatkan waktu berakhir hari kerja sebelumnya.

## Langkah 14: Dapatkan Tanggal Mulai Dari Selesai Dan Durasi

Untuk mendapatkan tanggal mulai berdasarkan tanggal selesai dan durasi, ikuti langkah-langkah berikut:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Penjelasan:
- Muat file proyek.
- Dapatkan kalender dengan UID.
- Hitung tanggal mulai dari tanggal selesai dan durasi.

## Langkah 15: Dapatkan Jam Kerja

Untuk mendapatkan jam kerja pada tanggal tertentu, ikuti langkah-langkah berikut:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Penjelasan:
- Muat file proyek.
- Dapatkan kalender dengan UID.
- Dapatkan jam kerja untuk tanggal yang ditentukan.

## Langkah 16: Dapatkan Waktu Kerja

Untuk mendapatkan waktu kerja pada tanggal tertentu, ikuti langkah-langkah berikut:

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

Penjelasan:
- Muat file proyek.
- Dapatkan kalender dengan UID.
- Dapatkan waktu kerja untuk tanggal yang ditentukan.

## Kesimpulan

Bekerja dengan kalender di Aspose.Tasks untuk .NET sangat penting untuk mengelola jadwal proyek secara efektif. Dengan contoh yang diberikan dan panduan langkah demi langkah, Anda dapat dengan mudah memanipulasi data kalender, menghitung durasi tugas, dan menangani pengecualian secara efisien. Dengan mengintegrasikan fungsi-fungsi ini ke dalam aplikasi Anda, Anda dapat menyederhanakan proses manajemen proyek dan memastikan penjadwalan yang akurat.

## FAQ

### Q1: Apakah saya memerlukan lisensi untuk menggunakan Aspose.Tasks untuk .NET?

 A1: Ya, Anda memerlukan lisensi yang valid untuk menggunakan Aspose.Tasks untuk .NET di aplikasi Anda. Anda dapat membeli lisensi penuh atau mendapatkan lisensi sementara selama 30 hari dari[Di Sini](https://purchase.aspose.com/temporary-license/).

### Q2: Dapatkah saya mengubah pengecualian kalender secara terprogram?

A2: Ya, Anda dapat menambahkan, memperbarui, atau menghapus pengecualian kalender secara terprogram menggunakan Aspose.Tasks untuk .NET API.

### Q3: Bagaimana cara menghitung tanggal selesai tugas dengan durasi khusus?

 A3: Aspose.Tasks untuk .NET menyediakan metode seperti`GetTaskFinishDateFromDuration()` untuk menghitung tanggal penyelesaian tugas berdasarkan durasi khusus.

### Q4: Apakah mungkin membuat kalender khusus, seperti kalender shift malam?

A4: Ya, Anda dapat membuat kalender khusus seperti kalender shift malam menggunakan Aspose.Tasks untuk .NET API.

### Q5: Dapatkah saya mengambil informasi tentang pengecualian kalender dari file proyek?

A5: Ya, Anda dapat dengan mudah mengambil informasi tentang pengecualian kalender dari file proyek menggunakan Aspose.Tasks untuk .NET.