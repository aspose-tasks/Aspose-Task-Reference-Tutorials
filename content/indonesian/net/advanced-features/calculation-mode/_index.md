---
title: Mode Perhitungan di Aspose.Tasks
linktitle: Mode Perhitungan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola mode perhitungan secara efektif di Aspose.Tasks untuk .NET untuk menyederhanakan penjadwalan proyek dan dependensi tugas.
type: docs
weight: 29
url: /id/net/advanced-features/calculation-mode/
---
## Perkenalan

Aspose.Tasks untuk .NET adalah API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram dalam aplikasi .NET mereka. Salah satu aspek penting dalam bekerja dengan file proyek adalah mengelola mode perhitungan, yang menentukan bagaimana tugas dan jadwal proyek dihitung dan diperbarui. Dalam tutorial ini, kita akan mempelajari berbagai mode perhitungan yang didukung oleh Aspose.Tasks untuk .NET dan menunjukkan cara menggunakannya secara efektif.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pemahaman dasar pemrograman C#: Biasakan diri Anda dengan konsep pemrograman C#.

## Impor Namespace

Sebelum kita mulai bekerja dengan Aspose.Tasks untuk .NET, mari impor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;


```

## Menerapkan Mode Perhitungan Otomatis

### Langkah 1: Buat instance Proyek baru

 Inisialisasi yang baru`Project` objek dan mengaturnya`CalculationMode` properti ke`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Langkah 2: Tetapkan tanggal mulai proyek dan tambahkan tugas

Tentukan tanggal mulai proyek dan tambahkan tugas ke dalamnya.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Langkah 3: Tautkan tugas

Tetapkan ketergantungan antar tugas.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Langkah 4: Verifikasi tanggal penghitungan ulang

Periksa apakah tanggal telah dihitung ulang secara otomatis.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Tambahkan lebih banyak verifikasi sesuai kebutuhan
```

## Menerapkan Mode Perhitungan Manual

### Langkah 1: Buat instance Proyek baru

 Inisialisasi yang baru`Project` objek dan mengaturnya`CalculationMode` properti ke`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Langkah 2: Tetapkan tanggal mulai proyek dan tambahkan tugas

Tentukan tanggal mulai proyek dan tambahkan tugas ke dalamnya.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Langkah 3: Verifikasi properti tugas

Periksa apakah properti tugas diatur dengan benar dalam mode manual.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Tambahkan lebih banyak verifikasi sesuai kebutuhan
```

### Langkah 4: Tautkan tugas dan verifikasi tanggal

Tautkan tugas bersama-sama dan periksa apakah tanggalnya tidak dihitung ulang.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Menerapkan Mode Perhitungan Tidak Ada

### Langkah 1: Buat instance Proyek baru

 Inisialisasi yang baru`Project` objek dan mengaturnya`CalculationMode` properti ke`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Langkah 2: Tambahkan tugas baru

Tambahkan tugas baru ke proyek.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Langkah 3: Verifikasi properti tugas

Periksa apakah properti tugas tidak dihitung secara otomatis.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Tambahkan lebih banyak verifikasi sesuai kebutuhan
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi mode penghitungan yang tersedia di Aspose.Tasks untuk .NET dan mempelajari cara menerapkannya dalam skenario praktis. Baik Anda memerlukan mode perhitungan otomatis, manual, atau tanpa perhitungan, Aspose.Tasks memberikan fleksibilitas untuk menyesuaikan dengan kebutuhan proyek Anda.

## FAQ

### Q1: Bisakah saya mengubah mode perhitungan secara dinamis selama runtime?

A1: Ya, Anda dapat mengubah mode penghitungan proyek kapan saja selama runtime dengan memodifikasi`CalculationMode` Properti.

### Q2: Apakah Aspose.Tasks mendukung format file manajemen proyek lain selain Microsoft Project?

A2: Aspose.Tasks terutama berfokus pada format file Microsoft Project, tetapi juga mendukung format lain seperti Primavera P6 XML, Primavera DB, dan Asta Powerproject XML.

### Q3: Apakah Aspose.Tasks cocok untuk proyek skala kecil dan tingkat perusahaan?

A3: Tentu saja! Aspose.Tasks dirancang untuk memenuhi kebutuhan proyek skala kecil dan tingkat perusahaan dengan fitur komprehensif dan API yang kuat.

### Q4: Dapatkah saya mengintegrasikan Aspose.Tasks dengan pustaka dan kerangka kerja .NET lainnya?

A4: Ya, Anda dapat dengan mudah mengintegrasikan Aspose.Tasks dengan pustaka dan kerangka kerja .NET lainnya untuk meningkatkan fungsionalitas aplikasi Anda.

### Q5: Apakah ada forum komunitas atau saluran dukungan yang tersedia untuk pengguna Aspose.Tasks?

 A5: Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.