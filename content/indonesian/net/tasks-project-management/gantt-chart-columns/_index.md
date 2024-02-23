---
title: Sesuaikan Kolom Gantt Chart dengan Aspose.Tasks
linktitle: Kolom Gantt Chart di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyesuaikan kolom bagan Gantt di Aspose.Tasks untuk .NET guna menampilkan informasi tugas tertentu secara efisien.
type: docs
weight: 21
url: /id/net/tasks-project-management/gantt-chart-columns/
---
## Perkenalan
Bagan Gantt adalah alat mendasar dalam manajemen proyek, yang memberikan representasi visual tugas, jadwal, dan sumber daya. Aspose.Tasks untuk .NET menawarkan kemampuan canggih untuk memanipulasi bagan Gantt, termasuk menyesuaikan kolom untuk menampilkan informasi tugas tertentu. Dalam tutorial ini, kita akan mempelajari cara bekerja dengan kolom bagan Gantt menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Instalasi: Aspose.Tasks untuk .NET diinstal pada sistem Anda. Jika tidak, unduh dan instal dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan .NET: Pengetahuan tentang C# dan kerangka .NET.
3. Contoh File Proyek: Miliki contoh file Microsoft Project (`.mpp`) berguna untuk bereksperimen. Jika Anda tidak memilikinya, Anda dapat membuat proyek sederhana di MS Project dan menyimpannya.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan agar berfungsi dengan Aspose.Tasks untuk .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Langkah 1: Muat File Proyek
 Muat file proyek menggunakan`Project` kelas yang disediakan oleh Aspose.Tugas:
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Langkah 2: Tentukan Kolom Gantt Chart
Tentukan kolom yang ingin Anda tampilkan di bagan Gantt. Anda dapat menentukan kolom bawaan atau membuat kolom khusus:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Langkah 3: Ulangi Kolom
Ulangi kolom yang ditentukan untuk mengakses propertinya dan menampilkan informasi:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Langkah 4: Simpan Gantt Chart ke CSV
Simpan bagan Gantt dengan kolom yang ditentukan ke file CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Dengan mengikuti langkah-langkah ini, Anda dapat bekerja secara efektif dengan kolom bagan Gantt di Aspose.Tasks untuk .NET, memungkinkan Anda menyesuaikan dan menampilkan informasi tugas sesuai kebutuhan.

## Kesimpulan
Menguasai manipulasi kolom bagan Gantt di Aspose.Tasks untuk .NET membuka kemungkinan tak terbatas untuk menyesuaikan visual manajemen proyek dengan kebutuhan spesifik Anda. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menangani informasi tugas secara efisien dan meningkatkan kejelasan dan pengorganisasian proyek.
## FAQ
### T: Bisakah saya membuat kolom khusus di Aspose.Tasks untuk .NET?
J: Ya, Anda dapat menentukan kolom khusus untuk menampilkan atribut tugas tertentu sesuai dengan kebutuhan proyek Anda.
### T: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi file Microsoft Project?
J: Aspose.Tasks untuk .NET mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di berbagai lingkungan proyek.
### T: Bagaimana cara menangani struktur proyek yang kompleks dengan Aspose.Tasks untuk .NET?
J: Aspose.Tasks untuk .NET menyediakan API dan fitur komprehensif untuk mengelola struktur proyek yang kompleks, menawarkan fleksibilitas dan skalabilitas.
### T: Apakah ada batasan jumlah kolom yang dapat saya tambahkan ke bagan Gantt?
J: Aspose.Tasks untuk .NET menawarkan opsi penyesuaian yang luas, memungkinkan Anda menambahkan sejumlah besar kolom ke bagan Gantt tanpa batasan.
### T: Di mana saya dapat menemukan dukungan dan sumber daya tambahan untuk Aspose.Tasks untuk .NET?
J: Anda dapat menjelajahi dokumentasi, forum komunitas, dan saluran dukungan yang disediakan oleh Aspose.Tasks untuk .NET untuk mengakses sumber daya dan bantuan yang komprehensif.