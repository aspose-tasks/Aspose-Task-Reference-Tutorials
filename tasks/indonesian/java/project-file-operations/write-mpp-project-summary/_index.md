---
date: 2025-12-23
description: Pelajari cara membuat ringkasan MPP dan memperbarui penulis proyek menggunakan
  Aspose.Tasks untuk Java. Atur dan ambil informasi proyek dengan mudah.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membuat Ringkasan MPP dan Memperbarui Penulis Proyek dengan Aspose.Tasks
url: /id/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tulis Ringkasan Proyek MPP di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, Anda akan **membuat ringkasan MPP** untuk file Microsoft Project dan mempelajari cara **memperbarui penulis proyek** menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda sedang membangun alat manajemen proyek atau mengotomatiskan pelaporan, mengendalikan properti ringkasan secara programatik menghemat waktu dan memastikan konsistensi di seluruh proyek Anda.

## Jawaban Cepat
- **Apa arti “create MPP summary”?** Itu berarti mengatur properti proyek tingkat tinggi (penulis, revisi, kata kunci, dll.) yang muncul di dialog Informasi Ringkasan Proyek Microsoft Project.  
- **Pustaka mana yang menangani ini?** Aspose.Tasks untuk Java menyediakan API yang fluens untuk membaca dan menulis properti tersebut.  
- **Apakah saya membutuhkan lisensi?** Versi percobaan gratis tersedia, tetapi lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya juga mengubah penulis setelah file disimpan?** Ya – Anda dapat **memperbarui penulis proyek** dengan memanggil `project.set(Prj.AUTHOR, "New Author")` dan kemudian menyimpan ulang file.  
- **Format file apa yang didukung?** Baik MPP maupun XML (SaveFileFormat.Xml) didukung sepenuhnya.

## Apa itu create MPP summary?
Membuat ringkasan MPP melibatkan pengisian metadata proyek—penulis, nomor revisi, kata kunci, komentar, tanggal pembuatan, dan tanggal cetak. Metadata ini disimpan di dalam catatan Informasi Ringkasan Proyek dan ditampilkan di bagian **File → Info** Microsoft Project.

## Mengapa memperbarui penulis proyek?
Menjaga informasi **penulis proyek** tetap akurat sangat penting untuk jejak audit, kolaborasi, dan pelaporan. Ketika banyak anggota tim berkontribusi, Anda mungkin perlu **memperbarui penulis proyek** untuk mencerminkan perubahan terbaru atau memberikan atribusi kerja yang tepat.

## Prasyarat
1. Java Development Kit (JDK) terpasang di mesin Anda.  
2. Aspose.Tasks untuk Java – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. Sebuah IDE seperti IntelliJ IDEA, Eclipse, atau NetBeans.

## Impor Paket
Pertama, impor paket yang diperlukan ke dalam kelas Java Anda:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Langkah 1: Siapkan Proyek dan Tentukan Informasi Ringkasan
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Dalam kode di atas kami **membuat ringkasan MPP** seperti penulis, revisi, dan kata kunci. Anda juga dapat **memperbarui penulis proyek** nanti dengan memanggil `project.set(Prj.AUTHOR, "New Name")`.

## Langkah 2: Simpan Informasi Ringkasan Proyek
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Menyimpan proyek menyimpan semua data ringkasan yang baru saja Anda definisikan.

## Langkah 3: Baca Informasi Ringkasan Proyek
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Potongan kode ini menunjukkan cara **membaca kembali** informasi ringkasan, mengonfirmasi bahwa operasi **create MPP summary** berhasil.

## Masalah Umum dan Solusinya
- **Nilai null setelah membaca:** Pastikan proyek telah disimpan dengan sukses sebelum dimuat ulang. Periksa jalur file dan izin.  
- **Perbedaan format tanggal:** `project.get(Prj.CREATION_DATE)` mengembalikan `java.util.Date`. Gunakan `SimpleDateFormat` jika Anda memerlukan format tampilan khusus.  
- **Lisensi tidak diatur:** Tanpa lisensi yang valid, Aspose.Tasks berjalan dalam mode evaluasi dan mungkin menyisipkan watermark. Daftarkan lisensi Anda di awal kode.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan pustaka Java lainnya?**  
A: Ya, Aspose.Tasks untuk Java dapat terintegrasi secara mulus dengan pustaka Java lainnya untuk meningkatkan kemampuan manajemen proyek Anda.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis dari [here](https://releases.aspose.com/).

**Q: Seberapa sering Aspose.Tasks untuk Java diperbarui?**  
A: Aspose.Tasks untuk Java secara teratur diperbarui untuk memastikan kompatibilitas dengan versi terbaru Java dan file Microsoft Project.

**Q: Bisakah saya menyesuaikan informasi ringkasan proyek lebih lanjut?**  
A: Tentu saja, Aspose.Tasks untuk Java menyediakan opsi yang luas untuk menyesuaikan informasi ringkasan proyek sesuai dengan kebutuhan spesifik Anda.

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Kesimpulan
Dalam tutorial ini kami telah menunjukkan cara **membuat data ringkasan MPP**, **memperbarui penulis proyek**, dan memverifikasi perubahan tersebut menggunakan Aspose.Tasks untuk Java. Dengan mengotomatisasi langkah-langkah ini Anda memperoleh kontrol penuh atas metadata proyek, membuat aplikasi Anda lebih kuat dan laporan proyek Anda lebih akurat.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}