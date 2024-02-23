---
title: Menguasai Kriteria Filter Proyek MS dengan Aspose.Tasks
linktitle: Filter Kriteria di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menerapkan kriteria filter di MS Project menggunakan Aspose.Tasks untuk .NET. Tingkatkan efisiensi manajemen proyek dengan analisis data yang ditargetkan.
type: docs
weight: 18
url: /id/net/tasks-project-management/filter-criteria/
---
## Perkenalan
Di bidang manajemen proyek, Microsoft Project berdiri sebagai alat pendukung, menawarkan banyak fitur untuk membantu perencana dan manajer proyek. Di antara banyak fungsinya terdapat kemampuan untuk memfilter data proyek, memungkinkan pengguna untuk fokus pada aspek tertentu dari tugas proyek mereka. Namun, menguasai kemampuan pemfilteran ini bisa menjadi tugas yang sulit tanpa panduan yang tepat. Tutorial ini bertujuan untuk memperjelas proses dengan memberikan panduan langkah demi langkah tentang penerapan kriteria filtera di MS Project menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# diperlukan untuk memahami konsep yang dibahas dalam tutorial ini.
2.  Pemasangan Aspose.Tasks for .NET: Pastikan Anda telah menginstal Aspose.Tasks for .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/net/).
3. File Microsoft Project: Siapkan file Microsoft Project (misalnya Project2003.mpp), yang akan Anda gunakan untuk menerapkan kriteria filter.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan agar berfungsi dengan Aspose.Tasks untuk .NET. Ikuti langkah ini:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Langkah 1: Muat File Proyek
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Penjelasan: Baris kode ini menginisialisasi instance baru dari`Project` kelas dan memuat file Microsoft Project yang ditentukan oleh jalurnya.
## Langkah 2: Ambil Filter Tugas
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Penjelasan: Di sini, kami mengambil filter tugas dari proyek. Sesuaikan indeks (`[1]`) sesuai kebutuhan Anda untuk memilih filter yang diinginkan.
## Langkah 3: Tampilkan Baris Kriteria
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Penjelasan: Bagian ini mengulangi setiap baris kriteria filter dan menampilkan bidang, operasi, pengujian, dan nilainya (jika ada).
## Langkah 4: Kriteria Filter Cetak
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Penjelasan: Mencetak pengoperasian kriteria filter.
## Langkah 5: Tampilkan Detail Kriteria
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Penjelasan: Bagian ini mengambil dan menampilkan informasi mendetail tentang setiap baris kriteria, memberikan wawasan tentang konfigurasi filter.

## Kesimpulan
Menguasai kriteria filter di MS Project menggunakan Aspose.Tasks untuk .NET adalah keterampilan berharga yang dapat meningkatkan efisiensi manajemen proyek secara signifikan. Dengan mengikuti tutorial ini, Anda telah mempelajari cara memanipulasi kriteria filter secara terprogram, sehingga memberdayakan Anda untuk menyesuaikan tampilan proyek dengan kebutuhan spesifik Anda.
## FAQ
### T: Bisakah saya menerapkan beberapa filter secara bersamaan di MS Project?
J: Ya, Anda dapat menggabungkan beberapa filter untuk menyempurnakan data proyek Anda lebih lanjut.
### T: Apakah Aspose.Tasks mendukung file Microsoft Project versi lama?
J: Ya, Aspose.Tasks menyediakan kompatibilitas mundur, memungkinkan Anda bekerja dengan berbagai versi file Microsoft Project.
### T: Apakah Aspose.Tasks kompatibel dengan kerangka .NET lainnya?
J: Aspose.Tasks mendukung .NET Framework, .NET Core, dan .NET Standard, memastikan fleksibilitas di berbagai lingkungan pengembangan.
### T: Dapatkah saya menyesuaikan kriteria filter berdasarkan kondisi dinamis?
J: Tentu saja, Anda dapat menyesuaikan kriteria filter secara terprogram berdasarkan parameter dinamis, sehingga memungkinkan analisis data proyek adaptif.
### T: Di mana saya dapat mencari bantuan jika saya mengalami masalah dengan Aspose.Tasks?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk mencari dukungan dari komunitas atau langsung menghubungi dukungan Aspose.Tasks untuk bantuan yang dipersonalisasi.