---
date: 2026-01-05
description: Pelajari cara mengatur tanggal mulai proyek dan menyimpan XML MS Project
  menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah untuk pengembang
  Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Atur Tanggal Mulai Proyek dengan Aspose.Tasks untuk Java
url: /id/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Tanggal Mulai Proyek dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan mempelajari **cara mengatur tanggal mulai proyek** dalam file Microsoft Project dan kemudian **menyimpan MS Project XML** menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda mengotomatisasi pipeline pelaporan maupun membangun alat manajemen proyek khusus, menguasai tugas ini akan menghemat waktu dan menghilangkan kesalahan manual.

## Jawaban Cepat
- **Apa metode utama untuk mengatur tanggal mulai?** Gunakan `project.set(Prj.START_DATE, …)`.
- **Format apa yang harus saya gunakan untuk mengekspor file?** Simpan sebagai XML dengan `SaveFileFormat.Xml`.
- **Apakah saya memerlukan lisensi untuk operasi ini?** Versi percobaan dapat digunakan, tetapi lisensi penuh menghilangkan watermark.
- **Bisakah saya mengubah tanggal mulai setelah membuat tugas?** Ya, perbarui properti proyek sebelum menambahkan tugas.
- **Apakah ini kompatibel dengan semua versi MS Project?** Aspose.Tasks mendukung XML, MPP, dan lainnya.

## Apa itu “Set Project Start Date”?
Mengatur tanggal mulai proyek mendefinisikan kalender dasar dari mana semua perhitungan penjadwalan tugas dimulai. Ini adalah langkah pertama dalam membangun jadwal proyek yang dapat diandalkan secara programatik.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks menyediakan API murni‑Java yang bekerja di platform apa pun tanpa memerlukan instalasi Microsoft Project. Ini memungkinkan Anda membuat, memodifikasi, dan mengekspor data proyek dengan cepat, menjadikannya ideal untuk otomasi sisi server.

## Prasyarat
1. **Java Development Kit (JDK)** – versi JDK terbaru apa saja.
2. **Aspose.Tasks untuk Java** – unduh dari [here](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse, atau IDE Java pilihan Anda.

## Impor Paket
Pertama, impor kelas yang diperlukan:

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
Tentukan di mana file yang dihasilkan akan disimpan.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Buat Instance Proyek
Instansiasi proyek baru yang kosong.

```java
Project project = new Project();
```

### Langkah 3: Atur Properti Informasi Proyek
Di sini kita **mengatur tanggal mulai proyek** dan properti jadwal terkait.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Langkah 4: Simpan MS Project XML
Ekspor proyek yang telah dikonfigurasi ke file XML.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya
- **Format tanggal tidak tepat:** Pastikan Anda menggunakan `java.util.Calendar` dan memanggil `getTime()` sebelum menetapkan.
- **File tidak tersimpan:** Verifikasi bahwa `dataDir` mengarah ke folder yang ada dan dapat ditulisi.
- **Peringatan lisensi:** Versi percobaan menambahkan watermark; terapkan lisensi yang valid untuk menghilangkannya.

## Pertanyaan yang Sering Diajukan

### Q: Bisakah saya menggunakan Aspose.Tasks untuk Java membaca file MS Project?  
**A:** Ya, Aspose.Tasks untuk Java menyediakan fungsionalitas kuat untuk membaca maupun menulis file MS Project.

### Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?  
**A:** Tentu saja, Aspose.Tasks untuk Java mendukung berbagai format MS Project, memastikan kompatibilitas yang luas.

### Q: Apakah ada batasan pada versi percobaan Aspose.Tasks untuk Java?  
**A:** Versi percobaan memungkinkan Anda menjelajahi pustaka tetapi menambahkan watermark pada file output.

### Q: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk Java?  
**A:** Anda dapat mencari bantuan di forum komunitas Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

### Q: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?  
**A:** Ya, lisensi sementara tersedia untuk penggunaan jangka pendek. Dapatkan satu dari [here](https://purchase.aspose.com/temporary-license/).

### Q: Apakah menyimpan sebagai XML mempertahankan bidang khusus?  
**A:** Ya, ketika Anda menyimpan menggunakan `SaveFileFormat.Xml`, semua atribut khusus dan bidang ekstended tetap dipertahankan.

### Q: Bisakah saya mengubah tanggal mulai setelah menambahkan tugas?  
**A:** Anda dapat memperbarui tanggal mulai kapan saja sebelum menyimpan; cukup panggil `project.set(Prj.START_DATE, …)` lagi.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}