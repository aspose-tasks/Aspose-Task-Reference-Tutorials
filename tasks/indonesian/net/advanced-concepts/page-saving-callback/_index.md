---
date: 2026-03-16
description: Pelajari cara mengimplementasikan callback penyimpanan halaman di Aspose.Tasks
  untuk .NET, memungkinkan penanganan khusus aliran output dokumen multi‑halaman.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementasikan callback penyimpanan halaman pada Aspose.Tasks
url: /id/net/advanced-concepts/page-saving-callback/
weight: 12
---

**Tested With:** Aspose.Tasks 24.12 for .NET -> "**Diuji dengan:** Aspose.Tasks 24.12 untuk .NET"

**Author:** Aspose -> "**Penulis:** Aspose"

Now ensure shortcodes remain.

Now produce final content with same structure.

Let's assemble.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menerapkan callback penyimpanan halaman di Aspose.Tasks

## Pendahuluan

Dalam tutorial ini, Anda akan belajar cara **menerapkan callback penyimpanan halaman** di Aspose.Tasks untuk .NET. Fitur kuat ini memungkinkan Anda mengarahkan setiap halaman dokumen multi‑halaman ke aliran (stream) pilihan Anda, memberi Anda kontrol penuh atas cara output disimpan atau diproses lebih lanjut.

## Jawaban Cepat
- **Apa yang dilakukan callback penyimpanan halaman?** Callback ini menangkap setiap halaman yang dirender ke dalam aliran terpisah sehingga Anda dapat menangani masing‑masing secara individual.  
- **Format apa yang dapat saya ekspor?** Format apa pun yang didukung oleh `ImageSaveOptions`, misalnya PNG, JPEG, PDF.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya menggunakan ini dengan .NET Core?** Ya, Aspose.Tasks sepenuhnya mendukung .NET Core dan .NET 5/6+.  
- **Apakah callback ini thread‑safe?** Callback dijalankan pada thread yang sama dengan proses rendering, sehingga aturan thread‑safety normal berlaku.

## Apa itu **callback penyimpanan halaman**?
Pola **callback penyimpanan halaman** memungkinkan Anda menyisipkan logika khusus ke dalam alur penyimpanan Aspose.Tasks. Alih‑alih menulis langsung ke file, Anda menerima objek `Stream` untuk setiap halaman, memungkinkan Anda menyimpannya di memori, mengunggah ke penyimpanan cloud, atau menerapkan pemrosesan tambahan.

## Mengapa mengekspor proyek sebagai PNG dengan callback?
Mengekspor proyek sebagai PNG memberikan Anda gambar raster dari setiap halaman diagram Gantt, yang ideal untuk laporan, email, atau penyematan di halaman web. Menggunakan callback berarti Anda dapat menyimpan setiap halaman dalam `MemoryStream` terpisah tanpa membuat file sementara di disk.

## Prasyarat

1. **Pengetahuan C#** – pemahaman dasar tentang kelas, antarmuka, dan aliran.  
2. **Aspose.Tasks untuk .NET** – unduh dan instal dari [di sini](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider, atau editor kompatibel .NET apa pun.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Langkah 1: Buat Objek Project

Muat file MPP yang ada ke dalam instance `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Langkah 2: Konfigurasikan Image Save Options

Siapkan `ImageSaveOptions` untuk output PNG dan lampirkan callback khusus:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Tips pro:** Mengatur `RenderToSinglePage = false` memastikan setiap halaman diagram Gantt dirender secara terpisah, yang penting agar callback menerima aliran yang berbeda.

## Langkah 3: Simpan Project dengan Callback

Panggil metode `Save`, dengan mengirim `Stream.Null` karena aliran sebenarnya disediakan oleh callback:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Langkah 4: Proses Aliran Halaman yang Disimpan

Setelah operasi penyimpanan selesai, callback menyimpan koleksi objek `MemoryStream`—satu per halaman. Anda sekarang dapat mengiterasinya:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Langkah 5: Implementasikan Callback Penyimpanan Halaman Kustom

Buat kelas sealed yang mengimplementasikan `IPageSavingCallback`. Kelas ini menangkap aliran setiap halaman dan menyimpannya dalam daftar untuk penggunaan selanjutnya.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Kesalahan Umum & Pemecahan Masalah

| Masalah | Penyebab | Solusi |
|-------|--------|----------|
| **Tidak ada halaman yang dikembalikan** | `RenderToSinglePage` dibiarkan `true`. | Setel `RenderToSinglePage = false` untuk menghasilkan halaman terpisah. |
| **Aliran kosong** | `KeepStreamOpen` diatur ke `true` tanpa dibuang kemudian. | Biarkan `false` (default) dan biarkan callback menutup aliran secara otomatis. |
| **Kesalahan kehabisan memori** | Proyek sangat besar menghasilkan banyak PNG beresolusi tinggi. | Proses aliran satu per satu atau tingkatkan batas memori VM. |

## Pertanyaan yang Sering Diajukan

**Q1: Apa itu callback penyimpanan halaman di Aspose.Tasks?**  
A: Callback penyimpanan halaman memungkinkan Anda menyela proses penyimpanan untuk setiap halaman dokumen multi‑halaman, menyediakan `Stream` khusus untuk halaman tersebut.

**Q2: Apakah saya dapat menggunakan format berbeda untuk menyimpan halaman menggunakan callback ini?**  
A: Ya. Dengan mengubah `SaveFileFormat` Anda dapat mengekspor ke PNG, JPEG, PDF, SVG, dll.

**Q3: Apakah Aspose.Tasks kompatibel dengan .NET Core?**  
A: Tentu saja. Aspose.Tasks mendukung .NET Core, .NET 5, dan .NET 6.

**Q4: Bagaimana saya dapat menangani kesalahan selama proses penyimpanan halaman?**  
A: Bungkus logika callback dalam blok try/catch dan catat pengecualian. Metode `OnFinish` adalah tempat yang baik untuk pembersihan akhir.

**Q5: Di mana saya dapat menemukan lebih banyak sumber daya dan dukungan untuk Aspose.Tasks?**  
A: Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan, mengakses dokumentasi [di sini](https://reference.aspose.com/tasks/net/), atau menjelajahi fitur tambahan dan opsi lisensi di [situs web Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Terakhir diperbarui:** 2026-03-16  
**Diuji dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}