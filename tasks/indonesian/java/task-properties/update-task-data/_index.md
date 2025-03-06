---
title: Perbarui Data Tugas ke Format MPP di Aspose.Tasks
linktitle: Perbarui Data Tugas ke Format MPP di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara memperbarui data tugas ke format MPP menggunakan Aspose.Tasks untuk Java. Ikuti panduan langkah demi langkah kami untuk manajemen proyek yang efisien.
type: docs
weight: 35
url: /id/java/task-properties/update-task-data/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang memperbarui data tugas ke format MPP menggunakan Aspose.Tasks untuk Java. Dalam tutorial ini, kami akan memandu Anda melalui prosesnya, memastikan bahwa Anda memahami setiap langkah dengan jelas. Aspose.Tasks untuk Java memberikan solusi tangguh untuk bekerja dengan file Microsoft Project, dan di akhir panduan ini, Anda akan dapat memperbarui data tugas dalam format MPP secara efisien.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Tasks untuk Java: Pastikan Anda telah menginstal perpustakaan Aspose.Tasks. Anda dapat mengunduhnya dari[halaman rilis](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda.
- Lingkungan Pengembangan Terpadu (IDE): Gunakan IDE pilihan Anda untuk pengembangan Java.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda. Cuplikan berikut menunjukkan cara mengimpor paket:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Membuat dan Konfigurasi Tugas Awal
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Lanjutkan dengan kode lainnya)
```
## 2. Tetapkan Tanggal Mulai dan Durasi
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Lanjutkan dengan kode lainnya)
```
## 3. Buat Tugas Ringkasan
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Lanjutkan dengan kode lainnya)
```
## 4. Tetapkan Batas Waktu dan Catatan Tugas
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Lanjutkan dengan kode lainnya)
```
## 5. Konfigurasikan Batasan Tugas
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Lanjutkan dengan kode lainnya)
```
## 6. Buat Tugas Tambahan
```java
//Buat 10 tugas baru
for (int i = 0; i < 10; i++) {
    //... (Lanjutkan dengan kode lainnya)
}
//... (Lanjutkan dengan kode lainnya)
```
## 7. Simpan Proyek
```java
// Simpan Proyek
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Dengan mengikuti langkah-langkah ini, Anda telah berhasil memperbarui data tugas ke format MPP menggunakan Aspose.Tasks untuk Java.
## Kesimpulan
Selamat! Anda telah menyelesaikan panduan komprehensif tentang memperbarui data tugas dalam format MPP menggunakan Aspose.Tasks untuk Java. Pustaka yang kuat ini menyederhanakan tugas manajemen proyek, menjadikannya alat yang berharga bagi pengembang Java.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk Java?
 J: Dokumentasinya tersedia[Di Sini](https://reference.aspose.com/tasks/java/).
### T: Bagaimana cara mengunduh Aspose.Tasks untuk Java?
 A: Anda dapat mendownloadnya dari[halaman rilis](https://releases.aspose.com/tasks/java/).
### T: Apakah tersedia uji coba gratis?
 A: Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
 J: Kunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Apakah Anda menawarkan lisensi sementara untuk tujuan pengujian?
 A: Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).