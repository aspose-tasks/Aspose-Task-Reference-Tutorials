---
date: 2025-12-21
description: Pelajari cara membuat proyek dan mengatur atribut MS Project untuk tugas
  baru menggunakan Aspose.Tasks untuk Java, termasuk cara menyimpan proyek sebagai
  XML dan menyesuaikan properti tugas.
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membuat Proyek – Menetapkan Atribut Tugas Baru dengan Aspose.Tasks
url: /id/java/project-file-operations/set-attributes-new-tasks/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Proyek – Mengatur Atribut Tugas Baru dengan Aspose.Tasks

## Pendahuluan
Dalam panduan komprehensif ini Anda akan menemukan **cara membuat proyek** file dan mengatur atribut Microsoft Project untuk tugas baru menggunakan pustaka Aspose.Tasks Java. Kami akan memandu Anda melalui setiap langkah, mulai dari menyiapkan lingkungan pengembangan hingga menyimpan proyek sebagai file XML, sehingga Anda dapat dengan mudah **menyesuaikan properti tugas** dan menyederhanakan alur kerja manajemen proyek Anda.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Mengatur tanggal mulai default untuk tugas baru dan menyimpan proyek sebagai XML.  
- **Pustaka apa yang diperlukan?** Aspose.Tasks for Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Apakah saya dapat mengubah default tugas lainnya?** Ya, Aspose.Tasks memungkinkan Anda memodifikasi banyak default pada tingkat tugas.  
- **Format output apa yang digunakan?** XML (SaveFileFormat.Xml).

## Apa itu Proyek dalam Aspose.Tasks?
*Proyek* adalah model objek yang mencerminkan file Microsoft Project. Ia menyimpan tugas, sumber daya, kalender, dan data penjadwalan lainnya, memungkinkan Anda secara programatis membaca, memodifikasi, dan menghasilkan file proyek.

## Mengapa Mengatur Default Tugas?
Mengatur nilai default seperti tanggal mulai untuk tugas baru memastikan konsistensi di seluruh rencana. Ini menghemat Anda dari memperbarui setiap tugas secara manual dan mengurangi risiko kesalahan penjadwalan.

## Prasyarat
1. **Lingkungan Pengembangan Java** – Java 8 atau lebih tinggi terpasang.  
2. **Aspose.Tasks for Java** – Unduh dari [tautan unduhan](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, atau editor yang kompatibel dengan Java.

## Impor Paket
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## Cara Membuat Proyek – Mengatur Atribut Tugas Baru
### Langkah 1: Tentukan Direktori Data
```java
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan jalur absolut tempat Anda ingin menyimpan file output.

### Langkah 2: Buat Instance Proyek
```java
Project prj = new Project();
```
Ini membuat proyek kosong yang siap untuk disesuaikan.

### Langkah 3: Atur Properti Tugas Baru
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
Baris di atas memberi tahu Aspose.Tasks untuk menetapkan **tanggal saat ini** sebagai tanggal mulai untuk setiap tugas yang Anda tambahkan nanti.

### Langkah 4: Simpan Proyek
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Di sini kami **menyimpan proyek sebagai XML**, yang merupakan format yang banyak didukung untuk pertukaran dan pemrosesan lebih lanjut.

### Langkah 5: Tampilkan Hasil
```java
System.out.println("Project file generated Successfully");
```
Pesan konsol sederhana mengonfirmasi bahwa file telah dibuat tanpa kesalahan.

## Cara Mengatur Atribut Tugas
Selain tanggal mulai, Anda dapat memodifikasi pengaturan default tugas lainnya seperti durasi, kalender, dan prioritas menggunakan enumerasi `Prj`. Fleksibilitas ini memungkinkan Anda **menyesuaikan properti tugas** agar sesuai dengan standar organisasi Anda.

## Cara Menyimpan Proyek sebagai XML
Menyimpan sebagai XML mempertahankan struktur proyek secara lengkap sekaligus membuat file dapat dibaca manusia. Ini ideal untuk integrasi dengan alat lain, kontrol versi, atau pipeline otomatis.

## Masalah Umum dan Solusinya
- **Jalur direktori data tidak valid** – Pastikan folder ada dan aplikasi memiliki izin menulis.  
- **Lisensi tidak ditemukan** – Muat lisensi Aspose.Tasks Anda sebelum membuat objek `Project` untuk menghindari watermark evaluasi.  
- **Tanggal mulai tidak terduga** – Pastikan tidak ada kode lain yang menimpa `Prj.NEW_TASK_START_DATE` setelah Anda mengaturnya.

## FAQ
### T: Apakah saya dapat menggunakan Aspose.Tasks for Java untuk memanipulasi file proyek yang ada?
J: Ya, Aspose.Tasks for Java menyediakan fungsionalitas luas untuk memanipulasi file proyek yang ada, termasuk membaca, memodifikasi, dan menyimpannya dalam berbagai format.

### T: Di mana saya dapat menemukan dokumentasi dan sumber daya lebih lanjut untuk Aspose.Tasks for Java?
J: Anda dapat menjelajahi dokumentasi dan sumber daya di [halaman dokumentasi Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

### T: Apakah ada percobaan gratis untuk Aspose.Tasks for Java?
J: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks for Java dari [di sini](https://releases.aspose.com/).

### T: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Tasks for Java?
J: Lisensi sementara untuk Aspose.Tasks for Java dapat diperoleh dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

### T: Di mana saya dapat mendapatkan dukungan untuk masalah atau pertanyaan terkait Aspose.Tasks for Java?
J: Anda dapat mendapatkan dukungan dan berinteraksi dengan komunitas di [forum dukungan Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15).

**T: Bisakah saya mengubah tanggal mulai default setelah membuat proyek?**  
J: Ya, Anda dapat memanggil `prj.set(Prj.NEW_TASK_START_DATE, ...)` kapan saja sebelum menambahkan tugas baru.  

**T: Apakah menyimpan sebagai XML memengaruhi kinerja untuk proyek besar?**  
J: XML berbasis teks, sehingga ukuran file dapat lebih besar daripada format biner, tetapi tetap cepat untuk kebanyakan ukuran proyek tipikal.  

**T: Apakah ada default tugas lain yang dapat saya atur secara global?**  
J: Tentu – properti seperti `NEW_TASK_DURATION`, `NEW_TASK_COST`, dan `NEW_TASK_PRIORITY` juga dapat dikonfigurasi melalui enumerasi `Prj`.

## Kesimpulan
Anda kini telah mempelajari **cara membuat proyek** file, mengatur tanggal mulai default untuk tugas baru, dan **menyimpan proyek sebagai XML** menggunakan Aspose.Tasks for Java. Dengan menguasai langkah‑langkah ini Anda dapat dengan mudah **menyesuaikan properti tugas** untuk memenuhi skenario manajemen proyek apa pun, meningkatkan konsistensi dan menghemat waktu berharga.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}