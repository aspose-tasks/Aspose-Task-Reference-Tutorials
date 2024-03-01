---
title: Mengelola Pengumpulan Sumber Daya Proyek di Aspose.Tasks
linktitle: Mengelola Pengumpulan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola koleksi sumber daya Microsoft Project secara efisien di .NET menggunakan Aspose.Tasks API. Meningkatkan produktivitas dan fleksibilitas.
type: docs
weight: 13
url: /id/net/resource-risk-analysis/managing-resource-collection/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola koleksi sumber daya Microsoft Project secara efektif menggunakan Aspose.Tasks untuk .NET. Aspose.Tasks adalah API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram, memungkinkan integrasi dan manipulasi data proyek tanpa hambatan.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan tentang C# dan .NET Framework: Tutorial ini mengasumsikan keakraban dengan bahasa pemrograman C# dan .NET Framework.
2. Pemasangan Aspose.Tasks untuk .NET: Pastikan Anda telah menginstal Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengaturan Lingkungan Pengembangan: Siapkan lingkungan pengembangan Anda dengan Visual Studio atau IDE pilihan lainnya.

## Impor Namespace
Sebelum kita mulai, impor namespace yang diperlukan untuk mengakses fungsi Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Langkah 1: Muat File Proyek
Pertama, muat file Microsoft Project ke objek proyek Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Langkah 2: Tambahkan Sumber Daya Kosong
Selanjutnya, mari tambahkan sumber daya kosong ke proyek:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Langkah 3: Tambahkan Sumber Daya dengan Nama
Sekarang, tambahkan sumber daya dengan nama tertentu ke proyek:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Langkah 4: Tambahkan Sumber Daya Sebelum Sumber Daya Lain
Tambahkan sumber daya dengan nama tertentu sebelum sumber daya lain berdasarkan ID-nya:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Langkah 5: Mengakses Sumber Daya berdasarkan ID atau UID
Anda dapat mengakses sumber daya berdasarkan ID atau UID-nya:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Langkah 6: Mencetak Informasi Sumber Daya
Cetak informasi tentang sumber daya proyek:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Langkah 7: Menghapus Sumber Daya
Hapus sumber daya dari proyek:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Kesimpulan
Mengelola koleksi sumber daya Microsoft Project menggunakan Aspose.Tasks untuk .NET memberi pengembang seperangkat alat canggih untuk menangani sumber daya proyek secara terprogram secara efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat memanipulasi sumber daya dalam proyek Anda dengan lancar, meningkatkan produktivitas dan fleksibilitas dalam tugas manajemen proyek.
## FAQ
### T: Bisakah Aspose.Tasks menangani file proyek berskala besar?

J: Ya, Aspose.Tasks dirancang untuk menangani file proyek berskala besar secara efisien, menawarkan kinerja dan keandalan tinggi.

### T: Apakah Aspose.Tasks kompatibel dengan versi Microsoft Project yang berbeda?

J: Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### T: Bisakah saya mengkustomisasi properti sumber daya menggunakan Aspose.Tasks?

J: Tentu saja, Aspose.Tasks memberikan kemampuan ekstensif untuk menyesuaikan properti sumber daya sesuai dengan kebutuhan proyek tertentu.

### T: Apakah Aspose.Tasks mendukung multi-threading untuk operasi bersamaan?

J: Ya, Aspose.Tasks mendukung multi-threading, memungkinkan operasi bersamaan pada data proyek untuk meningkatkan kinerja.

### T: Apakah dukungan teknis tersedia untuk pengguna Aspose.Tasks?

 J: Ya, pengguna Aspose.Tasks dapat mengakses dukungan teknis melalui forum[Di Sini](https://forum.aspose.com/c/tasks/15).