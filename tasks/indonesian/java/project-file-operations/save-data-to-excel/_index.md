---
date: 2026-05-31
description: Pelajari cara mengekspor MPP ke Excel dan mengonversi file proyek ke
  Excel menggunakan Aspose.Tasks untuk Java. Langkah sederhana untuk pengembang Java.
keywords:
- export mpp to excel
- convert mpp to xlsx
- write excel workbook java
- project file to spreadsheet
- export project schedule excel
linktitle: Simpan Data ke Excel di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  headline: How to Export MPP to Excel with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  name: How to Export MPP to Excel with Aspose.Tasks for Java
  steps:
  - name: Define the Data Directory Path
    text: Set the folder where your `.mpp` file resides. Replace the placeholder with
      your actual path. The `dataDir` string tells the API where to locate the source
      file and where to write the resulting Excel workbook. java String dataDir =
      "Your Data Directory";
  - name: Load the Project File
    text: Create a `Project` instance by loading the `.mpp` file you want to convert.
      The `Project` class represents a Microsoft Project file in memory, allowing
      further manipulation or direct export. java Project project = new Project(dataDir
      + "project5.mpp");
  - name: Save the Project as XLSX
    text: 'Finally, export the loaded project to an Excel workbook. The `SaveFileFormat`
      enum specifies the output file format; `SaveFileFormat.Xlsx` tells Aspose.Tasks
      to generate a modern `.xlsx` file, effectively **convert MPP file to XLSX**.
      You can also specify `SaveOptions` to fine‑tune column widths or '
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides extensive APIs to read, write, and
      modify project files, including tasks, resources, calendars, and custom fields.
    question: Can I use Aspose.Tasks for Java to manipulate project data programmatically?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: The official documentation is available [here](https://reference.aspose.com/tasks/java/).
    question: Where can I find documentation for Aspose.Tasks for Java?
  - answer: Support is provided through the Aspose.Tasks forum, reachable [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for issues or queries related to Aspose.Tasks
      for Java?
  - answer: Yes, a temporary license can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java
url: /id/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java

## Pendahuluan
Aspose.Tasks for Java adalah perpustakaan yang kuat yang memungkinkan Anda **mengekspor MPP ke Excel** dengan cepat dan andal. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah tepat yang diperlukan untuk mengonversi file Microsoft Project (.mpp) menjadi buku kerja Excel (.xlsx). Pada akhir tutorial Anda akan memahami cara **mengonversi file proyek ke Excel**, mengapa konversi ini berguna, dan bagaimana mengintegrasikan proses ini ke dalam aplikasi Java apa pun.

## Jawaban Cepat
- **Apa yang dilakukan API?** Membaca file Project dan menyimpannya langsung sebagai buku kerja XLSX.  
- **Format apa yang dihasilkan?** File Excel menggunakan opsi `SaveFileFormat.Xlsx`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Apa saja prasyaratnya?** JDK terpasang dan perpustakaan Aspose.Tasks untuk Java ditambahkan ke proyek Anda.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk ekspor dasar.

## Apa itu “cara mengekspor MPP ke Excel”?
Mengekspor MPP ke Excel berarti mengambil jadwal, sumber daya, dan data tugas yang disimpan dalam file Microsoft Project dan menuliskannya ke dalam spreadsheet Excel yang terstruktur. Hal ini memudahkan berbagi data proyek dengan pemangku kepentingan yang mungkin tidak memiliki Project terpasang.

## Mengapa mengonversi file MPP ke XLSX?
Mengekspor MPP ke Excel memungkinkan Anda berbagi informasi proyek dalam format yang tersedia secara universal. **Jawaban langsung:** Mengonversi MPP ke XLSX memberi setiap pengguna bisnis kemampuan untuk membuka, mengedit, dan menganalisis data proyek dengan alat native Excel—pivot table, grafik, dan formula—tanpa perlu menginstal Microsoft Project. Ini meningkatkan aksesibilitas, mempercepat pelaporan, dan memungkinkan pipeline otomatisasi yang mengonsumsi file Excel biasa.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK)** – terpasang dan ditambahkan ke PATH sistem Anda.  
2. **Aspose.Tasks for Java library** – unduh dari [tautan unduhan](https://releases.aspose.com/tasks/java/) dan tambahkan JAR ke classpath proyek Anda.

## Impor Paket
`com.aspose.tasks` menyediakan API inti untuk menangani file Project, sementara `java.io` menyediakan utilitas sistem file.  
Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Kelas `Project` mewakili file Microsoft Project yang dimuat ke memori. Impor namespace yang diperlukan sebelum Anda mulai bekerja dengan API.

```text
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
```

## Panduan Langkah‑per‑Langkah

### Bagaimana cara mengekspor MPP ke Excel menggunakan Aspose.Tasks?
Muat file `.mpp` Anda dengan `new Project("yourfile.mpp")` dan segera panggil `project.save("output.xlsx", SaveFileFormat.Xlsx)`. Pola dua baris ini melakukan konversi penuh, mempertahankan tugas, sumber daya, dan bidang khusus. Operasi ini selesai dalam kurang dari satu detik untuk proyek dengan sekitar 100 tugas pada mesin pengembangan standar.

#### Langkah 1: Tentukan Jalur Direktori Data
Tetapkan folder tempat file `.mpp` Anda berada. Ganti placeholder dengan jalur aktual Anda. String `dataDir` memberi tahu API di mana menemukan file sumber dan di mana menulis buku kerja Excel yang dihasilkan.

```text
```java
String dataDir = "Your Data Directory";
```
```

#### Langkah 2: Muat File Proyek
Buat instance `Project` dengan memuat file `.mpp` yang ingin Anda konversi. Kelas `Project` mewakili file Microsoft Project dalam memori, memungkinkan manipulasi lebih lanjut atau ekspor langsung.

```text
```java
Project project = new Project(dataDir + "project5.mpp");
```
```

#### Langkah 3: Simpan Proyek sebagai XLSX
Akhirnya, ekspor proyek yang dimuat ke buku kerja Excel. Enum `SaveFileFormat` menentukan format file output; `SaveFileFormat.Xlsx` memberi tahu Aspose.Tasks untuk menghasilkan file `.xlsx` modern, secara efektif **mengonversi file MPP ke XLSX**. Anda juga dapat menentukan `SaveOptions` untuk menyesuaikan lebar kolom atau menyertakan hanya tabel tertentu.

```text
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
```

## Kasus Penggunaan Umum
- **Pelaporan eksekutif:** Menyediakan snapshot proyek tingkat tinggi dalam Excel untuk manajemen senior.  
- **Analisis data:** Mengirim data tugas dan sumber daya ke Power Query Excel untuk wawasan yang lebih mendalam.  
- **Integrasi:** Mengirim file Excel yang diekspor ke sistem hilir yang hanya menerima input CSV/Excel.

## Tips & Praktik Terbaik Tambahan
- **Tip kinerja:** Untuk proyek dengan lebih dari 500 tugas, aktifkan `project.setReadWriteMode(ReadWriteMode.MemoryOptimized)` untuk mengurangi konsumsi memori. `ReadWriteMode.MemoryOptimized` meminimalkan penggunaan RAM saat menangani proyek besar.  
- **Tip pemformatan:** Gunakan `project.save("output.xlsx", SaveFileFormat.Xlsx, new XlsxSaveOptions { ExportAllFields = true })` untuk menyertakan bidang khusus dalam ekspor. `XlsxSaveOptions` memungkinkan Anda menyesuaikan ekspor Excel, seperti mengekspor semua bidang.  
- **Penanganan error:** Bungkus panggilan load dan save dalam blok try‑catch untuk menangkap `FileNotFoundException` atau `LicenseException` dan memberikan umpan balik pengguna yang jelas.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java untuk memanipulasi data proyek secara programatis?**  
A: Ya, Aspose.Tasks untuk Java menyediakan API yang luas untuk membaca, menulis, dan memodifikasi file proyek, termasuk tugas, sumber daya, kalender, dan bidang khusus.

**Q: Apakah tersedia versi percobaan gratis untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks untuk Java dari [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk Java?**  
A: Dokumentasi resmi tersedia [di sini](https://reference.aspose.com/tasks/java/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk masalah atau pertanyaan terkait Aspose.Tasks untuk Java?**  
A: Dukungan disediakan melalui forum Aspose.Tasks, dapat diakses [di sini](https://forum.aspose.com/c/tasks/15).

**Q: Apakah saya dapat membeli lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Ya, lisensi sementara dapat diperoleh dari [di sini](https://purchase.aspose.com/temporary-license/).

## Kesimpulan
Dalam panduan ini kami menunjukkan **cara mengekspor MPP ke Excel** menggunakan Aspose.Tasks untuk Java. Dengan mengikuti tiga langkah sederhana—menentukan direktori data, memuat file Proyek, dan menyimpannya sebagai XLSX—Anda dapat dengan mudah **mengekspor data proyek ke Excel** dan memberdayakan tim Anda dengan laporan yang fleksibel dan dapat dibagikan. Kemampuan perpustakaan untuk **menulis kode Java gaya workbook Excel** membuat integrasi menjadi mulus untuk alur kerja berbasis Java apa pun.

---

**Terakhir Diperbarui:** 2026-05-31  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat File MPP – Membuat & Menyimpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspose.Tasks untuk Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}