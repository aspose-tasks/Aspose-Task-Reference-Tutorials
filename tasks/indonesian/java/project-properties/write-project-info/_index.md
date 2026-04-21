---
date: 2025-12-31
description: Pelajari cara mengatur tanggal mulai proyek, menulis informasi proyek,
  dan menyimpan proyek sebagai XML menggunakan Aspose.Tasks untuk Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java
url: /id/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini, Anda akan menemukan cara **set project start date** dan menulis informasi tambahan MS Project dengan Aspose.Tasks untuk Java. Baik Anda mengotomatisasi jadwal proyek, menghasilkan laporan, atau mengintegrasikan data Project ke dalam sistem yang lebih besar, mengendalikan tanggal mulai secara programatik memberi Anda kontrol yang tepat atas timeline Anda. Kami akan membimbing Anda melalui setiap langkah—dari menyiapkan lingkungan hingga menyimpan proyek yang diperbarui sebagai file XML—sehingga Anda dapat langsung menerapkan teknik ini.

## Jawaban Cepat
- **Apa kelas utama untuk memanipulasi proyek?** `Project` dari pustaka Aspose.Tasks.  
- **Bagaimana cara mengatur tanggal mulai proyek?** Gunakan `project.set(Prj.START_DATE, <date>)`.  
- **Apakah saya juga dapat mengatur tanggal status?** Ya, dengan `project.set(Prj.STATUS_DATE, <date>)`.  
- **Format apa yang harus saya gunakan untuk mengekspor proyek?** Simpan sebagai XML dengan `SaveFileFormat.Xml`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi Aspose.Tasks yang valid diperlukan untuk fungsionalitas penuh.

## Apa itu **set project start date**?
Mengatur tanggal mulai proyek mendefinisikan hari kalender di mana semua tugas terjadwal dimulai. Ini adalah titik jangkar untuk perhitungan seperti durasi tugas, ketergantungan, dan jalur kritis. Dengan mengatur tanggal ini secara programatik, Anda memastikan konsistensi di seluruh file proyek dan menghilangkan kesalahan entri manual.

## Mengapa menggunakan Aspose.Tasks untuk Java untuk menulis informasi proyek?
- **Cakupan API lengkap:** Membaca, memodifikasi, dan menulis setiap properti Proyek tanpa perlu menginstal Microsoft Project.  
- **Lintas‑platform:** Berfungsi di Windows, Linux, dan macOS.  
- **Siap otomatisasi:** Ideal untuk pemrosesan batch, pipeline CI, atau layanan back‑end yang menghasilkan jadwal proyek secara dinamis.  

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi terbaru apa pun (disarankan 8+).  
2. **Pustaka Aspose.Tasks untuk Java** – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor Java favorit Anda.  

## Impor Paket
Pertama, impor paket yang diperlukan dalam proyek Java Anda:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Langkah 1: Siapkan Direktori Data
Tentukan direktori tempat data proyek Anda akan disimpan.
```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Buat Instance Proyek
Inisialisasi instance proyek baru.
```java
Project project = new Project();
```

## Langkah 3: Atur Properti Informasi Proyek
Di sini kami mengatur **project start date**, schedule from start, dan status date—mencakup kata kunci utama dan sekunder *write project information* dan *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Langkah 4: Simpan Proyek sebagai XML
Akhirnya, simpan file proyek yang diperbarui. Ini menunjukkan kata kunci sekunder **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Tanggal mulai tidak tepat** | Bulan kalender di Java dimulai dari nol. | Gunakan `Calendar.JULY` (atau tambahkan 1 ke indeks bulan) seperti yang ditunjukkan. |
| **File tidak tersimpan** | `dataDir` tidak ada atau tidak memiliki izin menulis. | Buat direktori terlebih dahulu atau pilih jalur yang dapat ditulisi. |
| **Peringatan lisensi** | Menjalankan tanpa lisensi menambahkan watermark. | Terapkan lisensi Aspose.Tasks yang valid sebelum membuat objek `Project`. |

## FAQ
### Q: Bisakah saya menggunakan Aspose.Tasks untuk Java untuk membaca file MS Project?
A: Ya, Aspose.Tasks untuk Java menyediakan fungsionalitas kuat untuk membaca dan menulis file MS Project.  
### Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?
A: Tentu saja, Aspose.Tasks untuk Java mendukung berbagai versi MS Project, memastikan kompatibilitas lintas format file.  
### Q: Apakah ada batasan pada versi percobaan Aspose.Tasks untuk Java?
A: Meskipun versi percobaan memungkinkan Anda menjelajahi kemampuan pustaka, ada beberapa batasan seperti watermark pada file output.  
### Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?
A: Anda dapat mencari bantuan di forum komunitas Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).  
### Q: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
A: Ya, lisensi sementara tersedia untuk penggunaan jangka pendek. Anda dapat memperoleh satu dari [here](https://purchase.aspose.com/temporary-license/).  

## Kesimpulan
Anda kini telah mempelajari cara **set project start date**, menulis informasi proyek penting, dan **save project as XML** menggunakan Aspose.Tasks untuk Java. Blok bangunan ini memungkinkan Anda mengotomatisasi alur kerja manajemen proyek, menghasilkan jadwal yang konsisten, dan mengintegrasikan data MS Project ke dalam aplikasi Java Anda.

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}