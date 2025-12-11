---
date: 2025-12-09
description: Pelajari cara membuat objek proyek Java dan mendukung fungsi evaluasi
  dalam formula Aspose.Tasks menggunakan Java. Temukan cara membuat atribut tambahan
  untuk tugas.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Buat Objek Proyek Java – Dukung Fungsi Evaluasi di Aspose.Tasks
url: /id/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mendukung Fungsi Evaluasi dalam Rumus Aspose.Tasks

## Pendahuluan
Aspose.Tasks for Java memungkinkan Anda **create project object java** instance dan mengevaluasi fungsi Microsoft Project langsung di dalam kode Java Anda. Dengan menyematkan rumus ini, Anda dapat menjalankan perhitungan canggih, menghasilkan laporan khusus, dan mengotomatisasi analisis proyek tanpa meninggalkan lingkungan pengembangan Anda. Tutorial ini memandu Anda melalui seluruh proses—dari menyiapkan objek proyek hingga menambahkan atribut ekstended yang dapat menyimpan data khusus.

## Jawaban Cepat
- **Apa arti “create project object java”?** Ini membuat instance `Project` dalam memori yang dapat Anda manipulasi secara programatik.  
- **Perpustakaan mana yang diperlukan?** Aspose.Tasks for Java (download dari situs resmi).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara atau penuh diperlukan untuk penggunaan produksi; versi percobaan gratis tersedia.  
- **Bisakah saya menggunakan bidang khusus?** Ya – Anda dapat mendefinisikan dan melampirkan atribut ekstended ke tugas.  
- **Apakah ini kompatibel dengan semua format file Project?** Aspose.Tasks mendukung format MPP, MPT, dan XML.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Environment** – JDK 8+ dan IDE seperti IntelliJ IDEA atau Eclipse.  
2. **Aspose.Tasks for Java Library** – Unduh dan sertakan perpustakaan dari [halaman unduhan Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Impor Paket
Tambahkan namespace Aspose.Tasks ke kelas Java Anda sehingga Anda dapat bekerja dengan proyek, tugas, dan atribut ekstended:

```java
import com.aspose.tasks.*;
```

## Langkah 1: Buat Project Object Java
Instansiasi objek `Project` baru. Ini akan berfungsi sebagai wadah untuk semua tugas, sumber daya, dan data khusus yang akan Anda definisikan.

```java
Project project = new Project();
```

Baris di atas **creates project object java** yang dimulai kosong dan siap untuk dikustomisasi.

## Langkah 2: Cara Membuat Atribut Ekstended
Definisikan atribut ekstended yang akan menyimpan data numerik khusus (mis., nilai sinus) untuk setiap tugas.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Di sini kami **create extended attribute** bertipe `Number` bernama “Sine” dan mengaitkannya dengan tugas.

## Langkah 3: Tambahkan Atribut Ekstended ke Proyek
Daftarkan definisi atribut ke proyek sehingga setiap tugas dapat merujuknya.

```java
project.getExtendedAttributes().add(attr);
```

## Langkah 4: Buat Tugas Baru
Tambahkan tugas sederhana bernama “Task” di bawah tugas root proyek.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Langkah 5: Kaitkan Atribut Ekstended dengan Tugas
Hubungkan atribut ekstended yang telah didefinisikan sebelumnya ke tugas yang baru dibuat.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Sekarang tugas memiliki bidang khusus “Sine” yang dapat Anda gunakan dalam rumus atau perhitungan.

## Mengapa Menggunakan Fungsi Evaluasi?
Menyematkan fungsi MS Project dalam rumus Aspose.Tasks memungkinkan Anda untuk:
- Melakukan perhitungan secara langsung (mis., `Sin([Start])`) tanpa alat eksternal.  
- Menjaga semua logika proyek dalam satu basis kode yang dapat dipelihara.  
- Menghasilkan laporan dinamis yang mencerminkan perubahan data secara real‑time.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Formula mengembalikan `NaN`** | Verifikasi bahwa tipe bidang khusus cocok dengan tipe numerik yang diharapkan. |
| **Atribut ekstended tidak terlihat** | Pastikan definisi atribut ditambahkan ke proyek **sebelum** membuat tugas. |
| **Pengecualian lisensi** | Pasang lisensi sementara atau penuh; mode percobaan mungkin membatasi beberapa fitur. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah Aspose.Tasks for Java menangani rumus MS Project yang kompleks?**  
A: Ya, Aspose.Tasks for Java mendukung evaluasi berbagai fungsi MS Project, memungkinkan perhitungan kompleks dalam aplikasi Java.

**Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai versi file Microsoft Project?**  
A: Ya, Aspose.Tasks for Java mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.

**Q: Bisakah saya mencoba Aspose.Tasks for Java sebelum membeli?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks for Java dari situs web [di sini](https://purchase.aspose.com/buy).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks for Java?**  
A: Anda dapat memperoleh dukungan dari forum komunitas Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

**Q: Apakah ada lisensi sementara yang tersedia untuk Aspose.Tasks for Java?**  
A: Ya, Anda dapat memperoleh lisensi sementara untuk tujuan pengujian dari situs web Aspose [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2025-12-09  
**Diuji Dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}