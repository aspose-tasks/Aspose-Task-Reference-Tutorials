---
date: 2026-04-06
description: Pelajari cara menghapus semua baseline dan mengelola koleksi baseline
  di Aspose.Tasks untuk .NET dengan contoh kode langkah demi langkah.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Hapus Semua Baseline dengan Koleksi Baseline Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hapus Semua Baseline dengan Koleksi Baseline Aspose.Tasks
url: /id/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hapus Semua Baseline dengan Koleksi Baseline Aspose.Tasks

## Pendahuluan

Aspose.Tasks untuk .NET memungkinkan Anda memanipulasi file Microsoft Project langsung dari aplikasi .NET Anda. Salah satu fitur paling kuat adalah kemampuan untuk **menghapus semua baseline** untuk sebuah sumber daya, yang penting ketika Anda perlu mengatur ulang data pelacakan proyek atau memulai periode baseline baru. Dalam tutorial ini kami akan membimbing Anda melalui seluruh proses—dari memuat file proyek hingga menghapus setiap baseline yang terlampir pada sumber daya tertentu—dengan penjelasan yang jelas, bersahabat, dan kode C# yang siap dijalankan.

## Jawaban Cepat
- **Apa yang dilakukan “delete all baselines”?** Ini menghapus setiap catatan baseline yang disimpan untuk sumber daya yang dipilih, membersihkan data biaya dan pekerjaan historis.  
- **Mengapa saya membutuhkan ini?** Untuk mengatur ulang pelacakan setelah perubahan proyek besar atau ketika baseline asli tidak lagi relevan.  
- **Perpustakaan mana yang menyediakan kemampuan ini?** Aspose.Tasks for .NET.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia.  
- **Apakah kode kompatibel dengan .NET 6+?** Ya, API bekerja dengan .NET Framework 4.5+, .NET Core 3.1+, dan .NET 5/6.

## Apa Itu Baseline dan Mengapa Menghapus Semua Baseline?

Baseline menangkap rencana asli untuk biaya, pekerjaan, dan jadwal pada titik waktu tertentu. Sepanjang siklus hidup proyek Anda mungkin membuat beberapa baseline (Baseline 1, Baseline 2, dll.) untuk membandingkan kemajuan aktual dengan snapshot perencanaan yang berbeda. Namun, ada skenario—seperti perubahan ruang lingkup proyek atau memulai kembali—di mana mempertahankan baseline historis menjadi membingungkan. Menghapus semua baseline memberi Anda lembar bersih, memungkinkan Anda menetapkan baseline baru yang mencerminkan realitas saat ini.

## Prasyarat

1. **Visual Studio** – edisi terbaru apa pun (Community, Professional, atau Enterprise).  
2. **Aspose.Tasks for .NET** – unduh dari [tautan unduhan](https://releases.aspose.com/tasks/net/).  
3. **Pengetahuan dasar C#** – Anda harus nyaman dengan variabel, loop, dan output konsol.  
4. **File Microsoft Project** (`.mpp`) – file contoh bernama *WorkWithBaselineCollection.mpp* akan digunakan dalam contoh.

## Impor Namespace

Pertama, bawa namespace yang diperlukan ke dalam ruang lingkup sehingga kompilator mengetahui di mana menemukan kelas yang akan kami gunakan.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Langkah 1: Muat File Proyek

Kami memulai dengan memuat file Project yang ada. Sesuaikan `DataDir` untuk menunjuk ke folder yang berisi file `.mpp` Anda.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Langkah 2: Dapatkan Sumber Daya Target

Untuk demonstrasi kami mengambil sumber daya dengan UID = 1. Dalam skenario dunia nyata Anda akan menemukan sumber daya berdasarkan nama atau pengidentifikasi lain.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Langkah 3: Tampilkan Informasi Baseline yang Ada

Sebelum menghapus apa pun, berguna untuk melihat baseline apa yang saat ini terlampir pada sumber daya. Ini memberi Anda keyakinan bahwa Anda menghapus data yang tepat.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Langkah 4: Iterasi Melalui Semua Baseline

Di sini kami melakukan loop melalui setiap baseline, mencetak metrik kunci seperti biaya, pekerjaan, dan nilai yang diperoleh (BCWP/BCWS). Langkah ini opsional tetapi berguna untuk tujuan pencatatan atau audit.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Hapus Semua Baseline

Sekarang kami melakukan aksi inti: **menghapus semua baseline** untuk sumber daya yang dipilih. Kami pertama-tama menyalin koleksi ke dalam daftar untuk menghindari memodifikasi koleksi saat iterasi, kemudian menghapus setiap baseline satu per satu.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Setelah blok ini dijalankan, `resource.Baselines.Count` akan menjadi `0`, mengonfirmasi bahwa semua catatan baseline telah dihapus.

## Masalah Umum dan Tips

- **NullReferenceException** – Pastikan file proyek benar‑benar berisi sumber daya yang Anda targetkan; jika tidak, `GetByUid` akan mengembalikan `null`.  
- **Lisensi** – Tanpa lisensi Aspose.Tasks yang valid Anda akan melihat watermark pada output dan fungsionalitas terbatas.  
- **Kinerja** – Untuk proyek yang sangat besar, pertimbangkan iterasi dengan `Parallel.ForEach` untuk mempercepat proses penghapusan, tetapi ingat bahwa koleksi dasar tidak thread‑safe.

## Pertanyaan yang Sering Diajukan

**Q: Dapatkah Aspose.Tasks menangani file proyek besar?**  
A: Ya, Aspose.Tasks dioptimalkan untuk kinerja dan dapat memproses file `.mpp` multi‑gigabyte secara efisien.

**Q: Apakah perpustakaan ini kompatibel dengan semua versi Microsoft Project?**  
A: Aspose.Tasks mendukung Project 2000 hingga Project 2024, mencakup format `.mpp` lama serta file berbasis XML yang lebih baru.

**Q: Bisakah saya menyesuaikan baseline sebelum menghapusnya?**  
A: Tentu saja. Anda dapat membaca atau memodifikasi properti baseline apa pun (biaya, pekerjaan, tanggal) sebelum memutuskan untuk menghapusnya.

**Q: Apakah Aspose.Tasks bekerja di platform cloud?**  
A: Ya, API berjalan di lingkungan apa pun yang kompatibel dengan .NET, termasuk Azure App Service, AWS Lambda (via .NET Core), dan kontainer Docker.

**Q: Di mana saya dapat bertanya kepada komunitas untuk bantuan?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk terhubung dengan pengembang lain dan staf Aspose.

## Kesimpulan

Dalam panduan ini kami menunjukkan cara **menghapus semua baseline** dari sebuah sumber daya menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti kode langkah‑demi‑langkah, Anda dapat mengatur ulang data baseline, menjaga pelacakan proyek tetap bersih, dan menyiapkan jadwal Anda untuk siklus perencanaan baru. Jangan ragu untuk bereksperimen dengan membuat baseline baru setelah penghapusan untuk melihat bagaimana perpustakaan memperbarui file proyek.

---

**Terakhir Diperbarui:** 2026-04-06  
**Diuji Dengan:** Aspose.Tasks 24.12 for .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}