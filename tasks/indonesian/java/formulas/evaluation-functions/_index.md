---
date: 2026-10-10
description: Pelajari cara menambahkan atribut tambahan dalam Aspose.Tasks, menggunakan
  fungsi evaluasi, dan menghasilkan laporan proyek dengan pustaka manajemen proyek
  Java ini.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Dukung Fungsi Evaluasi dalam Formula Aspose.Tasks
og_description: Pelajari cara menambahkan atribut tambahan dalam Aspose.Tasks, menggunakan
  fungsi evaluasi, dan menghasilkan laporan proyek dengan pustaka manajemen proyek
  Java ini.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Cara menambahkan atribut tambahan dalam formula Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Cara menambahkan atribut tambahan dalam formula Aspose.Tasks
url: /id/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan atribut ekstensi dalam formula Aspose.Tasks

## Pendahuluan
Aspose.Tasks for Java adalah **Java project management library** yang memungkinkan Anda menghasilkan laporan proyek dengan membuat objek `Project` dalam Java dan mengevaluasi fungsi Microsoft Project secara langsung di dalam kode Anda. Dengan menyematkan formula ini, Anda dapat melakukan perhitungan yang canggih, menghasilkan laporan khusus, dan mengotomatiskan analisis proyek tanpa meninggalkan lingkungan pengembangan Anda. Dalam tutorial ini kami akan menjelaskan cara membuat objek proyek, menambahkan atribut ekstensi, dan menggunakan fungsi evaluasi untuk **add custom field task** data.

## Jawaban Cepat
- **Apa arti “create project object java”?** Ini membuat instance `Project` dalam memori yang dapat Anda manipulasi secara programatik.  
- **Perpustakaan mana yang diperlukan?** Aspose.Tasks for Java (unduh dari situs resmi).  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks sementara atau penuh diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia.  
- **Bisakah saya menggunakan custom fields?** Ya – Anda dapat **add extended attribute** ke tugas dan memperlakukannya sebagai custom fields.  
- **Apakah ini kompatibel dengan semua format file Project?** Aspose.Tasks mendukung 3 format utama (MPP, MPT, XML) dan lebih dari 50 format input/output tambahan.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Environment** – JDK 8+ dan IDE seperti IntelliJ IDEA atau Eclipse.  
2. **Aspose.Tasks for Java Library** – Unduh dan sertakan perpustakaan dari [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Impor paket
Tambahkan namespace Aspose.Tasks ke kelas Java Anda sehingga Anda dapat bekerja dengan proyek, tugas, dan atribut ekstensi:

```java
import com.aspose.tasks.*;
```

## Hasilkan laporan proyek – create project object java
Kelas `Project` mewakili file Microsoft Project dalam memori, menampilkan tugas, sumber daya, dan data khusus. Menginstansiasi kelas ini memberi Anda wadah untuk semua elemen proyek yang akan Anda definisikan.

```java
Project project = new Project();
```

Baris di atas **creates project object java** yang dimulai kosong dan siap untuk penyesuaian.

## Cara menambahkan atribut ekstensi
Kelas `ExtendedAttributeDefinition` mendefinisikan custom field yang dapat dilampirkan ke tugas. Untuk menambahkan atribut ekstensi, buat instance kelas ini dengan tipe `Number`, beri alias seperti “Sine”, tambahkan ke koleksi `ExtendedAttributes` proyek, dan kemudian hubungkan ke setiap tugas yang memerlukan custom field.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Di sini kami **add extended attribute** dengan tipe `Number` bernama “Sine” dan mengaitkannya dengan tugas.

## Tambahkan atribut ekstensi ke proyek
Daftarkan definisi atribut ke proyek sehingga setiap tugas dapat merujuknya.

```java
project.getExtendedAttributes().add(attr);
```

## Buat tugas baru
`Task` mewakili item kerja dalam proyek dan dapat berisi custom fields.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Tambahkan custom field task ke proyek
Hubungkan atribut ekstensi yang telah didefinisikan sebelumnya ke tugas yang baru dibuat, memberikan tugas tersebut custom “Sine” field yang dapat Anda gunakan dalam formula atau perhitungan.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Sekarang tugas memiliki custom “Sine” field yang dapat Anda gunakan dalam formula atau perhitungan. Ini juga cara Anda **add custom field task** data secara programatik.

## Mengapa menggunakan fungsi evaluasi?
Fungsi evaluasi memungkinkan Anda menyematkan formula Microsoft Project asli (mis., `Sin([Start])`) langsung di Aspose.Tasks, memungkinkan perhitungan secara langsung tanpa pemrosesan eksternal. Ini menjaga semua logika proyek di satu tempat, mengurangi kesalahan sinkronisasi data, dan mempercepat pembuatan laporan. Aspose.Tasks mendukung evaluasi lebih dari 100 fungsi MS Project, menyediakan mesin perhitungan komprehensif di dalam Java.

## Masalah umum dan solusi
| Masalah | Solusi |
|-------|----------|
| **Formula returns `NaN`** | Verifikasi bahwa tipe custom field cocok dengan tipe numerik yang diharapkan. |
| **Extended attribute not visible** | Pastikan definisi atribut ditambahkan ke proyek **sebelum** membuat tugas. |
| **License exception** | Instal lisensi **Aspose.Tasks** sementara atau penuh; mode percobaan mungkin membatasi beberapa fitur. |
| **Missing temporary license** | Dapatkan **lisensi Aspose sementara** dari situs web Aspose. |

## Pertanyaan yang sering diajukan

**Q: Bisakah Aspose.Tasks for Java menangani formula MS Project yang kompleks?**  
A: Ya, Aspose.Tasks for Java mendukung evaluasi berbagai fungsi MS Project, memungkinkan perhitungan kompleks dalam aplikasi Java.

**Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai versi file Microsoft Project?**  
A: Ya, Aspose.Tasks for Java mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.

**Q: Bisakah saya mencoba Aspose.Tasks for Java sebelum membeli?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks for Java dari situs web [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks for Java?**  
A: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Apakah ada lisensi sementara yang tersedia untuk Aspose.Tasks for Java?**  
A: Ya, Anda dapat memperoleh lisensi sementara untuk tujuan pengujian dari situs web Aspose [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Dengan mengikuti langkah-langkah ini Anda telah belajar cara **create project object**, **add extended attribute**, dan memanfaatkan fungsi evaluasi untuk **generate project report** secara otomatis. Anda kini dapat memperluas fondasi ini untuk membangun analitik proyek yang lebih kaya, dasbor khusus, atau alat penjadwalan otomatis—semua didukung oleh Aspose.Tasks for Java.

---

**Terakhir Diperbarui:** 2026-10-10  
**Diuji Dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose

## Tutorial Terkait

- [Kolom khusus dan atribut ekstensi dalam manajemen proyek Java](/tasks/java/project-management/extended-attributes/)
- [Baca Atribut Tugas Ekstensi dengan Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [Cara Menggunakan Aspose.Tasks for Java – Tambahkan Atribut Ekstensi ke Penugasan Sumber Daya](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}