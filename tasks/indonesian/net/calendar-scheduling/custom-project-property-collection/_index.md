---
date: 2026-10-15
description: Pelajari cara menambahkan properti khusus dan mengelola properti proyek
  khusus di Aspose.Tasks untuk .NET, meningkatkan kontrol metadata proyek Anda.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Mengelola Koleksi Properti Proyek Khusus di Aspose.Tasks
og_description: Tambahkan properti khusus ke file proyek Anda dengan Aspose.Tasks
  untuk .NET. Panduan ini menunjukkan cara mengelola properti khusus, membacanya,
  dan menambahkan nilai boolean atau string secara efisien.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Tambahkan properti khusus menggunakan Aspose.Tasks .NET API untuk proyek
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Cara menambahkan properti khusus di Aspose.Tasks untuk .NET
url: /id/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan properti khusus di Aspose.Tasks untuk .NET

## Pendahuluan

Dukungan properti khusus memungkinkan Anda menyimpan metadata proyek‑spesifik yang tidak tercakup oleh bidang bawaan. Dalam tutorial ini Anda akan belajar cara **menambahkan properti khusus**, membacanya kembali, dan mengelola seluruh koleksi properti khusus menggunakan Aspose.Tasks untuk .NET. Pada akhir tutorial Anda akan dapat menyesuaikan file proyek dengan nilai Boolean, DateTime, Double, dan String yang sesuai dengan aturan bisnis Anda.

## Jawaban Cepat
- **Bisakah saya menambahkan properti khusus Boolean?** Ya – gunakan `CustomPropertyType.Boolean`.
- **Berapa banyak tipe properti khusus yang didukung?** Empat: Boolean, DateTime, Double, String.
- **Apakah koleksi properti khusus bersifat read‑only?** Itu dapat bersifat read‑only jika proyek dimuat dari sumber yang hanya dapat dibaca.
- **Apakah saya memerlukan lisensi untuk menggunakan fitur ini?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.
- **Versi .NET mana yang kompatibel?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu properti khusus?

Properti khusus adalah bidang metadata yang didefinisikan pengguna yang Anda lampirkan ke objek Project. Ini memungkinkan Anda menyimpan informasi tambahan seperti “Risk Level”, “Customer ID”, atau flag Boolean apa pun yang tidak tercakup oleh bidang standar MS‑Project.

## Mengapa menambahkan properti khusus di Aspose.Tasks?

Aspose.Tasks mendukung **lebih dari 50 format input dan output** dan dapat menangani proyek dengan **hingga 10.000 tugas** tanpa memuat seluruh file ke memori. Menambahkan properti khusus memungkinkan Anda menyematkan data penting bisnis langsung ke dalam file proyek, menghilangkan kebutuhan basis data eksternal dan memastikan data tersebut ikut bersama proyek.

## Prasyarat

- Visual Studio (edisi terbaru apa pun) terpasang di workstation Anda.  
- Aspose.Tasks untuk .NET – unduh dari [download link](https://releases.aspose.com/tasks/net/).  
- Pemahaman dasar tentang sintaks C# dan struktur proyek .NET.

## Impor namespace

Namespace berikut memberi Anda akses ke model proyek inti dan API properti khusus.

```csharp
using Aspose.Tasks;
using System;


```

## Cara menambahkan properti khusus di Aspose.Tasks?

Untuk menambahkan properti khusus, pertama muat proyek, kemudian buat objek `CustomProperty`, atur nama, tipe, dan nilainya, dan akhirnya tambahkan ke koleksi `CustomProperties` proyek. Operasi ini menyematkan metadata langsung ke dalam file proyek, dan perubahan disimpan saat Anda memanggil `project.Save(...)`.  

`CustomProperty` mewakili satu bidang yang didefinisikan pengguna yang terlampir pada proyek.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Langkah 1: inisialisasi proyek

`Project` adalah kelas utama yang mewakili file proyek dalam Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Langkah 2: periksa kesiapan koleksi properti khusus

`CustomProperties` adalah koleksi yang menyimpan semua objek properti khusus untuk sebuah proyek.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Langkah 3: tambahkan properti khusus

Metode `Add` menyisipkan properti khusus baru ke dalam koleksi proyek.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Langkah 4: akses properti khusus

Koleksi `CustomProperties` mengimplementasikan IEnumerable, memungkinkan iterasi atas setiap `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Langkah 5: ambil nilai properti khusus

Metode `Get` mengembalikan nilai properti khusus berdasarkan namanya.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Langkah 6: iterasi nama properti khusus

Properti `Names` menyediakan daftar semua nama properti khusus dalam koleksi.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Langkah 7: hapus atau bersihkan properti khusus

Metode `Remove` menghapus properti tertentu, sementara `Clear` mengosongkan seluruh koleksi.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Kesulitan umum dan pemecahan masalah

- **Koleksi read‑only** – Jika `project.CustomProperties.IsReadOnly` mengembalikan `true`, pastikan file sumber tidak dibuka dengan akses baca eksklusif atau salin ke lokasi yang dapat ditulis sebelum mengedit.  
- **Ketidaksesuaian tipe** – Menetapkan nilai yang tidak cocok dengan `CustomPropertyType` yang dideklarasikan akan melempar `ArgumentException`. Selalu setel `Value` setelah menentukan `Type` yang benar.  
- **Menyimpan perubahan** – Setelah menambahkan atau menghapus properti, panggil `project.Save("output.mpp")` untuk menyimpan modifikasi; jika tidak, perubahan hanya tetap di memori.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menambahkan properti khusus dengan tipe data apa pun ke proyek saya menggunakan Aspose.Tasks untuk .NET?**  
A: Ya, Anda dapat menambahkan properti khusus yang mendukung tipe Boolean, DateTime, Double, dan String.

**Q: Apakah memungkinkan untuk mengiterasi nama properti khusus di Aspose.Tasks untuk .NET?**  
A: Tentu saja, Anda dapat mengiterasi nama properti khusus menggunakan properti `Names`.

**Q: Bagaimana cara menghapus properti khusus tertentu dari proyek saya?**  
A: Anda dapat menghapus properti khusus dengan namanya menggunakan metode `Remove`.

**Q: Apakah Aspose.Tasks untuk .NET menyediakan dukungan untuk lisensi sementara?**  
A: Ya, Anda dapat memperoleh lisensi sementara dari situs web Aspose untuk tujuan evaluasi.

**Q: Di mana saya dapat menemukan dukungan atau bantuan lebih lanjut mengenai Aspose.Tasks untuk .NET?**  
A: Anda dapat mengunjungi forum Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk pertanyaan atau bantuan apa pun.

---

**Terakhir Diperbarui:** 2026-10-15  
**Diuji Dengan:** Aspose.Tasks 24.11 for .NET  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara membaca properti proyek bawaan menggunakan Aspose.Tasks untuk .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Kelola Koleksi Atribut MS Project di Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Tipe Bidang Kustom Aspose.Tasks – Kalender dan Penjadwalan](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}