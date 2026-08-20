---
date: 2026-03-08
description: Pelajari cara mengimpor file proyek menggunakan Aspose.Tasks untuk .NET,
  termasuk cara menentukan enkoding file dan memuat file Microsoft Project secara
  efisien.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Impor File Proyek – Opsi untuk Memuat di Aspose.Tasks
url: /id/net/advanced-concepts/loading-options/
weight: 16
---

 content with same markdown.

Let's craft translation.

Note: Keep code block placeholders unchanged.

Also keep shortcodes at top and bottom unchanged.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Impor File Proyek – Opsi untuk Memuat di Aspose.Tasks

## Pendahuluan

Aspose.Tasks untuk .NET memudahkan **mengimpor file proyek** dari Microsoft Project, Primavera, dan format lainnya. Baik Anda perlu membaca file yang dilindungi kata sandi, mengatur enkoding khusus, atau menangani kesalahan parsing, perpustakaan ini memberi Anda kontrol yang sangat detail melalui opsi pemuatan. Dalam tutorial ini kami akan membahas skenario paling umum sehingga Anda dapat dengan percaya diri **memuat file Microsoft Project** dalam aplikasi .NET Anda.

## Jawaban Cepat
- **Apa cara utama untuk mengimpor file proyek?** Gunakan konstruktor `Project` dengan instance `LoadOptions`.  
- **Apakah saya dapat membuka file yang dilindungi kata sandi?** Ya—atur properti `Password` pada `LoadOptions`.  
- **Bagaimana cara menentukan enkoding file?** Tetapkan objek `Encoding` ke `LoadOptions.Encoding`.  
- **Apakah penanganan kesalahan dapat disesuaikan?** Tentu—sediakan delegate ke `LoadOptions.ErrorHandler`.  
- **Apakah opsi ini bekerja dengan file Primavera?** Ya, melalui `PrimaveraReadOptions` di dalam `LoadOptions`.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

1. **Visual Studio** (atau IDE .NET pilihan Anda).  
2. **Aspose.Tasks untuk .NET** – unduh dari [situs web](https://releases.aspose.com/tasks/net/).  
3. Pemahaman dasar tentang sintaks **C#** dan struktur proyek.

Setelah semuanya siap, mari impor namespace yang diperlukan.

## Mengimpor Namespace

Di proyek C# Anda, tambahkan pernyataan `using` berikut agar kelas API tersedia:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Cara Mengimpor File Proyek dengan Opsi Pemuatan

Berikut empat contoh praktis yang mencakup skenario pemuatan paling sering.

### Langkah 1: Memuat Proyek yang Dilindungi Kata Sandi

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Langkah 2: Memuat Proyek Primavera dengan Opsi Kustom

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Langkah 3: **Menentukan Enkoding File** Saat Mengimpor File XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Langkah 4: Memuat Proyek Primavera dengan Penanganan Kesalahan Kustom

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Dengan mengikuti langkah‑langkah ini Anda dapat secara tepat **mengimpor data file proyek**, menyesuaikan proses pemuatan sesuai kebutuhan, dan menjaga aplikasi tetap kuat.

## Masalah Umum & Tips

- **Kata sandi salah** – properti `Password` akan melempar pengecualian; verifikasi kredensial sebelum memuat.  
- **Enkoding tidak didukung** – pastikan halaman kode yang Anda tentukan ada di mesin target (`Encoding.GetEncoding(1251)` berfungsi untuk Cyrillic).  
- **Opsi Primavera tidak ada** – jika Anda perlu mempertahankan UID tugas, atur `PreserveUids = true`; jika tidak, ID duplikat mungkin muncul.  
- **Penangan kesalahan mengembalikan null** – mengembalikan `null` memberi sinyal pada parser untuk melewati elemen yang bermasalah; sesuaikan sesuai kebutuhan.

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi Microsoft Project?**  
J: Ya, ia mendukung berbagai versi Microsoft Project, sehingga Anda dapat **memuat file Microsoft Project** mulai dari file MPP lama hingga format terbaru.

**T: Bisakah saya mengintegrasikan Aspose.Tasks untuk .NET dengan perpustakaan pihak ketiga lainnya?**  
J: Tentu. Perpustakaan ini bekerja mulus dengan paket .NET lainnya, memungkinkan Anda menggabungkannya dengan kerangka kerja pelaporan, UI, atau akses data.

**T: Apakah Aspose.Tasks untuk .NET menyediakan dokumentasi dan sumber dukungan?**  
J: Ya, Anda dapat merujuk ke [dokumentasi](https://reference.aspose.com/tasks/net/) yang komprehensif dan mengakses dukungan melalui [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**T: Apakah ada opsi lisensi yang tersedia untuk Aspose.Tasks untuk .NET?**  
J: Ya, Anda dapat menjelajahi berbagai opsi lisensi, termasuk percobaan gratis dan lisensi sementara, di [situs Aspose.Tasks](https://purchase.aspose.com/buy).

**T: Seberapa sering pembaruan dan fitur baru dirilis untuk Aspose.Tasks untuk .NET?**  
J: Aspose.Tasks menerima pembaruan reguler yang menambah fitur, meningkatkan kinerja, dan menjaga kompatibilitas dengan rilis Microsoft Project terbaru.

---

**Terakhir Diperbarui:** 2026-03-08  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk .NET  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}