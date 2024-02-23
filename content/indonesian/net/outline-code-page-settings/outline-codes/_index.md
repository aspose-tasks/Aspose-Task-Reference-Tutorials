---
title: Kelola Kode Garis Besar Proyek di Aspose.Tasks untuk .NET
linktitle: Mengelola Kode Garis Besar di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola kode kerangka Proyek MS dengan Aspose.Tasks untuk .NET. Sederhanakan organisasi proyek dengan mudah.
type: docs
weight: 10
url: /id/net/outline-code-page-settings/outline-codes/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola kode kerangka Microsoft Project menggunakan Aspose.Tasks untuk .NET. Kode kerangka adalah bidang khusus di Microsoft Project yang memungkinkan pengguna mengkategorikan dan mengatur tugas berdasarkan kriteria tertentu. Aspose.Tasks menyederhanakan proses membaca dan memanipulasi kode kerangka ini secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai untuk pemrograman .NET, seperti Visual Studio.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat untuk memahami contoh kode.

## Mengimpor Namespace
Untuk memulai, Anda perlu mengimpor namespace yang diperlukan ke proyek C# Anda. Ini memungkinkan Anda mengakses kelas dan metode yang disediakan oleh perpustakaan Aspose.Tasks.
1. Buka Visual Studio: Luncurkan Visual Studio IDE Anda.
2. Buat Proyek Baru: Mulai proyek C# baru atau buka proyek yang sudah ada di mana Anda ingin menggunakan Aspose.Tasks.
3. Tambahkan Referensi Aspose.Tasks: Klik kanan proyek Anda di Solution Explorer, pilih "Kelola Paket NuGet", cari "Aspose.Tasks", dan instal versi terbaru.
4. Impor Aspose.Tasks Namespace: Di bagian atas file C# Anda, tambahkan arahan penggunaan berikut:
```csharp
using Aspose.Tasks;
using System;

```
## Langkah 1: Tentukan Direktori Dokumen
Pertama, atur path ke direktori yang berisi file MS Project Anda.
```csharp
String DataDir = "Your Document Directory";
```
 mengganti`"Your Document Directory"` dengan jalur sebenarnya ke file proyek Anda.
## Langkah 2: Muat File Proyek
 Buat instance yang baru`Project` objek dengan memuat file MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Ini menginisialisasi objek proyek dengan file yang ditentukan.
## Langkah 3: Baca Kode Garis Besar
Ulangi semua tugas dalam proyek dan ambil kode kerangkanya.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Cuplikan kode ini menelusuri setiap tugas, memeriksa apakah tugas tersebut memiliki kode kerangka, dan mencetak detail seperti Id Bidang, Panduan Nilai, dan Id Nilai untuk setiap kode kerangka yang terkait dengan tugas tersebut.

## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk .NET memberikan kemampuan canggih untuk mengelola kode kerangka Proyek Microsoft secara terprogram. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efisien membaca dan memanipulasi kode kerangka dalam file MS Project Anda menggunakan C#.
## FAQ
### T: Dapatkah saya mengubah kode kerangka menggunakan Aspose.Tasks?
J: Ya, Anda dapat mengubah kode kerangka secara terprogram menggunakan Aspose.Tasks untuk .NET. Cukup akses kode garis besar tugas dan perbarui nilainya sesuai kebutuhan.
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?
J: Aspose.Tasks mendukung berbagai versi Microsoft Project, termasuk 2003, 2007, 2010, 2013, 2016, dan 2019.
### T: Apakah Aspose.Tasks memerlukan lisensi untuk penggunaan komersial?
J: Ya, lisensi yang valid diperlukan untuk penggunaan komersial Aspose.Tasks. Anda dapat memperoleh lisensi dari situs Aspose.
### T: Dapatkah saya mencoba Aspose.Tasks sebelum membeli?
J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis dari situs web untuk mengevaluasi fitur dan kemampuannya.
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 A: Anda bisa mendapatkan dukungan untuk Aspose.Tasks dengan mengunjungi forum di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).## Kode Sumber Lengkap