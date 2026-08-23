---
date: 2026-03-21
description: Pelajari cara mengelola periode ketersediaan sumber daya dan mencapai
  ketersediaan sumber daya proyek yang efektif dengan Aspose.Tasks untuk .NET. Panduan
  langkah demi langkah ini menunjukkan cara menambah, memperbarui, dan menghapus periode
  ketersediaan.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ketersediaan Sumber Daya Proyek – Mengelola Periode Ketersediaan di Aspose.Tasks
url: /id/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ketersediaan Sumber Daya Proyek: Kumpulan Periode Ketersediaan di Aspose.Tasks

Mengelola **ketersediaan sumber daya proyek** merupakan bagian inti dari perencanaan proyek yang berhasil. Pada tutorial ini Anda akan mempelajari **cara mengelola ketersediaan** untuk sumber daya menggunakan API Aspose.Tasks untuk .NET, langkah demi langkah, mulai dari memuat proyek hingga menyalin periode antar sumber daya.

## Jawaban Cepat
- **Apa kelas utama untuk periode ketersediaan?** `AvailabilityPeriod` di namespace `Aspose.Tasks`.  
- **Apakah saya dapat menghapus periode yang ada?** Ya, panggil `resource.AvailabilityPeriods.Clear()`.  
- **Bagaimana cara menambahkan periode baru?** Buat objek `AvailabilityPeriod` dan gunakan `Add` atau `Insert`.  
- **Apakah memungkinkan menyalin periode ke sumber daya lain?** Tentu – gunakan `CopyTo` lalu tambahkan setiap item ke sumber daya target.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Ya, lisensi komersial Aspose.Tasks diperlukan untuk penyebaran non‑trial.

## Apa itu ketersediaan sumber daya proyek?
Ketersediaan sumber daya proyek mendefinisikan tanggal dan unit (persentase kapasitas) ketika sebuah sumber daya dapat ditugaskan ke tugas. Dengan mengontrol periode ini Anda mencegah kelebihan beban dan meningkatkan akurasi jadwal.

## Mengapa menggunakan Aspose.Tasks untuk mengelola periode ketersediaan?
- **Integrasi .NET penuh** – tanpa interop COM, kode murni yang dikelola.  
- **Kontrol detail** – atur tanggal mulai/selesai yang tepat serta unit fraksional.  
- **Penyalinan mudah** – pindahkan data ketersediaan antar sumber daya tanpa parsing manual.  
- **Dioptimalkan untuk performa** – bekerja dengan file MPP besar secara efisien.

## Prasyarat
1. **Visual Studio** – versi terbaru apa saja (2019, 2022, atau lebih baru).  
2. **Aspose.Tasks untuk .NET** – unduh dari [here](https://releases.aspose.com/tasks/net/).  
3. **Pengetahuan dasar C#** – Anda harus nyaman dengan kelas, koleksi, dan LINQ.

## Impor Namespace

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Kami mengimpor namespace inti Aspose.Tasks bersama dengan koleksi standar .NET yang akan dibutuhkan nanti.

## Langkah 1: Inisialisasi Proyek dan Sumber Daya

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Di sini kami memuat file MPP yang sudah ada dan mengambil sumber daya yang ketersediaannya ingin diedit (ID = 1).

## Langkah 2: Hapus Periode Ketersediaan yang Ada

```csharp
resource.AvailabilityPeriods.Clear();
```

Menghapus menghilangkan semua periode yang sebelumnya didefinisikan, memberi kita kanvas bersih.

## Langkah 3: Tambahkan Periode Ketersediaan

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Kami mengambil koleksi objek `AvailabilityPeriod` (asumsi helper `GetPeriods` telah didefinisikan di tempat lain) dan menambahkan masing‑masing, memeriksa bahwa koleksi dapat ditulisi.

## Langkah 4: Sisipkan Periode Ketersediaan Baru

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Ini membuat periode khusus untuk tahun 2013 dan menyisipkannya pada posisi 1 (slot kedua) jika belum ada.

## Langkah 5: Tampilkan Periode Ketersediaan

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Dump cepat ke konsol menampilkan total jumlah dan detail tiap periode – berguna untuk debugging atau verifikasi.

## Langkah 6: Salin Periode Ketersediaan ke Sumber Daya Lain

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Kami menyalin seluruh koleksi ke dalam array, menghapus periode sumber daya target, lalu mengisinya kembali. Ini memperlihatkan cara menduplikasi data ketersediaan antar sumber daya.

## Langkah 7: Perbarui dan Hapus Periode Ketersediaan

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Di sini kami menyesuaikan `AvailableUnits` untuk periode sebelum terakhir dan kemudian menghapus periode 2013 yang sebelumnya ditambahkan.

## Masalah Umum dan Solusinya
- **Error koleksi read‑only** – Pastikan proyek tidak dibuka dalam mode read‑only atau Anda telah memanggil `resource.AvailabilityPeriods.Clear()` sebelum menambahkan item baru.  
- **Periode tumpang tindih** – Aspose.Tasks tidak secara otomatis menggabungkan tumpang tindih; Anda mungkin perlu menulis logika khusus untuk mendeteksi dan menyelesaikannya.  
- **Format tanggal tidak tepat** – Selalu gunakan objek `DateTime`; parsing string dapat menimbulkan bug yang bergantung pada locale.

## Pertanyaan yang Sering Diajukan

**T: Apakah saya dapat menambahkan bidang khusus ke periode ketersediaan?**  
J: Tidak, periode ketersediaan di Aspose.Tasks untuk .NET tidak mendukung bidang khusus.

**T: Apakah periode ketersediaan terhubung dengan tugas tertentu?**  
J: Tidak, periode tersebut terkait dengan sumber daya dan mendefinisikan kapan sumber daya secara umum tersedia untuk tugas.

**T: Apakah saya dapat mengimpor periode ketersediaan dari sumber eksternal?**  
J: Ya, Anda dapat mengimpor periode dari CSV, XML, atau basis data dengan membuat objek `AvailabilityPeriod` dan menambahkannya ke koleksi.

**T: Bagaimana cara menangani periode ketersediaan yang tumpang tindih?**  
J: Tumpang tindih tidak diselesaikan secara otomatis; Anda perlu mengimplementasikan validasi khusus untuk menggabungkan atau menolak periode yang konflik.

**T: Apakah ada batas jumlah periode ketersediaan yang dapat dimiliki sebuah sumber daya?**  
J: Tidak ada batas yang dikodekan secara keras, tetapi koleksi yang sangat besar dapat memengaruhi performa; pertimbangkan untuk mengkonsolidasikan periode bila memungkinkan.

## Kesimpulan

Dalam panduan ini kami membahas semua yang perlu Anda ketahui untuk mengelola **ketersediaan sumber daya proyek** dengan Aspose.Tasks untuk .NET—dari inisialisasi proyek dan penghapusan data lama, hingga penambahan, penyisipan, penyalinan, pembaruan, dan penghapusan periode ketersediaan. Menguasai langkah‑langkah ini membantu Anda menjaga kalender sumber daya tetap akurat dan jadwal proyek tetap realistis.

---

**Terakhir Diperbarui:** 2026-03-21  
**Diuji Dengan:** Aspose.Tasks untuk .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}