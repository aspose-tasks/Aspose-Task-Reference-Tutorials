---
title: Menguasai Data Proyek dengan Aspose.Tasks
linktitle: Bekerja dengan Data Proyek di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memanipulasi data Microsoft Project menggunakan Aspose.Tasks di .NET. Buat tugas, tambahkan sumber daya, dan simpan proyek dengan mudah.
weight: 16
url: /id/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Data Proyek dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara bekerja dengan data Microsoft Project menggunakan perpustakaan Aspose.Tasks untuk .NET. Aspose.Tasks menyediakan fitur canggih untuk memanipulasi file proyek, termasuk membuat tugas, menambahkan sumber daya, mengatur properti, dan menyimpan proyek dalam berbagai format.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1.  Instalasi Perpustakaan Aspose.Tasks: Unduh dan instal perpustakaan Aspose.Tasks dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace
Sebelum bekerja dengan Aspose.Tasks, impor namespace yang diperlukan ke dalam proyek Anda:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Langkah 1: Inisialisasi Objek Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Baris ini menginisialisasi instance baru dari`Project` kelas, yang mewakili file Microsoft Project.
## Langkah 2: Tetapkan Properti Proyek
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Baris ini menunjukkan cara mengatur properti proyek seperti format kerja dan mode pembuatan tugas.
## Langkah 3: Menambahkan Tugas
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Di sini, tugas baru bernama "Tugas 1" ditambahkan ke tugas utama proyek.
## Langkah 4: Mengatur Properti Tugas
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Baris ini menetapkan tanggal mulai, durasi, dan tanggal selesai untuk "Tugas 1".
## Langkah 5: Menambahkan Sumber Daya
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Bagian ini menunjukkan cara menambahkan sumber daya kerja ke proyek.
## Langkah 6: Menetapkan Sumber Daya ke Tugas
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Baris ini memperlihatkan cara menetapkan sumber daya kerja yang ditambahkan sebelumnya ke "Tugas 1" dengan tanggal mulai, pekerjaan, dan selesai tertentu.
## Langkah 7: Menyimpan Proyek
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Terakhir, proyek disimpan dalam format file Microsoft Project XML.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara bekerja dengan data Microsoft Project menggunakan pustaka Aspose.Tasks di .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat memanipulasi file proyek, menambahkan tugas, sumber daya, menetapkan sumber daya ke tugas, dan menyimpan proyek dalam berbagai format.
## FAQ
### T: Dapatkah Aspose.Tasks menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks memberikan dukungan komprehensif untuk struktur proyek yang kompleks, memungkinkan Anda mengelola tugas, sumber daya, dan penugasan secara efisien.
### T: Apakah Aspose.Tasks kompatibel dengan versi Microsoft Project yang berbeda?
J: Aspose.Tasks mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.
### T: Bisakah saya mengintegrasikan Aspose.Tasks dengan perpustakaan .NET lainnya?
J: Tentu saja, Aspose.Tasks terintegrasi secara mulus dengan pustaka .NET lainnya, memberikan fleksibilitas dalam proyek pengembangan Anda.
### T: Apakah Aspose.Tasks menawarkan dukungan untuk algoritma penjadwalan proyek?
J: Ya, Aspose.Tasks menyertakan algoritme penjadwalan tingkat lanjut untuk membantu Anda mengoptimalkan jadwal proyek dan pemanfaatan sumber daya.
### T: Apakah ada forum komunitas untuk pengguna Aspose.Tasks?
 J: Ya, Anda dapat menemukan sumber daya yang bermanfaat dan berinteraksi dengan pengguna Aspose.Tasks lainnya di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
