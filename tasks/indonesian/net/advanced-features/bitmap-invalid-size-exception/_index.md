---
date: 2026-03-21
description: Pelajari cara mengekspor gambar dan menangani BitmapInvalidSizeException
  saat menyimpan proyek sebagai gambar di Aspose.Tasks untuk .NET. Termasuk langkah-langkah
  untuk menyimpan proyek sebagai gambar dan mengekspor proyek ke PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Mengekspor Gambar dan Menangani Pengecualian Ukuran Tidak Valid
url: /id/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekspor Gambar – Menangani Pengecualian Ukuran Tidak Valid untuk Bitmap di Aspose.Tasks

Dalam tutorial ini Anda akan belajar **cara mengekspor gambar** dari file Microsoft Project menggunakan Aspose.Tasks untuk .NET dan, yang lebih penting, cara menangkap `BitmapInvalidSizeException` yang dapat terjadi selama proses. Mengekspor proyek sebagai gambar adalah kebutuhan umum untuk dasbor pelaporan, dokumentasi, atau sekadar berbagi snapshot visual dari jadwal. Pada akhir panduan ini Anda akan dapat **menyimpan proyek sebagai gambar** dengan andal dan bahkan **mengekspor proyek ke format PNG** tanpa crash yang tidak terduga.

## Jawaban Cepat
- **Exception apa yang dapat terjadi saat mengekspor gambar?** `BitmapInvalidSizeException`  
- **Format apa yang digunakan dalam contoh?** PNG (`SaveFileFormat.Png`)  
- **Apakah saya memerlukan lisensi khusus?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya mengubah skala waktu?** Ya – Anda dapat mengatur unit skala waktu (menit, jam, hari, dll.).  
- **Apakah kode kompatibel dengan .NET Core?** Tentu – API yang sama bekerja pada .NET Framework dan .NET Core.

## Apa itu BitmapInvalidSizeException?
`BitmapInvalidSizeException` dilemparkan ketika dimensi bitmap yang dihitung untuk gambar berada di luar rentang yang didukung (mis., lebar atau tinggi nol atau melebihi batas internal). Hal ini biasanya terjadi ketika skala waktu atau pengaturan tampilan menghasilkan gambar yang terlalu besar atau terlalu kecil.

## Mengapa mengekspor proyek sebagai gambar?
- **Pelaporan visual** – menyematkan diagram Gantt dalam PDF, dokumen Word, atau halaman web.  
- **Berbagi lintas‑platform** – file PNG dapat dilihat di perangkat apa pun tanpa memerlukan Microsoft Project.  
- **Kinerja** – gambar lebih ringan dibandingkan file proyek lengkap untuk pratinjau cepat.

## Prasyarat
1. Pengetahuan dasar tentang pengembangan C# dan .NET.  
2. Aspose.Tasks untuk .NET terinstal (paket NuGet `Aspose.Tasks`).  
3. File contoh Microsoft Project (mis., `Blank2010.mpp`).  

## Impor Namespace
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Inisialisasi Proyek dan Pilih Tampilan
Pertama, buat instance `Project` dan pilih tampilan yang ingin Anda render (di sini kami menggunakan tampilan diagram Gantt pertama).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Langkah 2: Konfigurasi Opsi Penyimpanan Gambar (Ekspor Proyek ke PNG)
Atur format gambar yang diinginkan dan beri tahu Aspose.Tasks untuk menggunakan skala waktu yang ditentukan dalam tampilan.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Langkah 3: Sesuaikan Unit Skala Waktu (Kontrol Ukuran Gambar)
Mengubah skala waktu memengaruhi dimensi bitmap. Dalam contoh ini kami menggunakan **menit** untuk menjaga ukuran gambar tetap dapat dikelola.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Langkah 4: Coba Simpan Proyek sebagai Gambar
Baris ini melakukan operasi **menyimpan proyek sebagai gambar** yang sebenarnya.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Langkah 5: Tangkap dan Tangani BitmapInvalidSizeException
Bungkus pemanggilan penyimpanan dalam blok `try / catch` sehingga aplikasi Anda dapat merespon dengan elegan jika ukuran bitmap tidak valid.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|----------|
| Pengecualian masih dilempar setelah menyesuaikan skala waktu | Skala waktu masih menghasilkan bitmap yang terlalu besar | Kurangi `view.MiddleTimescaleTier.Count` atau beralih ke `TimescaleUnit` yang lebih kasar (mis., Jam). |
| File output kosong | Path file tidak benar atau izin menulis tidak ada | Verifikasi `DataDir` mengarah ke folder yang dapat ditulis dan nama file berakhiran `.png` jika Anda mengubah format. |
| Kualitas gambar buruk | DPI default mungkin rendah | Setel `options.DpiX` dan `options.DpiY` ke nilai yang lebih tinggi (mis., 300). |

## Pertanyaan yang Sering Diajukan

**Q: Apa yang menyebabkan BitmapInvalidSizeException di Aspose.Tasks?**  
A: Itu terjadi ketika dimensi bitmap yang dihitung tidak valid—biasanya karena skala waktu menghasilkan gambar yang terlalu besar atau memiliki lebar/tinggi nol.

**Q: Bisakah saya menyesuaikan skala waktu saat mengekspor gambar?**  
A: Ya. Anda dapat memodifikasi `view.MiddleTimescaleTier.Unit` dan `Count` sesuai kebutuhan Anda, seperti yang ditunjukkan dalam tutorial.

**Q: Apakah Aspose.Tasks mendukung format gambar lain selain PNG?**  
A: Tentu. `SaveFileFormat` juga mencakup JPEG, BMP, GIF, dan TIFF. Cukup ubah nilai enum di `ImageSaveOptions`.

**Q: Apakah lisensi diperlukan untuk mengekspor gambar di lingkungan produksi?**  
A: Ya. Meskipun perpustakaan berfungsi dalam mode evaluasi, lisensi komersial menghapus batasan evaluasi dan menyediakan dukungan penuh.

**Q: Bagaimana saya dapat meningkatkan kualitas PNG yang diekspor?**  
A: Tingkatkan pengaturan DPI (`options.DpiX` dan `options.DpiY`) atau sesuaikan skala waktu tampilan untuk menghasilkan bitmap yang lebih besar.

## Kesimpulan
Dengan mengikuti langkah-langkah di atas Anda kini tahu **cara mengekspor gambar** dari file Project, cara **menyimpan proyek sebagai gambar**, dan cara menangani `BitmapInvalidSizeException` dengan elegan. Teknik ini membuat alur pelaporan Anda lebih kuat dan memastikan bahwa ekspor visual berfungsi secara andal di berbagai ukuran proyek dan skala waktu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-03-21  
**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose