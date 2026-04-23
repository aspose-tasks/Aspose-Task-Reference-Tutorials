---
date: 2026-02-05
description: Pelajari cara menambahkan hari libur ke kalender, menetapkan kalender
  ke proyek, dan menyimpan file MS Project sebagai MPP menggunakan Aspose.Tasks untuk
  Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tambahkan Hari Libur ke Kalender dan Simpan sebagai MPP dengan Aspose.Tasks
url: /id/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Hari Libur ke Kalender dan Simpan sebagai MPP dengan Aspose.Tasks

## Pendahuluan

Dalam manajemen proyek modern Anda sering perlu **menambahkan hari libur ke file kalender**, membuat **kalender MS Project**, dan kemudian membagikan jadwal dalam format MPP asli. Baik Anda mengkonsolidasikan timeline dari berbagai sumber atau memigrasikan data warisan, menghasilkan kalender secara programatik menghilangkan kesalahan manual dan mempercepat penyampaian. Tutorial ini memandu Anda melalui proses lengkap membuat kalender di MS Project, menyesuaikannya dengan hari libur, **menetapkan kalender ke proyek**, dan akhirnya **mengonversi proyek ke MPP** menggunakan Aspose.Tasks Java API.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan hari libur ke kalender, menetapkannya ke proyek, dan menyimpan hasilnya sebagai file MPP dengan Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang dibutuhkan?** Java 8 atau lebih tinggi (JDK 8+).  
- **Bisakah saya menyesuaikan kalender?** Ya – Anda dapat menambahkan jam kerja, pengecualian, dan hari libur.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk kalender dasar.  

## Apa itu “create calendar MS Project”?

Membuat kalender MS Project berarti secara programatik mendefinisikan hari kerja, jam kerja, dan pengecualian yang mengatur penjadwalan tugas dalam file Microsoft Project. Dengan menggunakan Aspose.Tasks Anda dapat **java create project calendar**, memodifikasinya, dan menyimpan perubahan tanpa pernah membuka UI Microsoft Project.

## Mengapa menggunakan Aspose.Tasks untuk tugas ini?

- **Kompatibilitas .NET/Java penuh** – bekerja pada platform apa pun yang mendukung Java.  
- **Tanpa COM atau instalasi Office** – ideal untuk otomatisasi sisi‑server dan **automate schedule generation**.  
- **API kaya** – mendukung setiap properti kalender, termasuk minggu kerja khusus dan hari libur.  
- **Output MPP langsung** – Anda dapat **save project as MPP** tanpa konversi perantara.

## Prasyarat

1. **Java Development Kit (JDK) 8+** – pastikan `java -version` menampilkan 1.8 atau lebih baru.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [situs Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor lain yang Anda sukai.  
4. **Pengetahuan dasar Java** – familiar dengan kelas, metode, dan I/O file.

## Cara Menambahkan Hari Libur ke Kalender

Berikut kami menjelaskan setiap langkah, mulai dari menyiapkan lingkungan hingga menyimpan file MPP akhir. Blok kode tidak diubah dari tutorial asli; penjelasan di sekitarnya telah diperluas untuk kejelasan.

### Langkah 1: Impor Paket yang Diperlukan

Pertama, bawa kelas Aspose.Tasks dan utilitas Java ke dalam ruang lingkup.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Langkah 2: Siapkan Direktori Data

Tentukan di mana template input dan file output Anda akan disimpan. Ganti placeholder dengan jalur sebenarnya di mesin Anda.

```java
String dataDir = "Your Data Directory";
```

### Langkah 3: Definisikan Nama File Input dan Output

Kita akan memuat file MPP yang sudah ada (atau proyek kosong) dan menulis hasilnya ke file baru.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Langkah 4: Muat Proyek dan Tambahkan Kalender Baru

Buat instance `Project` dari file sumber dan tambahkan kalender bernama **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Langkah 5: Sesuaikan Kalender (Opsional)

Jika Anda memerlukan jam kerja khusus, hari libur, atau pengecualian, panggil metode bantu Anda sendiri. Contoh menggunakan `GetTestCalendar` sebagai placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Anda dapat langsung memanipulasi `cal1.getWeekDays()` untuk mengatur jam kerja setiap hari dalam seminggu, atau gunakan `cal1.getExceptions()` untuk **add holidays to calendar**.

### Langkah 6: Tetapkan Kalender ke Proyek

Beritahu proyek untuk menggunakan kalender yang baru dibuat untuk semua perhitungan penjadwalannya.

```java
project.set(Prj.CALENDAR, cal1);
```

### Langkah 7: Simpan Proyek sebagai MPP

Sekarang **convert project to MPP** dengan menyimpannya menggunakan opsi `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Langkah 8: Konfirmasi Penyelesaian Berhasil

Pesan konsol sederhana memberi tahu Anda bahwa proses selesai tanpa error.

```java
System.out.println("Process completed Successfully");
```

## Kasus Penggunaan Umum

- **Automated schedule generation** untuk proyek berulang (misalnya sprint mingguan).  
- **Migrasi kalender CSV atau Excel lama** ke file MS Project yang lengkap fiturnya.  
- **Pelaporan sisi‑server** di mana layanan web mengembalikan file MPP sesuai permintaan.  

## Pemecahan Masalah & Jebakan Umum

| Masalah | Penyebab | Solusi |
|---------|----------|--------|
| `NullPointerException` pada `project.save` | `dataDir` mengarah ke folder yang tidak ada | Pastikan direktori ada atau buat secara programatik. |
| Kalender tidak diterapkan pada tugas | Tugas masih merujuk ke kalender default | Setelah mengatur `Prj.CALENDAR`, juga perbarui setiap `Task.CALENDAR` jika sebelumnya telah ditimpa. |
| File output berukuran 0 KB | Hak tulis tidak tersedia | Jalankan JVM dengan hak akses file yang tepat atau pilih jalur yang dapat ditulisi. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?**  
J: Ya, Aspose.Tasks untuk Java mendukung beragam versi MS Project, mulai dari Project 2007 hingga rilis terbaru, memastikan kompatibilitas yang mulus.

**T: Bisakah saya menyesuaikan kalender sesuai kebutuhan proyek tertentu?**  
J: Tentu saja. Anda dapat mendefinisikan hari kerja, mengatur minggu kerja khusus, menambahkan hari libur, dan bahkan membuat beberapa kalender dalam satu file proyek.

**T: Apakah Aspose.Tasks untuk Java menyediakan dukungan untuk pemecahan masalah dan bantuan?**  
J: Ya, Anda dapat mendapatkan bantuan melalui forum komunitas Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

**T: Apakah ada versi percobaan gratis untuk Aspose.Tasks untuk Java?**  
J: Ya, versi percobaan penuh fungsi tersedia [di sini](https://releases.aspose.com/).

**T: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Tasks untuk Java?**  
J: Lisensi sementara dapat diminta melalui situs Aspose [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-02-05  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}