---
date: 2026-03-24
description: Pelajari cara mengatur mode perhitungan di Aspose.Tasks untuk .NET, mencakup
  mode perhitungan otomatis, manual, dan none untuk mengelola ketergantungan tugas.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cara Mengatur Mode Perhitungan di Aspose.Tasks untuk .NET
url: /id/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Mode Perhitungan di Aspose.Tasks untuk .NET

## Pendahuluan

Aspose.Tasks untuk .NET adalah API yang kuat yang memungkinkan Anda bekerja dengan file Microsoft Project secara programatis. Salah satu pengaturan terpenting yang akan Anda temui adalah **mode perhitungan**, yang mengontrol bagaimana tanggal tugas dan jadwal proyek diperbarui. Dalam tutorial ini Anda akan belajar **cara mengatur mode perhitungan**, menjelajahi **mode perhitungan otomatis**, **mode perhitungan manual**, dan **mode perhitungan none**, serta melihat bagaimana opsi-opsi ini memengaruhi **mengelola ketergantungan tugas**, **membuat tanggal mulai proyek**, dan **menautkan hubungan selesai‑mulai** antar tugas.

## Jawaban Cepat
- **Apa itu mode perhitungan?** Menentukan apakah tanggal tugas dihitung ulang secara otomatis, manual, atau tidak sama sekali.  
- **Mengapa menggunakan mode perhitungan manual?** Untuk mendapatkan kontrol penuh atas kapan jadwal diperbarui, berguna dalam pembaruan massal.  
- **Mode apa yang menjadi default?** Mode perhitungan otomatis, yang memperbarui tanggal secara instan setelah perubahan.  
- **Bisakah saya mengubah mode saat runtime?** Ya—cukup set properti `CalculationMode` pada objek `Project`.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.

## Apa itu “cara mengatur perhitungan” di Aspose.Tasks?
Mengatur mode perhitungan semudah menetapkan nilai enum ke properti `Project.CalculationMode`. Enum tersebut menyediakan tiga pilihan: `Automatic`, `Manual`, dan `None`. Memilih mode yang tepat tergantung pada alur kerja Anda—apakah Anda menginginkan pembaruan instan, pemrosesan batch, atau kontrol penuh.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

1. **Visual Studio** – versi terbaru apa pun (2019, 2022, atau lebih baru).  
2. **Aspose.Tasks for .NET** – unduh dan instal pustaka dari [sini](https://releases.aspose.com/tasks/net/).  
3. **Pengetahuan dasar C#** – Anda harus nyaman membuat aplikasi konsol dan menggunakan paket NuGet.

## Impor Namespace

Sebelum kita mulai bekerja dengan Aspose.Tasks untuk .NET, mari impor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;
```

## Cara Mengatur Mode Perhitungan

Berikut Anda akan menemukan contoh langkah demi langkah untuk setiap mode perhitungan. Blok kode tidak diubah dari tutorial asli; penjelasan di sekitarnya telah diperluas untuk kejelasan.

### Menerapkan Mode Perhitungan Otomatis

Mode otomatis menghitung ulang tanggal secara instan setiap kali Anda memodifikasi tugas atau tautan.

#### Langkah 1: Buat instance Project baru

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Langkah 2: Atur tanggal mulai proyek dan tambahkan tugas

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Langkah 3: Tautkan tugas (selesai‑ke‑mulai)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Langkah 4: Verifikasi tanggal yang dihitung ulang

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Menerapkan Mode Perhitungan Manual

Mode manual menonaktifkan pembaruan otomatis, memberi Anda kesempatan untuk memproses perubahan secara batch sebelum memaksa perhitungan ulang.

#### Langkah 1: Buat instance Project baru

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Langkah 2: Atur tanggal mulai proyek dan tambahkan tugas

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Langkah 3: Verifikasi properti tugas

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Langkah 4: Tautkan tugas dan verifikasi tanggal (tanpa perhitungan otomatis)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Menerapkan Mode Perhitungan None

Mode none mematikan semua perhitungan internal. Gunakan ketika Anda hanya perlu membaca atau mengekspor data tanpa perubahan jadwal.

#### Langkah 1: Buat instance Project baru

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Langkah 2: Tambahkan tugas baru

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Langkah 3: Verifikasi properti tugas (tanpa ID otomatis)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Masalah Umum dan Solusinya

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| Dates don’t update after linking tasks | Project is in **Manual** or **None** mode | Set `project.CalculationMode = CalculationMode.Automatic` or call `project.Calculate()` manually |
| Task IDs stay at 0 | Using **None** mode prevents ID generation | Switch to **Automatic** or **Manual** mode, then recalculate |
| Linking fails with `ArgumentException` | The start date of the predecessor is later than the successor when using **Manual** mode without recalculation | Ensure correct start dates or recalculate after adding links |

## Pertanyaan yang Sering Diajukan

**T1: Bisakah saya mengubah mode perhitungan secara dinamis selama runtime?**  
A1: Ya, Anda dapat memodifikasi properti `CalculationMode` kapan saja dalam kode Anda dan kemudian memanggil `project.Calculate()` jika memerlukan pembaruan segera.

**T2: Apakah Aspose.Tasks mendukung format file manajemen proyek lain selain Microsoft Project?**  
A2: Aspose.Tasks terutama berfokus pada format Microsoft Project, tetapi juga mendukung Primavera P6 XML, Primavera DB, dan Asta Powerproject XML.

**T3: Apakah Aspose.Tasks cocok untuk proyek skala kecil maupun tingkat perusahaan?**  
A3: Tentu saja. API ini dapat diskalakan dari daftar tugas sederhana hingga jadwal perusahaan yang kompleks dan multi‑fase.

**T4: Bisakah saya mengintegrasikan Aspose.Tasks dengan pustaka dan kerangka kerja .NET lainnya?**  
A4: Ya, Anda dapat menggabungkan Aspose.Tasks dengan ASP.NET, WPF, Xamarin, atau teknologi .NET lainnya untuk membangun solusi manajemen proyek yang kaya.

**T5: Apakah ada forum komunitas atau saluran dukungan yang tersedia untuk pengguna Aspose.Tasks?**  
A5: Ya, Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas dan diskusi.

---

**Terakhir Diperbarui:** 2026-03-24  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}