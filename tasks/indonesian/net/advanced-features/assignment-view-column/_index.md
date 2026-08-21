---
date: 2026-03-19
description: Pelajari cara menambahkan beberapa kolom kustom dan memformat lebar kolom
  kustom saat mengekspor proyek ke XML menggunakan Aspose.Tasks untuk .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Tambahkan Beberapa Kolom Kustom ke Tampilan Penugasan di Aspose.Tasks
url: /id/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Beberapa Kolom Kustom ke Tampilan Penugasan di Aspose.Tasks

## Pendahuluan

Dalam tutorial ini Anda akan menemukan **cara menambahkan beberapa kolom kustom** ke tampilan penugasan dengan Aspose.Tasks untuk .NET. Kolom kustom memungkinkan Anda menampilkan data tambahan—seperti catatan, biaya, atau flag kustom—langsung dalam laporan yang diekspor. Pada akhir panduan Anda akan dapat mengatur lebar kolom kustom, mengekspor proyek ke XML, dan menyesuaikan tampilan agar sesuai dengan kebutuhan manajemen proyek Anda.

## Jawaban Cepat
- **Apa yang dapat saya capai?** Tampilkan data penugasan apa pun dalam kolom kustom dan kontrol tampilannya.  
- **Format apa yang mendukungnya?** Mengekspor proyek ke XML (atau format lain) menggunakan `Spreadsheet2003SaveOptions`.  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Versi .NET apa yang bekerja?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Berapa banyak kolom yang dapat saya tambahkan?** Tidak terbatas – cukup buat instance `AssignmentViewColumn` tambahan.

## Apa itu beberapa kolom kustom?
Beberapa kolom kustom adalah bidang yang didefinisikan pengguna yang muncul bersamaan dengan kolom penugasan default saat proyek disimpan atau diekspor. Mereka memberi Anda fleksibilitas untuk menampilkan properti apa pun dari objek `ResourceAssignment`, seperti catatan kustom, kode biaya, atau nilai yang dihitung.

## Mengapa menambahkan beberapa kolom kustom ke tampilan penugasan?
- **Pelaporan yang ditingkatkan:** Sertakan informasi spesifik proyek yang tidak tercakup oleh kolom bawaan.  
- **Pengambilan keputusan yang lebih baik:** Pemangku kepentingan dapat melihat data tepat yang mereka butuhkan tanpa harus menggali file mentah.  
- **Pemformatan konsisten:** Kontrol lebar kolom dan konversi teks untuk output yang bersih dan mudah dibaca.  

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. Pengetahuan dasar tentang bahasa pemrograman C#.
2. Perpustakaan Aspose.Tasks untuk .NET terpasang. Jika belum, Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/tasks/net/)**.
3. Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.  

## Panduan Langkah demi Langkah

### Langkah 1: Impor Namespace
Pertama, impor namespace yang menyediakan kelas yang akan kita gunakan untuk bekerja dengan proyek dan visualisasi.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Langkah 2: Muat Proyek
Buat instance `Project` dan muat file MPP yang ada.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Langkah 3: Buat Opsi Penyimpanan Spreadsheet
Instansiasi `Spreadsheet2003SaveOptions` – objek ini memungkinkan kita menyesuaikan tampilan penugasan sebelum mengekspor.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Langkah 4: Definisikan Kolom Kustom
Buat `AssignmentViewColumn` untuk setiap data yang ingin Anda tampilkan. Di bawah ini kami menambahkan kolom **Notes** dengan lebar 200 poin.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** Untuk menambahkan *beberapa* kolom kustom, ulangi langkah ini dengan nama bidang dan logika delegate yang berbeda, kemudian tambahkan setiap instance ke `options.AssignmentView.Columns`.

### Langkah 5: Tambahkan Kolom Kustom ke Opsi
Tambahkan kolom (atau kolom-kolom) ke koleksi `Columns` dari tampilan penugasan.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Langkah 6: Iterasi Melalui Penugasan (Debugging Opsional)
Anda dapat melakukan loop melalui penugasan untuk memverifikasi bahwa teks kolom kustom dihasilkan dengan benar.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Langkah 7: Simpan Proyek dengan Kolom Kustom
Akhirnya, simpan proyek. Contoh ini menyimpan ke XML, tetapi Anda dapat memilih format apa pun yang didukung.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Cara mengekspor proyek ke XML dengan kolom kustom?
Saat Anda memanggil `project.Save` dengan `Spreadsheet2003SaveOptions` yang telah dikonfigurasi, Aspose.Tasks menulis data proyek—termasuk semua **beberapa kolom kustom**—ke file XML yang dipilih. Hal ini memudahkan berbagi informasi proyek yang diperkaya dengan sistem atau pemangku kepentingan lain.

## Format lebar kolom kustom untuk keterbacaan yang lebih baik
Parameter kedua dari konstruktor `AssignmentViewColumn` mengontrol lebar kolom (diukur dalam poin). Sesuaikan nilai ini dengan jumlah teks yang Anda harapkan. Misalnya, lebar **300** cocok untuk catatan yang lebih panjang, sementara **100** cukup untuk flag singkat.

## Masalah Umum dan Solusinya
- **Teks kolom muncul kosong:** Pastikan delegate mengembalikan string dan properti penugasan yang mendasarinya (mis., `Asn.NotesText`) terisi.  
- **Kolom tidak terlihat dalam file yang diekspor:** Verifikasi bahwa `options.AssignmentView.Columns` berisi kolom kustom Anda sebelum memanggil `Save`.  
- **Lebar tampaknya diabaikan:** Beberapa format ekspor memiliki aturan tata letak sendiri; XML menghormati lebar, tetapi PDF/HTML mungkin memerlukan styling tambahan.  

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menambahkan beberapa kolom kustom ke tampilan penugasan?
**J:** Ya, cukup buat objek `AssignmentViewColumn` tambahan dan tambahkan masing-masing ke `options.AssignmentView.Columns`.

### Q2: Apakah ada konverter bawaan yang tersedia untuk bidang penugasan umum?
**J:** Ya, Aspose.Tasks menyediakan konverter bawaan untuk banyak bidang standar, memudahkan pengambilan data tanpa menulis delegate kustom.

### Q3: Bisakah saya menyesuaikan tampilan kolom kustom, seperti memformat teks atau menerapkan gaya?
**J:** Tentu saja. Selain mengatur lebar, Anda dapat memodifikasi font, perataan, dan properti visual lainnya melalui opsi styling kolom.

### Q4: Apakah memungkinkan menghapus kolom default dari tampilan penugasan?
**J:** Anda dapat mengecualikan kolom default dengan menghapusnya dari koleksi `Columns` atau dengan mengatur lebar mereka menjadi nol.

### Q5: Apakah Aspose.Tasks mendukung mengekspor proyek ke format lain selain spreadsheet dengan kolom kustom?
**J:** Ya, Aspose.Tasks dapat mengekspor ke PDF, HTML, XML, dan banyak format lain sambil mempertahankan definisi kolom kustom.

---

**Terakhir Diperbarui:** 2026-03-19  
**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}