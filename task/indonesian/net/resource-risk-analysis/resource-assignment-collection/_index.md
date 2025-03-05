---
title: Kumpulan Penugasan Sumber Daya di Aspose.Tasks
linktitle: Kumpulan Penugasan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola penetapan sumber daya di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Tutorial langkah demi langkah dengan contoh kode.
type: docs
weight: 12
url: /id/net/resource-risk-analysis/resource-assignment-collection/
---
## Perkenalan
Selamat datang di tutorial komprehensif tentang mengelola penetapan sumber daya di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dalam tutorial ini, kami akan mempelajari prosesnya langkah demi langkah, memastikan Anda memiliki pemahaman yang kuat tentang cara memanipulasi penetapan sumber daya secara efisien. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui semua yang perlu Anda ketahui.
## Prasyarat
Sebelum kita mendalami kodenya, pastikan Anda telah menyiapkan yang berikut:
1.  Aspose.Tasks for .NET Installed: Pastikan Anda telah menginstal Aspose.Tasks for .NET di lingkungan pengembangan Anda. Jika tidak, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang bahasa pemrograman C#.
3. File Proyek Microsoft: Siapkan file Microsoft Project untuk tujuan pengujian. Jika Anda tidak memilikinya, Anda dapat membuat file sampel.

## Impor Namespace
Pertama, mari impor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Langkah 1: Muat File Proyek
Mulailah dengan memuat file Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Langkah 2: Tambahkan Tugas dan Sumber Daya
Sekarang, mari tambahkan tugas dan sumber daya ke proyek:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Langkah 3: Tetapkan Sumber Daya ke Tugas
Selanjutnya, kita akan menetapkan sumber daya untuk tugas tersebut:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Langkah 4: Bekerja dengan Berbagai Jenis Tugas
Anda juga dapat mengerjakan tugas yang melibatkan unit atau biaya:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Tetapkan properti untuk penugasan dengan unit dan biaya sama seperti yang ditunjukkan pada Langkah 3
```
## Langkah 5: Cetak Tugas
Cetak tugas untuk proyek:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Cetak detail tugas
}
```
## Langkah 6: Ambil Tugas oleh UID
Anda dapat mengambil tugas dengan UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Langkah 7: Periksa Status Hanya-Baca
Verifikasi apakah kumpulan penetapan sumber daya bersifat baca-saja:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Langkah 8: Ubah Koleksi menjadi Daftar dan Ulangi
Ubah koleksi menjadi daftar dan ulangi:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Kesimpulan
Selamat! Anda telah mempelajari cara mengelola penetapan sumber daya di Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memanipulasi tugas dan sumber daya secara efisien, sehingga memudahkan manajemen proyek.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks untuk .NET dengan versi file Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks untuk .NET mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.
### T: Apakah ada versi uji coba yang tersedia sebelum membeli Aspose.Tasks untuk .NET?
 J: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah apa pun saat menggunakan Aspose.Tasks untuk .NET?
 J: Anda dapat mencari dukungan dari forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Dapatkah saya menggunakan lisensi sementara untuk Aspose.Tasks untuk .NET?
 J: Ya, lisensi sementara tersedia untuk tujuan evaluasi. Anda bisa mendapatkannya dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat membeli lisensi penuh Aspose.Tasks untuk .NET?
 J: Anda dapat membeli lisensi penuh dari toko online Aspose[Di Sini](https://purchase.aspose.com/buy).