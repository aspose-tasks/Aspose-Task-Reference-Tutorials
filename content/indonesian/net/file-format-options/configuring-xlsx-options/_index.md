---
title: Konfigurasikan Opsi MS Project XLSX di Aspose.Tasks untuk .NET
linktitle: Mengonfigurasi Opsi XLSX di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengonfigurasi opsi MS Project XLSX di Aspose.Tasks untuk .NET. Sesuaikan kolom, pengkodean, dan lainnya dengan mudah.
type: docs
weight: 11
url: /id/net/file-format-options/configuring-xlsx-options/
---
## Perkenalan
Microsoft Project (MS Project) adalah alat yang ampuh untuk manajemen proyek, dan Aspose.Tasks untuk .NET menyediakan integrasi yang lancar untuk bekerja dengan file MS Project secara terprogram. Dalam tutorial ini, kita akan memandu proses mengonfigurasi opsi MS Project XLSX menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
### 1. Aspose.Tasks untuk .NET Terinstal
 Pastikan Anda telah menginstal Aspose.Tasks untuk .NET di lingkungan pengembangan Anda. Jika belum, Anda dapat mendownloadnya dari[Aspose.Tasks untuk halaman unduhan .NET](https://releases.aspose.com/tasks/net/).
### 2. Pemahaman Dasar C# dan .NET Framework
Keakraban dengan bahasa pemrograman C# dan kerangka .NET diperlukan untuk mengikuti tutorial ini.
### 3. File Proyek Microsoft
Siapkan file Microsoft Project (MPP) yang ingin Anda konfigurasi dan simpan sebagai file XLSX.

## Mengimpor Namespace
Untuk memulai, impor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Langkah 1: Muat Proyek
```csharp
var project = new Project("YourProjectFile.mpp");
```
Muat file Microsoft Project yang ingin Anda konfigurasi.
## Langkah 2: Tentukan XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Buat sebuah contoh dari`XlsxOptions` untuk mengonfigurasi pengaturan untuk menyimpan sebagai XLSX.
## Langkah 3: Tambahkan Kolom Gantt Chart
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Tambahkan kolom Gantt Chart yang diinginkan ke opsi.
## Langkah 4: Tambahkan Kolom Tampilan Sumber Daya
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Sertakan kolom yang diinginkan untuk tampilan sumber daya dalam opsi.
## Langkah 5: Tambahkan Kolom Tampilan Tugas
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Tambahkan kolom yang diinginkan untuk tampilan tugas di opsi.
## Langkah 6: Atur Pengkodean
```csharp
options.Encoding = Encoding.Unicode;
```
Atur pengkodean untuk file keluaran.
## Langkah 7: Simpan Proyek sebagai XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Simpan proyek dengan opsi yang dikonfigurasi sebagai file XLSX.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengonfigurasi opsi MS Project XLSX menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat menyesuaikan format keluaran sesuai dengan kebutuhan Anda, sehingga meningkatkan fleksibilitas dan kegunaan alur kerja manajemen proyek Anda.
## FAQ

### T: Bisakah saya mengonfigurasi kolom berbeda untuk Gantt Chart, Resource View, dan Assignment View secara terpisah?

J: Ya, Anda dapat mengkustomisasi kolom secara independen untuk setiap tampilan menggunakan Aspose.Tasks untuk .NET.

### T: Apakah ada versi uji coba yang tersedia sebelum membeli Aspose.Tasks untuk .NET?

 J: Ya, Anda dapat mengunduh uji coba gratis dari[Aspose.Tasks untuk halaman rilis .NET](https://releases.aspose.com/).

### T: Bagaimana saya bisa mendapatkan dukungan jika saya menemui masalah atau memiliki pertanyaan selama penerapan?

 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan dari komunitas dan tim dukungan Aspose.

### T: Dapatkah saya membuat file XLSX dengan Aspose.Tasks untuk .NET pada platform non-Windows?

J: Aspose.Tasks untuk .NET terutama dirancang untuk platform Windows, namun Anda dapat menjelajahi opsi kompatibilitas untuk platform lain.

### T: Apakah ada opsi lisensi sementara yang tersedia untuk tujuan pengujian?

 J: Ya, Anda bisa mendapatkan lisensi sementara dari[Halaman lisensi sementara Aspose.Tasks](https://purchase.aspose.com/temporary-license/).