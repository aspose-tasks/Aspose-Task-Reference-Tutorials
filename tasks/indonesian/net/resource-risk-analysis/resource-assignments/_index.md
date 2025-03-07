---
title: Menangani Penugasan Sumber Daya Proyek MS di Aspose.Tasks
linktitle: Menangani Penugasan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani penetapan sumber daya MS Project secara efisien menggunakan Aspose.Tasks untuk .NET. Komprehensif ini memberikan panduan langkah demi langkah bagi pengembang.
weight: 11
url: /id/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menangani Penugasan Sumber Daya Proyek MS di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menangani penetapan sumber daya Microsoft Project secara efisien menggunakan Aspose.Tasks untuk .NET. Aspose.Tasks adalah API canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Dengan mengikuti langkah-langkah ini, Anda akan mempelajari cara mengelola penetapan sumber daya secara efektif dalam aplikasi .NET Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Tasks di proyek .NET Anda. Ini termasuk:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Sekarang mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk pemahaman komprehensif tentang cara menangani penetapan sumber daya Proyek MS menggunakan Aspose.Tasks.
## Langkah 1: Siapkan Pengaturan Proyek dan Kalender
Untuk memulai, buat instance Project baru dan siapkan pengaturan kalender proyek:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Langkah 2: Tambahkan Tugas ke Proyek
Selanjutnya, tambahkan tugas baru ke tugas utama proyek:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Langkah 3: Buat Penugasan Sumber Daya dan Hasilkan Data Bertahap Waktu
Sekarang, buat penetapan sumber daya baru untuk tugas tersebut dan hasilkan data bertahap:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Langkah 4: Bagi Tugas
Bagi tugas menjadi beberapa bagian dengan memberikan tanggal mulai dan selesai:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Langkah 5: Tetapkan Kontur Kerja
Tetapkan jenis kontur kerja untuk tugas:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Langkah 6: Simpan Proyek
Terakhir, simpan file proyek dengan perubahan yang dilakukan:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Kesimpulan
Kesimpulannya, menangani penetapan sumber daya Microsoft Project menggunakan Aspose.Tasks untuk .NET adalah proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengelola penetapan sumber daya secara efisien dalam aplikasi .NET Anda.
## FAQ
### Bisakah Aspose.Tasks menangani struktur proyek yang kompleks?
Ya, Aspose.Tasks menyediakan fungsionalitas komprehensif untuk menangani struktur proyek yang kompleks secara efisien.
### Apakah Aspose.Tasks kompatibel dengan versi Microsoft Project yang berbeda?
Ya, Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.
### Bisakah saya menyesuaikan penetapan sumber daya berdasarkan kebutuhan spesifik?
Tentu saja, Aspose.Tasks menawarkan opsi penyesuaian yang luas untuk penetapan sumber daya guna memenuhi kebutuhan proyek tertentu.
### Apakah Aspose.Tasks mendukung ekspor data proyek ke format lain?
Ya, Aspose.Tasks memungkinkan mengekspor data proyek ke berbagai format seperti XML, PDF, dan HTML, antara lain.
### Apakah dukungan teknis tersedia untuk pengguna Aspose.Tasks?
Ya, Aspose menyediakan dukungan teknis khusus melalui forumnya dan saluran lainnya untuk membantu pengguna dengan pertanyaan atau masalah apa pun.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
