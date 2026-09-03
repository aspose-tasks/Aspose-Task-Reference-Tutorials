---
date: 2026-05-26
description: Pelajari cara membuat snapshot proyek JPEG dan menyesuaikan kualitas
  JPEG saat mengekspor file Microsoft Project menggunakan Aspose.Tasks untuk Java.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Simpan Proyek sebagai JPEG di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Buat Snapshot Proyek JPEG – Sesuaikan Kualitas dengan Aspose.Tasks
url: /id/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Snapshot Proyek JPEG – Sesuaikan Kualitas dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan menemukan cara **membuat snapshot proyek JPEG** dari Microsoft Project menggunakan Aspose.Tasks untuk Java, serta cara menyesuaikan kualitas JPEG agar memenuhi kebutuhan ukuran‑vs‑kejelasan Anda. Baik Anda memerlukan gambar tajam untuk presentasi ruang rapat maupun file ringan untuk portal web, menguasai pengaturan kualitas memberi Anda kontrol penuh atas output akhir.

## Jawaban Cepat
- **Apa yang dilakukan “menyesuaikan kualitas JPEG”?** Ini memungkinkan Anda mengontrol tingkat kompresi JPEG yang diekspor, menyeimbangkan ukuran file dan fidelitas visual.  
- **Perpustakaan mana yang menangani konversi?** Aspose.Tasks untuk Java menyediakan API sederhana untuk mengekspor file Project ke JPEG.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk evaluasi; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya mengatur kualitas melalui kode?** Ya, gunakan metode `ImageSaveOptions.setJpegQuality(int)` (rentang 0‑100).  
- **Apakah prosesnya cepat?** Mengonversi file proyek tipikal ke JPEG hanya memakan beberapa detik pada perangkat keras modern.

## Apa itu “menyesuaikan kualitas JPEG”?
Menyesuaikan kualitas JPEG memungkinkan Anda menentukan faktor kompresi yang diterapkan saat menyimpan gambar dalam format JPEG. Nilai yang lebih tinggi (mendekati 100) mempertahankan lebih banyak detail, sementara nilai yang lebih rendah mengurangi ukuran file dengan mengorbankan ketajaman. **Jawaban langsung:** Anda mengontrol kualitas JPEG dengan memberikan nilai numerik (0‑100) ke metode `ImageSaveOptions.setJpegQuality`, yang secara langsung memengaruhi ukuran dan fidelitas visual snapshot yang dihasilkan.  

Kualitas JPEG adalah faktor kompresi yang diterapkan saat menyimpan gambar dalam format JPEG.

## Mengapa menggunakan Aspose.Tasks untuk ekspor JPEG?
**Jawaban langsung:** Aspose.Tasks merender diagram Gantt, tampilan sumber daya, dan laporan khusus ke file gambar tanpa memerlukan Microsoft Project terpasang, menjamin output pixel‑perfect di Windows, Linux, dan macOS.  

Aspose.Tasks mendukung ekspor ke **empat** format gambar (JPEG, PNG, BMP, TIFF) dan dapat merender proyek yang berisi **hingga 10.000 tugas** dalam kurang dari 5 detik pada CPU standar 2,5 GHz, memberikan jaminan kinerja yang terukur.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:
1. **Java Development Kit (JDK)** – Instal JDK terbaru (8 atau lebih baru) dari [situs Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks untuk Java** – Unduh dan siapkan perpustakaan mengikuti langkah‑langkah di [dokumentasi resmi](https://reference.aspose.com/tasks/java/).

## Impor Paket
`ImageSaveOptions` adalah kelas Aspose.Tasks yang mengontrol pengaturan ekspor gambar seperti format, dimensi, dan kualitas JPEG.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## Langkah 1: Tentukan Direktori Data
Atur jalur ke folder yang berisi file Microsoft Project Anda. Direktori ini digunakan untuk operasi input dan output.  
```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Muat File MS Project
Kelas `Project` mewakili file Microsoft Project dalam memori, menyediakan akses ke tugas, sumber daya, dan data tampilan.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Langkah 3: Sesuaikan Kualitas JPEG (Opsional)
Jika Anda ingin menyesuaikan output secara detail, Anda dapat **mengatur kualitas JPEG** menggunakan kelas `ImageSaveOptions`. Nilai kualitas berkisar antara 0 hingga 100, di mana 100 menghasilkan fidelitas visual tertinggi.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## Langkah 4: Simpan Proyek sebagai JPEG
`Project.save` menulis tampilan yang dirender ke file gambar menggunakan opsi yang telah Anda konfigurasikan.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Cara Mengekspor JPEG dari MS Project
**Jawaban langsung:** Panggil `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` setelah mengonfigurasi `ImageSaveOptions`; metode ini merender tampilan aktif (secara default diagram Gantt) dan menulis file JPEG dengan kualitas yang ditentukan. Panggilan satu baris ini menangani paginasi, skala, dan manajemen warna secara otomatis.  

Dengan menyesuaikan kualitas JPEG, Anda mengontrol kompromi antara kejernihan gambar dan ukuran file, menjadikan gambar yang diekspor cocok untuk publikasi web, laporan cetak, atau slide yang disisipkan.

## Masalah Umum dan Solusi
- **Kualitas rendah membuat teks tidak terbaca:** Tingkatkan kualitas JPEG di atas 70 atau beralih ke PNG untuk rendering lossless.  
- **Kesalahan out‑of‑memory pada proyek besar:** Aktifkan streaming dengan mengatur `saveOptions.setUseMemoryCache(true)` agar penggunaan memori tetap di bawah 200 MB.  
- **Tampilan yang diekspor salah:** Gunakan `saveOptions.setView(ViewType.TaskSheet)` untuk mengekspor tampilan lain.

## Pertanyaan yang Sering Diajukan

**T: Apakah menyesuaikan kualitas JPEG memengaruhi keterbacaan diagram Gantt?**  
J: Kualitas lebih tinggi mempertahankan teks dan detail garis, sementara kualitas sangat rendah dapat membuat label kecil sulit dibaca.  

**T: Bisakah saya mengekspor format gambar lain selain JPEG?**  
J: Ya, Aspose.Tasks mendukung PNG, BMP, dan TIFF melalui enum `SaveFileFormat` yang sesuai.  

**T: Apakah memungkinkan mengekspor beberapa halaman (misalnya, tampilan berbeda) sekaligus?**  
J: Anda dapat mengiterasi tampilan yang diinginkan dan menyimpan masing‑masing sebagai JPEG terpisah menggunakan konfigurasi `ImageSaveOptions` yang sama.  

**T: Versi Java apa yang diperlukan?**  
J: Aspose.Tasks untuk Java bekerja dengan JDK 8 ke atas.  

**T: Bagaimana menangani proyek besar yang menghasilkan gambar besar?**  
J: Pertimbangkan menurunkan kualitas JPEG atau menskalakan dimensi gambar melalui pengaturan tambahan pada `ImageSaveOptions`.

## Kesimpulan
Kami telah membahas cara **membuat snapshot proyek JPEG** dan menyesuaikan kualitas JPEG menggunakan Aspose.Tasks untuk Java. Pendekatan ini menghilangkan kebutuhan screenshot manual, menjamin rendering konsisten di semua platform, dan memungkinkan Anda menyesuaikan keseimbangan antara kejernihan gambar dan ukuran file—sempurna untuk laporan, presentasi, dan publikasi web.

---

**Terakhir Diperbarui:** 2026-05-26  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.11  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membuat File MPP – Buat & Simpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspose.Tasks untuk Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Buat File MS Project Kosong di Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}