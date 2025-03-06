---
title: Rumus Proyek MS dengan Aspose.Tasks untuk Java
linktitle: Bekerja dengan Rumus di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara memanipulasi file MS Project di Java menggunakan perpustakaan Aspose.Tasks. Membuat, memodifikasi, dan menghitung atribut dengan mudah.
type: docs
weight: 11
url: /id/java/formulas/work-with-formulas/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara bekerja dengan Rumus Proyek MS menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Dengan fiturnya yang luas, Anda dapat dengan mudah membuat, membaca, memodifikasi, dan mengonversi file proyek di aplikasi Java.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan prasyarat berikut:
### Lingkungan Pengembangan Jawa
Pastikan Anda memiliki Java Development Kit (JDK) yang terinstal di sistem Anda. Anda dapat mengunduh dan menginstal JDK terbaru dari situs Oracle.
### Perpustakaan Aspose.Tugas
Anda perlu menambahkan perpustakaan Aspose.Tasks ke proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Aspose.Tasks untuk halaman unduh Java](https://releases.aspose.com/tasks/java/) dan sertakan dalam dependensi proyek Anda.

## Paket Impor
Sebelum mendalami contoh, impor paket yang diperlukan ke kode Java Anda:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Buat Proyek Uji dengan Bidang Kustom
```java
Project project = CreateTestProjectWithCustomField();
```
 Pertama, buat proyek uji dengan bidang khusus menggunakan`CreateTestProjectWithCustomField()` metode. Metode ini akan mengembalikan objek Proyek yang mewakili proyek yang baru dibuat.
## Langkah 2: Tentukan Definisi Atribut yang Diperluas
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Ambil definisi atribut yang diperluas dari proyek dan atur alias dan rumusnya. Dalam contoh ini, kita mendefinisikan atribut untuk menghitung jumlah hari dari tanggal selesai hingga tenggat waktu.
## Langkah 3: Tetapkan Batas Waktu untuk suatu Tugas
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Buat objek Kalender dan atur tanggal tenggat waktu. Kemudian, ambil tugas dari proyek dan tetapkan tenggat waktunya menggunakan objek Kalender.
## Langkah 4: Simpan Proyek
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Terakhir, simpan proyek ke file dengan nama dan format yang ditentukan. Dalam hal ini, kami menyimpannya sebagai file MPP.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara bekerja dengan Rumus Proyek MS menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat memanipulasi file proyek secara efektif secara terprogram, menambahkan bidang khusus, dan menghitung atribut berdasarkan rumus.

## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
J: Ya, Aspose.Tasks mendukung berbagai bahasa pemrograman termasuk Java, .NET, dan lainnya.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda dapat mengunduh uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks?
 J: Anda dapat menemukan dokumentasi untuk Aspose.Tasks[Di Sini](https://reference.aspose.com/tasks/java/).
### T: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 A: Untuk dukungan, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### T: Apakah saya memerlukan lisensi sementara untuk menggunakan Aspose.Tasks?
J: Jika Anda memerlukan fitur tambahan, Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).