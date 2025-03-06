---
title: Menangani Jalur Kemajuan Proyek MS dengan Aspose.Tasks
linktitle: Menangani Garis Kemajuan di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memanipulasi garis kemajuan dalam file MS Project menggunakan Aspose.Tasks untuk .NET, sehingga meningkatkan visualisasi dan manajemen proyek.
weight: 15
url: /id/net/project-management-integration/progress-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menangani Jalur Kemajuan Proyek MS dengan Aspose.Tasks

## Perkenalan
Microsoft Project (MS Project) adalah alat yang ampuh untuk manajemen proyek, memungkinkan pengguna melacak berbagai aspek proyek mereka. Salah satu fitur penting dari MS Project adalah kemampuan untuk memvisualisasikan garis kemajuan, yang membantu pemangku kepentingan memahami status dan lintasan proyek. Dalam tutorial ini, kita akan menjelajahi cara menangani garis kemajuan di MS Project menggunakan perpustakaan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Visual Studio: Instal Visual Studio atau lingkungan pengembangan .NET pilihan lainnya.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Mengimpor Namespace
Untuk memulai, mari impor namespace yang diperlukan:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Sekarang, mari kita uraikan setiap langkah dalam menangani garis kemajuan:
## Langkah 1: Muat File Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Di sini, kami memuat file MS Project`Project2.mpp` dan atur tanggal statusnya.
## Langkah 2: Tentukan Tampilan Gantt Chart
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Kami memasukkan tampilan proyek ke tampilan bagan Gantt untuk manipulasi lebih lanjut.
## Langkah 3: Tentukan Garis Kemajuan
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Kami menginisialisasi garis kemajuan untuk tampilan bagan Gantt.
## Langkah 4: Konfigurasikan Pengaturan Jalur Kemajuan
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Di sini, kami mengatur berbagai properti untuk garis kemajuan, seperti warna garis, pola, font, dll.
## Langkah 5: Periksa Konfigurasi Garis Kemajuan
```csharp
// Pengaturan jalur kemajuan keluaran
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Keluarkan pengaturan lainnya...
```
Kami menampilkan pengaturan garis kemajuan yang dikonfigurasi untuk verifikasi.
## Langkah 6: Simpan File Proyek
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Terakhir, kami menyimpan file proyek yang dimodifikasi dengan garis kemajuan.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menangani jalur kemajuan Proyek MS menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif mengkustomisasi dan memvisualisasikan garis kemajuan dalam file MS Project Anda secara terprogram.
## FAQ
### T: Dapatkah saya menyesuaikan tampilan garis kemajuan lebih lanjut?
J: Ya, Anda dapat menyesuaikan berbagai properti seperti warna garis, pola, dan font agar sesuai dengan kebutuhan Anda.
### T: Apakah Aspose.Tasks mendukung fitur manajemen proyek lainnya?
J: Ya, Aspose.Tasks menyediakan dukungan ekstensif untuk memanipulasi berbagai aspek file MS Project, termasuk tugas, sumber daya, dan kalender.
### T: Bisakah saya mengintegrasikan Aspose.Tasks dengan perpustakaan .NET lainnya?
J: Tentu saja, Aspose.Tasks dirancang untuk berintegrasi secara mulus dengan pustaka .NET lainnya, memungkinkan Anda untuk lebih meningkatkan aplikasi manajemen proyek Anda.
### T: Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 J: Ya, Anda dapat menemukan sumber daya yang bermanfaat dan mencari bantuan di forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Apakah Aspose.Tasks menawarkan lisensi sementara untuk tujuan evaluasi?
 A: Ya, Anda bisa mendapatkan lisensi sementara untuk evaluasi dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
