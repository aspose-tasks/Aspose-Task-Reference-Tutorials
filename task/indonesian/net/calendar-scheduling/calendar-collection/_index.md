---
title: Mengelola Koleksi Kalender di Aspose.Tasks
linktitle: Mengelola Koleksi Kalender di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola koleksi kalender di Aspose.Tasks untuk .NET secara efisien. Membuat, memodifikasi, dan memanipulasi kalender dengan mudah.
type: docs
weight: 11
url: /id/net/calendar-scheduling/calendar-collection/
---
## Perkenalan

Dalam tutorial ini, kita akan menjelajahi cara mengelola koleksi kalender di Aspose.Tasks untuk .NET. Kalender memainkan peran penting dalam manajemen proyek, menentukan hari kerja, hari libur, dan pengecualian. Aspose.Tasks menyediakan fungsionalitas yang kuat untuk memanipulasi kalender dalam proyek Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Instal Visual Studio atau IDE lain yang kompatibel untuk pengembangan .NET.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk bekerja dengan Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Membuat Kalender Baru

###  Langkah 1: Inisialisasi yang baru`Project` object.
```csharp
var project = new Project();
```

### Langkah 2: Tambahkan kalender ke koleksi kalender proyek.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Langkah 3: Ulangi kalender dan tampilkan namanya.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Mengganti Kalender dengan Kalender Baru

### Langkah 1: Muat proyek yang sudah ada.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Langkah 2: Hapus kalender yang ada (jika ada).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Langkah 3: Tambahkan kalender baru.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Mendapatkan Kalender berdasarkan Nama atau ID

### Langkah 1: Muat proyek.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Langkah 2: Ambil kalender berdasarkan nama atau UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Langkah 3: Tampilkan detail kalender.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Mengulangi Kalender

### Langkah 1: Muat proyek.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Langkah 2: Ambil hitungan kalender.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Langkah 3: Ulangi koleksi kalender dan nama tampilan.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Membuat Kalender Standar

### Langkah 1: Inisialisasi proyek baru.
```csharp
var project = new Project();
```

### Langkah 2: Tentukan kalender baru dan jadikan standar.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Langkah 3: Simpan proyek.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Kesimpulan

Mengelola koleksi kalender di Aspose.Tasks untuk .NET sangat penting untuk manajemen proyek yang efektif. Dengan fungsionalitas yang disediakan, Anda dapat membuat, memodifikasi, dan memanipulasi kalender secara efisien sesuai dengan kebutuhan proyek Anda.

## FAQ

### Q1: Bisakah saya membuat hari kerja khusus di Aspose.Tasks?

A1: Ya, Anda dapat membuat hari kerja khusus dengan menambahkan pengecualian pada kalender.

### Q2: Apakah mungkin mengimpor kalender dari file Microsoft Project?

A2: Tentu saja, Aspose.Tasks mendukung impor kalender dari file Microsoft Project.

### Q3: Bagaimana cara menghapus kalender tertentu dari suatu proyek?

 A3: Anda dapat menghapus kalender dengan mengambilnya dari koleksi lalu menelepon`Remove` metode.

### Q4: Apakah Aspose.Tasks mendukung ekspor kalender ke format berbeda?

A4: Ya, Aspose.Tasks memungkinkan mengekspor kalender ke berbagai format seperti XML, MPP, dll.

### Q5: Bisakah saya menyesuaikan jam kerja untuk hari tertentu di kalender?

A5: Tentu saja, Anda dapat menentukan jam kerja untuk setiap hari menggunakan pengecualian di kalender.