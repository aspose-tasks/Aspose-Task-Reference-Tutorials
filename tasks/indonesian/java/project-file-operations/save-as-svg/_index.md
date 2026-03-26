---
date: 2025-12-21
description: Pelajari cara membuat SVG dari file MPP di Java dan menyimpan proyek
  sebagai SVG menggunakan pustaka Aspose.Tasks. Panduan langkah demi langkah dengan
  contoh kode.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara membuat SVG dari MPP di Java menggunakan Aspose.Tasks
url: /id/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat SVG dari MPP di Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **create SVG from MPP** file menggunakan Aspose.Tasks for Java. Mengonversi file Microsoft Project (MPP) ke scalable vector graphics (SVG) memungkinkan Anda menyematkan diagram berkualitas tinggi dan independen resolusi langsung ke halaman web, laporan, atau dasbor. Kami akan membimbing melalui pengaturan yang diperlukan, menampilkan kode tepat yang Anda butuhkan, dan menjelaskan setiap langkah sehingga Anda dapat dengan percaya diri **save project as SVG** dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Apa arti “create SVG from MPP”?**  
  Itu mengonversi file Microsoft Project (.mpp) menjadi gambar SVG yang dapat ditampilkan di browser apa pun tanpa kehilangan kualitas.  
- **Perpustakaan mana yang menangani konversi?**  
  Aspose.Tasks for Java menyediakan metode `save` satu baris untuk melakukan konversi.  
- **Apakah saya memerlukan lisensi?**  
  Lisensi sementara diperlukan untuk penggunaan komersial; versi percobaan gratis tersedia.  
- **Apa prasyaratnya?**  
  Java JDK 8+ dan JAR Aspose.Tasks for Java.  
- **Berapa lama proses konversi?**  
  Biasanya kurang dari satu detik untuk file proyek standar.

## Apa itu “create SVG from MPP”?
Membuat SVG dari file MPP berarti mengekspor representasi visual dari jadwal proyek—tugas, garis waktu, dan sumber daya—ke dalam format Scalable Vector Graphics. SVG berbasis XML, ringan, dan dapat diskalakan dengan sempurna pada tampilan beresolusi tinggi.

## Mengapa menggunakan Aspose.Tasks untuk menyimpan proyek sebagai SVG?
- **Tidak memerlukan instalasi Microsoft Project** – perpustakaan ini bekerja secara independen.  
- **Fidelity penuh** – grafik, batang Gantt, dan milestone mempertahankan gaya mereka.  
- **Cross‑platform** – jalankan kode di Windows, Linux, atau macOS.  
- **Integrasi mudah** – panggilan API satu baris cocok secara alami ke dalam pipeline Java yang ada.

## Prasyarat
- **Java Development Kit (JDK)** – versi 8 atau lebih baru. Unduh dari situs web Oracle.  
- **Aspose.Tasks for Java** – dapatkan perpustakaan dari halaman unduhan resmi **[here](https://releases.aspose.com/tasks/java/)**.  

## Impor Paket
Pertama, impor kelas yang Anda perlukan. Blok impor tetap tidak berubah.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Langkah 1: Tentukan Direktori Data
Tentukan di mana file MPP sumber Anda berada dan di mana SVG akan ditulis.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Gunakan path absolut atau path relatif ke folder sumber daya proyek Anda untuk menghindari `FileNotFoundException`.

## Langkah 2: Muat File MPP
Buat instance `Project` dengan memuat file Microsoft Project yang ada.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Baris ini membaca *HomeMovePlan.mpp* dari folder yang Anda tentukan sebelumnya.

## Langkah 3: Simpan Proyek sebagai SVG
Sekarang Anda dapat **save project as SVG** dengan satu perintah.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metode ini menulis `project5.svg` ke direktori yang sama. SVG yang dihasilkan dapat dibuka di browser modern apa pun atau disematkan langsung dalam HTML.

## Masalah Umum dan Solusinya
| Issue | Reason | Fix |
|-------|--------|-----|
| **File tidak ditemukan** | Path `dataDir` tidak benar | Pastikan string direktori diakhiri dengan pemisah (`/` atau `\\`). |
| **Output SVG kosong** | Proyek dimuat tanpa tampilan | Pastikan file MPP berisi tampilan diagram Gantt sebelum menyimpan. |
| **Pengecualian lisensi** | Tidak ada lisensi yang valid diterapkan | Terapkan lisensi sementara menggunakan `License.setLicense("path/to/license.xml")` sebelum memanggil `save`. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Tasks for Java kompatibel dengan semua versi file Microsoft Project?**  
A: Ya, ia mendukung format MPP, MPT, dan XML dari versi lama hingga rilis Project terbaru.

**Q: Bisakah saya menyesuaikan tampilan output SVG?**  
A: Tentu saja. Gunakan `SvgOptions` untuk mengatur font, warna, dan opsi tata letak sebelum memanggil `save`.

**Q: Apakah Aspose.Tasks for Java memerlukan lisensi untuk penggunaan komersial?**  
A: Ya, lisensi yang valid diperlukan untuk produksi. Anda dapat memperoleh lisensi sementara **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Bisakah saya mencoba Aspose.Tasks for Java sebelum membeli?**  
A: Ya, percobaan gratis tersedia **[here](https://purchase.aspose.com/buy)**.

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks for Java?**  
A: Kunjungi forum komunitas **[here](https://forum.aspose.com/c/tasks/15)** untuk mengajukan pertanyaan dan berbagi umpan balik.

## Kesimpulan
Anda sekarang tahu cara **create SVG from MPP** file di Java dan secara efisien **save project as SVG** menggunakan Aspose.Tasks. Kemampuan ini memungkinkan Anda mengintegrasikan visualisasi proyek yang kaya ke dalam portal web, dasbor pelaporan, atau tempat mana pun yang membutuhkan grafik skalabel. Bereksperimenlah dengan `SvgOptions` untuk menyempurnakan output, dan Anda akan memiliki alat yang kuat dalam toolkit pengembangan Anda.

---

**Terakhir Diperbarui:** 2025-12-21  
**Diuji Dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}