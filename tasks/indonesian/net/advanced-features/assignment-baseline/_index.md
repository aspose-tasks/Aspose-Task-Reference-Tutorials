---
title: Mengelola Baseline Penugasan di Aspose.Tasks
linktitle: Mengelola Baseline Penugasan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola garis dasar penugasan secara efisien dengan Aspose.Tasks untuk .NET, memastikan pelacakan kemajuan dan kinerja proyek secara akurat.
weight: 14
url: /id/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengelola Baseline Penugasan di Aspose.Tasks

## Perkenalan

Saat mengerjakan tugas manajemen proyek, mengelola garis dasar penugasan sangat penting untuk melacak kemajuan secara akurat. Aspose.Tasks untuk .NET menyediakan seperangkat alat komprehensif untuk menangani garis dasar penugasan secara efisien. Dalam tutorial ini, kita akan mempelajari proses pengelolaan garis dasar penugasan langkah demi langkah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Pengetahuan dasar bahasa pemrograman C#.
- Visual Studio diinstal pada sistem Anda.
- Aspose.Tasks untuk perpustakaan .NET ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
- Akses ke file proyek dalam format MPP.

## Impor Namespace

Untuk mulai bekerja dengan Aspose.Tasks, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Tambahkan namespace berikut di awal file C# Anda:

```csharp
using Aspose.Tasks;
using System;


```

## Langkah 1: Muat Proyek dan Tetapkan Garis Dasar

 Pertama, muat file proyek menggunakan`Project` kelas dari Aspose.Tasks. Kemudian, tetapkan tipe dasar untuk proyek tersebut menggunakan`SetBaseline` metode.

```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Langkah 2: Baca Informasi Dasar Penugasan

Ulangi setiap penetapan sumber daya dalam proyek dan ambil informasi dasar untuk setiap penetapan.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Langkah 3: Periksa Kesetaraan Dasar

Bandingkan informasi dasar untuk tugas yang berbeda menggunakan berbagai metode perbandingan yang disediakan oleh Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Periksa kesetaraan dasar
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Periksa perbandingan dasar
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Tampilkan kode hash dasar
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Kesimpulan

Mengelola garis dasar penugasan merupakan bagian integral dari manajemen proyek, memungkinkan pelacakan kemajuan dan kinerja secara akurat. Dengan Aspose.Tasks untuk .NET, penanganan garis dasar penugasan menjadi efisien dan efisien, memberikan pengembang alat canggih untuk meningkatkan alur kerja manajemen proyek.

## FAQ

### Q1: Bisakah Aspose.Tasks menangani beberapa garis dasar untuk satu tugas?

A1: Ya, Aspose.Tasks mendukung beberapa garis dasar untuk setiap tugas, memungkinkan pelacakan kemajuan proyek secara komprehensif dari waktu ke waktu.

### Q2: Apakah Aspose.Tasks kompatibel dengan berbagai format file proyek selain MPP?

A2: Ya, Aspose.Tasks mendukung berbagai format file proyek, termasuk XML, MPX, dan MPP, memastikan kompatibilitas dengan berbagai alat manajemen proyek.

### Q3: Dapatkah saya mengubah informasi dasar secara terprogram menggunakan Aspose.Tasks?

A3: Tentu saja, Aspose.Tasks menyediakan API ekstensif untuk mengubah informasi dasar secara dinamis sesuai dengan kebutuhan proyek, menawarkan fleksibilitas dan kontrol atas proses manajemen proyek.

### Q4: Apakah Aspose.Tasks menawarkan dokumentasi dan sumber daya dukungan untuk pengembang?

A4: Ya, pengembang dapat mengakses dokumentasi, tutorial, dan forum komprehensif di situs web Aspose.Tasks, sehingga memfasilitasi integrasi dan pemecahan masalah yang lancar.

### Q5: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?

 A5: Ya, pengembang dapat memperoleh versi uji coba gratis Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/), memungkinkan mereka mengevaluasi fitur dan kemampuannya sebelum membuat keputusan pembelian.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
