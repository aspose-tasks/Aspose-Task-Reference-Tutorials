---
date: 2026-03-27
description: Pelajari cara mengekspor MPP ke SVG dalam Java dengan Aspose.Tasks. Panduan
  langkah demi langkah, contoh kode, dan tip untuk menyimpan proyek sebagai SVG dengan
  cepat.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara mengekspor MPP ke SVG di Java menggunakan Aspose.Tasks
url: /id/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengekspor MPP ke SVG di Java

## Ekspor MPP ke SVG – Pendahuluan
Dalam tutorial ini Anda akan belajar cara **mengekspor MPP ke SVG** menggunakan Aspose.Tasks untuk Java. Mengonversi file Microsoft Project (MPP) menjadi gambar Scalable Vector Graphics (SVG) memungkinkan Anda menyematkan diagram berkualitas tinggi, independen resolusi langsung ke halaman web, laporan, atau dasbor. Kami akan memandu Anda melalui pengaturan yang diperlukan, menampilkan kode yang tepat, dan menjelaskan setiap langkah sehingga Anda dapat dengan percaya diri **menyimpan proyek sebagai SVG** dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Apa arti “export MPP to SVG”?**  
  Ini mengonversi file Microsoft Project (.mpp) menjadi gambar SVG yang dapat ditampilkan di browser apa pun tanpa kehilangan kualitas.  
- **Perpustakaan mana yang menangani konversi?**  
  Aspose.Tasks untuk Java menyediakan metode `save` satu baris untuk melakukan konversi.  
- **Apakah saya memerlukan lisensi?**  
  Lisensi sementara diperlukan untuk penggunaan komersial; versi percobaan gratis tersedia.  
- **Apa prasyaratnya?**  
  Java JDK 8+ dan JAR Aspose.Tasks untuk Java.  
- **Berapa lama proses konversi?**  
  Biasanya kurang dari satu detik untuk file proyek standar.

## Apa itu “export MPP to SVG”?
Mengekspor MPP ke SVG berarti mengambil representasi visual dari jadwal proyek—tugas, garis waktu, dan sumber daya—dan menuliskannya sebagai file SVG. SVG berbasis XML, ringan, dan berskala sempurna pada tampilan resolusi tinggi.

## Mengapa mengekspor MPP ke SVG dengan Aspose.Tasks?
- **Tidak memerlukan instalasi Microsoft Project** – perpustakaan berfungsi secara independen.  
- **Fidelity penuh** – diagram, batang Gantt, dan milestone mempertahankan gaya mereka.  
- **Lintas platform** – jalankan kode di Windows, Linux, atau macOS.  
- **API satu baris** – satu panggilan menyimpan proyek sebagai SVG, cocok secara alami ke dalam pipeline Java yang ada.

## Prasyarat
- **Java Development Kit (JDK)** – versi 8 atau lebih baru. Unduh dari situs web Oracle.  
- **Aspose.Tasks untuk Java** – dapatkan perpustakaan dari halaman unduhan resmi **[di sini](https://releases.aspose.com/tasks/java/)**.  

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
Tentukan di mana file MPP sumber Anda berada dan ke mana SVG akan ditulis.

```java
String dataDir = "Your Data Directory";
```

> **Tip Pro:** Gunakan path absolut atau path relatif ke folder sumber daya proyek Anda untuk menghindari `FileNotFoundException`.

## Langkah 2: Muat File MPP
Buat instance `Project` dengan memuat file Microsoft Project yang ada.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Baris ini membaca *HomeMovePlan.mpp* dari folder yang Anda definisikan sebelumnya.

## Langkah 3: Simpan Proyek sebagai SVG
Sekarang Anda dapat **mengekspor MPP ke SVG** dengan satu perintah.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metode ini menulis `project5.svg` ke direktori yang sama. SVG yang dihasilkan dapat dibuka di browser modern apa pun atau disematkan langsung dalam HTML.

## Kasus Penggunaan Umum
- **Dasbor proyek** – sematkan diagram Gantt langsung di portal web tanpa mengharuskan klien menginstal Microsoft Project.  
- **Pelaporan otomatis** – hasilkan gambar SVG secara dinamis untuk laporan PDF atau HTML.  
- **Kolaborasi lintas tim** – bagikan jadwal visual kepada pemangku kepentingan yang hanya memerlukan browser untuk melihatnya.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **File tidak ditemukan** | Path `dataDir` tidak tepat | Pastikan string direktori diakhiri dengan pemisah (`/` atau `\\`). |
| **Output SVG kosong** | Proyek dimuat tanpa tampilan | Pastikan file MPP berisi tampilan diagram Gantt sebelum disimpan. |
| **Pengecualian lisensi** | Tidak ada lisensi yang valid diterapkan | Terapkan lisensi sementara menggunakan `License.setLicense("path/to/license.xml")` sebelum memanggil `save`. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Tasks untuk Java kompatibel dengan semua versi file Microsoft Project?**  
J: Ya, ia mendukung format MPP, MPT, dan XML dari versi lama hingga rilis Project terbaru.

**T: Bisakah saya menyesuaikan tampilan output SVG?**  
J: Tentu saja. Gunakan `SvgOptions` untuk mengatur font, warna, dan opsi tata letak sebelum memanggil `save`.

**T: Apakah Aspose.Tasks untuk Java memerlukan lisensi untuk penggunaan komersial?**  
J: Ya, lisensi yang valid diperlukan untuk produksi. Anda dapat memperoleh lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

**T: Bisakah saya mencoba Aspose.Tasks untuk Java sebelum membeli?**  
J: Ya, versi percobaan gratis tersedia **[di sini](https://purchase.aspose.com/buy)**.

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
J: Kunjungi forum komunitas **[di sini](https://forum.aspose.com/c/tasks/15)** untuk mengajukan pertanyaan dan berbagi umpan balik.

## Kesimpulan
Anda kini tahu cara **mengekspor MPP ke SVG** di Java dan secara efisien **menyimpan proyek sebagai SVG** menggunakan Aspose.Tasks. Kemampuan ini memungkinkan Anda mengintegrasikan visualisasi proyek yang kaya ke portal web, dasbor pelaporan, atau tempat lain yang memerlukan grafik skalabel. Bereksperimenlah dengan `SvgOptions` untuk menyempurnakan output, dan Anda akan memiliki alat yang kuat dalam kotak peralatan pengembangan Anda.

---

**Terakhir Diperbarui:** 2026-03-27  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.10  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}