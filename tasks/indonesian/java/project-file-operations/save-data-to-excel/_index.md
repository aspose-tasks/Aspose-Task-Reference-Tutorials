---
date: 2025-12-21
description: Pelajari cara mengekspor MPP ke Excel dan mengonversi file proyek ke
  Excel menggunakan Aspose.Tasks untuk Java. Langkah sederhana untuk pengembang Java.
linktitle: Save Data to Excel in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java
url: /id/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java

## Perkenalan
Aspose.Tasks untuk Java adalah perpustakaan kuat yang memungkinkan Anda **mengekspor MPP ke Excel** dengan cepat dan andal. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah tepat yang diperlukan untuk mengubah file Microsoft Project (.mpp) menjadi buku kerja Excel (.xlsx). Pada akhir tutorial Anda akan memahami cara **mengonversi file proyek ke Excel**, mengapa konversi ini berguna, dan bagaimana mengintegrasikan proses ini ke dalam aplikasi Java apa pun.

## Jawaban Cepat
- **Apa fungsi API?** Ia membaca file Proyek dan menyimpannya langsung sebagai buku kerja XLSX.
- **Format apa yang dihasilkan?** File Excel menggunakan opsi `SaveFileFormat.Xlsx`.
- **Apakah saya memerlukan lisensi?** Uji coba berfungsi untuk pengujian; izin komersial diperlukan untuk produksi.
- **Apa saja prasyaratnya?** JDK diinstal dan Aspose.Tasks untuk perpustakaan Java ditambahkan ke proyek Anda.
- **Berapa lama waktu penerapannya?** Biasanya kurang dari 10 menit untuk ekspor dasar.

## Apa itu “cara mengekspor MPP ke Excel”?
Mengekspor MPP ke Excel berarti mengambil jadwal, sumber daya, dan tugas data yang disimpan dalam file Microsoft Project dan menuliskannya ke dalam spreadsheet Excel yang terstruktur. Hal ini memudahkan berbagi data proyek dengan pemangku kepentingan yang mungkin tidak memiliki Proyek terpasang.

## Mengapa mengonversi file MPP ke XLSX?
- **Aksesibilitas yang lebih luas:** Excel ada di mana-mana dalam lingkungan bisnis.
- **Pelaporan yang disederhanakan:** Gunakan tabel pivot, bagan, dan rumus Excel untuk menganalisis metrik proyek.
- **Ramah otomatisasi:** File Excel dapat diproses oleh sistem atau skrip lain tanpa memerlukan Project.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK)** – terpasang dan ditambahkan ke sistem PATH Anda.
2. **Aspose.Tasks untuk perpustakaan Java** – unduh dari [tautan unduh](https://releases.aspose.com/tasks/java/) dan tambahkan JAR ke proyek classpath Anda.

## Impor Paket
Pertama, impor kelas‑kelas yang Anda perlukan. Pertahankan blok ini tetap seperti yang ditampilkan – diperlukan agar API berfungsi.

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Panduan Langkah demi Langkah

### Langkah 1: Tentukan Jalur Direktori Data
Tetapkan folder tempat file `.mpp` Anda berada. Ganti placeholder dengan jalur aktual Anda.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Muat File Proyek
Buat instance `Project` dengan memuat file `.mpp` yang ingin Anda konversi. Ini akan membaca semua tugas, sumber daya, dan informasi penjadwalan.

```java
Project project = new Project(dataDir + "project5.mpp");
```

### Langkah 3: Simpan Proyek sebagai XLSX
Akhirnya, ekspor proyek yang sudah dimuat ke buku kerja Excel. Flag `SaveFileFormat.Xlsx` memberi tahu Aspose.Tasks untuk menghasilkan file `.xlsx` modern, secara efektif **mengonversi file MPP ke XLSX**.

```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```

## Kasus Penggunaan Umum
- **Pelaporan eksekutif:** Menyediakan ringkasan proyek tingkat tinggi di Excel untuk manajemen senior.
- **Analisis data:** Masukkan data tugas dan sumber daya ke Power Query Excel untuk wawasan yang lebih mendalam.
- **Integrasi:** Meneruskan file Excel yang diekspor ke sistem hilir yang hanya menerima masukan CSV/Excel.

## Kesimpulan
Dalam panduan ini kami menunjukkan **cara mengekspor MPP ke Excel** menggunakan Aspose.Tasks untuk Java. Dengan mengikuti tiga langkah sederhana—menentukan direktori data, memuat file Project, dan menyimpannya sebagai XLSX—Anda dapat dengan mudah **mengekspor data proyek ke Excel** dan memberi tim Anda laporan yang fleksibel serta dapat diiklankan.

## FAQ
### Dapatkah saya menggunakan Aspose.Tasks untuk Java untuk memanipulasi data proyek secara terprogram?
Ya, Aspose.Tasks untuk Java menyediakan fitur ekstensif untuk memanipulasi data proyek, termasuk membaca, menulis, dan memodifikasi file proyek.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java? 

Ya, Anda dapat mengunduh versi uji coba gratis Aspose.Tasks untuk Java dari [sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk Java?

Anda dapat menemukan dokumentasi untuk Aspose.Tasks untuk Java [sini](https://reference.aspose.com/tasks/java/).

### Bagaimana saya bisa mendapatkan dukungan untuk masalah atau pertanyaan apa pun terkait Aspose.Tasks untuk Java?

Anda bisa mendapatkan dukungan dengan mengunjungi forum Aspose.Tasks [sini](https://forum.aspose.com/c/tasks/15).

### Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?

Ya, Anda dapat membeli lisensi sementara dari [sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2025-12-21
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (versi terbaru pada saat penulisan)
**Pengarang:** Aspose 

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
