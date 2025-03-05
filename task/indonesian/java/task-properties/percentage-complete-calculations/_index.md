---
title: Persentase Perhitungan Selesai untuk Tugas di Aspose.Tasks
linktitle: Persentase Perhitungan Selesai untuk Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi Aspose.Tasks untuk Java dan sederhanakan pelacakan kemajuan proyek. Hitung persentase tugas dengan mudah untuk manajemen proyek yang efisien.
type: docs
weight: 25
url: /id/java/task-properties/percentage-complete-calculations/
---
## Perkenalan
Selamat datang di panduan mendalam kami tentang menguasai penghitungan persentase tugas menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah pustaka Java canggih yang dirancang untuk bekerja dengan file Microsoft Project, menawarkan serangkaian fitur canggih untuk manajemen proyek. Dalam tutorial ini, kami akan fokus pada penghitungan Persentase Lengkap, memberi Anda pengetahuan untuk memantau dan menganalisis kemajuan proyek secara efektif.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda.
-  Perpustakaan Aspose.Tasks: Unduh perpustakaan Aspose.Tasks untuk Java dari[Link ini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Mari kita mulai dengan mengimpor paket yang diperlukan untuk proyek Aspose.Tasks for Java Anda. Sertakan cuplikan kode berikut dalam proyek Anda:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Sekarang, mari kita uraikan setiap langkah dengan penjelasan mendetail.
## Langkah 1: Mengimpor Paket
Pada langkah pertama, kami mengimpor paket yang diperlukan untuk menyiapkan proyek Aspose.Tasks kami.
## Langkah 2: Mengatur Direktori Dokumen
 Tentukan jalur ke direktori dokumen Anda menggunakan`dataDir`variabel. Pastikan file Microsoft Project Anda, seperti "Software Development.mpp," ada di direktori ini.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
```
## Langkah 3: Memuat Proyek
 Inisialisasi yang baru`Project` objek dan muat file Microsoft Project Anda ke dalam instance proyek.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Langkah 4: Mengambil Kumpulan Tugas
 Dapatkan tugas root proyek dan ambil turunannya sebagai koleksi menggunakan`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Langkah 5: Persentase Pencetakan Selesai
Ulangi setiap tugas dalam koleksi dan cetak Persentase Selesai, Persentase Pekerjaan Selesai, dan Persentase Fisik Selesai.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Ulangi langkah-langkah ini untuk setiap tugas dalam proyek Anda untuk mendapatkan wawasan tentang kemajuan masing-masing tugas.
## Kesimpulan
Selamat! Anda telah berhasil menguasai penghitungan persentase tugas menggunakan Aspose.Tasks untuk Java. Pustaka canggih ini memberdayakan pengembang untuk mengelola dan menganalisis kemajuan proyek secara efisien.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi Aspose.Tasks?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/tasks/java/).
### T: Bagaimana cara mengunduh perpustakaan Aspose.Tasks untuk Java?
 Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/java/).
### T: Apakah tersedia uji coba gratis?
Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 Kunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/tasks/15).
### Q: Bagaimana cara mendapatkan lisensi sementara?
 Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).