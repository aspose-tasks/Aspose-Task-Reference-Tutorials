---
date: 2026-04-13
description: Pelajari cara mengatur jam kerja dan mengelola koleksi kalender di Aspose.Tasks
  untuk .NET. Impor kalender dari Microsoft Project, hapus kalender proyek, dan dapatkan
  kalender berdasarkan nama dengan mudah.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Mengelola Koleksi Kalender dalam Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Atur Jam Kerja di Koleksi Kalender Aspose.Tasks
url: /id/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Jam Kerja dalam Koleksi Kalender Aspose.Tasks

Dalam tutorial ini, Anda akan belajar cara **mengatur jam kerja** dan mengelola koleksi kalender menggunakan Aspose.Tasks untuk .NET. Kalender mendefinisikan hari kerja, hari libur, dan pengecualian, sehingga menguasainya memungkinkan Anda mengontrol jadwal proyek secara tepat. Kami juga akan menunjukkan cara mengimpor kalender Microsoft Project, menghapus kalender dari sebuah proyek, dan mendapatkan kalender berdasarkan nama.

## Jawaban Cepat
- **Apa kelas utama untuk kalender?** `Project.Calendars` collection.
- **Bagaimana cara mengatur jam kerja?** Buat atau modifikasi objek `Calendar` dan definisikan `WorkingTime`-nya.
- **Apakah saya dapat mengimpor kalender dari Microsoft Project?** Ya – muat file MPP dan akses kalendarnya.
- **Bagaimana cara menghapus kalender dari proyek?** Gunakan `Project.Calendars.Remove(calendar)`.
- **Bagaimana cara mengambil kalender berdasarkan nama?** Panggil `Project.Calendars.GetByName("YourCalendar")`.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Instal Visual Studio atau IDE kompatibel lainnya untuk pengembangan .NET.  
2. Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari [here](https://releases.aspose.com/tasks/net/).  
3. Pemahaman dasar tentang C#: Familiaritas dengan bahasa pemrograman C# akan sangat membantu.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk bekerja dengan Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Membuat Kalender Baru

### Langkah 1: Inisialisasi objek `Project` baru.
```csharp
var project = new Project();
```

### Langkah 2: Tambahkan kalender ke koleksi kalender proyek.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Langkah 3: Iterasi melalui kalender dan tampilkan namanya.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Cara Mengatur Jam Kerja untuk Kalender?

Untuk **mengatur jam kerja**, Anda memodifikasi koleksi `WorkingTime` dari sebuah `Calendar`.  
Sebagai contoh, Anda dapat mendefinisikan hari kerja standar 9 am‑5 pm atau menambahkan pengecualian khusus.  
Kode untuk ini identik dengan contoh yang ditunjukkan nanti ketika kami membuat kalender standar.

## Mengganti Kalender dengan Kalender Baru

### Langkah 1: Muat proyek yang ada.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Langkah 2: Hapus kalender yang ada (jika ada).  
Ini menunjukkan skenario **remove calendar project**.
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
Ini menggambarkan operasi **get calendar by name**.
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

## Mengiterasi Kalender

### Langkah 1: Muat proyek.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Langkah 2: Dapatkan jumlah kalender.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Langkah 3: Iterasi koleksi kalender dan tampilkan nama.
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

### Langkah 2: Definisikan kalender baru dan jadikan standar.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Langkah 3: Simpan proyek.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya

- **Calendar not found when using `GetByName`** – Pastikan nama yang tepat cocok dengan huruf besar/kecil yang digunakan saat kalender ditambahkan.  
- **Working hours not applied** – Setelah mengatur `WorkingTime`, ingat untuk menyimpan proyek; jika tidak, perubahan hanya tetap di memori.  
- **Importing calendars from an MPP file fails** – Verifikasi bahwa file sumber adalah file Microsoft Project yang valid dan Anda memiliki izin membaca.

## FAQ

### Q1: Bisakah saya membuat hari kerja khusus di Aspose.Tasks?

A1: Ya, Anda dapat membuat hari kerja khusus dengan menambahkan pengecualian ke kalender.

### Q2: Apakah memungkinkan mengimpor kalender dari file Microsoft Project?

A2: Tentu saja, Aspose.Tasks mendukung mengimpor kalender dari file Microsoft Project.

### Q3: Bagaimana saya dapat menghapus kalender tertentu dari proyek?

A3: Anda dapat menghapus kalender dengan mengambilnya dari koleksi dan kemudian memanggil metode `Remove`.

### Q4: Apakah Aspose.Tasks mendukung mengekspor kalender ke format berbeda?

A4: Ya, Aspose.Tasks memungkinkan mengekspor kalender ke berbagai format seperti XML, MPP, dll.

### Q5: Bisakah saya menyesuaikan jam kerja untuk hari tertentu dalam kalender?

A5: Tentu, Anda dapat mendefinisikan jam kerja untuk hari tertentu menggunakan pengecualian dalam kalender.

## Pertanyaan yang Sering Diajukan

**Q: Apa cara terbaik untuk mengatur kalender shift 24‑jam?**  
A: Buat kalender baru, bersihkan entri `WorkingTime` yang ada, dan tambahkan satu rentang `WorkingTime` dari 00:00 hingga 24:00 untuk setiap hari kerja.

**Q: Bisakah saya menyalin kalender dari satu proyek ke proyek lain?**  
A: Ya—ekspor kalender ke XML menggunakan `project.Save` dan kemudian impor ke proyek lain dengan `new Project(xmlPath)`.

**Q: Bagaimana cara mengimpor kalender Microsoft Project secara programatis?**  
A: Muat file MPP dengan `new Project("source.mpp")`; kalender akan tersedia melalui `project.Calendars`.

**Q: Apakah ada batas jumlah kalender dalam sebuah proyek?**  
A: Praktis tidak; koleksi dapat menampung sebanyak mungkin kalender sesuai memori yang tersedia, namun tetap jaga daftar agar dapat dikelola untuk kinerja.

**Q: Apakah perubahan pada kalender secara otomatis memperbarui tugas yang menggunakannya?**  
A: Ya—tugas yang terhubung ke kalender akan mencerminkan jam kerja yang diperbarui setelah Anda menyimpan proyek.

---

**Terakhir Diperbarui:** 2026-04-13  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}