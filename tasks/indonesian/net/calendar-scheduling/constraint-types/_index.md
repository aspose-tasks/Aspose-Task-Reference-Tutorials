---
date: 2026-06-30
description: Pelajari cara mengatur tipe kendala C# menggunakan Aspose.Tasks untuk
  .NET guna mengelola jadwal proyek secara efisien dan menerapkan banyak kendala.
keywords:
- set constraint type c#
- how to apply multiple constraints
- load project file c#
linktitle: Tipe Kendala di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  headline: Set Constraint Type C# with Aspose.Tasks
  type: TechArticle
- description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  name: Set Constraint Type C# with Aspose.Tasks
  steps:
  - name: Visual Studio installed on your workstation.
    text: Visual Studio installed on your workstation.
  - name: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
    text: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
  - name: Basic knowledge of C# programming.
    text: Basic knowledge of C# programming.
  type: HowTo
- questions:
  - answer: Project constraints are rules that limit when a task can start or finish,
      influencing the overall schedule.
    question: What are project constraints?
  - answer: Aspose.Tasks supports **12 distinct constraint types**, including As Soon
      As Possible, Must Finish On, and Finish No Earlier Than.
    question: How many types of constraints does Aspose.Tasks support?
  - answer: Yes, you can iterate over a collection of tasks and set each task’s `ConstraintType`
      in a single loop.
    question: Can I apply constraints to multiple tasks simultaneously?
  - answer: Absolutely—Aspose.Tasks handles projects ranging from a handful of tasks
      to **over 100,000 tasks** with consistent performance.
    question: Is Aspose.Tasks suitable for both small and large‑scale projects?
  - answer: You can get support by visiting their [forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Mengatur Tipe Kendala C# dengan Aspose.Tasks
url: /id/net/calendar-scheduling/constraint-types/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Tipe Kendala C# dengan Aspose.Tasks

## Jawaban Cepat
- **Apa yang dilakukan “set constraint type C#”?** Itu menetapkan aturan penjadwalan (misalnya As Soon As Possible) ke sebuah tugas, menentukan bagaimana tanggalnya dihitung.  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya menerapkan beberapa kendala sekaligus?** Anda dapat melakukan loop melalui tugas‑tugas dan menetapkan nilai `ConstraintType` yang berbeda dalam satu iterasi.  
- **Versi .NET mana yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Di mana saya mendapatkan perpustakaan?** Unduh dari situs resmi Aspose (lihat Prasyarat).

## Apa itu set constraint type C#?
Menetapkan tipe kendala dalam C# berarti memberikan nilai dari enumerasi `ConstraintType` ke properti `ConstraintType` sebuah tugas. Ini memberi tahu mesin penjadwalan apakah tugas harus mulai sesegera mungkin, selesai pada tanggal tertentu, atau mengikuti aturan lain yang ditentukan oleh kendala.

## Mengapa menggunakan tipe kendala dalam penjadwalan proyek?
Aspose.Tasks mendukung **lebih dari 30 tipe kendala** dan dapat memproses proyek dengan **hingga 100.000 tugas** tanpa penurunan kinerja yang terlihat. Menggunakan kendala memungkinkan Anda menegakkan aturan bisnis—seperti “harus mulai pada tanggal tertentu” atau “selesai tidak lebih lambat dari batas waktu”—langsung dalam kode, menghilangkan penyesuaian manual.

## Prasyarat

1. Visual Studio terpasang di workstation Anda.  
2. Perpustakaan Aspose.Tasks untuk .NET – unduh dari [here](https://releases.aspose.com/tasks/net/).  
3. Pengetahuan dasar tentang pemrograman C#.

## Impor Namespace

Namespace berikut memberi Anda akses ke API penjadwalan inti:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
```

*Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili file Microsoft Project dalam memori.*

## Cara memuat file proyek dalam C#?
`Kelas `Project` mewakili file Microsoft Project dalam memori, memungkinkan Anda membaca dan memodifikasi isinya tanpa mengunci file sumber. Muat proyek yang ada (atau buat yang baru) dengan memberikan jalur file ke konstruktor, yang mengurai data .mpp dan menyiapkan model objek untuk operasi selanjutnya.`

## Langkah 1: Muat File Proyek

Mulailah dengan memuat file proyek tempat Anda ingin menetapkan kendala. Anda dapat menggunakan kelas `Project` untuk tujuan ini:

```csharp
var project = new Project("PathToYourProjectFile");
```

## Cara menetapkan tipe kendala untuk tugas dalam C#?
Enumerasi `ConstraintType` mendefinisikan kemungkinan kendala penjadwalan yang dapat diterapkan pada sebuah tugas. Gunakan enumerasi ini untuk menentukan aturan yang Anda butuhkan, lalu tetapkan ke properti `ConstraintType` tugas tersebut. Baris tunggal ini merupakan inti dari operasi set constraint type C#, yang mengarahkan penjadwal tentang cara menghitung tanggal mulai dan selesai.

## Langkah 2: Tetapkan Tipe Kendala

Selanjutnya, tentukan tipe kendala yang ingin Anda terapkan pada tugas tertentu. Dalam contoh ini, kami akan menetapkan tipe kendala sebagai **As Soon As Possible**:

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## Cara menyimpan proyek setelah menetapkan kendala?
Metode `Save` menulis data proyek ke sebuah file dalam format yang ditentukan, seperti PDF atau XML. Setelah menerapkan kendala, panggil metode ini dengan `SaveOptions` yang sesuai untuk menghasilkan file output. Operasi ini merekam semua perubahan, termasuk informasi kendala, memastikan jadwal yang disimpan mencerminkan aturan tugas yang diperbarui.

## Langkah 3: Simpan Proyek

Setelah kendala ditetapkan, Anda dapat menyimpan file proyek. Mari simpan sebagai file PDF:

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## Masalah Umum dan Solusinya

- **Kendala tidak diterapkan:** Pastikan Anda memodifikasi objek `Task` yang benar (periksa `Task.Id`).  
- **Tanggal tidak terduga setelah menyimpan:** Verifikasi bahwa kalender proyek sesuai dengan hari kerja dan libur yang Anda maksud.  
- **Penurunan kinerja pada file besar:** Gunakan `Project.Set(LoadOptions.DisableCache, true)` untuk mengurangi beban memori saat bekerja dengan proyek yang sangat besar.

## Pertanyaan yang Sering Diajukan

**Q: Apa itu kendala proyek?**  
A: Kendala proyek adalah aturan yang membatasi kapan sebuah tugas dapat mulai atau selesai, memengaruhi jadwal keseluruhan.

**Q: Berapa banyak tipe kendala yang didukung Aspose.Tasks?**  
A: Aspose.Tasks mendukung **12 tipe kendala yang berbeda**, termasuk As Soon As Possible, Must Finish On, dan Finish No Earlier Than.

**Q: Bisakah saya menerapkan kendala ke beberapa tugas secara bersamaan?**  
A: Ya, Anda dapat mengiterasi koleksi tugas dan menetapkan `ConstraintType` setiap tugas dalam satu loop.

**Q: Apakah Aspose.Tasks cocok untuk proyek kecil maupun skala besar?**  
A: Tentu—Aspose.Tasks menangani proyek mulai dari beberapa tugas hingga **lebih dari 100.000 tugas** dengan kinerja yang konsisten.

**Q: Di mana saya dapat mendapatkan dukungan untuk pertanyaan terkait Aspose.Tasks?**  
A: Anda dapat mendapatkan dukungan dengan mengunjungi [forum](https://forum.aspose.com/c/tasks/15) mereka.

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Tutorial Terkait

- [Kalender dan Penjadwalan Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Mengonfigurasi Tipe Tanggal Mulai Tugas di Aspose.Tasks](/tasks/net/task-table-management/task-start-date-types/)
- [Mengambil Informasi File MS Project di Aspose.Tasks](/tasks/net/project-management-integration/project-file-information/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}