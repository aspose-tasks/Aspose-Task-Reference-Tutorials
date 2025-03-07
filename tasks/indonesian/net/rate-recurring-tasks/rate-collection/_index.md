---
title: Kuasai Tarif Proyek MS dengan Aspose.Tasks
linktitle: Pengumpulan Tarif di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola tarif dalam file MS Project menggunakan Aspose.Tasks untuk .NET. Tutorial langkah demi langkah untuk pengelolaan sumber daya yang efektif.
weight: 11
url: /id/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kuasai Tarif Proyek MS dengan Aspose.Tasks

## Perkenalan
Selamat datang di tutorial kami tentang mengelola tarif di MS Project menggunakan Aspose.Tasks untuk .NET! Dalam panduan ini, kami akan memandu Anda melalui proses bekerja dengan tarif di file MS Project Anda menggunakan Aspose.Tasks. Baik Anda seorang pengembang berpengalaman atau baru memulai pengembangan .NET, tutorial ini akan memberi Anda petunjuk langkah demi langkah untuk menangani tarif dalam proyek Anda secara efektif.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:
### 1. Visual Studio Terpasang
Pastikan Anda telah menginstal Visual Studio di sistem Anda. Anda dapat mendownloadnya dari situs web jika Anda belum melakukannya.
### 2. Aspose.Tugas untuk .NET
 Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
### 3. Pengetahuan Dasar C# dan .NET
Biasakan diri Anda dengan bahasa pemrograman C# dan dasar-dasar kerangka .NET untuk lebih memahami contoh kode yang diberikan dalam tutorial ini.
## Impor Namespace
Dalam proyek C# Anda, impor namespace yang diperlukan untuk menggunakan fungsionalitas Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah:
## Langkah 1: Muat File Proyek MS
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Di sini, kami membuat yang baru`Project` objek dengan memuat file MS Project yang ada.
## Langkah 2: Tambahkan Sumber Daya dan Tetapkan Pekerjaan dan Tarif
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Kami menambahkan sumber daya baru ke proyek, menetapkan jenisnya sebagai pekerjaan, jumlah pekerjaan, dan tarif standar.
## Langkah 3: Tambahkan Tarif ke Sumber Daya
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Kami menambahkan tarif ke sumber daya dengan menentukan tanggal mulai dan berakhir, tarif standar, dan format tarif.
## Langkah 4: Informasi Tarif Cetak
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Langkah ini mencetak informasi tentang tarif yang terkait dengan sumber daya.
## Langkah 5: Perbarui Tarif
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Kami memperbarui tanggal akhir tarif tertentu.
## Langkah 6: Hapus Tarif
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Langkah ini menghapus semua tarif jenis tertentu.
## Langkah 7: Ulangi Tarif yang Tersisa
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Terakhir, kami mengulangi tarif yang tersisa setelah penghapusan.
## Kesimpulan
Kesimpulannya, tutorial ini memberi Anda panduan komprehensif tentang mengelola tarif dalam file MS Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti petunjuk langkah demi langkah yang diuraikan dalam tutorial ini, Anda dapat menangani tarif dalam proyek Anda secara efisien, memastikan pengelolaan sumber daya yang akurat.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan perangkat lunak manajemen proyek lainnya?
J: Ya, Aspose.Tasks untuk .NET mendukung integrasi dengan berbagai perangkat lunak manajemen proyek, termasuk MS Project, Primavera, dan banyak lagi.
### T: Apakah Aspose.Tasks untuk .NET kompatibel dengan versi file MS Project yang berbeda?
J: Tentu saja, Aspose.Tasks untuk .NET mendukung bekerja dengan file MS Project dari versi berbeda, memastikan fleksibilitas dan kompatibilitas.
### T: Apakah Aspose.Tasks untuk .NET menawarkan dokumentasi dan dukungan?
 J: Ya, Anda dapat menemukan dokumentasi komprehensif dan akses ke forum dukungan di Aspose.Tasks[situs web](https://reference.aspose.com/tasks/net/).
### T: Dapatkah saya mencoba Aspose.Tasks untuk .NET sebelum membeli?
J: Ya, Anda dapat memanfaatkan uji coba gratis Aspose.Tasks untuk .NET untuk mengevaluasi fitur dan kompatibilitasnya dengan kebutuhan Anda.
### T: Bagaimana cara membeli lisensi Aspose.Tasks untuk .NET?
 J: Anda dapat membeli lisensi Aspose.Tasks untuk .NET dari[situs web](https://purchase.aspose.com/temporary-license/)yang memberikan opsi lisensi fleksibel sesuai kebutuhan Anda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
