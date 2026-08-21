---
date: 2026-03-16
description: Pelajari cara menggabungkan beberapa kondisi dan memfilter tugas proyek
  menggunakan operasi AND lanjutan di Aspose.Tasks untuk .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Cara menggabungkan beberapa kondisi dengan Operasi AND Lanjutan di Aspose.Tasks
url: /id/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Operasi AND Lanjutan di Aspose.Tasks

## Pendahuluan

Dalam tutorial ini Anda akan menemukan **cara menggabungkan beberapa kondisi** dengan *operasi AND lanjutan* di Aspose.Tasks untuk .NET. Pada akhir panduan Anda akan dapat **menyaring tugas proyek** berdasarkan beberapa kriteria—sesuatu yang penting ketika Anda perlu **menyaring tugas** seperti item ringkasan, entri non‑null, atau flag khusus dalam satu kali proses.

## Jawaban Cepat
- **Apa yang dilakukan operasi AND Lanjutan?** Ia menggabungkan dua atau lebih kondisi filter sehingga hanya tugas yang memenuhi *semua* kriteria yang dikembalikan.  
- **Kelas mana yang menggabungkan kondisi?** `Util.And<T>` (ditampilkan sebagai `And<T>` dalam API).  
- **Apakah saya memerlukan lisensi khusus?** Lisensi Aspose.Tasks reguler diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia.  
- **Bisakah saya menggabungkan lebih dari dua kondisi?** Ya—`And<T>` menerima sejumlah kondisi apa pun.  
- **Versi .NET apa yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Apa itu “menggabungkan beberapa kondisi” di Aspose.Tasks?

Menggabungkan beberapa kondisi berarti membuat filter komposit yang mengevaluasi setiap tugas terhadap beberapa aturan secara bersamaan. Pendekatan ini jauh lebih efisien daripada mengiterasi daftar tugas berkali‑kali karena perpustakaan menerapkan logika dalam satu kali proses.

## Mengapa menggunakan operasi AND lanjutan?

- **Kinerja:** Mengurangi jumlah iterasi pada koleksi tugas.  
- **Keterbacaan:** Menjaga logika filter tetap deklaratif dan mudah dipelihara.  
- **Fleksibilitas:** Anda dapat mencampur kondisi bawaan (misalnya, `SummaryCondition`) dengan predikat khusus.  

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. Pengetahuan dasar pemrograman C#.  
2. Aspose.Tasks untuk .NET terinstal. Jika Anda belum mengunduhnya, dapatkan **[di sini](https://releases.aspose.com/tasks/net/)**.  
3. IDE seperti Visual Studio (semua edisi dapat digunakan).  

## Impor Namespace

Pertama, impor namespace yang menyediakan model tugas dan kelas utilitas:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Langkah 1: Inisialisasi Proyek dan Kumpulkan Tugas

Kami akan membuat instance `Project` dan menggunakan `ChildTasksCollector` untuk mengumpulkan semua tugas dalam file. Ini mendemonstrasikan **cara menggunakan collector** untuk mengambil daftar tugas datar.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Langkah 2: Definisikan Kondisi Filter

Di sini kami mendefinisikan kondisi individual yang ingin diterapkan. Dalam contoh ini kami **menyaring tugas ringkasan** dan juga memastikan objek tugas tidak null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Langkah 3: Gabungkan Kondisi dengan Operasi AND

Sekarang kami **menggabungkan beberapa kondisi** menggunakan kelas `And<T>`. Ini adalah inti dari **operasi AND lanjutan**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Langkah 4: Terapkan Kondisi dan Saring Tugas

Dengan kondisi komposit siap, kami memanggil `Filter` untuk **menyaring tugas proyek** berdasarkan logika yang digabungkan.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Langkah 5: Keluarkan Tugas yang Disaring

Akhirnya, kami menampilkan tugas yang memenuhi **semua** kondisi. Anda dapat mengganti pemanggilan `Console.WriteLine` dengan pemrosesan khusus apa pun yang Anda perlukan.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi Cepat |
|-------|----------------|-----------|
| `Filter` method tidak ditemukan | Tidak ada `using Aspose.Tasks.Util;` | Pastikan namespace Util diimpor (lihat Impor Namespace). |
| Tidak ada tugas yang dikembalikan | Kondisi terlalu ketat (misalnya, menyaring tugas ringkasan padahal tidak ada) | Verifikasi proyek memang berisi tugas ringkasan atau sesuaikan kondisi. |
| NullReferenceException | `coll.Tasks` berisi entri null | `NotNullCondition` sudah melindungi dari ini; pertahankan dalam rantai AND. |

## FAQ

### Q1: Apa itu Aspose.Tasks untuk .NET?

A: Aspose.Tasks untuk .NET adalah API yang kuat yang memungkinkan pengembang memanipulasi file Microsoft Project secara programatis dalam aplikasi .NET.

### Q2: Bisakah saya menerapkan lebih dari dua kondisi menggunakan Util.And?

A: Ya, Util.And dapat digunakan untuk menggabungkan sejumlah kondisi apa pun untuk membuat kriteria filter yang kompleks.

### Q3: Apakah tersedia percobaan gratis untuk Aspose.Tasks untuk .NET?

A: Ya, Anda dapat mengunduh percobaan gratis **[di sini](https://releases.aspose.com/)**.

### Q4: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk .NET?

A: Anda dapat menemukan dokumentasi **[di sini](https://reference.aspose.com/tasks/net/)**.

### Q5: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk .NET?

A: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.Tasks **[di sini](https://forum.aspose.com/c/tasks/15)**.

**Additional Q&A**

**Q: Bagaimana cara saya menyaring tugas berdasarkan nilai bidang khusus?**  
A: Buat `CustomFieldCondition` (atau implementasikan `ICondition<Task>`) dan tambahkan ke rantai `And<T>`.

**Q: Bisakah saya menggunakan pendekatan yang sama untuk menyaring sumber daya?**  
A: Ya—ganti `Task` dengan `Resource` dan gunakan kelas kondisi yang sesuai.

## Kesimpulan

Dengan mengikuti langkah-langkah di atas, Anda sekarang tahu **cara menggabungkan beberapa kondisi** menggunakan **operasi AND lanjutan** di Aspose.Tasks untuk .NET. Teknik ini memungkinkan Anda **menyaring tugas proyek** secara efisien, baik Anda menargetkan item ringkasan, entri non‑null, atau kriteria khusus apa pun yang Anda definisikan.

---

**Terakhir Diperbarui:** 2026-03-16  
**Diuji Dengan:** Aspose.Tasks for .NET (latest)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}