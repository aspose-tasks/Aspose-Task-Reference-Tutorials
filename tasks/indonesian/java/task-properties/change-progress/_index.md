---
title: Ubah Kemajuan Tugas di Aspose.Tasks
linktitle: Ubah Kemajuan Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Tingkatkan manajemen proyek Java dengan Aspose.Tasks. Pelajari cara mengubah kemajuan tugas dengan lancar dalam tutorial langkah demi langkah ini. Unduh sekarang!
weight: 12
url: /id/java/task-properties/change-progress/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ubah Kemajuan Tugas di Aspose.Tasks

## Perkenalan
Dalam bidang manajemen proyek yang dinamis, pelacakan kemajuan tugas yang efektif sangatlah penting. Aspose.Tasks untuk Java menonjol sebagai solusi tangguh, menyederhanakan proses dengan fitur-fitur canggihnya. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengubah kemajuan tugas menggunakan Aspose.Tasks untuk Java.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
1. Lingkungan Pengembangan Java: Instal dan atur lingkungan pengembangan Java yang fungsional di sistem Anda.
2.  Aspose.Tugas untuk Perpustakaan Java: Unduh perpustakaan dari[tautan](https://releases.aspose.com/tasks/java/).
3. Direktori Dokumen: Buat direktori untuk menyimpan dokumen proyek Anda.
## Paket Impor
Mari kita mulai dengan mengimpor paket yang diperlukan ke proyek Java Anda. Cuplikan kode ini menginisialisasi proyek dan menambahkan tugas dengan kemajuan 50%.
```java
import com.aspose.tasks.*;

```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek Java baru di lingkungan pengembangan Anda.
## Langkah 2: Impor Paket yang Diperlukan
 Di kelas Java Anda, impor paket yang diperlukan:`Project` Dan`Task`.
## Langkah 3: Tentukan Direktori Dokumen
Tentukan jalur ke direktori dokumen Anda untuk menyimpan file proyek.
```java
String dataDir = "Your Document Directory";
```
## Langkah 4: Buat Proyek Baru
 Menggunakan`Project` kelas untuk membuat proyek baru.
```java
Project project = new Project(dataDir + "project.mpp");
```
## Langkah 5: Tambahkan Tugas
 Memanfaatkan`Task` kelas untuk menambahkan tugas baru ke proyek Anda.
```java
Task task = project.getRootTask().getChildren().add("Task");
```
## Langkah 6: Tetapkan Kemajuan Tugas
 Atur kemajuan tugas menggunakan`set` metode dan`Tsk.PERCENT_COMPLETE` atribut.
```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```
### Langkah 7: Tampilkan Kemajuan
Ambil dan tampilkan kemajuan tugas.
```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```
Dengan mengikuti langkah-langkah ini, Anda telah berhasil mengubah kemajuan tugas menggunakan Aspose.Tasks untuk Java.
## Kesimpulan
Menyederhanakan pelacakan kemajuan tugas sangat penting dalam manajemen proyek. Aspose.Tasks untuk Java menyederhanakan proses ini, menyediakan antarmuka yang ramah pengguna dan fitur-fitur canggih. Menguasai langkah-langkah yang diuraikan dalam panduan ini akan meningkatkan kemampuan manajemen proyek Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks kompatibel dengan semua lingkungan pengembangan Java?
Pastikan kompatibilitas dengan mengikuti petunjuk instalasi dalam dokumentasi.
### Bisakah saya melacak kemajuan beberapa tugas dalam satu proyek?
Replikasi langkah-langkah untuk setiap tugas yang ingin Anda pantau.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 Akses versi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks untuk Java?
 Jelajahi dokumentasi komprehensif[Di Sini](https://reference.aspose.com/tasks/java/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 Mengunjungi[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
