---
date: 2025-12-04
description: Pelajari cara mengatur mata uang dalam proyek Aspose.Tasks Java, termasuk
  cara mengubah mata uang dan mengubah simbol mata uang di Java. Manipulasi file Microsoft
  Project dengan mudah.
language: id
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Cara Mengatur Mata Uang dalam Proyek Aspose.Tasks – Panduan Java
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Mata Uang dalam Proyek Aspose.Tasks – Panduan Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara mengatur mata uang** untuk file Microsoft Project menggunakan Aspose.Tasks Java API. Baik Anda perlu *mengubah mata uang* untuk tim internasional atau menyesuaikan *simbol mata uang* di Java, langkah‑langkah di bawah ini akan memandu Anda melalui proses dengan penjelasan yang jelas dan kode siap‑jalankan.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks for Java.  
- **Apakah saya dapat mengubah simbol mata uang?** Ya – gunakan `CurrencySymbolPositionType` dan `Prj.CURRENCY_SYMBOL`.  
- **Format file apa yang didukung?** XML, MPP, dan banyak lainnya melalui `SaveFileFormat`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk pengaturan dasar.

## Apa itu “mata uang” dalam file Project?
Mata uang dalam Project menentukan bagaimana nilai biaya ditampilkan—kode (mis., `AUD`), jumlah digit desimal, simbol (`$`), dan posisi simbol. Menetapkan properti ini memastikan setiap bidang yang terkait biaya (tarif sumber daya, anggaran tugas, dll.) menampilkan format moneter yang tepat untuk audiens Anda.

## Mengapa menggunakan Aspose.Tasks untuk mengubah mata uang?
- **Tidak perlu instalasi Microsoft Project** – manipulasi file di server mana pun.  
- **Cakupan API lengkap** – semua bidang yang terkait mata uang tersedia melalui konstanta `Prj`.  
- **Lintas platform** – bekerja di Windows, Linux, dan macOS dengan IDE yang kompatibel dengan Java apa pun.  
- **Kinerja tinggi** – memproses file proyek besar dengan cepat dan andal.

## Prasyarat
Sebelum Anda mulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, atau editor apa pun yang Anda sukai.  
4. **Folder yang dapat ditulisi** – tempat file proyek yang dihasilkan akan disimpan.

## Impor Paket
Pertama, impor kelas yang menyediakan akses ke properti proyek dan penanganan file.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Tentukan Direktori Data
Tentukan folder yang berisi file sumber Anda dan tempat output akan ditulis.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Buat Instance Project Baru
Buat objek `Project` baru. Objek ini mewakili file Microsoft Project yang berada di memori.

```java
Project project = new Project();
```

### Langkah 3: Atur Properti Mata Uang
Berikut tempat kami **cara mengatur mata uang** detail seperti kode, digit, simbol, dan posisi simbol.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** Jika Anda perlu **mengubah mata uang** untuk proyek yang ada, cukup muat file dengan `new Project("file.mpp")` sebelum menerapkan pengaturan di atas.

### Langkah 4: Simpan Proyek yang Diperbarui
Tuliskan kembali proyek ke disk dalam format yang diinginkan. Pada contoh ini kami menggunakan format XML, tetapi Anda juga dapat memilih `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Langkah 5: Konfirmasi Keberhasilan
Cetak pesan ramah sehingga Anda tahu operasi selesai tanpa error.

```java
System.out.println("Process completed Successfully");
```

## Masalah Umum & Solusi
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` bukan jalur yang valid atau tidak memiliki izin menulis. | Pastikan direktori ada dan proses Java Anda memiliki akses menulis. |
| **Currency symbol not showing** | Posisi simbol diatur tidak tepat untuk locale Anda. | Gunakan `CurrencySymbolPositionType.Before` jika simbol harus berada sebelum jumlah. |
| **Project file does not open in MS Project** | Menyimpan dalam format lama dengan pengaturan yang tidak kompatibel. | Simpan menggunakan `SaveFileFormat.MPP` untuk kompatibilitas penuh dengan versi MS Project terbaru. |

## Pertanyaan yang Sering Diajukan

**T: Apakah saya dapat mengatur beberapa mata uang dalam satu proyek menggunakan Aspose.Tasks?**  
J: Ya, Aspose.Tasks memungkinkan Anda menangani beberapa mata uang dalam satu file proyek dengan mengatur properti mata uang per‑sumber daya atau per‑tugas.

**T: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
J: Tentu saja. Perpustakaan ini mendukung file MPP dari Project 2000 hingga rilis terbaru, serta XML dan format lainnya.

**T: Apakah Aspose.Tasks menyediakan dukungan untuk format mata uang khusus?**  
J: Ya, Anda dapat mendefinisikan simbol khusus, digit desimal, dan posisi untuk memenuhi kebutuhan regional apa pun.

**T: Bisakah saya mengintegrasikan Aspose.Tasks dengan perpustakaan atau kerangka kerja Java lainnya?**  
J: Tentu. API ini murni Java, sehingga bekerja mulus dengan Spring, Hibernate, Maven, Gradle, dan ekosistem lainnya.

**T: Di mana saya dapat menemukan dukungan atau bantuan tambahan untuk Aspose.Tasks?**  
J: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan komunitas, atau lihat dokumentasi resmi untuk referensi API yang detail.

## Kesimpulan
Anda sekarang tahu **cara mengatur mata uang**, cara **mengubah nilai mata uang**, dan cara **mengubah simbol mata uang gaya Java** menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda menyesuaikan data biaya untuk tim global, menghasilkan laporan spesifik locale, dan menjaga konsistensi file proyek Anda di seluruh batas.

---

**Terakhir Diperbarui:** 2025-12-04  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}