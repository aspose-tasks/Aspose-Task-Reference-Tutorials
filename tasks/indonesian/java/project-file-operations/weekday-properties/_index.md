---
date: 2026-03-29
description: Pelajari cara mengubah hari per bulan dan mengelola properti hari kerja
  lainnya di Aspose.Tasks untuk Java. Sesuaikan tanggal mulai minggu, ubah kalender
  proyek, dan simpan proyek sebagai XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ubah Hari Per Bulan dengan Properti Hari Minggu Aspose.Tasks
url: /id/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ubah Hari Per Bulan dengan Properti Hari Minggu Aspose.Tasks

## Pendahuluan
Aspose.Tasks for Java memungkinkan Anda **mengubah hari per bulan** dan menyesuaikan pengaturan hari minggu lainnya tanpa perlu menginstal Microsoft Project. Baik Anda menyelaraskan kalender proyek dengan bulan fiskal yang tidak standar atau hanya perlu menyesuaikan hari mulai minggu, tutorial ini memandu Anda melalui skenario paling umum—mengambil hari mulai minggu saat ini, menyesuaikan tanggal mulai minggu, memodifikasi kalender proyek, dan menyimpan proyek sebagai XML.

## Jawaban Cepat
- **Apakah saya dapat mengubah jumlah hari per bulan?** Ya, gunakan `Prj.DAYS_PER_MONTH` pada objek `Project`.  
- **Bagaimana cara menyesuaikan tanggal mulai minggu?** Atur `Prj.WEEK_START_DAY` ke nilai `DayType` (misalnya, `DayType.Monday`).  
- **Format apa yang dapat saya gunakan untuk mengekspor proyek?** Contoh ini menyimpan file sebagai XML dengan `SaveFileFormat.Xml`.  
- **Apakah lisensi diperlukan untuk penggunaan produksi?** Lisensi Aspose.Tasks yang valid diperlukan untuk penyebaran non‑evaluasi.  
- **IDE mana yang didukung?** Semua IDE Java seperti IntelliJ IDEA, Eclipse, atau NetBeans dapat digunakan.

## Apa itu “ubah hari per bulan” dalam Aspose.Tasks?
Mengubah hari per bulan berarti memperbarui properti `Prj.DAYS_PER_MONTH` dari sebuah instance `Project`. Properti ini memberi tahu mesin berapa banyak hari kerja yang harus dipertimbangkan setiap bulan, yang secara langsung memengaruhi penjadwalan tugas dan perhitungan biaya.

## Mengapa memodifikasi properti kalender proyek?
Menyesuaikan kalender proyek—seperti mengatur hari mulai minggu yang berbeda atau mengubah menit per hari—membantu Anda:

- Menyelaraskan jadwal dengan minggu kerja regional.  
- Memodelkan pola kerja non‑standar (misalnya, minggu 4‑hari).  
- Menjamin pelaporan yang akurat untuk kontrak yang menggunakan kalender khusus.

## Prasyarat
- **Java Development Kit (JDK)** – Instal JDK terbaru dari Oracle.  
- **Aspose.Tasks for Java library** – Unduh dari situs resmi [here](https://releases.aspose.com/tasks/java/).  
- **IDE pilihan Anda** – IntelliJ IDEA, Eclipse, atau NetBeans.

## Impor Paket
Pertama, impor kelas-kelas Aspose.Tasks yang penting:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Langkah 1: Muat File Proyek
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Ini memuat file Microsoft Project yang ada (`project.mpp`) dari folder yang Anda tentukan.

## Langkah 2: Tampilkan Properti Hari Minggu
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Di sini kami mengambil dan mencetak pengaturan hari minggu saat ini, termasuk **hari mulai minggu** dan **hari per bulan**.

## Langkah 3: Mengatur Properti Hari Minggu
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Pada langkah ini kami **mengubah hari per bulan** menjadi 24, mengatur minggu mulai pada Senin, dan menyesuaikan menit per hari/minggu. Ini menunjukkan cara **memodifikasi kalender proyek** secara programatis.

## Langkah 4: Simpan Proyek
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Proyek yang dimodifikasi disimpan menggunakan format **save project as XML**, yang berguna untuk integrasi dengan alat lain atau penyimpanan yang dikontrol versi.

## Langkah 5: Tampilkan Hasil
```java
System.out.println("Process completed Successfully");
```
Konfirmasi sederhana bahwa operasi selesai tanpa error.

## Cara Menyesuaikan Tanggal Mulai Minggu
Jika organisasi Anda menggunakan kalender yang dimulai pada hari Minggu, ganti `DayType.Monday` dengan `DayType.Sunday`. Properti yang sama (`Prj.WEEK_START_DAY`) digunakan, sehingga perubahan menjadi sederhana.

## Cara Mengambil Hari Mulai Minggu
Anda dapat memanggil `project.get(Prj.WEEK_START_DAY)` kapan saja untuk **mengambil informasi hari mulai minggu**, seperti yang ditunjukkan pada Langkah 2.

## Cara Memodifikasi Kalender Proyek
Selain hari mulai minggu, Anda juga dapat menyesuaikan `Prj.MINUTES_PER_DAY` dan `Prj.MINUTES_PER_WEEK` untuk mencerminkan jam kerja khusus atau pola shift.

## Masalah Umum dan Solusi
- **Nilai tipe hari tidak tepat** – Pastikan Anda menggunakan enum `DayType` (misalnya, `DayType.Monday`).  
- **Kesalahan jalur file** – Verifikasi bahwa `dataDir` diakhiri dengan pemisah file yang tepat (`/` atau `\`).  
- **Lisensi belum diatur** – Jika Anda melihat peringatan lisensi, daftarkan lisensi Aspose.Tasks Anda sebelum membuat objek `Project`.

## Pertanyaan yang Sering Diajukan

**Q: Dapatkah Aspose.Tasks for Java menangani struktur proyek yang kompleks?**  
A: Ya, Aspose.Tasks for Java menyediakan dukungan komprehensif untuk menangani struktur proyek yang kompleks dengan mudah.

**Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai versi file Microsoft Project?**  
A: Tentu saja, Aspose.Tasks for Java mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di seluruh platform.

**Q: Bisakah saya mengintegrasikan Aspose.Tasks for Java ke dalam aplikasi Java saya yang sudah ada?**  
A: Ya, Aspose.Tasks for Java menawarkan kemampuan integrasi yang mulus, memungkinkan Anda meningkatkan aplikasi Java dengan fitur manajemen proyek yang kuat.

**Q: Apakah Aspose.Tasks for Java menyediakan dokumentasi dan dukungan?**  
A: Ya, Anda dapat mengakses dokumentasi lengkap dan dukungan komunitas untuk Aspose.Tasks for Java di [website](https://releases.aspose.com/).

**Q: Apakah ada versi percobaan gratis untuk Aspose.Tasks for Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks for Java dari [website](https://reference.aspose.com/tasks/java/) untuk menjelajahi fiturnya sebelum melakukan pembelian.

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}