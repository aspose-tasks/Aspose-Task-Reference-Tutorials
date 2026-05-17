---
date: 2026-02-10
description: Pelajari cara mendapatkan nilai mata uang, membaca file MS Project, dan
  mengonversi file proyek Java menggunakan Aspose.Tasks. Panduan langkah demi langkah
  untuk mengekstrak digit mata uang.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mendapatkan Mata Uang dari MS Project menggunakan Aspose.Tasks
url: /id/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mendapatkan Mata Uang dari MS Project menggunakan Aspose.Tasks

## Pendahuluan
Jika Anda bertanya‑tanya **bagaimana cara mendapatkan mata uang** dari file Microsoft Project, Anda berada di tempat yang tepat. Dalam tutorial komprehensif ini Anda akan menemukan **cara bekerja dengan nilai ms project currency** menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda sedang membangun alat pelaporan, utilitas migrasi, atau sekadar perlu membaca pengaturan mata uang dari **java project file**, panduan ini akan membawa Anda melalui setiap langkah—dari memuat file *.mpp* hingga mengekstrak digit mata uang. Pada akhir tutorial, Anda akan merasa nyaman menangani data ms project currency dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Library apa yang membaca file MS Project?** Aspose.Tasks untuk Java.  
- **Berapa baris kode yang diperlukan untuk mendapatkan digit mata uang?** Hanya tiga baris singkat setelah proyek dimuat.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis cukup untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 atau lebih tinggi (setiap JDK yang dapat menjalankan Aspose.Tasks).  
- **Bisakah saya mengambil properti Project lainnya?** Ya – Aspose.Tasks menyediakan seluruh set bidang Project (mis., tanggal mulai, tarif biaya, dll.).

## Apa itu ms project currency?
`ms project currency` mengacu pada presisi numerik (jumlah tempat desimal) yang digunakan Microsoft Project saat menampilkan nilai moneter. Nilai ini disimpan dalam file Project sebagai properti **CURRENCY_DIGITS** dan menentukan apakah jumlah ditampilkan sebagai bilangan bulat, satu desimal, dua desimal, dll.

## Mengapa menggunakan Aspose.Tasks untuk menangani ms project currency?
- **Tidak memerlukan instalasi Microsoft Project** – bekerja langsung dengan file *.mpp* di platform apa pun yang mendukung Java.  
- **Keamanan tipe yang kuat** – API mengembalikan nilai bertipe kuat, mengurangi kesalahan parsing.  
- **Dioptimalkan untuk kinerja** – memuat proyek besar dengan cepat dan mengekstrak hanya bidang yang Anda perlukan.  
- **Lintas platform** – berjalan di Windows, Linux, atau macOS tanpa modifikasi.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Lingkungan Pengembangan Java** – JDK 8 atau lebih baru terpasang dan terkonfigurasi.  
2. **Aspose.Tasks untuk Java** – unduh JAR terbaru dari situs resmi: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Pengetahuan dasar Java** – Anda harus nyaman membuat proyek Java, menambahkan pustaka eksternal, dan menjalankan metode `main`.  

## Impor Paket
Pertama, impor kelas yang kita perlukan.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Langkah 1: Tentukan Direktori Data
Tentukan folder yang berisi **java project file** Anda (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan jalur absolut atau relatif tempat `project.mpp` berada.

## Langkah 2: Muat File MPP  
Sekarang kita akan melihat **cara memuat file mpp** menggunakan Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Pastikan nama file cocok persis; jika tidak, `IOException` akan dilempar.

## Langkah 3: Ambil Digit Mata Uang  
Dengan proyek dimuat, mengekstrak digit **ms project currency** adalah satu baris kode:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Pemanggilan ini mengembalikan `Integer` yang mewakili jumlah tempat desimal (mis., `2` untuk sen). Nilai ini dicetak ke konsol, tetapi Anda juga dapat menyimpannya dalam variabel untuk pemrosesan lebih lanjut.

## Masalah Umum & Tips
- **File tidak ditemukan** – periksa kembali jalur `dataDir` dan pastikan nama file sudah benar, termasuk ekstensi `.mpp`.  
- **Versi file tidak didukung** – Aspose.Tasks mendukung format Project 2000‑2024; file yang lebih lama atau rusak mungkin memerlukan konversi.  
- **Lisensi belum diatur** – selama pengembangan versi percobaan cukup, tetapi untuk produksi Anda harus menerapkan lisensi yang valid agar tidak muncul watermark evaluasi.

## Pertanyaan yang Sering Diajukan

**T: Bisakah Aspose.Tasks menangani atribut Project lain selain digit mata uang?**  
J: Ya, Aspose.Tasks menawarkan berbagai fungsionalitas untuk memanipulasi berbagai aspek file Project, seperti tugas, sumber daya, dan bidang khusus.

**T: Apakah Aspose.Tasks cocok untuk aplikasi tingkat perusahaan?**  
J: Tentu saja, Aspose.Tasks dirancang untuk memenuhi kebutuhan proyek kelas enterprise, menawarkan kinerja tinggi dan skalabilitas.

**T: Apakah Aspose.Tasks mendukung pengembangan lintas platform?**  
J: Ya, Anda dapat menggunakan Aspose.Tasks untuk Java di platform apa pun yang mendukung Java Runtime Environment (Windows, Linux, macOS).

**T: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
J: Ya, Anda dapat mengunduh versi percobaan gratis dari [sini](https://releases.aspose.com/).

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks?**  
J: Anda dapat menemukan dukungan di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Kesimpulan
Anda kini tahu **bagaimana cara mendapatkan digit mata uang** dari file MS Project menggunakan Aspose.Tasks untuk Java. Prosesnya sederhana: muat proyek, panggil `project.get(Prj.CURRENCY_DIGITS)`, dan gunakan hasilnya dalam aplikasi Anda. Jangan ragu untuk menjelajahi properti proyek lainnya dengan pola yang sama, serta mengintegrasikan logika ini ke dalam solusi pelaporan atau migrasi yang lebih besar.

---

**Terakhir Diperbarui:** 2026-02-10  
**Diuji Dengan:** Aspose.Tasks untuk Java (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}