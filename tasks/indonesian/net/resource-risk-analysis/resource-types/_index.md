---
title: Jenis Sumber Daya di Aspose.Tugas
linktitle: Jenis Sumber Daya di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara bekerja dengan berbagai jenis sumber daya di Aspose.Tasks untuk .NET, termasuk sumber daya pekerjaan, material, dan biaya, melalui tutorial langkah demi langkah.
weight: 14
url: /id/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jenis Sumber Daya di Aspose.Tugas

## Perkenalan
Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram. Baik Anda mengelola tugas, sumber daya, atau jadwal, Aspose.Tasks menyederhanakan proses dengan menyediakan serangkaian API yang komprehensif. Dalam tutorial ini, kami akan mempelajari berbagai jenis sumber daya yang dapat Anda manfaatkan dalam proyek Anda menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Visual Studio: Instal Visual Studio, lingkungan pengembangan terintegrasi (IDE) yang kuat untuk pengembangan .NET.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengetahuan Dasar C#: Biasakan diri Anda dengan C#, bahasa pemrograman yang digunakan untuk pengembangan .NET.

## Impor Namespace
Pertama, mari impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Tasks untuk .NET:
```csharp
    
```

## Langkah 1: Buat instance Proyek baru
```csharp
var project = new Project();
```
Baris ini menginisialisasi objek Project baru, yang berfungsi sebagai wadah untuk semua data dan operasi terkait proyek.
## Langkah 2: Tambahkan Sumber Daya Kerja
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Di sini, kita membuat sumber daya kerja baru bernama "Sumber daya kerja" dan menentukan tipenya sebagai ResourceType.Work.
## Langkah 3: Tambahkan Sumber Daya Material
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Langkah ini menambahkan sumber daya material bernama "Sumber daya material" dengan tipenya diatur ke ResourceType.Material. Selain itu, kami menetapkan label bahan sebagai "kg" untuk menunjukkan satuan pengukuran.
## Langkah 4: Tambahkan Sumber Daya Biaya
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Terakhir, kami menambahkan sumber daya biaya bernama "Sumber daya biaya" dan menetapkan jenisnya sebagai ResourceType.Cost. Selain itu, kami menetapkan nilai biaya menjadi 59,99, yang mewakili nilai moneter yang terkait dengan sumber daya ini.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara bekerja dengan berbagai jenis sumber daya di Aspose.Tasks untuk .NET, termasuk sumber daya pekerjaan, material, dan biaya. Dengan mengikuti panduan langkah demi langkah, Anda dapat mengelola sumber daya dalam proyek Anda secara terprogram secara efektif.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks untuk .NET dengan format perangkat lunak manajemen proyek lainnya?
J: Ya, Aspose.Tasks mendukung berbagai format, termasuk Microsoft Project (MPP), Primavera P6, dan banyak lagi.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk .NET?
 A: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Bagaimana saya bisa mendapatkan dukungan teknis untuk Aspose.Tasks untuk .NET?
 J: Anda dapat mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk bantuan teknis.
### T: Bisakah saya membeli lisensi sementara Aspose.Tasks untuk .NET?
 J: Ya, Anda dapat membeli lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Apakah Aspose.Tasks untuk .NET menyediakan dokumentasi untuk referensi?
 A: Ya, Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
