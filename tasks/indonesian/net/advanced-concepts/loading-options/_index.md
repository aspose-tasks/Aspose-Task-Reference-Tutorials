---
title: Opsi untuk Memuat di Aspose.Tasks
linktitle: Opsi untuk Memuat di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara memanfaatkan kekuatan Aspose.Tasks untuk .NET untuk mengelola dokumen Microsoft Project secara efisien dengan panduan langkah demi langkah.
weight: 16
url: /id/net/advanced-concepts/loading-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opsi untuk Memuat di Aspose.Tasks

## Perkenalan

Aspose.Tasks untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi dokumen Microsoft Project secara terprogram. Baik Anda perlu membuat, membaca, menulis, atau mengonversi file Proyek, Aspose.Tasks menyediakan berbagai fungsi untuk menyederhanakan tugas Anda. Dalam tutorial ini, kita akan mempelajari esensi penggunaan Aspose.Tasks untuk .NET, memecah proses utama menjadi langkah-langkah sederhana dan dapat ditindaklanjuti.

## Prasyarat

Sebelum mendalami Aspose.Tasks untuk .NET, pastikan Anda telah menyiapkan prasyarat berikut:

1. Visual Studio: Instal Visual Studio atau IDE lain pilihan Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[situs web](https://releases.aspose.com/tasks/net/).
3. Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

Sekarang setelah prasyarat kita terpenuhi, mari jelajahi namespace penting dan selami panduan langkah demi langkah.

## Mengimpor Namespace

Dalam proyek C# Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Tasks:

1. Aspose.Tasks: Namespace ini menyediakan kelas inti dan antarmuka untuk bekerja dengan dokumen Proyek.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Sekarang, mari kita bagi berbagai tugas menjadi panduan langkah demi langkah.

## Langkah 1: Memuat Proyek yang Dilindungi Kata Sandi

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Inisialisasi FileStream untuk memuat file proyek
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Buat instance LoadOptions
        var options = new LoadOptions
        {
            Password = "password" // Tetapkan kata sandi
        };

        // Muat proyek dengan opsi tertentu
        var project = new Project(stream, options);

        // Tampilkan nama proyek
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Langkah 2: Memuat Proyek Primavera dengan Opsi Kustom

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Buat instance LoadOptions
    var loadOptions = new LoadOptions();

    // Konfigurasikan opsi membaca Primavera
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Atur UID Proyek
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Atur opsi membaca Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Muat proyek Primavera dengan opsi yang ditentukan
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Tampilkan nama proyek
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Lakukan operasi lebih lanjut dengan proyek yang dimuat
}
```

## Langkah 3: Menentukan Pengkodean File

```csharp
public void SpecifyFileEncoding()
{
    // Buat instance LoadOptions
    LoadOptions lo = new LoadOptions();

    // Tentukan pengkodean saat membuka proyek dari file Primavera XER
    lo.Encoding = Encoding.GetEncoding(1251);

    // Muat proyek dengan pengkodean yang ditentukan
    var project = new Project("encoding1251.xer", lo);

    // Lakukan operasi lebih lanjut dengan proyek yang dimuat
}
```

## Langkah 4: Memuat Proyek Primavera dengan Penanganan Kesalahan

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Buat instance LoadOptions
    var loadOptions = new LoadOptions();

    // Konfigurasikan opsi membaca Primavera
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Atur UID Proyek
    };

    // Atur opsi membaca Primavera
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Atur penanganan kesalahan khusus
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Muat proyek Primavera dengan opsi tertentu dan penanganan kesalahan
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Lakukan operasi lebih lanjut dengan proyek yang dimuat
}

// Metode penanganan kesalahan khusus
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Menerapkan logika penanganan kesalahan khusus
}
```

Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif memanfaatkan opsi pemuatan di Aspose.Tasks untuk .NET guna memanipulasi dokumen Proyek sesuai dengan kebutuhan Anda.

## Kesimpulan

Dalam tutorial ini, kami telah menjelajahi dasar-dasar bekerja dengan opsi pemuatan di Aspose.Tasks untuk .NET. Dari memuat proyek yang dilindungi kata sandi hingga menentukan penanganan kesalahan khusus, menguasai teknik ini akan memberdayakan Anda untuk mengelola file Proyek secara efisien dalam aplikasi .NET Anda.

## FAQ

### Q1: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi Microsoft Project?

A1: Ya, Aspose.Tasks untuk .NET mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### Q2: Bisakah saya mengintegrasikan Aspose.Tasks untuk .NET dengan perpustakaan pihak ketiga lainnya?

A2: Tentu saja, Aspose.Tasks untuk .NET terintegrasi secara mulus dengan pustaka .NET lainnya, menawarkan fungsionalitas dan fleksibilitas yang ditingkatkan.

### Q3: Apakah Aspose.Tasks untuk .NET menyediakan dokumentasi dan sumber daya dukungan?

 A3: Ya, Anda bisa merujuk ke komprehensif[dokumentasi](https://reference.aspose.com/tasks/net/) dan mengakses dukungan melalui[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).

### Q4: Apakah ada opsi lisensi yang tersedia untuk Aspose.Tasks untuk .NET?

 A4: Ya, Anda dapat menjelajahi berbagai opsi lisensi, termasuk uji coba gratis dan lisensi sementara, di[Situs web Aspose.Tasks](https://purchase.aspose.com/buy).

### Q5: Seberapa sering pembaruan dan fitur baru dirilis untuk Aspose.Tasks untuk .NET?

A5: Aspose.Tasks untuk .NET menerima pembaruan rutin dan peningkatan fitur untuk memastikan kinerja optimal dan kompatibilitas dengan teknologi yang berkembang.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
