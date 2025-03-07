---
title: Kuasai Masker Garis Besar Proyek MS dengan Aspose.Tasks
linktitle: Koleksi Masker Garis Besar di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memanipulasi masker kerangka koleksi MS Project menggunakan Aspose.Tasks untuk .NET. Tingkatkan produktivitas dengan tutorial komprehensif ini.
weight: 15
url: /id/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kuasai Masker Garis Besar Proyek MS dengan Aspose.Tasks

## Perkenalan
Apakah Anda ingin memanfaatkan kekuatan masker garis besar Microsoft Project menggunakan Aspose.Tasks untuk .NET? Anda datang ke tempat yang tepat! Dalam tutorial komprehensif ini, kami akan memandu Anda melalui proses langkah demi langkah, memastikan Anda mendapatkan pemahaman yang kuat tentang cara memanipulasi outline mask secara efektif dalam proyek Anda. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan membekali Anda dengan pengetahuan dan keterampilan yang dibutuhkan untuk mengoptimalkan alur kerja Anda.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
### 1. Instalasi Aspose.Tasks untuk .NET
Pastikan Anda telah menginstal Aspose.Tasks untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduh perpustakaan dari situs web Aspose[Di Sini](https://releases.aspose.com/tasks/net/).
### 2. Pengetahuan Dasar C# dan .NET Framework
Biasakan diri Anda dengan bahasa pemrograman C# dan .NET Framework, karena tutorial ini akan memanfaatkan keduanya.
### 3. File Proyek Microsoft
Siapkan file Microsoft Project (MPP) untuk tujuan pengujian. Anda dapat menggunakan file yang sudah ada atau membuat file baru untuk eksperimen.
## Impor Namespace
Mari kita mulai dengan mengimpor namespace yang diperlukan ke proyek C# Anda. Langkah ini memastikan bahwa Anda memiliki akses ke kelas dan fungsi yang diperlukan yang disediakan oleh Aspose.Tasks untuk .NET.

Tambahkan namespace berikut di awal file kode Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah dan jelaskan setiap langkah secara detail:
## Langkah 1: Inisialisasi Objek Proyek
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Di sini, kami membuat instance baru dari`Project` kelas dan memuat file Microsoft Project yang ada bernama "OutlineValues2010.mpp".
## Langkah 2: Akses Kode Garis Besar
```csharp
var outline = project.OutlineCodes[0];
```
Kami mengakses kode garis besar dari proyek. Kode kerangka adalah bidang khusus di Microsoft Project yang memungkinkan Anda mengkategorikan dan mengatur tugas.
## Langkah 3: Hapus Masker Garis Besar
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Langkah ini memastikan bahwa semua outline mask yang ada telah dibersihkan sebelum melanjutkan lebih jauh.
## Langkah 4: Buat Masker Garis Besar
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Kami membuat masker garis besar baru dan menentukan tipenya. Dalam contoh ini, kita membuat outline mask yang valid dan yang salah.
## Langkah 5: Sisipkan dan Edit Masker
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Di sini, kita memasukkan masker yang salah ke dalam koleksi dan mengedit panjang masker menggunakan indeksnya.
## Langkah 6: Hapus Masker
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Kami menghapus topeng yang salah dari koleksi berdasarkan indeksnya.
## Langkah 7: Ulangi Masker
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Perulangan ini mengulangi setiap topeng kerangka dalam koleksi dan mencetak propertinya seperti panjang, level, pemisah, dan jenis.
## Langkah 8: Salin Masker ke Proyek Lain
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Terakhir, kami menyalin outline mask dari satu proyek ke proyek lainnya, memastikan konsistensi di berbagai proyek.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara memanipulasi masker kerangka koleksi MS Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti tutorial ini, Anda kini dibekali dengan keterampilan untuk mengelola masker kerangka secara efisien dalam proyek Anda, yang pada akhirnya meningkatkan produktivitas dan alur kerja Anda.
## FAQ
### Q1: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan versi file Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks untuk .NET mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.
### Q2: Apakah Aspose.Tasks untuk .NET kompatibel dengan .NET Core?
J: Ya, Aspose.Tasks untuk .NET kompatibel dengan .NET Core, memungkinkan Anda menggunakannya dalam aplikasi lintas platform.
### Q3: Dapatkah saya menyesuaikan properti masker garis besar sesuai dengan kebutuhan proyek saya?
J: Tentu saja! Anda dapat mengkustomisasi masker kerangka dengan menyesuaikan panjang, level, pemisah, dan jenisnya agar sesuai dengan kebutuhan spesifik proyek Anda.
### Q4: Apakah Aspose.Tasks untuk .NET menyediakan dokumentasi dan dukungan?
J: Ya, Aspose.Tasks untuk .NET menawarkan dokumentasi komprehensif dan dukungan khusus melalui situs web mereka dan[forum](https://forum.aspose.com/c/tasks/15).
### Q5: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda dapat mengakses uji coba gratis Aspose.Tasks untuk .NET dari mereka[situs web](https://releases.aspose.com/tasks/net/). untuk menjelajahi fitur dan fungsinya sebelum melakukan pembelian.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
