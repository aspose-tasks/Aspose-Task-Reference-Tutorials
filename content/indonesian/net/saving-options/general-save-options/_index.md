---
title: Menguasai Opsi Penyimpanan Proyek MS untuk Aspose.Tasks
linktitle: Opsi Penyimpanan Umum untuk Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyimpan file MS Project secara efisien menggunakan Aspose.Tasks untuk .NET. Sesuaikan opsi keluaran dengan mudah untuk proyek Anda.
type: docs
weight: 17
url: /id/net/saving-options/general-save-options/
---
## Perkenalan
Aspose.Tasks untuk .NET menawarkan fitur canggih untuk memanipulasi file Microsoft Project secara terprogram. Dalam tutorial ini, kita akan mempelajari seluk-beluk menyimpan file MS Project menggunakan berbagai opsi yang disediakan oleh Aspose.Tasks. Secara khusus, kami akan fokus pada opsi penyimpanan umum yang tersedia untuk Aspose.Tasks, memungkinkan Anda menyesuaikan output dengan kebutuhan spesifik Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
2. Pemahaman Dasar .NET Framework: Keakraban dengan konsep pemrograman .NET bermanfaat.

## Mengimpor Namespace
Sebelum mendalami kode, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Langkah 1: Muat File Proyek
Pertama, Anda perlu memuat file MS Project menggunakan Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Langkah 2: Tentukan Opsi Simpan
 Tentukan opsi penyimpanan sesuai dengan kebutuhan Anda. Dalam contoh ini, kami menggunakan`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Langkah 3: Sesuaikan Kolom Tampilan
Anda dapat mengkustomisasi kolom tampilan seperti bagan Gantt, tampilan sumber daya, dan tampilan tugas. Berikut cara menambahkan kolom ke masing-masing kolom:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Langkah 4: Simpan Proyek dengan Opsi
Terakhir, simpan proyek dengan opsi yang ditentukan:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Kesimpulan
Menguasai opsi penyimpanan Proyek MS umum dengan Aspose.Tasks untuk .NET memberdayakan Anda untuk menyesuaikan format keluaran secara efisien sesuai dengan kebutuhan proyek Anda.
## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan versi file MS Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai versi file MS Project, memastikan kompatibilitas di berbagai lingkungan.
### T: Dapatkah saya mencoba Aspose.Tasks sebelum membeli?
 J: Ya, Anda dapat menjelajahi Aspose.Tasks dengan uji coba gratis yang tersedia[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks?
J: Dokumentasi terperinci dapat ditemukan[Di Sini](https://reference.aspose.com/tasks/net/), memberikan panduan komprehensif tentang penggunaan fitur Aspose.Tasks.
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?
 J: Lisensi sementara tersedia untuk tujuan evaluasi.[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat mencari dukungan untuk pertanyaan terkait Aspose.Tasks?
 A: Anda dapat bergabung dengan forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk mendapatkan bantuan dari para ahli dan sesama pengembang.