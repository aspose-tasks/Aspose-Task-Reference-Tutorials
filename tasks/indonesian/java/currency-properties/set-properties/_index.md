---
date: 2026-02-07
description: Pelajari cara mengatur kode mata uang Java dalam proyek Aspose.Tasks,
  mengubah simbol mata uang, dan menerapkan format mata uang khusus untuk file Microsoft
  Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: kode mata uang java – Cara Mengatur di Proyek Aspose.Tasks
url: /id/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Kode Mata Uang di Aspose.Tasks – Panduan Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara mengatur kode mata uang java** untuk file Microsoft Project menggunakan Aspose.Tasks Java API. Baik Anda perlu *mengubah mata uang* untuk tim internasional, menyesuaikan *simbol mata uang*, atau menerapkan **format mata uang khusus**, langkah‑langkah di bawah ini akan memandu Anda melalui proses dengan penjelasan yang jelas dan kode siap‑jalankan.

## Jawaban Cepat
- **Library apa yang diperlukan?** Aspose.Tasks for Java.  
- **Apakah saya dapat mengubah simbol mata uang?** Ya – gunakan `CurrencySymbolPositionType` dan `Prj.CURRENCY_SYMBOL`.  
- **Format file apa yang didukung?** XML, MPP, dan banyak lainnya melalui `SaveFileFormat`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Berapa lama implementasinya?** Sekitar 5‑10 menit untuk pengaturan dasar.

## Cara Mengatur Kode Mata Uang Java di Aspose.Tasks
Mata uang sebuah Proyek menentukan bagaimana nilai biaya ditampilkan—kode (mis., `AUD`), jumlah digit desimal, simbol (`$`), dan posisi simbol. Menetapkan properti‑properti ini memastikan bahwa setiap bidang yang terkait dengan biaya (tarif sumber daya, anggaran tugas, dll.) mencerminkan format moneter yang tepat untuk audiens Anda.

## Mengapa Menggunakan Aspose.Tasks untuk Mengubah Mata Uang?
- **Tidak diperlukan instalasi Microsoft Project** – memanipulasi file di server mana pun.  
- **Cakupan API lengkap** – semua bidang yang terkait dengan mata uang tersedia melalui konstanta `Prj`.  
- **Lintas platform** – berfungsi di Windows, Linux, dan macOS dengan IDE yang kompatibel dengan Java apa pun.  
- **Kinerja tinggi** – memproses file proyek besar dengan cepat dan andal.  
- **Mendukung format mata uang khusus** – Anda dapat menentukan simbol, digit desimal, dan posisi untuk menyesuaikan standar regional.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih tinggi.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, atau editor apa pun yang Anda sukai.  
4. **Folder yang dapat ditulisi** – tempat file proyek yang dihasilkan akan disimpan.

## Impor Paket
Pertama, impor kelas‑kelas yang memberikan akses ke properti proyek dan penanganan file.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Panduan Langkah‑demi‑Langkah

### Langkah 1: Tentukan Direktori Data
Tentukan folder yang berisi file sumber Anda dan tempat output akan ditulis.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Buat Instance Proyek Baru
Instansiasi objek `Project` baru. Objek ini mewakili file Microsoft Project dalam memori.

```java
Project project = new Project();
```

### Langkah 3: Atur Properti Mata Uang
Di sinilah kita **cara mengatur mata uang** detail seperti kode, digit, simbol, dan posisi simbol.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Tip pro:** Jika Anda perlu **mengubah mata uang proyek** untuk file yang sudah ada, cukup muat dengan `new Project("file.mpp")` sebelum menerapkan pengaturan di atas.

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
| **`NullPointerException` pada `project.save`** | `dataDir` bukan path yang valid atau tidak memiliki izin menulis. | Pastikan direktori ada dan proses Java Anda memiliki akses menulis. |
| **Simbol mata uang tidak muncul** | Posisi simbol diatur tidak tepat untuk locale Anda. | Gunakan `CurrencySymbolPositionType.Before` jika simbol harus berada sebelum jumlah. |
| **File proyek tidak dapat dibuka di MS Project** | Menyimpan dalam format lama dengan pengaturan yang tidak kompatibel. | Simpan menggunakan `SaveFileFormat.MPP` untuk kompatibilitas penuh dengan versi MS Project terbaru. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya mengatur beberapa mata uang dalam satu proyek menggunakan Aspose.Tasks?**  
A: Ya, Aspose.Tasks memungkinkan Anda menangani beberapa mata uang dalam satu file proyek dengan mengatur properti mata uang per‑sumber daya atau per‑tugas.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
A: Tentu saja. Perpustakaan ini mendukung file MPP dari Project 2000 hingga rilis terbaru, serta XML dan format lainnya.

**Q: Apakah Aspose.Tasks menyediakan dukungan untuk format mata uang khusus?**  
A: Ya, Anda dapat mendefinisikan simbol khusus, digit desimal, dan posisi untuk memenuhi kebutuhan regional apa pun.

**Q: Bisakah saya mengintegrasikan Aspose.Tasks dengan perpustakaan atau kerangka kerja Java lain?**  
A: Tentu. API ini murni Java, sehingga bekerja mulus dengan Spring, Hibernate, Maven, Gradle, dan ekosistem lainnya.

**Q: Di mana saya dapat menemukan dukungan atau bantuan tambahan untuk Aspose.Tasks?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan komunitas, atau lihat dokumentasi resmi untuk referensi API yang detail.

## Kesimpulan
Anda kini tahu **cara mengatur kode mata uang java**, cara **mengubah nilai mata uang**, dan cara **mengubah simbol mata uang** menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda menyesuaikan data biaya untuk tim global, menghasilkan laporan spesifik locale, dan menjaga konsistensi file proyek Anda di seluruh batas.

---

**Terakhir Diperbarui:** 2026-02-07  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}