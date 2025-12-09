---
date: 2025-12-07
description: Pelajari cara menyimpan file proyek, menulis dan membaca rumus MS Project,
  serta menambahkan rumus bidang khusus menggunakan Aspose.Tasks untuk Java.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Simpan File Proyek dan Tulis Rumus MS Project dengan Aspose.Tasks
url: /id/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan File Proyek dan Tulis Rumus MS Project dengan Aspose.Tasks

## Pendahuluan
Di dunia manajemen proyek, penanganan data yang efektif sangat penting. Aspose.Tasks untuk Java adalah solusi kuat yang memfasilitasi manipulasi dan ekstraksi data dari file Microsoft Project. Salah satu fitur kuat yang ditawarkannya adalah kemampuan menulis dan membaca rumus MS Project. **Anda juga akan belajar cara *save project file* setelah menerapkan rumus tersebut**, memastikan perubahan Anda disimpan untuk analisis di masa mendatang. Tutorial ini akan memandu Anda melalui proses memanfaatkan fungsionalitas ini untuk meningkatkan tugas manajemen proyek Anda.

## Jawaban Cepat
- **Apa yang dilakukan “save project file”?** Itu menulis semua perubahan dalam memori kembali ke file .mpp di disk.  
- **Bisakah saya menambahkan rumus bidang khusus?** Ya – Anda dapat membuat bidang khusus dan menetapkan rumus seperti “double task cost”.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk produksi.  
- **IDE mana yang paling cocok?** Semua IDE Java (IntelliJ IDEA, Eclipse, VS Code) dapat mengompilasi contoh.  
- **Apakah API kompatibel dengan versi MS Project terbaru?** Aspose.Tasks mendukung semua format .mpp terbaru.

## Apa itu “save project file” di Aspose.Tasks?
Menyimpan file proyek berarti mempertahankan keadaan saat ini dari objek `Project`—termasuk tugas, sumber daya, dan semua rumus khusus—ke dalam file Microsoft Project fisik (`.mpp`). Operasi ini penting setelah Anda memodifikasi data, seperti menambahkan bidang khusus atau mengubah biaya tugas.

## Mengapa menambahkan bidang khusus dan membuat rumus bidang khusus?
Menambahkan bidang khusus memberi Anda wadah fleksibel untuk informasi tambahan yang tidak tercakup oleh bidang standar. Dengan melampirkan rumus—seperti yang **double task cost**—Anda mengotomatisasi perhitungan, mengurangi kesalahan manual, dan menjaga konsistensi data jadwal Anda.

## Prasyarat
Sebelum memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:

1. **Java Development Kit (JDK)** – Java 8 atau lebih tinggi terpasang di mesin Anda.  
2. **Aspose.Tasks for Java** – Unduh dan instal dari [here](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Pilih IDE pilihan Anda untuk pengembangan Java (IntelliJ IDEA, Eclipse, VS Code, dll.).  

## Mengimpor Paket
Untuk memulai, impor paket yang diperlukan ke dalam proyek Java Anda:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Langkah 1: Siapkan Direktori Data
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Tentukan folder tempat file MS Project Anda berada. Ini adalah tempat Anda akan memuat file sumber dan kemudian **save project file**.

## Langkah 2: Muat File Proyek
```java
Project project = new Project(dataDir + "project.mpp");
```
Muat file Microsoft Project yang ada ke dalam objek `Project` sehingga Anda dapat membaca atau memodifikasi isinya.

## Langkah 3: Tambahkan Bidang Khusus dan Buat Rumus Bidang Khusus
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
Pada langkah ini kami **add custom field** “Double Costs” dan **create custom field formula** yang mengalikan `[Cost]` tugas dengan 2, secara efektif **double task cost**. Metode `setFormula` menyematkan perhitungan langsung ke dalam file proyek.

## Langkah 4: Tambahkan Tugas dan Tetapkan Biaya
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Buat tugas baru, lalu tetapkan biaya dasar `100`. Saat proyek disimpan, bidang khusus akan otomatis menampilkan `200` karena rumus yang didefinisikan sebelumnya.

## Langkah 5: Simpan File Proyek
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Akhirnya, **save project file** dengan semua modifikasi. Metode `save` menulis proyek yang diperbarui, termasuk bidang khusus baru dan nilai yang dihitung, ke `saved.mpp`.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Formula tidak diterapkan** | Bidang khusus tidak ditambahkan ke koleksi `ExtendedAttributes` proyek. | Pastikan `project.getExtendedAttributes().add(attr);` dijalankan sebelum menyimpan. |
| **File tidak ditemukan** | Path `dataDir` tidak benar. | Pastikan string direktori diakhiri dengan pemisah path (`/` atau `\\`). |
| **Biaya muncul sebagai 0** | Biaya tugas tidak diatur sebelum menyimpan. | Panggil `task.set(Tsk.COST, ...)` sebelum `project.save`. |

## Pertanyaan yang Sering Diajukan
**Q: Apakah Aspose.Tasks kompatibel dengan semua versi MS Project?**  
A: Ya, Aspose.Tasks mendukung berbagai versi MS Project, mulai dari format .mpp lama hingga rilis terbaru.

**Q: Bisakah saya mengintegrasikan Aspose.Tasks ke dalam proyek Java yang sudah ada?**  
A: Tentu saja. API dirancang untuk integrasi mulus; cukup tambahkan JAR Aspose.Tasks ke classpath proyek Anda.

**Q: Apakah ada batasan pada jenis rumus yang dapat saya buat?**  
A: Perpustakaan mendukung sebagian besar sintaks rumus native MS Project, termasuk aritmetika, logika, dan fungsi bawaan. Fungsi khusus yang kompleks mungkin memerlukan solusi alternatif.

**Q: Apakah Aspose.Tasks mendukung penyebaran multi‑platform?**  
A: Ya, perpustakaan dapat dijalankan di platform apa pun yang mendukung Java, termasuk Windows, Linux, dan macOS.

**Q: Bagaimana cara mendapatkan dukungan teknis untuk Aspose.Tasks?**  
A: Kunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk bantuan komunitas, atau buka tiket dukungan jika Anda memiliki lisensi komersial.

## Kesimpulan
Dalam tutorial ini kami membahas cara **save project file**, **add custom field**, dan **create a custom field formula** yang **double task cost** menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah ini Anda dapat mengotomatisasi perhitungan, memperkaya data proyek, dan memastikan semua perubahan disimpan untuk pelaporan dan analisis di masa mendatang.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}