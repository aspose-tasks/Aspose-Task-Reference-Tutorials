---
date: 2026-02-23
description: Pelajari cara mengatur tanggal mulai proyek, mengatur durasi tugas, dan
  menyimpan proyek sebagai MPP menggunakan Aspose.Tasks untuk Java. Kelola tugas induk
  dan anak secara efisien.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Atur Tanggal Mulai Proyek dan Kelola Tugas Induk serta Anak di Aspose.Tasks
url: /id/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Tanggal Mulai Proyek dan Kelola Tugas Induk serta Anak di Aspose.Tasks

## Pendahuluan
Organisasi tugas yang efektif adalah tulang punggung manajemen proyek yang sukses, dan **menetapkan tanggal mulai proyek** dengan benar adalah langkah pertama menuju jadwal yang terstruktur dengan baik. Dalam tutorial ini Anda akan melihat cara **menetapkan tanggal mulai proyek**, mengkonfigurasi durasi tugas, dan mengelola hubungan induk‑anak menggunakan Aspose.Tasks untuk Java. Pada akhir tutorial, Anda akan siap untuk **menyimpan proyek sebagai MPP**, memperbarui persentase penyelesaian tugas, dan menyesuaikan properti tugas agar sesuai dengan skenario dunia nyata apa pun.

## Jawaban Cepat
- **Bagaimana cara saya menetapkan tanggal mulai proyek?** Gunakan `proj.set(Prj.START_DATE, startDate);` setelah menginisialisasi objek `Project`.  
- **Bisakah saya menambahkan tugas anak di bawah tugas induk?** Ya – panggil `parentTask.getChildren().add("Child Task")`.  
- **Format apa yang digunakan Aspose.Tasks untuk menyimpan file?** Gunakan `SaveFileFormat.Mpp` untuk **menyimpan proyek sebagai MPP**.  
- **Bagaimana cara memperbarui penyelesaian tugas?** Atur `Tsk.PERCENT_COMPLETE` pada objek tugas.  
- **Di mana saya dapat memperoleh lisensi sementara?** Kunjungi halaman lisensi sementara yang ditautkan di FAQ.

## Prasyarat
Sebelum menyelam ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar tentang pemrograman Java.  
- Perpustakaan Aspose.Tasks untuk Java terinstal. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/tasks/java/).  
- Integrated Development Environment (IDE) Java yang telah disiapkan di sistem Anda.

## Impor Paket
Untuk memulai, impor paket yang diperlukan ke dalam proyek Java Anda. Paket-paket ini memfasilitasi integrasi mulus dengan fungsionalitas Aspose.Tasks untuk Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Langkah 1: Atur Tanggal Mulai Proyek
Mulailah dengan mengatur tanggal mulai proyek dan parameter relevan lainnya.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Langkah 2: Tambahkan Tugas Induk (Tugas 1)
Buat tugas induk bernama "Task 1" dan konfigurasikan propertinya, termasuk **menetapkan durasi tugas**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Langkah 3: Tambahkan Tugas Induk (Tugas 2) dengan Tugas Anak
Sekarang, tambahkan tugas induk lain bernama "Task 2" dan sertakan tugas anak (Tugas 3 dan Tugas 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Langkah 4: Konfigurasikan Tugas Anak
Tentukan tanggal mulai, durasi, dan batasan untuk Tugas 3 dan Tugas 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Langkah 5: Perbarui Persentase Penyelesaian Tugas
Sesuaikan persentase penyelesaian untuk Tugas 3 dan Tugas 4 – inilah cara Anda **memperbarui penyelesaian tugas**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Langkah 6: Simpan Proyek
Akhirnya, **simpan proyek sebagai MPP** dengan perubahan yang diterapkan.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Panduan langkah demi langkah ini menunjukkan cara mengelola tugas induk dan anak secara efektif menggunakan Aspose.Tasks untuk Java. Bereksperimenlah dengan konfigurasi yang berbeda untuk menyesuaikan kebutuhan proyek Anda.

## Mengapa Menyesuaikan Properti Tugas?
Menyesuaikan properti tugas seperti tanggal mulai, durasi, batasan, dan persentase penyelesaian memberi Anda kontrol granular atas perilaku jadwal. Baik Anda perlu menyelaraskan tugas dengan ketersediaan sumber daya atau menegakkan aturan bisnis, Aspose.Tasks memungkinkan Anda **menyesuaikan properti tugas** secara programatis.

## Masalah Umum dan Solusinya
| Issue | Solution |
|-------|----------|
| **Tanggal mulai tidak diterapkan** | Pastikan Anda memanggil `proj.set(Prj.START_DATE, …)` **setelah** membuat objek `Project` dan sebelum menambahkan tugas. |
| **Tugas anak mewarisi batasan yang salah** | Atur `ConstraintType` dan `ConstraintDate` setiap anak secara eksplisit, seperti yang ditunjukkan pada Langkah 4. |
| **File yang disimpan tidak dapat dibuka di MS Project** | Verifikasi bahwa Anda menggunakan versi Aspose.Tasks terbaru dan simpan dengan `SaveFileFormat.Mpp`. |
| **Persentase tidak terlihat di UI** | Setelah mengatur `Tsk.PERCENT_COMPLETE`, panggil `proj.calculateTaskSchedule()` jika Anda memerlukan tanggal yang dihitung ulang. |

## FAQ
### Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai format file proyek?
Ya, Aspose.Tasks untuk Java mendukung berbagai format file proyek, termasuk MPP dan XML.

### Bisakah saya menyesuaikan properti tugas di luar yang dibahas dalam tutorial ini?
Tentu saja! Aspose.Tasks untuk Java menyediakan opsi penyesuaian yang luas untuk properti tugas.

### Apakah ada forum komunitas untuk Aspose.Tasks tempat saya dapat mencari dukungan?
Ya, Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas.

### Bagaimana cara saya memperoleh lisensi sementara untuk Aspose.Tasks untuk Java?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Tasks untuk Java?
Dokumentasi tersedia [di sini](https://reference.aspose.com/tasks/java/).

**Pertanyaan Tambahan**

**Q: Bagaimana cara saya secara programatis memperoleh lisensi sementara?**  
A: Muat file lisensi sementara menggunakan `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Bisakah saya mengubah satuan durasi tugas default?**  
A: Ya – ubah argumen `TimeUnitType` dalam `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: Versi Aspose.Tasks apa yang diperlukan untuk menggunakan `SaveFileFormat.Mpp`?**  
A: Semua versi terbaru (2022‑2026) mendukung penyimpanan sebagai MPP; periksa catatan rilis untuk perubahan yang dapat memengaruhi.

---

**Terakhir Diperbarui:** 2026-02-23  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}