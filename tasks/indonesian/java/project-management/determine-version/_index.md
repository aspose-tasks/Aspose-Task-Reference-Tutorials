---
date: 2026-05-31
description: Pelajari cara mendapatkan versi proyek dan mengambil tanggal terakhir
  disimpan dari file MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah
  demi langkah dengan contoh kode.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Tentukan Versi Proyek dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Mendapatkan Versi Proyek – Aspose Tasks Java Tutorial
url: /id/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mendapatkan Versi Proyek – Tutorial Aspose Tasks Java

Dalam **tutorial Aspose Tasks Java** ini Anda akan belajar **cara mendapatkan versi proyek** dari file Microsoft Project dan juga cara **mengambil tanggal terakhir disimpan** menggunakan pustaka Aspose.Tasks untuk Java. Mengetahui versi file dan cap waktu penyimpanan membantu Anda menghindari masalah kompatibilitas, menegakkan kebijakan migrasi, dan menjaga log audit yang akurat. Kami akan membimbing Anda melalui setiap langkah—dari penyiapan lingkungan hingga mencetak versi dan tanggal—sehingga Anda dapat menyematkan pemeriksaan ini ke dalam aplikasi Java apa pun dengan percaya diri.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menentukan versi file MS Project dan tanggal terakhir disimpan dengan Aspose.Tasks untuk Java.  
- **Apakah saya perlu menginstal Microsoft Project?** Tidak, Aspose.Tasks berfungsi secara independen dari Microsoft Project.  
- **Format file apa yang didukung?** File Project berbasis XML seperti MPP dan XML didukung sepenuhnya.  
- **Berapa lama waktu implementasinya?** Sekitar 5‑10 menit untuk pemeriksaan versi dasar.  
- **Apakah diperlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi komersial diperlukan untuk penggunaan produksi.

## Apa itu Tutorial Aspose Tasks Java?
Tutorial Java `Aspose.Tasks` adalah panduan singkat dan praktis yang menunjukkan cara berinteraksi dengan data Microsoft Project secara programatik. Ini menunjukkan cara membaca, memodifikasi, dan menganalisis informasi proyek tanpa perlu menginstal Microsoft Project di server. Selain itu, tutorial ini mencakup pemuatan file, mengakses properti, dan menyimpan perubahan, memungkinkan pengembang mengotomatisasi tugas manajemen proyek secara efisien.

## Mengapa menggunakan Aspose.Tasks untuk menentukan versi proyek?
Aspose.Tasks menyediakan **metadata versi yang tepat** dan **cap waktu terakhir disimpan** sambil berjalan pada sistem operasi apa pun yang mendukung Java. Ia memproses file hingga **500 halaman dalam kurang dari 2 detik** pada CPU standar 2,5 GHz, menjadikannya ideal untuk otomatisasi batch dan skenario migrasi skala besar.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru.  
2. **Aspose.Tasks for Java JAR** – unduh dari [situs web](https://releases.aspose.com/tasks/java/) dan tambahkan ke classpath proyek Anda.  
3. **File MS Project** – file Project berbasis XML (misalnya `input.xml`) yang ingin Anda periksa.  

> **Pro tip:** Simpan file Project di folder `data` khusus untuk menjaga jalur tetap rapi dan menghindari penimpaan tidak sengaja.

## Impor Paket
Pertama, impor kelas Aspose.Tasks yang penting:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Cara Menyiapkan Direktori Proyek
Untuk menemukan file proyek Anda dengan benar, buat direktori khusus dalam struktur aplikasi Anda dan simpan semua file input di sana. Ini menjaga kode tetap bersih dan menghindari kesalahan terkait jalur saat memuat file. Gunakan nama variabel yang jelas untuk jalur direktori, yang dapat berupa absolut atau relatif terhadap root proyek.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan jalur absolut atau relatif tempat `input.xml` berada.

## Cara Memuat Proyek
`Project` adalah objek Aspose.Tasks utama yang mewakili file Microsoft Project dalam memori, memberi Anda akses ke semua properti dan koleksi proyek. Setelah membuat instance `Project`, Anda dapat menanyakan bidangnya, mengiterasi tugas, atau memodifikasi data sebelum menyimpan file kembali ke disk.

```java
Project project = new Project(dataDir + "input.xml");
```

Jika file Anda memiliki nama yang berbeda, sesuaikan `"input.xml"` sesuai kebutuhan.

## Cara Menentukan Versi Proyek
`Prj.SAVE_VERSION` adalah properti yang menunjukkan nomor versi Microsoft Project yang menyimpan file. `Prj.LAST_SAVED` adalah properti yang menyimpan tanggal dan waktu saat file terakhir disimpan. `Prj.SAVE_VERSION` mengembalikan versi numerik aplikasi Microsoft Project yang menyimpan file (mis., 12 untuk Project 2010). `Prj.LAST_SAVED` memberikan tanggal dan waktu tepat dari operasi penyimpanan terakhir.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Nilai-nilai ini memungkinkan Anda secara programatik menegakkan aturan bisnis spesifik versi atau menghasilkan laporan audit.

## Cara Menampilkan Hasil
Setelah mengambil informasi versi dan tanggal terakhir disimpan, biasanya Anda ingin menampilkannya ke konsol atau file log. Gunakan `System.out.println` untuk menampilkan nilai, format tanggal sesuai kebutuhan. Ini mengonfirmasi bahwa ekstraksi berhasil dan memberikan umpan balik langsung selama pengembangan atau dalam skrip otomatis.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | File tidak ditemukan atau jalur tidak benar | Verifikasi `dataDir` dan nama file; gunakan jalur absolut untuk pengujian. |
| Nomor versi tidak terduga (mis., 0) | Memuat file XML yang bukan Project | Pastikan file adalah file Microsoft Project yang valid (MPP/XML). |
| Pengecualian lisensi | Menggunakan versi percobaan tanpa lisensi yang valid di produksi | Terapkan lisensi Aspose.Tasks Anda (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Ya, Aspose.Tasks mendukung .NET, Java, dan C++ di antara lainnya.

**Q: Apakah Aspose.Tasks cocok untuk proyek berskala besar?**  
A: Tentu saja; ia dapat memproses proyek ratusan halaman dalam hitungan detik tanpa memuat seluruh file ke memori.

**Q: Bisakah saya menyesuaikan data proyek menggunakan Aspose.Tasks?**  
A: Ya, Anda dapat memodifikasi tugas, sumber daya, kalender, dan elemen proyek lainnya melalui API.

**Q: Apakah Aspose.Tasks memerlukan instalasi Microsoft Project?**  
A: Tidak, perpustakaan ini bekerja secara independen dan tidak memerlukan Microsoft Project pada mesin host.

**Q: Apakah dukungan teknis tersedia untuk Aspose.Tasks?**  
A: Ya, Anda dapat mendapatkan bantuan dari forum Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

**Additional Q&A**

**Q: Bagaimana cara mengambil properti proyek lain (mis., penulis, perusahaan)?**  
A: Gunakan `project.get(Prj.AUTHOR)` atau `project.get(Prj.COMPANY)` dengan cara yang sama seperti mengambil versi.

**Q: Bisakah saya memeriksa versi file MPP (biner)?**  
A: Ya, Aspose.Tasks memuat file `.mpp` secara langsung; properti `Prj.SAVE_VERSION` juga berfungsi untuk format biner.

**Q: Apakah ada cara untuk secara programatik meningkatkan file proyek lama ke versi yang lebih baru?**  
A: Muat file lama, lalu simpan dengan `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks menulis file dalam format terbaru secara default.

## Kesimpulan
Anda kini telah menguasai **cara mendapatkan versi proyek** dan **mengambil tanggal terakhir disimpan** dari file MS Project menggunakan Aspose.Tasks untuk Java. Gabungkan potongan kode ini ke dalam pipeline otomatisasi, alat pelaporan, atau utilitas migrasi untuk memastikan Anda selalu mengetahui versi Project yang tepat yang sedang Anda tangani.

---

**Terakhir Diperbarui:** 2026-05-31  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)
- [Baca basis data Microsoft Project dengan Aspose.Tasks untuk Java](/tasks/java/project-data-reading/read-project-database/)
- [Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspose.Tasks untuk Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}