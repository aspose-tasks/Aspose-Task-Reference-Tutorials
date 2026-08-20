---
date: 2026-03-14
description: Pelajari cara menggunakan boolean nullable di Aspose.Tasks untuk .NET,
  termasuk mengonversi nilai boolean nullable dan mengatur properti boolean nullable.
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Menggunakan Boolean Nullable di Aspose.Tasks
url: /id/net/advanced-concepts/nullable-booleans/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Boolean Nullable di Aspose.Tasks

Dalam tutorial ini kami akan menunjukkan **cara menggunakan nullable** boolean saat bekerja dengan API Aspose.Tasks .NET. Boolean nullable memberi Anda tiga kemungkinan keadaan—`true`, `false`, atau *undefined*—yang sangat berguna untuk pengaturan tingkat proyek yang mungkin tidak ditentukan secara eksplisit. Anda akan melihat cara membuat, mengonversi, dan **menetapkan boolean nullable**, serta mengapa penanganan boolean nullable dengan benar dapat mencegah perilaku tak terduga dalam aplikasi penjadwalan Anda.

## Jawaban Cepat
- **Apa itu nullable boolean?** Tipe yang dapat menyimpan `true`, `false`, atau tidak terdefinisi.  
- **Mengapa menggunakan nullable boolean di Aspose.Tasks?** Mereka memungkinkan Anda merepresentasikan properti proyek opsional tanpa menebak nilai default.  
- **Bagaimana mengonversi nullable boolean menjadi bool biasa?** Gunakan konversi implisit atau periksa `IsDefined` terlebih dahulu.  
- **Apa kelas utama?** `NullableBool` di namespace `Aspose.Tasks`.  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.

## Apa Itu Nullable Boolean?

Nullable boolean (`NullableBool`) memperluas tipe `bool` biasa dengan menambahkan flag *IsDefined*. Ketika `IsDefined` bernilai `false`, nilai dianggap tidak terdefinisi, memungkinkan Anda membedakan antara “false” dan “tidak disetel”.

## Mengapa Menangani Nullable Boolean dalam Pengaturan Proyek?

Banyak opsi proyek—seperti **ActualsInSync** atau **HonorConstraints**—adalah opsional. Menggunakan `bool` biasa memaksa Anda memilih `true` atau `false`, yang dapat secara tidak sengaja menimpa niat pengguna. Dengan **menangani nullable boolean**, Anda mempertahankan keadaan asli dan menghindari perubahan konfigurasi yang tidak disengaja.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

1. **Visual Studio** (atau IDE yang kompatibel dengan .NET apa pun).  
2. **Aspose.Tasks for .NET** – unduh dari [sini](https://releases.aspose.com/tasks/net/).

## Impor Namespace

Pertama, impor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

Sekarang mari kita bahas setiap contoh langkah demi langkah.

## Bekerja dengan `NullableBool`

### Langkah 1: Buat instance `Project` baru.

```csharp
var project = new Project();
```

### Langkah 2: Instansiasi objek `NullableBool` dengan nilai yang ditentukan.

```csharp
var actualsInSync = new NullableBool(false, false);
```

### Langkah 3: Periksa nilai dan status terdefinisi dari objek `NullableBool`.

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### Langkah 4: **Set nullable boolean** pada proyek.

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### Langkah 5: Instansiasi objek `NullableBool` lain dengan satu nilai.

```csharp
var honorConstraints = new NullableBool(true);
```

### Langkah 6: Tampilkan representasi string dari objek `NullableBool`.

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### Langkah 7: Gunakan instance `NullableBool` dengan menyetelnya di proyek.

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## Membandingkan Instance `NullableBool`

### Langkah 1: Instansiasi dua objek `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Langkah 2: Periksa representasi string dari masing-masing objek `NullableBool`.

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### Langkah 3: Konversi implisit ke `bool` dan cetak hasilnya.

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### Langkah 4: Bandingkan dua objek `NullableBool` untuk kesetaraan.

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## Mendapatkan Hash Code dari `NullableBool`

### Langkah 1: Instansiasi dua objek `NullableBool`.

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### Langkah 2: Cetak hash code untuk masing-masing objek `NullableBool`.

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## Kesalahan Umum & Tips

- **Jangan pernah menganggap nullable boolean terdefinisi.** Selalu periksa `IsDefined` sebelum menggunakan `Value`.  
- **Mengonversi ke bool biasa** tanpa pemeriksaan dapat melempar pengecualian jika nilai tidak terdefinisi. Gunakan konversi implisit hanya ketika Anda yakin itu terdefinisi.  
- **Saat menyetel properti proyek**, gunakan metode `Set` dengan `NullableBool` untuk mempertahankan keadaan tidak terdefinisi jika diperlukan.

## Pertanyaan yang Sering Diajukan

**T: Apa itu nullable boolean?**  
J: Nullable boolean dapat merepresentasikan `true`, `false`, atau keadaan tidak terdefinisi, memungkinkan tiga hasil yang berbeda.

**T: Bagaimana saya dapat mengonversi nullable boolean ke bool biasa dengan aman?**  
J: Periksa `IsDefined` terlebih dahulu, kemudian gunakan properti `Value` atau bergantung pada konversi implisit ketika Anda yakin itu terdefinisi.

**T: Mengapa saya harus menggunakan nullable boolean alih-alih bool biasa di Aspose.Tasks?**  
J: Mereka memungkinkan Anda menjaga pengaturan proyek opsional tetap tidak tersentuh, mencegah penimpaan yang tidak disengaja.

**T: Bisakah saya menyetel nullable boolean menjadi tidak terdefinisi?**  
J: Ya—gunakan konstruktor yang hanya menerima flag terdefinisi, misalnya `new NullableBool(false, false)`.

**T: Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Tasks untuk .NET?**  
J: Anda dapat menemukan dokumentasi detail [di sini](https://reference.aspose.com/tasks/net/).

---

**Terakhir Diperbarui:** 2026-03-14  
**Diuji Dengan:** Aspose.Tasks for .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}