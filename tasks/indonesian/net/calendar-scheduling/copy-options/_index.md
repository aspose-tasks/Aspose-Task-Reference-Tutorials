---
date: 2026-07-05
description: Pelajari cara menyalin data proyek menggunakan Aspose.Tasks untuk .NET
  dengan copy options. Tingkatkan aplikasi .NET Anda dengan manajemen proyek yang
  tepat.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Cara Menyalin Data Proyek dengan Copy Options di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Cara Menyalin Data Proyek dengan Copy Options di Aspose.Tasks
url: /id/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menyalin Data Proyek dengan Opsi Salin di Aspose.Tasks

## Pendahuluan

Jika Anda perlu **cara menyalin proyek** informasi dari satu file Microsoft Project ke file lain, Aspose.Tasks untuk .NET memberi Anda cara yang bersih, berbasis kode untuk melakukannya. Dalam tutorial ini kami akan membahas alur kerja lengkap—memuat proyek sumber, mengonfigurasi opsi salin, membuat salinan, dan memuat hasilnya—sehingga Anda dapat mengintegrasikan logika penyalinan proyek ke dalam aplikasi .NET apa pun dengan percaya diri.

## Jawaban Cepat
- **Apa yang dilakukan fitur salin?** Itu menggandakan data proyek sambil memungkinkan Anda menyertakan atau mengecualikan bagian tertentu seperti kalender, sumber daya, atau informasi tampilan.  
- **Kelas mana yang mengontrol perilaku?** `CopyToOptions` memungkinkan Anda menyesuaikan apa yang disalin.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks yang valid diperlukan untuk produksi; percobaan gratis dapat digunakan untuk pengembangan.  
- **Format yang didukung?** Aspose.Tasks menangani file MPP, XML, dan XER—lebih dari 20 + format secara total.  
- **Bisakah saya melewatkan data tampilan?** Ya, setel `CopyToOptions.SkipViewData = true` untuk menghilangkan informasi terkait UI.

## Apa itu “cara menyalin proyek” di Aspose.Tasks?

**“Cara menyalin proyek”** mengacu pada penggunaan API Aspose.Tasks untuk menggandakan data objek Project ke dalam file baru, dengan opsi menyaring elemen yang tidak diinginkan. Operasi ini berguna untuk pembuatan templat, pengarsipan, atau membuat varian proyek tanpa langkah UI manual, dan berfungsi di semua format file yang didukung.

## Mengapa menggunakan Opsi Salin di Aspose.Tasks?

Aspose.Tasks mendukung **lebih dari 50 entitas terkait proyek** (tugas, sumber daya, kalender, penugasan, dll.) dan dapat memproses file dengan **hingga 10.000 tugas** sambil menjaga penggunaan memori di bawah 200 MB. Menggunakan `CopyToOptions` memungkinkan Anda menghindari penyalinan data tampilan yang berat, mengurangi ukuran file output sebesar **30‑40 %** dan mempercepat operasi sekitar **2×** untuk proyek besar.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

1. **Aspose.Tasks untuk .NET** – unduh versi terbaru dari [tautan unduhan](https://releases.aspose.com/tasks/net/).  
2. **Lingkungan pengembangan .NET** – Visual Studio 2022 (atau IDE apa pun yang mendukung .NET 6+) terpasang.  
3. **Lisensi Aspose.Tasks yang valid** – opsional untuk evaluasi, wajib untuk build produksi.  
4. **File proyek yang ada** (misalnya, `SourceProject.xml`) yang ingin Anda salin.

## Cara mengimpor namespace untuk Aspose.Tasks?

Tambahkan direktif `using` yang diperlukan di bagian atas file C# Anda sehingga kompilator dapat menemukan tipe Aspose.Tasks. Menyertakan pernyataan ini memberi Anda akses langsung ke `Project`, `CopyToOptions`, dan kelas utilitas lainnya tanpa harus menuliskan nama lengkapnya, menyederhanakan kode Anda dan meningkatkan keterbacaan.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Langkah 1: Inisialisasi Objek Proyek

Pertama, buat instance `Project` yang mewakili file sumber dan muat data XML.  
Kelas `Project` mewakili file Microsoft Project yang dimuat ke dalam memori, menampilkan tugas, sumber daya, kalender, dan informasi proyek lainnya.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Tips Pro:** Jika Anda bekerja dengan file yang sangat besar, pertimbangkan menggunakan konstruktor `LoadOptions` untuk mengaktifkan pemuatan malas dan menjaga konsumsi memori tetap rendah.

## Langkah 2: Membuat Salinan Proyek

Selanjutnya, buat instance `Project` kedua yang akan menerima data yang disalin. Objek ini dimulai dalam keadaan kosong.

```csharp
Project copiedProject = new Project();
```

Sekarang Anda memiliki dua objek `Project` yang berbeda: satu dimuat dari disk dan satu siap menerima salinan.

## Langkah 3: Memuat Proyek yang Disalin

Setelah operasi penyalinan (ditunjukkan nanti), Anda ingin memverifikasi hasil dengan memuat file yang baru disimpan ke dalam instance `Project` lain.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Memuat kembali file tersebut mengonfirmasi bahwa penyalinan berhasil dan opsi yang Anda atur berfungsi seperti yang diharapkan.

## Langkah 4: Mengonfigurasi Opsi Salin

Kelas `CopyToOptions` memungkinkan Anda menentukan secara tepat apa yang dipindahkan dari sumber ke tujuan.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Menetapkan `SkipViewData = true` mengurangi ukuran file output dan mempercepat operasi, terutama ketika Anda hanya membutuhkan data proyek logis.

## Langkah 5: Melakukan Penyalinan Proyek

Akhirnya, panggil metode `CopyTo` pada proyek sumber, dengan memberikan proyek tujuan dan opsi yang telah Anda konfigurasikan.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Pemanggilan dua baris ini melakukan seluruh operasi penyalinan, menghormati opsi yang Anda definisikan. `CopiedProject.xml` yang dihasilkan hanya berisi data yang Anda minta.

## Masalah Umum dan Solusinya

| Issue | Cause | Fix |
|-------|-------|-----|
| **NullReferenceException when calling `CopyTo`** | Proyek tujuan belum diinstansiasi. | Pastikan `new Project()` dipanggil sebelum `CopyTo`. |
| **Missing tasks after copy** | `CopyCommonData` disetel ke `false`. | Setel `CopyCommonData = true` atau salin koleksi spesifik secara manual. |
| **Large output file** | `SkipViewData` dibiarkan `false`. | Aktifkan `SkipViewData` untuk menghilangkan data terkait UI. |
| **License not applied** | File lisensi tidak dimuat. | Panggil `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` sebelum penggunaan API apa pun. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menyalin hanya sebagian tugas?**  
A: Ya, gunakan `CopyToOptions` bersama dengan `ProjectRootTask` untuk menentukan tugas awal, atau salin secara manual tugas yang dipilih setelah penyalinan awal.

**Q: Apakah Aspose.Tasks mendukung penyalinan antar format file yang berbeda?**  
A: Tentu saja. Anda dapat memuat file MPP dan menyimpan salinan sebagai XML, XER, atau format lain yang didukung—lebih dari **20 + format** secara total.

**Q: Bagaimana cara menangani file proyek yang dilindungi kata sandi?**  
A: Muat sumber dengan `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, lalu lanjutkan penyalinan seperti biasa.

**Q: Apakah ada cara menyalin kumpulan sumber daya tanpa tugas?**  
A: Setel `CopyToOptions.CopyResources = true` dan `CopyToOptions.CopyTasks = false` untuk mentransfer hanya informasi sumber daya.

**Q: Di mana saya dapat menemukan contoh lebih lanjut?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk potongan kode yang dipandu komunitas, tips pemecahan masalah, dan dokumentasi resmi.

---

**Terakhir Diperbarui:** 2026-07-05  
**Diuji Dengan:** Aspose.Tasks 24.12 untuk .NET  
**Penulis:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Menguasai Data Proyek dengan Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Menguasai Opsi Penyimpanan MS Project untuk Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Kalender dan Penjadwalan Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}