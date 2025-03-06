---
title: Durasi Tugas di Unit Berbeda dengan Aspose.Tasks
linktitle: Durasi Tugas di Unit Berbeda dengan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi manajemen durasi tugas di proyek Java dengan Aspose.Tasks. Hitung dan ubah durasi secara akurat dalam menit, hari, jam, minggu, dan bulan.
type: docs
weight: 32
url: /id/java/task-properties/task-duration-different-units/
---
## Perkenalan
Dalam bidang manajemen proyek, pemahaman dan pengelolaan durasi tugas merupakan aspek penting. Aspose.Tasks untuk Java menyediakan perangkat canggih untuk menangani hal ini secara efisien. Dalam tutorial ini, kami akan memandu Anda dalam mengambil durasi tugas di berbagai unit menggunakan Aspose.Tasks.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:
- Kit Pengembangan Java (JDK) diinstal
-  Aspose.Tugas untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/java/)
- Pemahaman dasar tentang pemrograman Java
## Paket Impor
Dalam proyek Java Anda, sertakan perpustakaan Aspose.Tasks. Tambahkan pernyataan import berikut di awal kode Anda:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek Java baru di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda. Pastikan untuk menyertakan pustaka Aspose.Tasks dalam dependensi proyek Anda.
## Langkah 2: Baca Templat Proyek
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Baca file templat Proyek MS
String fileName = dataDir + "project.xml";
// Baca file input sebagai Project
Project project = new Project(fileName);
```
 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke file proyek Anda.
## Langkah 3: Ambil Tugas
```java
// Dapatkan tugas untuk menghitung durasinya dalam format berbeda
Task task = project.getRootTask().getChildren().getById(1);
```
 Di sini, kami mendapatkan tugas dari proyek tersebut. Menyesuaikan`getById(1)` berdasarkan ID tugas proyek Anda.
## Langkah 4: Durasi dalam Menit
```java
// Dapatkan durasinya dalam Menit
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Langkah ini menghitung durasi tugas dalam hitungan menit.
## Langkah 5: Durasi dalam Hari
```java
// Dapatkan durasinya dalam Hari
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Langkah ini menghitung durasi tugas dalam hari.
## Langkah 6: Durasi dalam Jam
```java
// Dapatkan durasinya dalam Jam
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Langkah ini menghitung durasi tugas dalam jam.
## Langkah 7: Durasi dalam Minggu
```java
// Dapatkan durasinya dalam Minggu
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Langkah ini menghitung durasi tugas dalam beberapa minggu.
## Langkah 8: Durasi dalam Bulan
```java
// Dapatkan durasinya dalam Bulan
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Langkah ini menghitung durasi tugas dalam bulan.
## Kesimpulan
Mengelola durasi tugas menjadi sederhana dengan Aspose.Tasks untuk Java. Tutorial ini telah memandu Anda melalui proses langkah demi langkah, memberikan kejelasan tentang berbagai satuan waktu.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.Tasks untuk Java dengan IDE Java apa pun?
Ya, Aspose.Tasks untuk Java kompatibel dengan Java Integrated Development Environment (IDE) apa pun.
### T: Bagaimana cara mendapatkan ID tugas dalam file Microsoft Project?
Anda dapat memeriksa file proyek atau menggunakan Aspose.Tasks API untuk mengambil ID tugas secara terprogram.
### T: Apakah Aspose.Tasks cocok untuk menangani proyek skala besar?
Sangat. Aspose.Tasks dirancang untuk menangani proyek dengan berbagai ukuran secara efisien.
### T: Di mana saya dapat menemukan dokumentasi lebih lanjut?
 Mengunjungi[dokumentasi](https://reference.aspose.com/tasks/java/)untuk sumber daya yang komprehensif.
### T: Dapatkah saya mencoba Aspose.Tasks untuk Java sebelum membeli?
 Ya, Anda dapat menjelajahi a[uji coba gratis](https://releases.aspose.com/) untuk mengevaluasi kemampuannya.