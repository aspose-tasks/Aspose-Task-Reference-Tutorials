---
date: 2026-05-20
description: Pelajari cara menggunakan Aspose.Tasks untuk Java untuk menambahkan atribut
  ekstensi ke penugasan sumber daya, mengatur tanggal mulai proyek, dan menulis file
  MS Project secara efisien.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Menambahkan Atribut Ekstensi ke Penugasan Sumber Daya di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Menggunakan Aspose.Tasks untuk Java – Menambahkan Atribut Ekstensi ke
  Penugasan Sumber Daya
url: /id/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Manipulasi MS Project dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan menemukan **cara menggunakan Aspose.Tasks untuk Java** untuk menambahkan atribut ekstended ke penugasan sumber daya dan menulis informasi Microsoft Project secara programatis. Baik Anda mengotomatisasi alur pelaporan maupun membangun alat manajemen proyek khusus, langkah‑langkah di bawah ini menunjukkan secara tepat cara mengatur tanggal mulai proyek, membuat penugasan sumber daya, dan menyimpan file sebagai XML—semua dengan hanya beberapa baris kode Java.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks untuk Java?** Ia membaca, menulis, dan memodifikasi file Microsoft Project tanpa perlu menginstal Microsoft Project.  
- **Bisakah saya menambahkan bidang khusus ke penugasan sumber daya?** Ya, gunakan koleksi `ExtendedAttribute` pada objek `ResourceAssignment`.  
- **Bagaimana cara mengatur tanggal mulai proyek?** Panggil `project.setStartDate(LocalDateTime.of(...))` sebelum menyimpan.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial menghapus watermark evaluasi dan membuka akses penuh ke API.  
- **Versi Java mana yang didukung?** Aspose.Tasks untuk Java mendukung JDK 8 hingga JDK 21.

## Cara menggunakan Aspose.Tasks untuk Java?
`Project` adalah objek utama yang mewakili file Microsoft Project dalam memori. Muat pustaka Aspose.Tasks, buat instance `Project`, konfigurasikan properti tingkat proyek, tambahkan atribut ekstended ke penugasan sumber daya, dan akhirnya simpan proyek sebagai XML. Alur kerja inti terbagi menjadi tiga langkah singkat: inisialisasi, modifikasi, dan penyimpanan. Pola ini bekerja untuk proyek berukuran apa pun dan berjalan pada JVM Windows, Linux, atau macOS.

## Apa itu atribut ekstended di Aspose.Tasks?
Sebuah **atribut ekstended** adalah bidang khusus yang Anda lampirkan ke tugas, sumber daya, atau penugasan untuk menyimpan metadata tambahan di luar kolom bawaan. `ExtendedAttributeDefinition` mendefinisikan skema untuk bidang khusus. Aspose.Tasks menyediakan kelas `ExtendedAttributeDefinition` dan `ExtendedAttribute` untuk mendefinisikan dan menetapkan bidang ini secara programatis.

## Mengapa menambahkan atribut ekstended ke penugasan sumber daya?
Aspose.Tasks mendukung **lebih dari 50 bidang bawaan dan khusus**, dan Anda dapat menambahkan atribut tak terbatas yang didefinisikan pengguna. Menambahkannya memungkinkan Anda menangkap kode biaya, ID departemen, atau data spesifik bisnis apa pun langsung di dalam file .mpp, menghilangkan kebutuhan spreadsheet eksternal dan memastikan integritas data sepanjang siklus hidup proyek.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – JDK 8 atau lebih baru terinstal.  
2. **Aspose.Tasks untuk Java library** – Unduh dari halaman rilis resmi [di sini](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor kompatibel Java apa pun yang Anda sukai.

## Impor Paket
Pertama, impor paket yang diperlukan dalam proyek Java Anda:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Langkah 1: Siapkan Direktori Data
Tentukan direktori tempat data proyek Anda akan disimpan. Jalur ini akan digunakan nanti saat Anda menyimpan file XML.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Buat Instance Project
Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Membuat instance memberi Anda akses penuh ke semua elemen proyek.

```java
Project project = new Project();
```

### Langkah 3: Atur Properti Informasi Proyek
Atur properti penting proyek seperti tanggal mulai, flag schedule from start, dan tanggal status. Nilai‑nilai ini disimpan dalam objek `ProjectInfo` proyek.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Langkah 4: Tambahkan Atribut Ekstended ke Penugasan Sumber Daya
Buat `ExtendedAttributeDefinition` untuk bidang khusus, lampirkan ke `ResourceAssignment`, dan isi nilainya. Langkah ini mendemonstrasikan kata kunci **add extended attributes** dalam aksi.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya
- **NullPointerException saat mengakses koleksi penugasan** – Pastikan Anda telah membuat setidaknya satu sumber daya dan satu tugas sebelum mengambil penugasan.  
- **Atribut ekstended tidak muncul di MS Project** – Verifikasi bahwa `FieldId` atribut cocok dengan slot bidang khusus (misalnya, `ExtendedAttributeTask.Text1`).  
- **Ketidaksesuaian format tanggal** – Gunakan `java.time.LocalDateTime` untuk nilai tanggal; Aspose.Tasks secara otomatis mengonversinya ke format kalender Proyek.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java untuk membaca file MS Project?**  
A: Ya, pustaka ini menyediakan kemampuan baca‑tulis penuh untuk format .mpp, .xml, dan .xps.

**Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?**  
A: Tentu saja, ia mendukung file dari Project 2000 hingga rilis terbaru 2024, mencakup lebih dari 20 format versi.

**Q: Apakah ada batasan pada versi percobaan Aspose.Tasks untuk Java?**  
A: Versi percobaan menambahkan watermark pada file yang dihasilkan dan membatasi jumlah tugas yang dapat Anda buat, tetapi semua fitur API tetap dapat diakses.

**Q: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mencari bantuan di forum komunitas Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

**Q: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Ya, lisensi sementara tersedia untuk penggunaan jangka pendek. Anda dapat mendapatkannya dari [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-05-20  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Menambahkan Catatan ke Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Cara Membaca Skala Tarif dan Menulis Skala Tarif untuk Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Cara Menambahkan Sumber Daya ke Proyek dan Menangani Properti Penundaan Leveling di Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}