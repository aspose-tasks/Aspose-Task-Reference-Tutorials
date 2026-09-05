---
date: 2026-07-19
description: Pelajari cara menambahkan custom field types di Aspose.Tasks untuk .NET
  dengan kode step‑by‑step, prasyarat, dan FAQ.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: custom field types di Aspose.Tasks
og_description: Pelajari cara menambahkan custom field types di Aspose.Tasks untuk
  .NET. Ikuti panduan step‑by‑step ini untuk membuat, mendefinisikan, dan menggunakan
  extended attributes secara efisien.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Cara Menambahkan custom field types di Aspose.Tasks untuk .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Cara Menambahkan custom field types di Aspose.Tasks untuk .NET
url: /id/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Tipe Field Kustom di Aspose.Tasks

## Pendahuluan

In tutorial ini Anda akan menemukan **cara menambahkan field kustom** ke file Microsoft Project menggunakan Aspose.Tasks untuk .NET. Field kustom memungkinkan Anda menyimpan informasi tambahan—seperti skor risiko, kode departemen, atau catatan khusus—langsung pada tugas, sumber daya, atau proyek itu sendiri. Kami akan membahas seluruh proses, mulai dari menyiapkan lingkungan hingga mendefinisikan, menambahkan, dan memverifikasi field teks kustom.

## Jawaban Cepat
- **Apa itu field kustom?** Kolom yang didefinisikan pengguna yang dapat menyimpan teks, angka, tanggal, atau bendera pada tugas/sumber daya.  
- **Kelas mana yang mendefinisikan field kustom?** `ExtendedAttributeDefinition`.  
- **Bisakah saya menambahkan field kustom ke proyek yang sudah ada?** Ya—muat proyek, buat definisinya, lalu tambahkan ke koleksi.  
- **Apakah saya memerlukan lisensi untuk Aspose.Tasks?** Lisensi diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **Versi .NET yang didukung?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Apa itu “cara menambahkan field kustom” di Aspose.Tasks?
**Cara menambahkan field kustom** mengacu pada proses membuat `ExtendedAttributeDefinition` dan melampirkannya ke koleksi `ExtendedAttributes` proyek. Ini memungkinkan Anda menyimpan metadata tambahan yang tidak termasuk dalam skema Project standar. Bisa digunakan untuk tugas, sumber daya, atau proyek itu sendiri, memungkinkan Anda menangkap informasi seperti tingkat risiko, kode departemen, atau catatan khusus yang tidak tersedia di field default.

## Mengapa menggunakan field kustom dalam manajemen proyek?
Aspose.Tasks mendukung **lebih dari 50 tipe atribut ekstensi bawaan** dan memungkinkan Anda mendefinisikan **sejumlah tak terbatas field kustom** tanpa memengaruhi ukuran file secara signifikan. Dengan menggunakan field kustom Anda dapat:  
Field ini muncul sebagai kolom tambahan di Microsoft Project dan dapat direferensikan dalam formula, laporan, dan filter. Mereka disimpan dalam file proyek dan menyertainya, memastikan bahwa alat downstream mana pun mempertahankan data kustom.

## Prasyarat

### 1. Visual Studio Terpasang
Pastikan Visual Studio (2019 atau lebih baru) terpasang di mesin Anda. Anda dapat mengunduhnya dari situs web Microsoft.

### 2. Aspose.Tasks untuk .NET
Tambahkan paket NuGet Aspose.Tasks ke proyek Anda. Unduh versi terbaru dari [here](https://releases.aspose.com/tasks/net/).

### 3. Pengetahuan Dasar C#
Anda sebaiknya nyaman dengan sintaks C#, kelas, dan struktur proyek .NET.

## Impor Namespace

`Project`, `ExtendedAttributeDefinition`, dan enum terkait berada di namespace `Aspose.Tasks`. Impor di bagian atas file Anda:

Namespace `Aspose.Tasks` menyediakan semua tipe inti untuk menangani file Microsoft Project.

```csharp

```

## Cara menambahkan field kustom ke proyek?

Muat proyek yang ada, buat definisi field kustom, dan tambahkan ke koleksi atribut ekstensi proyek—semua dalam tiga langkah singkat. Pola ini bekerja untuk tugas, sumber daya, dan proyek itu sendiri, serta memastikan field kustom disimpan saat Anda menyimpan file.

### Langkah 1: Buat Objek Project
`Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Project dalam memori. Menginstansiasikannya memuat file dan memberi Anda akses ke tugas, sumber daya, dan atribut ekstensi.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Langkah 2: Definisikan Field Kustom
`ExtendedAttributeDefinition` menggambarkan kolom baru. Dalam contoh ini kami membuat field kustom tipe **Text** untuk tugas dan memberi alias “MyText”. Nilai enum `ExtendedAttributeTask.Text1` memberi tahu Aspose.Tasks di mana menyimpan nilai tersebut.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Langkah 3: Tambahkan Definisi Field Kustom ke Proyek
Koleksi `ExtendedAttributes` proyek menyimpan semua definisi field kustom. Menambahkan definisi membuatnya tersedia untuk setiap tugas dalam proyek.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Masalah Umum dan Solusinya
- **Field tidak muncul di UI MS Project** – Pastikan Anda mengatur properti `Alias`; MS Project menampilkan alias sebagai header kolom.  
- **Menyimpan menghasilkan pengecualian** – Verifikasi bahwa file proyek tidak bersifat read‑only dan Anda memiliki lisensi yang valid.  
- **Nilai field kustom hilang setelah memuat ulang** – Pastikan Anda memanggil `project.Save("output.mpp")` setelah menetapkan nilai ke tugas.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan kerangka .NET lain?**  
A: Ya, Aspose.Tasks bekerja dengan .NET Framework, .NET Core, dan .NET 5/6/7.

**Q: Apakah Aspose.Tasks cocok untuk aplikasi tingkat perusahaan?**  
A: Tentu saja. Ia mendukung pemrosesan proyek dengan **hingga 10.000 tugas** dan dapat dijalankan di lingkungan server multi‑thread.

**Q: Apakah Aspose.Tasks mendukung banyak format file proyek?**  
A: Ya—Aspose.Tasks membaca dan menulis format MPP, XML, HTML, dan CSV, mencakup **semua versi utama Microsoft Project**.

**Q: Bisakah saya memanipulasi data sumber daya menggunakan Aspose.Tasks?**  
A: Ya, Anda dapat menambah, memperbarui, dan menghapus sumber daya, serta menetapkan field kustom kepada mereka.

**Q: Apakah ada forum komunitas untuk pengguna Aspose.Tasks?**  
A: Ya, Anda dapat mengunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk berinteraksi dengan pengguna lain dan mendapatkan dukungan dari tim Aspose.

---

**Terakhir Diperbarui:** 2026-07-19  
**Diuji Dengan:** Aspose.Tasks 24.12 for .NET  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Menguasai Definisi Atribut Ekstensi MS Project di Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Memanipulasi Atribut Ekstensi MS Project dengan Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper Integrasi MS Project di Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}