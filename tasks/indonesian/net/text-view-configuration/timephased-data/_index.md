---
title: Kuasai Penanganan Data Bertahap Waktu dengan Aspose.Tasks untuk .NET
linktitle: Menangani Data Berfase Waktu di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Jelajahi Aspose.Tasks untuk .NET untuk dengan mudah menangani data bertahap waktu, meningkatkan perencanaan proyek, dan mengoptimalkan manajemen sumber daya. #Aspose #Tugas #MS Project
weight: 14
url: /id/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kuasai Penanganan Data Bertahap Waktu dengan Aspose.Tasks untuk .NET

## Perkenalan
Dalam dunia manajemen proyek, penanganan data bertahap yang efektif sangat penting untuk alokasi sumber daya, estimasi biaya, dan perencanaan proyek secara keseluruhan. Aspose.Tasks untuk .NET memberikan solusi canggih untuk bekerja dengan data bertahap waktu khusus dengan lancar. Tutorial ini akan memandu Anda melalui proses penanganan data bertahap menggunakan Aspose.Tasks, memungkinkan Anda mengoptimalkan manajemen sumber daya dalam proyek Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar tentang konsep manajemen proyek.
-  Menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
- Editor kode, seperti Visual Studio, untuk mengimplementasikan contoh yang diberikan.
## Impor Namespace
Dalam proyek .NET Anda, pastikan untuk mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Tasks. Tambahkan baris berikut di awal file kode Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk memandu Anda dalam menangani data bertahap menggunakan Aspose.Tasks:
## Langkah 1: Siapkan Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Di sini, kami menginisialisasi proyek baru dan mengatur mode perhitungannya.
## Langkah 2: Tentukan Sumber Daya dan Tugas
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Buat sumber daya pekerjaan dan biaya, serta tugas, untuk mensimulasikan struktur proyek.
## Langkah 3: Tetapkan Sumber Daya ke Tugas
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Tetapkan sumber daya pekerjaan dan biaya untuk tugas tersebut.
## Langkah 4: Tambahkan Data Fase Waktu Khusus
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Langkah serupa untuk costAssignment
costAssignment.TimephasedData.Clear();
```
Tambahkan data bertahap waktu khusus untuk penetapan pekerjaan dan biaya.
## Langkah 5: Tampilkan Data Berfase Waktu
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Menampilkan informasi yang relevan tentang setiap entri data bertahap
    }
}
```
Terakhir, tampilkan data fase waktu untuk setiap tugas.
#
## Kesimpulan
Menangani data bertahap waktu secara efektif di Aspose.Tasks membuka kemungkinan baru untuk perencanaan proyek terperinci dan manajemen sumber daya. Dengan mengikuti panduan langkah demi langkah ini, Anda telah mempelajari cara memanipulasi data bertahap untuk memenuhi kebutuhan spesifik proyek Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan alat manajemen proyek lainnya?
Aspose.Tasks terutama dirancang untuk pengembangan .NET. Namun, fungsinya dapat melengkapi berbagai alat manajemen proyek.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?
 Ya, Anda dapat menjelajahi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan masyarakat.
### Apa yang dimaksud dengan izin sementara, dan bagaimana cara memperolehnya?
 Pelajari tentang lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk .NET?
 Lihat secara komprehensif[dokumentasi](https://reference.aspose.com/tasks/net/) untuk informasi rinci.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
