---
title: Menguasai Pengumpulan Data Bertahap Waktu di Aspose.Tasks
linktitle: Pengumpulan Data Bertahap Waktu di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi pengumpulan data bertahap di Aspose.Tasks untuk .NET. Panduan langkah demi langkah, FAQ, dan banyak lagi. Tingkatkan kemampuan manajemen proyek Anda hari ini!
type: docs
weight: 15
url: /id/net/text-view-configuration/timephased-data-collection/
---
## Perkenalan
Apakah Anda ingin memanfaatkan kekuatan data bertahap dalam aplikasi .NET Anda menggunakan Aspose.Tasks? Tidak perlu mencari lagi! Panduan komprehensif ini akan memandu Anda melalui proses pengumpulan data bertahap dengan Aspose.Tasks untuk .NET, memastikan bahwa Anda memanfaatkan perpustakaan canggih ini semaksimal mungkin.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan dari[Dokumentasi Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. Lingkungan Pengembangan .NET: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET yang berfungsi.
3. Direktori Dokumen Anda: Ganti placeholder "Direktori Dokumen Anda" di cuplikan kode dengan jalur ke direktori dokumen Anda.
## Impor Namespace
Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Buat Proyek dan Sumber Daya
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Tambahkan Tugas ke Proyek
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Tetapkan properti tugas...
var task2 = project.RootTask.Children.Add("Task 2");
// Setel properti tugas2...
```
## 3. Tetapkan Sumber Daya ke Tugas
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Tetapkan properti tugas...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Setel properti penugasan2...
```
## 4. Bekerja dengan Data Bertahap Waktu
```csharp
// Atur kontur kerja yang berkontur
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Periksa apakah pengumpulan data bertahap bersifat baca-saja
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Hapus data fase waktu yang dihasilkan
assignment.TimephasedData.Clear();
// Membuat dan menambahkan data berfase waktu
var td = new TimephasedData
{
    // Setel properti data berfase waktu...
};
assignment.TimephasedData.Add(td);
// Tambahkan daftar data berfase waktu
var list = new List<TimephasedData>();
// Tambahkan lebih banyak item data berfase waktu ke daftar...
assignment.TimephasedData.AddRange(list);
// Filter data bertahap berdasarkan jenis dan rentang tanggal
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Cetak data bertahap yang difilter...
```
## 5. Memanipulasi Data Bertahap Waktu
```csharp
//Tambahkan item data berfase waktu yang salah lalu hapus
var td4 = new TimephasedData
{
    // Menyetel properti data fase waktu yang salah...
};
assignment.TimephasedData.Add(td4);
// Hapus item data berfase waktu yang salah
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Ulangi semua item berfase waktu
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Cetak detail item berfase waktu...
}
```
## 6. Salin Data Bertahap Waktu ke Tugas Lain
```csharp
// Salin data berfase waktu ke tugas lain
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Ubah koleksi menjadi daftar biasa
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Hapus item data berfase waktu satu per satu
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Kesimpulan
Sebagai kesimpulan, tutorial ini telah memberikan panduan mendetail tentang pengumpulan data bertahap menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam proyek Anda, sehingga memungkinkan pelacakan waktu dan pengelolaan sumber daya yang efektif.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan alat manajemen proyek lainnya?
Ya, Aspose.Tasks untuk .NET dirancang untuk bekerja dengan alat manajemen proyek populer dan mendukung berbagai format file.
### Apakah ada batasan jumlah sumber daya dan tugas yang dapat saya kelola dengan Aspose.Tasks?
Aspose.Tasks menangani proyek dengan berbagai ukuran, dan tidak ada batasan ketat mengenai jumlah sumber daya dan tugas.
### Bagaimana saya bisa mendapatkan dukungan untuk masalah atau pertanyaan apa pun terkait Aspose.Tasks untuk .NET?
 Untuk dukungan, kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk berhubungan dengan masyarakat dan mendapatkan bantuan.
### Bisakah saya mencoba Aspose.Tasks untuk .NET sebelum membelinya?
 Ya, Anda dapat menjelajahi fitur Aspose.Tasks untuk .NET dengan mengakses[uji coba gratis](https://releases.aspose.com/).
### Di mana saya dapat membeli lisensi Aspose.Tasks untuk .NET?
 Anda dapat membeli lisensi Aspose.Tasks untuk .NET[Di Sini](https://purchase.aspose.com/buy).