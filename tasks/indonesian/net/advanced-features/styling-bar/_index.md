---
date: 2026-04-06
description: Pelajari cara mengubah gaya batang dan menyesuaikan warna batang di Aspose.Tasks
  untuk .NET guna meningkatkan visualisasi proyek.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Bar Gaya di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Mengubah Gaya Bar di Aspose.Tasks
url: /id/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengubah Gaya Bar di Aspose.Tasks

## Pendahuluan

Jika Anda perlu **mengubah tampilan bar** dalam file Microsoft Project, Aspose.Tasks untuk .NET memberi Anda kontrol penuh atas warna bar, bentuk, dan gaya teks. Dengan menyesuaikan warna bar dan atribut visual lainnya, Anda dapat membuat rencana proyek jauh lebih mudah dibaca dan lebih selaras dengan merek organisasi Anda. Dalam tutorial ini kami akan membimbing Anda melalui contoh lengkap langkah‑demi‑langkah yang menunjukkan cara mengubah gaya bar, mulai dari memuat proyek hingga mengekspornya dengan aturan visual baru yang diterapkan.

## Jawaban Cepat
- **Apa yang dapat saya gaya?** Bar, tonggak, dan teks tugas di diagram Gantt.  
- **Format apa yang mendukung bar bergaya?** PDF, XLSX, HTML, dan MPP asli ketika disimpan dengan `PdfSaveOptions`.  
- **Apakah saya memerlukan lisensi?** Lisensi komersial diperlukan untuk penggunaan produksi; percobaan gratis dapat digunakan untuk pengujian.  
- **Bisakah saya menerapkan beberapa gaya?** Ya – tambahkan sebanyak mungkin objek `BarStyle` yang Anda perlukan.  
- **Apakah kompatibel dengan .NET Core?** Tentu – bekerja dengan .NET Framework dan .NET Core/5/6+.

## Apa Itu Gaya Bar di Aspose.Tasks?

Gaya bar memungkinkan Anda mendefinisikan aturan visual yang diterapkan mesin Aspose.Tasks saat merender diagram Gantt. Setiap aturan (sebuah **BarStyle**) menargetkan tipe item tertentu—tugas, tonggak, atau tugas rangkuman—dan memungkinkan Anda mengatur warna, bentuk, serta teks khusus.

## Mengapa menyesuaikan warna bar?

Menyesuaikan warna bar membantu pemangku kepentingan langsung mengidentifikasi jalur kritis, tugas yang tertunda, atau tonggak. Ini juga memungkinkan Anda mencocokkan skema warna perusahaan, sehingga laporan terlihat profesional dan sesuai merek.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. **Aspose.Tasks for .NET** – unduh dari [halaman unduhan](https://releases.aspose.com/tasks/net/).  
2. Lingkungan pengembangan yang mendukung .NET (Framework 4.6+, .NET Core 3.1+, atau lebih baru).  
3. Familiaritas dasar dengan C# – contoh menggunakan kode sederhana yang berdiri sendiri.

## Impor Namespace

Pertama, impor namespace yang berisi kelas yang akan kita gunakan:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Langkah 1: Muat Proyek

Muat file MPP yang ada (atau buat yang baru) sehingga Anda memiliki objek proyek untuk bekerja:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Langkah 2: Konfigurasi Opsi Penyimpanan

Buat instance `PdfSaveOptions` dan inisialisasi koleksi `BarStyles` tempat kita akan menyimpan gaya khusus kita:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Langkah 3: Definisikan Gaya Bar

Sekarang kita membangun objek `BarStyle` dan mengatur properti yang mengontrol tampilan bar. Di sinilah kita **menyesuaikan warna bar** dan bentuk:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Langkah 4: Sesuaikan Konverter Teks (Opsional)

Jika Anda ingin menyesuaikan teks yang muncul pada bar, Anda dapat menetapkan konverter khusus. Contoh ini menambahkan awalan pada nama tugas yang belum dimulai dengan “T”:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Langkah 5: Tambahkan Gaya Bar ke Opsi

Tambahkan gaya yang telah dikonfigurasi sepenuhnya ke koleksi `BarStyles` pada opsi penyimpanan:

```csharp
options.BarStyles.Add(style);
```

## Langkah 6: Simpan Proyek

Akhirnya, ekspor proyek. PDF (atau format lain) akan merender diagram Gantt menggunakan gaya bar yang telah kita definisikan:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Masalah Umum dan Solusinya

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Gaya bar tidak diterapkan** | Koleksi `BarStyles` kosong atau tidak terhubung ke opsi penyimpanan. | Pastikan Anda menambahkan `BarStyle` ke `options.BarStyles` sebelum memanggil `Save`. |
| **Warna terlihat berbeda di PDF** | Rendering PDF mungkin menggunakan profil warna yang berbeda. | Gunakan nilai `System.Drawing.Color` standar atau definisikan warna ARGB khusus. |
| **Konverter teks menghasilkan referensi null** | Properti tugas `Tsk.Name` bernilai null untuk beberapa tugas. | Tambahkan pemeriksaan null sebelum mengakses `task.Get(Tsk.Name)`. |

## FAQ

### Q1: Bisakah saya menerapkan beberapa gaya bar pada satu proyek?

A1: Ya, Anda dapat mendefinisikan dan menerapkan beberapa gaya bar pada berbagai jenis tugas dalam proyek yang sama.

### Q2: Apakah memungkinkan mengubah gaya bar secara dinamis selama runtime?

A2: Ya, Anda dapat memodifikasi gaya bar secara dinamis berdasarkan kondisi tertentu atau preferensi pengguna dalam aplikasi Anda.

### Q3: Apakah Aspose.Tasks mendukung mengekspor proyek dengan bar bergaya ke berbagai format file?

A3: Ya, Aspose.Tasks mendukung mengekspor proyek dengan bar bergaya ke berbagai format seperti PDF, XLSX, dan HTML.

### Q4: Apakah ada gaya bar bawaan yang tersedia di Aspose.Tasks?

A4: Meskipun Aspose.Tasks menyediakan gaya bar default, pengembang juga dapat membuat gaya bar khusus yang disesuaikan dengan kebutuhan proyek mereka.

### Q5: Bisakah saya mengambil dan memodifikasi gaya bar yang ada dalam proyek menggunakan API?

A5: Ya, Anda dapat mengambil dan memodifikasi gaya bar yang ada secara programatis menggunakan API Aspose.Tasks untuk .NET.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara mengubah warna bar untuk tugas reguler bukan tonggak?**  
A: Set `style.ItemType = BarItemType.Task;` dan tetapkan `style.BarColor` ke `Color` yang diinginkan.

**Q: Bisakah saya menggunakan pendekatan ini untuk menata bar saat mengekspor ke HTML?**  
A: Ya. Gunakan `HtmlSaveOptions` dan isi koleksi `BarStyles`‑nya dengan cara yang sama.

**Q: Apakah ada batasan jumlah gaya bar yang dapat saya definisikan?**  
A: Praktis tidak; Anda dapat menambahkan sebanyak yang diperlukan, tetapi perhatikan kinerja untuk koleksi yang sangat besar.

**Q: Apakah saya perlu memanggil `project.Calculate()` setelah mengubah gaya?**  
A: Tidak, gaya diterapkan selama operasi penyimpanan; perhitungan ulang hanya diperlukan untuk perubahan jadwal.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}