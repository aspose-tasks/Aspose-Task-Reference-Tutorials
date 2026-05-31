---
date: 2026-05-31
description: Pelajari cara memuat file MPP di Java dan mengelola properti proyek dengan
  Aspose.Tasks, termasuk mengatur properti default dan mengonversi format.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Kelola Properti Proyek Default di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Muat File MPP Java – Kelola Properti Proyek dengan Aspose.Tasks
url: /id/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Muat File MPP Java – Kelola Properti Proyek dengan Aspose.Tasks

## Pendahuluan
Jika Anda perlu **load MPP file Java** proyek dan mengelola properti proyek default secara programatis, Aspose.Tasks untuk Java membuatnya mudah. Dalam tutorial ini kami akan membahas seluruh proses—dari memuat file Microsoft Project yang ada hingga menyesuaikan pengaturan tugas dan sumber daya default, dan akhirnya menyimpan proyek yang diperbarui. Pada akhir tutorial Anda akan memiliki pola yang jelas dan dapat digunakan kembali yang dapat Anda terapkan pada solusi manajemen proyek berbasis Java mana pun.

## Jawaban Cepat
- **What does “load MPP file Java” mean?** Itu berarti membaca file Microsoft Project (.mpp) menggunakan kode Java melalui Aspose.Tasks.  
- **Which library handles this?** Aspose.Tasks untuk Java menyediakan API lengkap untuk manipulasi proyek.  
- **Do I need a license?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Can I change default task start dates?** Ya—gunakan `Prj.DEFAULT_START_TIME` dan properti terkait untuk mengatur nilai default.  
- **What output formats are supported?** Selain MPP asli, Anda dapat menyimpan ke XML, PDF, HTML, dan lebih dari 20 format lainnya.

## Apa itu “load MPP file Java”?
Memuat file MPP di Java berarti menggunakan perpustakaan untuk mengurai format biner Microsoft Project, menampilkan objek-objeknya (tugas, sumber daya, kalender) sebagai kelas Java. Hal ini memungkinkan Anda membaca, memodifikasi, dan menyimpan data proyek tanpa harus membuka Microsoft Project itu sendiri.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks memungkinkan Anda mengelola properti proyek tanpa instalasi Microsoft Project, mendukung **lebih dari 50 format input dan output**, dan dapat memproses proyek dengan **hingga 10.000 tugas** sambil menjaga penggunaan memori di bawah 200 MB. Ia berjalan pada semua OS yang mendukung JDK, menjadikannya ideal untuk otomatisasi sisi server.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:

### 1. Java Development Kit (JDK)
- Install JDK 11 atau lebih baru.  
- Anda dapat mengunduhnya dari [di sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### 2. Perpustakaan Aspose.Tasks untuk Java
- Unduh JAR Aspose.Tasks terbaru dan tambahkan ke classpath proyek Anda.  
- Dapatkan dari [situs web](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pernyataan impor membawa kelas Aspose.Tasks penting ke dalam file sumber Java Anda.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Cara memuat MPP file Java dan mengatur properti default?
Kelas `Project` mewakili file Microsoft Project dan menyediakan akses ke tugas, sumber daya, serta pengaturannya. Muat proyek, periksa nilai defaultnya, ubah, dan simpan hasilnya—semua dalam beberapa baris kode yang sederhana. Pendekatan ini memberi Anda kontrol penuh atas default jadwal, pengaturan kalender, dan aturan akrual biaya, memungkinkan Anda menegakkan standar proyek yang konsisten di semua file yang dihasilkan.

### Langkah 1: Muat File Proyek
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Langkah 2: Tampilkan Properti Default
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Langkah 3: Atur Properti Default
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Langkah 4: Simpan Proyek ke Format XML
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Langkah 5: Tampilkan Hasil
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Dengan mengikuti langkah-langkah ini Anda telah berhasil **memuat file MPP di Java**, memeriksa pengaturan defaultnya, menyesuaikannya, dan menyimpan proyek yang diperbarui.

## Masalah Umum & Tips
- **File not found** – Verifikasi bahwa `dataDir` diakhiri dengan pemisah jalur (`/` atau `\\`).  
- **License not applied** – Jika Anda melihat watermark percobaan, tambahkan file lisensi Anda sebelum memuat proyek: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Date handling** – Gunakan `java.util.Calendar` atau API `java.time` yang lebih baru (konversi ke `java.util.Date` sebelum menetapkan).

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Ya, Aspose.Tasks juga tersedia untuk .NET, Python, dan platform lainnya.

**Q: Apakah Aspose.Tasks cocok untuk penggunaan pribadi maupun perusahaan?**  
A: Tentu saja! Ia dapat menangani proyek pribadi kecil hingga portofolio perusahaan berskala besar.

**Q: Apakah Aspose.Tasks menyediakan dukungan pelanggan?**  
A: Ya, Anda dapat menemukan bantuan dan dukungan komunitas di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
A: Tentu! Anda dapat memanfaatkan percobaan gratis dari [situs web](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?**  
A: Anda dapat memperoleh lisensi sementara dari [halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.

## Kesimpulan
Dalam tutorial ini kami membahas cara **load MPP file Java** proyek, membaca dan mengubah properti defaultnya, serta menyimpan perubahan menggunakan Aspose.Tasks untuk Java. Mengintegrasikan teknik ini ke dalam aplikasi Anda akan membantu mengotomatisasi tugas manajemen proyek, menegakkan default yang konsisten, dan mengurangi upaya manual.

---

**Terakhir Diperbarui:** 2026-05-31  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)
- [Cara Mengatur Kalender Proyek dengan Aspose.Tasks untuk Java](/tasks/java/calendars/properties/)
- [Cara Membuat File MPP – Membuat & Menyimpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}