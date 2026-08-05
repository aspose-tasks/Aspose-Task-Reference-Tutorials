---
date: 2026-02-13
description: Pelajari cara menghasilkan laporan proyek dengan membuat objek proyek
  di Java, menambahkan atribut tambahan, dan menggunakan fungsi evaluasi dengan Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Hasilkan Laporan Proyek – Buat Objek Proyek Java
url: /id/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mendukung Fungsi Evaluasi dalam Rumus Aspose.Tasks

## Pendahuluan
Aspose.Tasks for Java memungkinkan Anda **menghasilkan laporan proyek** dengan membuat **objek proyek** di Java dan mengevaluasi fungsi Microsoft Project langsung di dalam kode Anda. Dengan menyematkan rumus‑rumus ini, Anda dapat menjalankan perhitungan yang canggih, menghasilkan laporan khusus, dan mengotomatiskan analisis proyek tanpa meninggalkan lingkungan pengembangan Anda. Dalam tutorial ini kami akan menjelaskan cara membuat objek proyek, menambahkan atribut ekstensi, dan menggunakan fungsi evaluasi untuk **menambahkan data bidang khusus tugas**.

## Jawaban Cepat
- **Apa arti “create project object java”?** Itu membuat instance `Project` dalam memori yang dapat Anda manipulasi secara programatik.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks for Java (unduh dari situs resmi).  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks sementara atau penuh diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia.  
- **Bisakah saya menggunakan bidang khusus?** Ya – Anda dapat **menambahkan atribut ekstensi** ke tugas dan memperlakukannya sebagai bidang khusus.  
- **Apakah ini kompatibel dengan semua format file Project?** Aspose.Tasks mendukung format MPP, MPT, dan XML.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Lingkungan Pengembangan Java** – JDK 8+ dan IDE seperti IntelliJ IDEA atau Eclipse.  
2. **Perpustakaan Aspose.Tasks untuk Java** – Unduh dan sertakan perpustakaan dari [halaman unduhan Aspose.Tasks untuk Java](https://releases.aspose.com/tasks/java/).

## Mengimpor Paket
Tambahkan namespace Aspose.Tasks ke kelas Java Anda sehingga Anda dapat bekerja dengan proyek, tugas, dan atribut ekstensi:

```java
import com.aspose.tasks.*;
```

## Menghasilkan Laporan Proyek – Membuat Objek Proyek Java
Buat instance baru `Project`. Ini akan berfungsi sebagai wadah untuk semua tugas, sumber daya, dan data khusus yang akan Anda definisikan.

```java
Project project = new Project();
```

Baris di atas **creates project object java** yang dimulai kosong dan siap untuk disesuaikan.

## Cara Menambahkan Atribut Ekstensi
Definisikan atribut ekstensi yang akan menyimpan data numerik khusus (mis., nilai sinus) untuk setiap tugas.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Di sini kami **add extended attribute** dengan tipe `Number` bernama “Sine” dan mengaitkannya dengan tugas.

## Tambahkan Atribut Ekstensi ke Proyek
Daftarkan definisi atribut ke proyek sehingga setiap tugas dapat merujuknya.

```java
project.getExtendedAttributes().add(attr);
```

## Buat Tugas Baru
Tambahkan tugas sederhana bernama “Task” di bawah tugas root proyek.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Kaitkan Atribut Ekstensi dengan Tugas
Hubungkan atribut ekstensi yang telah didefinisikan sebelumnya ke tugas yang baru dibuat.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Sekarang tugas memiliki bidang khusus “Sine” yang dapat Anda gunakan dalam rumus atau perhitungan. Inilah cara Anda **add custom field task** data secara programatik.

## Mengapa Menggunakan Fungsi Evaluasi?
Menyematkan fungsi MS Project dalam rumus Aspose.Tasks memungkinkan Anda untuk:

- Melakukan perhitungan secara langsung (mis., `Sin([Start])`) tanpa alat eksternal.  
- Menjaga semua logika proyek dalam satu basis kode yang dapat dipelihara.  
- Menghasilkan laporan dinamis yang mencerminkan perubahan data waktu nyata, membantu Anda **generate project report** secara otomatis.

## Masalah Umum dan Solusinya
| Issue | Solution |
|-------|----------|
| **Formula mengembalikan `NaN`** | Pastikan tipe bidang khusus cocok dengan tipe numerik yang diharapkan. |
| **Atribut ekstensi tidak terlihat** | Pastikan definisi atribut ditambahkan ke proyek **sebelum** membuat tugas. |
| **Pengecualian lisensi** | Pasang lisensi **Aspose.Tasks** sementara atau penuh; mode percobaan mungkin membatasi beberapa fitur. |
| **Lisensi sementara hilang** | Dapatkan **lisensi Aspose sementara** dari situs web Aspose. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah Aspose.Tasks untuk Java menangani rumus MS Project yang kompleks?**  
A: Ya, Aspose.Tasks untuk Java mendukung evaluasi berbagai fungsi MS Project, memungkinkan perhitungan kompleks dalam aplikasi Java.

**Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi file Microsoft Project?**  
A: Ya, Aspose.Tasks untuk Java mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.

**Q: Bisakah saya mencoba Aspose.Tasks untuk Java sebelum membeli?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks untuk Java dari situs web [di sini](https://purchase.aspose.com/buy).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat memperoleh dukungan dari forum komunitas Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

**Q: Apakah ada lisensi sementara yang tersedia untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat memperoleh lisensi sementara untuk tujuan pengujian dari situs web Aspose [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda telah belajar cara **create project object**, **add extended attribute**, dan memanfaatkan fungsi evaluasi untuk **generate project report** secara otomatis. Sekarang Anda dapat memperluas fondasi ini untuk membangun analitik proyek yang lebih kaya, dasbor khusus, atau alat penjadwalan otomatis—semua didukung oleh Aspose.Tasks untuk Java.

---

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}