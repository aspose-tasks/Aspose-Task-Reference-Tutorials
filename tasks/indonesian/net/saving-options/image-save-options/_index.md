---
title: Simpan Gambar Opsi Proyek MS untuk Aspose.Tasks
linktitle: Opsi Penyimpanan Gambar untuk Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyimpan opsi MS Project sebagai gambar menggunakan Aspose.Tasks untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
weight: 11
url: /id/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan Gambar Opsi Proyek MS untuk Aspose.Tasks


## Perkenalan
Dalam dunia pengembangan perangkat lunak, menangani tugas-tugas proyek secara efisien sangat penting untuk keberhasilan manajemen proyek. Aspose.Tasks untuk .NET menawarkan solusi canggih bagi pengembang yang bekerja dengan file Microsoft Project, memungkinkan mereka memanipulasi, mengonversi, dan mengelola tugas proyek dengan lancar dalam aplikasi .NET mereka.
## Prasyarat
Sebelum mulai menggunakan Aspose.Tasks untuk .NET untuk menyimpan opsi MS Project sebagai gambar, pastikan Anda memiliki prasyarat berikut:
### 1. Instal Aspose.Tasks untuk .NET
Untuk memulai, Anda perlu menginstal Aspose.Tasks for .NET di lingkungan pengembangan Anda. Anda dapat mengunduh perpustakaan dari[situs web](https://releases.aspose.com/tasks/net/) dan ikuti petunjuk instalasi yang diberikan.
### 2. Dapatkan Lisensi (Opsional)
 Meskipun Aspose.Tasks untuk .NET dapat digunakan tanpa lisensi dalam mode evaluasi, disarankan untuk mendapatkan lisensi untuk fungsionalitas penuh dan untuk menghilangkan batasan evaluasi. Anda dapat memperoleh lisensi dari[halaman pembelian](https://purchase.aspose.com/buy) atau memilih a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.
### 3. Pengetahuan Dasar Pengembangan C# dan .NET
Pemahaman mendasar tentang bahasa pemrograman C# dan kerangka .NET diperlukan untuk mengikuti contoh dan mengintegrasikan fungsionalitas Aspose.Tasks ke dalam aplikasi Anda secara efektif.
## Impor Namespace
Sebelum kita mulai menyimpan opsi Proyek MS sebagai gambar menggunakan Aspose.Tasks untuk .NET, pastikan kita mengimpor namespace yang diperlukan ke proyek C# kita:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Langkah 1: Siapkan Jalur Direktori Dokumen
Pastikan Anda memiliki direktori khusus untuk dokumen Anda dan atur jalurnya sesuai:
```csharp
String DataDir = "Your Document Directory";
```
## Langkah 2: Muat File Proyek MS
 Inisialisasi yang baru`Project` objek dengan memuat file MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Langkah 3: Tentukan Opsi Penyimpanan Gambar
 Buat sebuah contoh dari`ImageSaveOptions`dan tentukan pengaturan yang diinginkan:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Langkah 4: Tentukan Halaman yang akan Disimpan
Jika perlu, tentukan halaman yang akan disimpan. Dalam contoh ini, kami menambahkan halaman 2:
```csharp
options.Pages.Add(2);
```
## Langkah 5: Simpan Gambar
Terakhir, simpan halaman yang dipilih sebagai gambar dengan opsi yang ditentukan:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Kesimpulan
Aspose.Tasks untuk .NET menyederhanakan proses bekerja dengan file MS Project, memungkinkan pengembang memanipulasi tugas proyek dengan mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menyimpan opsi MS Project secara efisien sebagai gambar dalam aplikasi .NET Anda.
## FAQ
### Q1: Bisakah saya menggunakan Aspose.Tasks untuk .NET tanpa lisensi?
J: Ya, Anda dapat menggunakan Aspose.Tasks untuk .NET tanpa lisensi dalam mode evaluasi. Namun, disarankan untuk mendapatkan lisensi untuk fungsionalitas penuh dan menghapus batasan evaluasi.
### Q2: Bagaimana saya bisa mendapatkan lisensi sementara untuk pengujian?
 J: Anda bisa mendapatkan lisensi sementara untuk tujuan pengujian dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
### Q3: Apakah Aspose.Tasks untuk .NET kompatibel dengan kerangka .NET lainnya?
J: Ya, Aspose.Tasks untuk .NET kompatibel dengan berbagai kerangka .NET, termasuk .NET Core dan .NET Standard.
### Q4: Dapatkah saya menyesuaikan opsi penyimpanan gambar lebih lanjut?
J: Ya, Anda dapat menyesuaikan opsi penyimpanan gambar sesuai dengan kebutuhan spesifik Anda, seperti menyesuaikan ukuran halaman, resolusi, atau format keluaran.
### Q5: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk .NET?
 J: Anda dapat menemukan dukungan dan bantuan untuk Aspose.Tasks untuk .NET di[forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
