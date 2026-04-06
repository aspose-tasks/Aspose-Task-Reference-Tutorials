---
date: 2026-04-06
description: Pelajari cara menambahkan sumber daya ke proyek dan mengatur periode
  ketersediaan sumber daya menggunakan Aspose.Tasks untuk .NET. Panduan langkah demi
  langkah untuk mengelola kalender sumber daya.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Bekerja dengan Periode Ketersediaan di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Tambahkan Sumber Daya ke Proyek dan Atur Ketersediaan di Aspose.Tasks
url: /id/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Sumber Daya ke Proyek dan Atur Ketersediaan di Aspose.Tasks

## Pendahuluan

Dalam tutorial ini Anda akan belajar **cara menambahkan sumber daya ke proyek** dan kemudian menentukan periode ketersediaannya menggunakan perpustakaan Aspose.Tasks .NET. Mengelola kalender sumber daya penting untuk jadwal proyek yang realistis, dan langkah-langkah di bawah ini akan memandu Anda melalui seluruh proses—dari membuat instance proyek hingga mencetak detail setiap periode.

## Jawaban Cepat
- **Apa tujuan utama?** Menambahkan sumber daya ke proyek dan mengonfigurasi periode ketersediaannya.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk .NET.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi komersial diperlukan.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Waktu implementasi?** Biasanya kurang dari 15 menit untuk skenario dasar.

## Apa itu “menambahkan sumber daya ke proyek”?

Menambahkan sumber daya ke proyek membuat placeholder untuk orang, peralatan, atau material yang dapat ditugaskan ke tugas. Setelah sumber daya ada, Anda dapat **mengatur ketersediaan sumber daya**, mendefinisikan kalender kerja, dan membiarkan penjadwal menghormati batasan tersebut.

## Mengapa mengonfigurasi jadwal kerja dan periode ketersediaan?

- **Perencanaan akurat:** Tugas dijadwalkan hanya ketika sumber daya benar‑benar tersedia.  
- **Kontrol biaya:** Unit ketersediaan mencerminkan upaya paruh waktu, membantu Anda menghitung biaya tenaga kerja dengan tepat.  
- **Leveling sumber daya:** Mesin dapat secara otomatis menyeimbangkan over‑allocation ketika mengetahui kalender masing‑masing sumber daya.

## Prasyarat

1. Visual Studio (atau IDE kompatibel .NET apa pun).  
2. Aspose.Tasks untuk .NET – unduh dari [here](https://releases.aspose.com/tasks/net/).  
3. Pengetahuan dasar C#.

## Impor Namespace

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Cara menambahkan sumber daya ke proyek?

### Langkah 1: Buat instance `Project` baru

```csharp
var project = new Project();
```

Objek ini mewakili seluruh file proyek dalam memori.

### Langkah 2: Tambahkan sumber daya ke proyek

```csharp
var resource = project.Resources.Add("Work Resource");
```

Pemanggilan ini membuat **sumber daya** bernama *Work Resource* yang nanti dapat Anda lampirkan ke tugas.

### Langkah 3: Definisikan periode ketersediaan

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` adalah metode bantu (implementasi tidak ditampilkan) yang mengembalikan koleksi objek `AvailabilityPeriod`. Setiap periode menentukan tanggal mulai, tanggal selesai, dan unit (persentase upaya penuh‑waktu) sumber daya tersedia.

### Langkah 4: Tambahkan periode ke sumber daya

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Di sini kami **mengatur ketersediaan sumber daya** dengan melakukan loop melalui koleksi dan menambahkan setiap periode ke kalender sumber daya.

### Langkah 5: Tampilkan detail ketersediaan

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Output konsol memungkinkan Anda memverifikasi bahwa periode telah disimpan dengan benar.

## Kesalahan Umum & Tips

- **Presisi tanggal:** `AvailableFrom` dan `AvailableTo` adalah nilai `DateTime`; pastikan mereka diatur ke tengah malam jika Anda menginginkan periode sepanjang hari.  
- **Rentang unit:** Nilai yang valid adalah 0‑100 %; nilai di luar rentang ini akan memicu pengecualian.  
- **Periode yang tumpang tindih:** Periode yang tumpang tindih digabungkan secara otomatis, tetapi lebih jelas jika dipisahkan.

## Pertanyaan yang Sering Diajukan

### Q1: Bisakah saya menggunakan Aspose.Tasks untuk .NET dalam proyek komersial?
A1: Ya, Aspose.Tasks untuk .NET dapat digunakan dalam proyek komersial. Anda dapat membeli lisensi [here](https://purchase.aspose.com/buy).

### Q2: Apakah ada percobaan gratis untuk Aspose.Tasks untuk .NET?
A2: Ya, Anda dapat memperoleh percobaan gratis Aspose.Tasks untuk .NET [here](https://releases.aspose.com/).

### Q3: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk .NET?
A3: Anda dapat menemukan dokumentasi [here](https://reference.aspose.com/tasks/net/).

### Q4: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk .NET?
A4: Anda dapat mendapatkan dukungan dari forum komunitas [here](https://forum.aspose.com/c/tasks/15).

### Q5: Apakah Anda menawarkan lisensi sementara untuk Aspose.Tasks untuk .NET?
A5: Ya, lisensi sementara tersedia [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-04-06  
**Diuji Dengan:** Aspose.Tasks untuk .NET (rilisan stabil terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}