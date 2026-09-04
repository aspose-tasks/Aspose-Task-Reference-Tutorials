---
date: 2026-07-05
description: Pelajari cara melacak anggaran proyek dan mengelola biaya proyek menggunakan
  Aspose.Tasks untuk .NET. Tentukan Cost Accrual Types untuk pelacakan biaya yang
  akurat.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Lacak Anggaran Proyek dengan Cost Accrual Types di Aspose.Tasks
url: /id/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lacak Anggaran Proyek dengan Jenis Akumulasi Biaya di Aspose.Tasks

## Pendahuluan

Secara akurat **melacak anggaran proyek** adalah tulang punggung keberhasilan penyampaian proyek. Ketika informasi biaya ditangkap pada momen yang tepat, Anda dapat memperkirakan kelebihan biaya, menyesuaikan sumber daya, dan memberi tahu pemangku kepentingan. Aspose.Tasks untuk .NET memberi pengembang kontrol yang sangat detail atas akumulasi biaya, memungkinkan Anda menentukan *kapan* biaya dicatat—apakah pada awal pekerjaan, secara terus‑menerus, atau hanya ketika pekerjaan selesai. Tutorial ini memandu Anda melalui konsep-konsep, menunjukkan cara mengatur jenis akumulasi, dan mendemonstrasikan praktik terbaik untuk pelacakan anggaran yang andal.

## Jawaban Cepat
- **Apa tujuan utama dari jenis akumulasi biaya?** Mereka menentukan titik dalam siklus hidup tugas ketika biaya diakui, memungkinkan pelacakan anggaran yang tepat.  
- **Nilai enum mana yang menunda biaya hingga pekerjaan selesai?** `CostAccrualType.End`.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya mengubah jenis akumulasi untuk banyak sumber daya sekaligus?** Ya—lakukan iterasi melalui koleksi `Resources` dan tetapkan jenis yang diinginkan.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu Jenis Akumulasi Biaya?
Sebuah **jenis akumulasi biaya** memberi tahu Aspose.Tasks kapan menerapkan biaya sumber daya ke anggaran proyek. Itu diwakili oleh enumerasi `CostAccrualType` dan dapat diatur per‑sumber daya atau per‑tugas. Memilih jenis yang tepat memastikan data biaya selaras dengan kebijakan penagihan organisasi Anda, apakah Anda memerlukan biaya dicatat pada awal pekerjaan, diprorata selama durasi, atau hanya setelah selesai.

## Mengapa Melacak Anggaran Proyek Menggunakan Jenis Akumulasi Biaya?
Aspose.Tasks mendukung **empat** opsi akumulasi—`Start`, `Prorated`, `Duration`, dan `End`—yang mencakup seluruh rentang skenario akuntansi proyek tipikal. Memilih opsi yang tepat memungkinkan Anda menyelaraskan pengakuan biaya dengan siklus penagihan kontraktual, mengurangi variasi dalam laporan keuangan, dan menghasilkan pernyataan biaya yang terintegrasi mulus dengan sistem ERP, sekaligus menjaga penggunaan memori tetap rendah untuk proyek besar.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

### 1. Instal Aspose.Tasks untuk .NET
Untuk memulai, Anda perlu menginstal Aspose.Tasks untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduh perpustakaan dari [halaman unduhan](https://releases.aspose.com/tasks/net/) dan mengikuti petunjuk instalasi yang disediakan.

### 2. Familiaritas dengan .NET Framework
Pengetahuan dasar tentang .NET framework dan bahasa pemrograman C# diperlukan untuk mengikuti contoh-contoh dalam tutorial ini.

## Cara Mengatur Jenis Akumulasi Biaya untuk Sumber Daya?

Muat proyek, temukan sumber daya target, dan tetapkan `CostAccrualType` yang diinginkan. Pola dua baris di bawah ini adalah pendekatan standar: buat instance `Project`, ambil sumber daya berdasarkan ID-nya, lalu set `CostAccrualType`. Urutan singkat ini memastikan Anda **melacak anggaran proyek** secara akurat sejak sumber daya ditambahkan.

### Langkah 1: Impor Namespace
Let's start by importing the necessary namespaces to access Aspose.Tasks functionality in our .NET project:

```csharp

```

Setelah namespace siap, kita dapat melanjutkan ke memuat file proyek.

### Langkah 2: Muat File Proyek
Kelas `Project` mewakili file Microsoft Project dan menyediakan akses ke tugas, sumber daya, dan data lainnya.

```csharp
var project = new Project("Project2.mpp");
```

Pertama, kita perlu memuat file proyek ke dalam aplikasi kita. Kita membuat objek `Project` baru dan menginisialisasinya dengan path ke file proyek kita.

### Langkah 3: Akses Sumber Daya
Koleksi `Resources` menyimpan semua sumber daya yang didefinisikan dalam proyek. Metode `GetById` mengambil sumber daya berdasarkan pengidentifikasi uniknya.

```csharp
var resource = project.Resources.GetById(1);
```

Selanjutnya, kita mengakses sumber daya yang ingin kita terapkan jenis akumulasi biaya. Kita menggunakan metode `GetById` dari koleksi `Resources` dan memberikan ID sumber daya sebagai argumen. Ini menunjukkan **akses sumber daya berdasarkan id**, kebutuhan umum saat mengotomatisasi pembaruan biaya.

### Langkah 4: Atur Jenis Akumulasi Biaya
Metode `Set` menetapkan nilai ke bidang sumber daya.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Di sini, kami mengatur jenis akumulasi biaya untuk sumber daya. Dalam contoh ini, kami mengaturnya ke `CostAccrualType.End`, yang berarti biaya tidak akan diakumulasi hingga pekerjaan yang tersisa menjadi nol. Memilih `End` ideal ketika Anda ingin **melacak anggaran proyek** hanya setelah tugas selesai sepenuhnya.

### Langkah 5: Lanjutkan Bekerja dengan Proyek
Setelah mengatur jenis akumulasi biaya, Anda dapat melanjutkan bekerja dengan proyek sesuai kebutuhan, melakukan operasi atau perhitungan tambahan seperti menghasilkan laporan biaya, memperbarui penugasan, atau mengekspor file.

## Kesalahan Umum dan Tips Pro
- **Tip pro:** Selalu panggil `project.Save` setelah memodifikasi jenis akumulasi untuk menyimpan perubahan.  
- **Jebakan:** Menetapkan `CostAccrualType.Start` pada sumber daya yang tidak pernah memulai pekerjaan akan memperbesar laporan anggaran—verifikasi jadwal tugas terlebih dahulu.  
- **Tip pro:** Gunakan `project.Resources.ToList()` ketika Anda perlu memperbarui banyak sumber daya secara batch; ini menghindari pencarian koleksi berulang dan meningkatkan kinerja pada proyek besar.

## Pertanyaan yang Sering Diajukan

**Q: Apakah saya dapat mengubah jenis akumulasi biaya untuk beberapa sumber daya secara bersamaan?**  
A: Ya, iterasi melalui `project.Resources` dan tetapkan `CostAccrualType` yang diinginkan ke setiap sumber daya dalam loop `foreach`.

**Q: Apa jenis akumulasi biaya lain yang tersedia selain `End`?**  
A: Aspose.Tasks menyediakan `Start`, `Prorated`, dan `Duration`—masing‑masing sesuai dengan strategi penagihan yang berbeda.

**Q: Bagaimana saya dapat menentukan jenis akumulasi biaya saat ini untuk sumber daya tertentu?**  
A: Ambil nilai melalui `resource.Get(TskResource.CostAccrualType)`; ini mengembalikan enum yang mewakili pengaturan saat ini.

**Q: Apakah memungkinkan menerapkan jenis akumulasi biaya yang berbeda pada tugas yang berbeda dalam proyek yang sama?**  
A: Tentu saja. Baik tugas maupun sumber daya memiliki properti `CostAccrualType`, memungkinkan konfigurasi independen per entitas.

**Q: Apakah Aspose.Tasks mendukung jenis akumulasi biaya khusus?**  
A: Tidak, perpustakaan saat ini hanya mendukung empat jenis bawaan; logika khusus harus diimplementasikan secara eksternal jika diperlukan.

---

**Terakhir Diperbarui:** 2026-07-05  
**Diuji Dengan:** Aspose.Tasks 24.8 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Kalender dan Penjadwalan Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Menangani Tarif MS Project dengan Aspose.Tasks untuk .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Kelola Sumber Daya MS Project dengan Mudah menggunakan Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}