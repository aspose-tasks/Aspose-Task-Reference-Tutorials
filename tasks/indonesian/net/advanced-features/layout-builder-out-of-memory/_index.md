---
date: 2026-03-24
description: Pelajari penanganan out of memory dan cara menyimpan gambar proyek menggunakan
  Aspose.Tasks Layout Builder di .NET. Panduan langkah demi langkah dengan contoh
  kode.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Penanganan Kekurangan Memori dengan Aspose.Tasks Layout Builder (C#)
url: /id/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Penanganan Out of Memory dengan Aspose.Tasks Layout Builder

## Pendahuluan

Penanganan out of memory merupakan bagian penting dalam membangun aplikasi .NET yang handal dan bekerja dengan file proyek berukuran besar. Saat Anda menghasilkan visualisasi dengan Aspose.Tasks Layout Builder, Anda dapat dengan cepat menemui pengecualian terkait memori, terutama pada diagram Gantt yang kompleks. Pada tutorial ini kami akan memandu Anda cara **menangani pengecualian memori**, **menyesuaikan tampilan Gantt**, dan **menyimpan gambar proyek** dengan aman, sehingga aplikasi Anda tetap responsif meskipun dengan jadwal yang sangat besar.

## Jawaban Cepat
- **Apa itu penanganan out of memory?** Mengelola penggunaan memori dan menangkap error tipe `OutOfMemoryException` saat memproses data besar.
- **API mana yang membantu?** Aspose.Tasks Layout Builder untuk .NET.
- **Skenario tipikal?** Merender diagram Gantt resolusi tinggi ke PNG.
- **Prasyarat utama?** .NET (Framework 4.5+ atau .NET 6) dengan Aspose.Tasks terpasang.
- **Bagaimana menangkap error?** Gunakan blok `try…catch` untuk `ApsLayoutBuilderOutOfMemoryException` dan pengecualian terkait.

## Prasyarat

Sebelum masuk ke kode, pastikan Anda memiliki:

1. **Dasar C#** – Anda harus nyaman dengan sintaks C# standar.
2. **Aspose.Tasks untuk .NET** terinstal. Jika belum menambahkannya, unduh dari [here](https://releases.aspose.com/tasks/net/).
3. **IDE** seperti Visual Studio (atau VS Code dengan ekstensi C#) untuk mengompilasi dan menjalankan contoh.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Muat Proyek

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Baris ini memuat **Blank2010.mpp** ke dalam instance `Project`, menyiapkannya untuk visualisasi.

### Langkah 2: Sesuaikan Tampilan Diagram Gantt

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Di sini kami **menyesuaikan tampilan Gantt** dengan mengatur tier skala waktu tengah dan bawah. Mengubah tier ini mengurangi jumlah data yang dirender sekaligus, yang dapat membantu mengurangi tekanan memori.

### Langkah 3: Konfigurasi Opsi Penyimpanan Gambar

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` memberi tahu Aspose.Tasks cara merender diagram. Kami memilih PNG sebagai format output dan mengikat skala waktu ke tampilan yang baru saja disesuaikan.

### Langkah 4: Simpan Proyek sebagai Gambar

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

Pemanggilan `Save` **menyimpan gambar proyek** menggunakan opsi yang telah didefinisikan di atas. Jika proyek sangat besar, inilah titik di mana kondisi out‑of‑memory paling mungkin muncul.

### Langkah 5: Tangani Pengecualian

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Dengan menangkap `ApsLayoutBuilderOutOfMemoryException` Anda **menangani pengecualian memori** secara elegan, memberikan pesan yang jelas alih-alih membuat aplikasi crash. Catch kedua menangani masalah ukuran bitmap yang juga dapat muncul saat merender diagram sangat besar.

## Masalah Umum dan Solusinya

| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **OutOfMemoryException** | Merender gambar beresolusi sangat tinggi mengonsumsi RAM lebih banyak daripada yang dapat dialokasikan proses. | Kurangi dimensi gambar, sederhanakan tier skala waktu, atau bagi diagram menjadi beberapa gambar. |
| **BitmapInvalidSizeException** | Ukuran bitmap yang diminta melebihi maksimum platform. | Batasi lebar/tinggi di `ImageSaveOptions` atau render dalam segmen. |
| **Performa lambat** | File proyek besar memerlukan banyak pemrosesan. | Aktifkan `project.Set(Prj.SaveToCache, true)` sebelum merender, atau gunakan thread latar belakang. |

## FAQ's

### Q1: Apa itu Aspose.Tasks untuk .NET?

A1: Aspose.Tasks untuk .NET adalah API kuat yang memungkinkan pengembang memanipulasi file Microsoft Project secara programatis dalam aplikasi .NET.

### Q2: Bagaimana saya mendapatkan lisensi sementara untuk Aspose.Tasks?

A2: Anda dapat memperoleh lisensi sementara untuk Aspose.Tasks dengan mengunjungi [this link](https://purchase.aspose.com/temporary-license/).

### Q3: Apakah Aspose.Tasks cocok untuk menangani file proyek besar?

A3: Ya, Aspose.Tasks menyediakan fitur dan optimisasi untuk menangani file proyek besar secara efisien, namun pengembang tetap harus mempertimbangkan strategi manajemen memori.

### Q4: Bisakah saya menyesuaikan tampilan diagram Gantt menggunakan Aspose.Tasks?

A4: Tentu saja! Aspose.Tasks menyediakan kemampuan luas untuk menyesuaikan tampilan dan tata letak diagram Gantt sesuai kebutuhan Anda.

### Q5: Di mana saya dapat menemukan bantuan dan dukungan lebih lanjut untuk Aspose.Tasks?

A5: Anda dapat menemukan bantuan dan dukungan lebih lanjut, serta berinteraksi dengan komunitas, di [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara mengurangi penggunaan memori saat menyimpan gambar proyek?**  
J: Turunkan resolusi gambar, batasi rentang skala waktu, atau simpan diagram dalam beberapa segmen yang lebih kecil.

**T: Apakah memungkinkan untuk men-stream gambar langsung ke respons web?**  
J: Ya, Anda dapat menggunakan `project.Save(stream, options)` dan menulis stream ke respons HTTP.

**T: Apakah Aspose.Tasks mendukung .NET Core dan .NET 5/6?**  
J: Perpustakaan ini sepenuhnya kompatibel dengan .NET Core, .NET 5, dan .NET 6.

**T: Apa yang harus saya lakukan jika masih mengalami error out‑of‑memory setelah optimasi?**  
J: Pertimbangkan memproses proyek pada mesin dengan RAM lebih besar atau memindahkan rendering ke layanan latar belakang.

**T: Bisakah saya mengekspor diagram Gantt ke format selain PNG?**  
J: Ya, `ImageSaveOptions` mendukung JPEG, BMP, dan TIFF selain PNG.

---

**Terakhir Diperbarui:** 2026-03-24  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}