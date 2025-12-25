---
date: 2025-12-25
description: Pelajari cara mengelola properti tahun fiskal dan memuat file MPP secara
  efisien menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah dengan
  contoh.
linktitle: Manage Fiscal Year Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Kelola Properti Tahun Fiskal di Aspose.Tasks
url: /id/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Properti Tahun Fiskal di Aspose.Tasks

## Pendahuluan
Aspose.Tasks adalah perpustakaan Java yang kuat yang memungkinkan pengembang untuk **mengelola tahun fiskal** pengaturan, memuat file MPP, dan mengonversi data proyek ke XML dengan hanya beberapa baris kode. Dalam tutorial ini Anda akan melihat secara tepat cara mengatur properti tahun fiskal, menampilkan informasi tahun fiskal, dan menyimpan hasilnya—semua sambil menjaga kode Anda tetap bersih dan dapat dipelihara.

## Jawaban Cepat
- **Apa arti “manage fiscal year” dalam Aspose.Tasks?** Ini memungkinkan Anda menentukan bulan mulai tahun fiskal dan mengaktifkan penomoran tahun fiskal untuk sebuah proyek.  
- **Bagaimana cara mengatur bulan mulai tahun fiskal?** Gunakan properti `Prj.FY_START_DATE` dengan nilai enum `Month` (misalnya, `Month.JULY`).  
- **Bisakah saya memuat file MPP?** Ya, cukup buat instance `Project` dengan path ke file *.mpp*.  
- **Bagaimana cara mengonversi MPP ke XML?** Panggil `project.save(..., SaveFileFormat.Xml)` setelah mengatur properti yang diinginkan.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.

## Apa itu “manage fiscal year” dalam file proyek?
Mengelola tahun fiskal berarti mengonfigurasi kalender yang diikuti proyek Anda untuk pelaporan keuangan. Ini mencakup pengaturan bulan mulai tahun fiskal dan secara opsional mengaktifkan penomoran tahun fiskal, yang memengaruhi cara tanggal dihitung dan ditampilkan dalam laporan.

## Mengapa menggunakan Aspose.Tasks untuk penanganan tahun fiskal?
- **Tidak memerlukan Microsoft Project** – bekerja dengan file proyek secara langsung di Java.  
- **Kontrol penuh** – mengatur awal tahun fiskal, mengaktifkan penomoran, dan mengonversi format secara programatis.  
- **API yang kuat** – penanganan file MPP besar yang andal dan ekspor XML yang mulus.

## Prasyarat
1. Java Development Kit (JDK) terpasang di sistem Anda.  
2. Aspose.Tasks for Java JAR – unduh dari [here](https://releases.aspose.com/tasks/java/) dan tambahkan ke classpath proyek Anda.

## Impor Paket
Untuk memulai, impor kelas yang diperlukan dalam file sumber Java Anda:
```java
import com.aspose.tasks.*;
```

## Cara memuat file MPP dan menampilkan informasi tahun fiskal
Di bawah ini kami memecah proses menjadi langkah-langkah berurutan yang jelas.

### Langkah 1: Muat File Proyek
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Di sini kami **memuat file MPP** (`project.mpp`) dari direktori yang ditentukan. Ini adalah langkah pertama dalam setiap manipulasi yang terkait dengan tahun fiskal.

### Langkah 2: Tampilkan Properti Tahun Fiskal
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Properti `Prj.FY_START_DATE` dan `Prj.FISCAL_YEAR_START` memungkinkan Anda **menampilkan detail tahun fiskal**, menjawab pertanyaan “apa konfigurasi fiskal saat ini?”.

### Langkah 3: Atur Awal Tahun Fiskal dan Aktifkan Penomoran
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Pada langkah ini kami **menunjukkan cara mengatur** pengaturan fiskal:
- `Month.JULY` menentukan bulan mulai tahun fiskal.  
- `NullableBool(true)` mengaktifkan penomoran tahun fiskal.  
- Akhirnya, proyek **dikonversi dari MPP ke XML** menggunakan `SaveFileFormat.Xml`.

### Langkah 4: Konfirmasi Operasi
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Pesan konsol sederhana mengonfirmasi bahwa tahun fiskal telah dikonfigurasi dan file telah disimpan.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Nilai bulan tidak tepat** | Pastikan Anda menggunakan enum `Month` (misalnya, `Month.JANUARY`). |
| **File tidak ditemukan** | Verifikasi `dataDir` mengarah ke folder yang benar dan nama file cocok. |
| **Gagal menyimpan** | Periksa izin menulis pada direktori target dan pastikan `SaveFileFormat` didukung. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java untuk memanipulasi properti proyek lainnya?**  
A: Ya, Aspose.Tasks menyediakan fungsionalitas komprehensif untuk mengelola berbagai properti proyek di luar pengaturan tahun fiskal.

**Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai format file proyek?**  
A: Ya, ia mendukung berbagai format termasuk MPP, XML, dan lainnya.

**Q: Bagaimana saya dapat mendapatkan dukungan jika saya mengalami masalah saat menggunakan Aspose.Tasks untuk Java?**  
A: Anda dapat mencari bantuan dari komunitas Aspose.Tasks di [forum](https://forum.aspose.com/c/tasks/15) atau menghubungi tim dukungan mereka secara langsung.

**Q: Apakah Aspose.Tasks menawarkan versi percobaan gratis?**  
A: Ya, Anda dapat mengakses versi percobaan gratis Aspose.Tasks dari [here](https://releases.aspose.com/).

**Q: Di mana saya dapat membeli lisensi untuk Aspose.Tasks untuk Java?**  
A: Anda dapat membeli lisensi untuk Aspase.Tasks untuk Java dari [here](https://purchase.aspose.com/buy).

## Kesimpulan
Mengelola properti tahun fiskal di Aspose.Tasks untuk Java sangat sederhana. Dengan mengikuti langkah-langkah di atas Anda dapat **mengelola tahun fiskal**, **memuat file MPP**, **menampilkan detail tahun fiskal**, dan **mengonversi MPP ke XML** dengan percaya diri. Gunakan teknik ini untuk menjaga jadwal proyek Anda tetap selaras dengan kalender keuangan organisasi Anda.

---

**Terakhir Diperbarui:** 2025-12-25  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}