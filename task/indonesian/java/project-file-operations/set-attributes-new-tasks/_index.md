---
title: Mengatur Atribut Proyek MS untuk Tugas Baru di Aspose.Tasks
linktitle: Tetapkan Atribut untuk Tugas Baru di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengatur atribut MS Project untuk tugas baru menggunakan Aspose.Tasks untuk Java. Sesuaikan properti tugas dengan mudah dengan panduan komprehensif ini.
type: docs
weight: 21
url: /id/java/project-file-operations/set-attributes-new-tasks/
---
## Perkenalan
Selamat datang di tutorial komprehensif kami tentang pengaturan atribut MS Project untuk tugas baru di Aspose.Tasks untuk Java! Dalam panduan ini, kami akan memandu Anda melalui proses langkah demi langkah, memastikan bahwa Anda dapat dengan mudah mengelola dan menyesuaikan tugas Anda dengan pustaka Java yang canggih ini.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda dan Anda memahami konsep dasar pemrograman Java.
2.  Aspose.Tasks for Java Library: Unduh dan instal perpustakaan Aspose.Tasks for Java dari[tautan unduhan](https://releases.aspose.com/tasks/java/).
3. Java IDE: Pilih Java Integrated Development Environment (IDE) seperti Eclipse atau IntelliJ IDEA untuk pengkodean.

## Paket Impor
Sebelum kita mulai mengatur atribut MS Project untuk tugas baru, mari impor paket yang diperlukan:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## Langkah 1: Tentukan Direktori Data
Pertama, tentukan jalur ke direktori tempat Anda ingin menyimpan file proyek Anda:
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke direktori yang Anda inginkan.
## Langkah 2: Buat Instans Proyek
Buat instance objek Project baru untuk mulai bekerja dengan proyek Anda:
```java
Project prj = new Project();
```
Ini menciptakan contoh proyek baru.
## Langkah 3: Tetapkan Properti Tugas Baru
Sekarang, mari tetapkan tanggal mulai untuk tugas baru. Dalam contoh ini, kami menetapkannya ke tanggal saat ini:
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
 Baris ini mengatur properti`NEW_TASK_START_DATE` ke`TaskStartDateType.CurrentDate`.
## Langkah 4: Simpan Proyek
Simpan proyek dengan atribut tugas baru dalam format XML:
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Baris ini menyimpan proyek dengan nama file tertentu di direktori yang ditentukan sebelumnya.
## Langkah 5: Tampilkan Hasil
Terakhir, mari cetak pesan untuk mengonfirmasi bahwa file proyek berhasil dibuat:
```java
System.out.println("Project file generated Successfully");
```
Baris ini menampilkan pesan sukses di konsol.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengatur atribut MS Project untuk tugas baru menggunakan Aspose.Tasks untuk Java. Dengan pengetahuan ini, Anda kini dapat menyesuaikan properti tugas sesuai dengan kebutuhan Anda, sehingga meningkatkan kemampuan manajemen proyek Anda.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks for Java untuk memanipulasi file proyek yang ada?
J: Ya, Aspose.Tasks for Java menyediakan fungsionalitas luas untuk memanipulasi file proyek yang ada, termasuk membaca, memodifikasi, dan menyimpannya dalam berbagai format.
### T: Di mana saya dapat menemukan lebih banyak dokumentasi dan sumber daya untuk Aspose.Tasks untuk Java?
 J: Anda dapat menjelajahi dokumentasi dan sumber daya di[Aspose.Tasks untuk halaman dokumentasi Java](https://reference.aspose.com/tasks/java/).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis untuk Java dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 A: Lisensi sementara untuk Aspose.Tasks untuk Java dapat diperoleh dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya bisa mendapatkan dukungan untuk masalah atau pertanyaan apa pun terkait Aspose.Tasks untuk Java?
 A: Anda bisa mendapatkan dukungan dan berinteraksi dengan komunitas di[Aspose.Tasks untuk forum dukungan Java](https://forum.aspose.com/c/tasks/15).