---
title: Kumpulkan Statistik Item Risiko Proyek MS di Aspose.Tasks
linktitle: Kumpulan Statistik Item Risiko di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengumpulkan statistik item risiko dari file MS Project menggunakan Aspose.Tasks untuk .NET. Tingkatkan kemampuan manajemen proyek Anda.
type: docs
weight: 22
url: /id/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengumpulkan statistik item risiko dari file MS Project menggunakan Aspose.Tasks untuk .NET. Perpustakaan ini menyediakan fungsionalitas canggih untuk menganalisis data proyek, termasuk penilaian risiko dan analisis statistik.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks. Anda bisa mendapatkannya dari[Unduh Halaman](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan untuk pemrograman .NET.

## Impor Namespace
Sebelum Anda memulai coding, pastikan untuk mengimpor namespace yang diperlukan dalam proyek Anda:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Langkah 1: Muat File Proyek
Pertama, Anda perlu memuat file MS Project ke dalam aplikasi Anda. Inilah cara Anda mencapainya:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Langkah 2: Tentukan Pengaturan Analisis Risiko
Inisialisasi pengaturan analisis risiko, termasuk jumlah iterasi, seperti yang ditunjukkan di bawah ini:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Langkah 3: Inisialisasi Pola Risiko
Tetapkan pola risiko untuk analisis, tentukan jenis distribusi, persentase optimis dan pesimistis, dan tingkat kepercayaan:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Langkah 4: Lakukan Analisis Risiko
 Buat instance`RiskAnalyzer` kelas dan menganalisis proyek:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Langkah 5: Ambil Statistik
Ambil statistik item risiko, seperti penyelesaian awal, dari hasil analisis:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Langkah 6: Cetak Statistik
Ulangi statistik dan cetak detailnya:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Cetak statistik relevan lainnya...
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara memanfaatkan Aspose.Tasks untuk .NET guna mengumpulkan statistik item risiko dari file MS Project. Dengan mengikuti langkah-langkah ini, Anda dapat menganalisis data proyek secara efektif dan menilai potensi risiko, sehingga membantu pengambilan keputusan dan manajemen proyek yang lebih baik.

## FAQ
### T: Bisakah Aspose.Tasks menangani file MS Project yang besar?
J: Ya, Aspose.Tasks mampu menangani file MS Project berukuran besar secara efisien, menawarkan kinerja dan skalabilitas yang andal.
### T: Apakah Aspose.Tasks mendukung format file proyek lain selain .mpp?
J: Ya, Aspose.Tasks mendukung berbagai format file proyek, termasuk XML dan MPT.
### T: Apakah Aspose.Tasks cocok untuk aplikasi manajemen proyek tingkat perusahaan?
J: Tentu saja, Aspose.Tasks dirancang untuk memenuhi tuntutan aplikasi manajemen proyek tingkat perusahaan, menyediakan fitur canggih dan dokumentasi ekstensif.
### T: Dapatkah saya menyesuaikan pengaturan analisis risiko di Aspose.Tasks?
J: Ya, Aspose.Tasks menawarkan fleksibilitas dalam mengonfigurasi pengaturan analisis risiko agar sesuai dengan kebutuhan dan skenario proyek spesifik Anda.
### T: Apakah dukungan teknis tersedia untuk pengguna Aspose.Tasks?
 J: Ya, pengguna Aspose.Tasks dapat mengakses dukungan teknis melalui Aspose.[forum](https://forum.aspose.com/c/tasks/15), tempat mereka dapat mengajukan pertanyaan, melaporkan masalah, dan berinteraksi dengan komunitas.