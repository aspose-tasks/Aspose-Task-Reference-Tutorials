---
title: Statistik untuk Item Risiko di Aspose.Tasks
linktitle: Statistik untuk Item Risiko di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Buka kekuatan analisis risiko dalam file MS Project menggunakan Aspose.Tasks untuk .NET. Dapatkan wawasan, mitigasi ketidakpastian, dan dorong kesuksesan proyek dengan mudah.
type: docs
weight: 21
url: /id/net/resource-risk-analysis/risk-item-statistics/
---
## Perkenalan
Apakah Anda ingin meningkatkan kecakapan manajemen proyek Anda menggunakan Aspose.Tasks untuk .NET? Selidiki bidang analisis risiko dengan tutorial langkah demi langkah kami tentang cara mendapatkan statistik item risiko dalam file MS Project. Dengan memanfaatkan kemampuan Aspose.Tasks yang kuat, Anda dapat memperoleh wawasan berharga tentang ketidakpastian proyek dan membuat keputusan yang tepat untuk memitigasi risiko secara efektif.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.Tasks untuk dokumentasi .NET](https://reference.aspose.com/tasks/net/). Pustaka ini membekali Anda dengan alat canggih untuk memanipulasi file MS Project secara terprogram.
2. Lingkungan Pengembangan .NET: Siapkan lingkungan pengembangan .NET Anda, termasuk Visual Studio atau IDE lain pilihan Anda, untuk memfasilitasi integrasi Aspose.Tasks ke dalam proyek Anda.

## Impor Namespace
Gabungkan namespace yang diperlukan ke dalam proyek Anda untuk memanfaatkan fungsionalitas Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Langkah 1: Tentukan Direktori Data
```csharp
String DataDir = "Your Document Directory";
```
 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur ke direktori dokumen tempat file MS Project Anda berada.
## Langkah 2: Konfigurasikan Pengaturan Analisis Risiko
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Sesuaikan`IterationsCount`parameter berdasarkan kebutuhan proyek Anda untuk mengontrol ketepatan analisis risiko.
## Langkah 3: Muat File Proyek MS
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Muat file MS Project yang diinginkan ke dalam`project` objek untuk dianalisis lebih lanjut.
## Langkah 4: Tentukan Tugas dan Inisialisasi Pola Risiko
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Tentukan tugas untuk analisis risiko dan konfigurasikan pola risiko dengan parameter yang sesuai seperti jenis distribusi, durasi optimis dan pesimistis, dan tingkat kepercayaan.
## Langkah 5: Analisis Risiko Proyek
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Memulai proses analisis risiko menggunakan pengaturan yang ditentukan dan data proyek.
## Langkah 6: Ambil dan Tampilkan Statistik
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Ambil dan tampilkan berbagai metrik statistik yang terkait dengan item risiko dalam file MS Project, termasuk nilai yang diharapkan, deviasi standar, persentil, nilai minimum, dan maksimum.

## Kesimpulan
Kesimpulannya, menguasai analisis risiko dalam file MS Project menggunakan Aspose.Tasks untuk .NET membuka banyak kemungkinan bagi manajer proyek dan pemangku kepentingan. Dengan mengikuti tutorial komprehensif kami, Anda dapat melewati ketidakpastian dengan percaya diri, memastikan hasil proyek yang sukses.
## FAQ
### Bisakah saya mengintegrasikan Aspose.Tasks dengan perpustakaan .NET lainnya untuk fungsionalitas yang diperluas?
Sangat! Aspose.Tasks terintegrasi secara mulus dengan berbagai pustaka .NET, memungkinkan Anda memperkuat kemampuannya sesuai dengan kebutuhan proyek Anda.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 Ya, Anda dapat menjelajahi fitur Aspose.Tasks dengan mengakses[uji coba gratis](https://releases.aspose.com/) tersedia di situs web kami.
### Seberapa sering pembaruan dan penyempurnaan dirilis untuk Aspose.Tasks?
Kami berusaha untuk terus meningkatkan Aspose.Tasks dengan merilis pembaruan dan penyempurnaan secara berkala, memastikan bahwa Anda selalu memiliki akses ke fitur dan pengoptimalan terbaru.
### Bisakah saya mendapatkan dukungan teknis untuk Aspose.Tasks?
Tentu! Tim dukungan kami yang berdedikasi tersedia di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk membantu Anda dengan pertanyaan atau tantangan apa pun yang mungkin Anda temui selama perjalanan penerapan Anda.
### Apakah Anda menawarkan lisensi sementara untuk proyek jangka pendek?
 Ya, jika Anda memerlukan Aspose.Tasks untuk proyek jangka pendek, Anda dapat memanfaatkan kemudahan kami[izin sementara](https://purchase.aspose.com/temporary-license/) pilihan untuk memenuhi kebutuhan lisensi Anda tanpa komitmen jangka panjang.