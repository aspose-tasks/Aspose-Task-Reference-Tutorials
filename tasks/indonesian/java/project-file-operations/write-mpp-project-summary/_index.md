---
title: Tulis Ringkasan Proyek MPP di Aspose.Tasks
linktitle: Tulis Ringkasan Proyek MPP di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menulis ringkasan proyek MPP di Java menggunakan Aspose.Tasks. Atur dan ambil informasi proyek dengan mudah.
weight: 27
url: /id/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tulis Ringkasan Proyek MPP di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks untuk Java untuk menulis ringkasan proyek MPP. Aspose.Tasks adalah perpustakaan Java yang kuat untuk bekerja dengan file Microsoft Project. Dengan mengikuti langkah-langkah yang diuraikan di bawah ini, Anda akan dapat mengatur dan mengambil berbagai informasi ringkasan tentang suatu proyek menggunakan perpustakaan ini.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks for Java: Unduh dan instal pustaka Aspose.Tasks for Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE pilihan Anda untuk pengembangan Java, seperti IntelliJ IDEA, Eclipse, atau NetBeans.

## Paket Impor
Pertama, impor paket yang diperlukan ke kelas Java Anda:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Langkah 1: Siapkan Proyek dan Tentukan Ringkasan Informasi
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
//Inisialisasi objek Proyek baru dengan jalur ke file proyek Anda
Project project = new Project(dataDir + "project.mpp");
// Tetapkan informasi ringkasan tentang proyek
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Tetapkan tanggal pembuatan proyek
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Tetapkan kata kunci untuk proyek tersebut
project.set(Prj.KEYWORDS, "MPP Aspose");
// Tetapkan tanggal cetak terakhir proyek
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Langkah 2: Simpan Informasi Ringkasan Proyek
```java
// Simpan Proyek kembali dalam format MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Tampilkan pesan sukses
System.out.println("Process completed Successfully");
```
## Langkah 3: Baca Informasi Ringkasan Proyek
```java
// Membaca Informasi Ringkasan Proyek
project = new Project(dataDir + "MppAspose.xml");
// Cetak penulis proyek
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Cetak penulis terakhir proyek tersebut
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Cetak nomor revisi proyek
System.out.println("Revision: " + project.get(Prj.REVISION));
// Cetak kata kunci proyek
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Cetak komentar proyek
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Cetak tanggal pembuatan proyek
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Cetak kata kunci proyek (lagi)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Cetak tanggal cetak terakhir proyek
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Kesimpulan
Dalam tutorial ini, kami telah membahas cara menulis ringkasan proyek MPP menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengatur dan mengambil berbagai informasi ringkasan tentang file proyek Anda secara efisien. Aspose.Tasks menyederhanakan proses bekerja dengan file Microsoft Project dalam aplikasi Java, menawarkan fungsionalitas yang kuat dan kemudahan penggunaan.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks untuk Java dengan pustaka Java lainnya?
J: Ya, Aspose.Tasks untuk Java dapat diintegrasikan secara lancar dengan pustaka Java lainnya untuk meningkatkan kemampuan manajemen proyek Anda.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Seberapa sering Aspose.Tasks untuk Java diperbarui?
J: Aspose.Tasks untuk Java diperbarui secara berkala untuk memastikan kompatibilitas dengan versi terbaru file Java dan Microsoft Project.
### T: Dapatkah saya menyesuaikan informasi ringkasan proyek lebih lanjut?
J: Tentu saja, Aspose.Tasks untuk Java menyediakan opsi luas untuk menyesuaikan informasi ringkasan proyek sesuai dengan kebutuhan spesifik Anda.
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
J: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
