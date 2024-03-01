---
title: Penanganan Durasi di Aspose.Tugas
linktitle: Penanganan Durasi di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani durasi secara efektif di Aspose.Tasks untuk .NET dengan tutorial langkah demi langkah.
type: docs
weight: 30
url: /id/net/calendar-scheduling/duration-handling/
---
## Perkenalan

Menangani durasi secara efektif sangat penting dalam aplikasi manajemen proyek. Aspose.Tasks untuk .NET menyediakan fungsionalitas yang kuat untuk mengelola durasi secara efisien. Dalam tutorial ini, kita akan menjelajahi berbagai aspek penanganan durasi menggunakan Aspose.Tasks untuk .NET.

## Prasyarat

Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:

1. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# sangat penting untuk memahami dan menerapkan contoh.
2. Visual Studio: Instal Visual Studio IDE untuk membuat dan menjalankan aplikasi .NET.
3.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk perpustakaan .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk menggunakan fungsi Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Mari kita bagi setiap contoh menjadi beberapa langkah dalam format panduan langkah demi langkah:

## Memperbarui Durasi Tugas

### Langkah 1: Muat File Proyek

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Langkah 2: Dapatkan Tugas dan Durasi

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Langkah 3: Perbarui Durasi

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Langkah 4: Tampilkan Durasi yang Diperbarui

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Mengurangi Durasi Tugas

### Langkah 1: Muat File Proyek

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Langkah 2: Dapatkan Tugas dan Durasi

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Langkah 3: Kurangi Durasi

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Langkah 4: Tampilkan Durasi yang Diperbarui

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Mengonversi Durasi ke TimeSpan

### Langkah 1: Muat File Proyek

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Langkah 2: Dapatkan Tugas dan Durasi

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Langkah 3: Ubah Durasi menjadi TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Mengonversi Durasi menjadi String

### Langkah 1: Muat File Proyek

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Langkah 2: Dapatkan Tugas dan Durasi

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Langkah 3: Ubah Durasi menjadi String

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Kesimpulan

Dalam tutorial ini, kami membahas berbagai aspek penanganan durasi di Aspose.Tasks untuk .NET. Memahami dan mengelola jangka waktu secara efektif sangat penting untuk keberhasilan manajemen proyek. Aspose.Tasks menyediakan fungsionalitas komprehensif untuk menyederhanakan tugas manajemen durasi di aplikasi .NET Anda.

## FAQ

### Q1: Apa itu Aspose.Tasks untuk .NET?

A1: Aspose.Tasks untuk .NET adalah perpustakaan yang kuat untuk bekerja dengan file Microsoft Project di aplikasi .NET.

### Q2: Dapatkah Aspose.Tasks menangani struktur proyek yang kompleks?

A2: Ya, Aspose.Tasks dapat menangani struktur proyek yang kompleks dengan mudah, menyediakan API ekstensif untuk manipulasi.

### Q3: Apakah Aspose.Tasks untuk .NET kompatibel dengan .NET Core?

A3: Ya, Aspose.Tasks untuk .NET kompatibel dengan .NET Core, memungkinkan Anda menggunakannya dalam aplikasi lintas platform.

### Q4: Apakah Aspose.Tasks mendukung membaca dan menulis file Microsoft Project?

A4: Ya, Aspose.Tasks mendukung membaca dan menulis file Microsoft Project dalam berbagai format, termasuk MPP, XML, dan MPX.

### Q5: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?

A5: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/).