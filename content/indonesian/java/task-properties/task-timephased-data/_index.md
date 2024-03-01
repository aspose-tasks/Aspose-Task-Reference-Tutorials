---
title: Data Fase Waktu Tugas di Aspose.Tasks
linktitle: Data Fase Waktu Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi Aspose.Tasks untuk Java dan kuasai pengelolaan data bertahap tugas. Unduh perpustakaan, nikmati uji coba gratis, dan sederhanakan pelacakan proyek Anda.
type: docs
weight: 34
url: /id/java/task-properties/task-timephased-data/
---
## Perkenalan
Dalam bidang manajemen proyek, pelacakan data tahapan waktu tugas yang tepat sangat penting untuk pelaksanaan proyek yang efisien. Aspose.Tasks untuk Java muncul sebagai alat yang ampuh untuk menyederhanakan proses ini, menawarkan fitur dan fleksibilitas yang tangguh. Tutorial ini akan memandu Anda dalam memanfaatkan Aspose.Tasks untuk Java untuk mengelola data fase waktu tugas secara efektif.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda.
-  Aspose.Tasks untuk Java Library: Unduh dan sertakan perpustakaan Aspose.Tasks dalam proyek Anda. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/tasks/java/).
- Direktori Dokumen: Siapkan direktori untuk dokumen proyek Anda.
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Langkah 1: Tetapkan Tanggal Mulai Proyek
```java
Project project = new Project(dataDir + "project.xml");
// Kode tambahan untuk impor paket
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Penjelasan: Inisialisasi objek kalender, atur tanggal mulai, dan terapkan pada proyek.
## Langkah 2: Tentukan Tugas dan Sumber Daya
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Penjelasan: Buat tugas dan sumber daya, tetapkan tarif standar dan lembur.
## Langkah 3: Tetapkan Durasi Tugas
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Penjelasan: Tentukan durasi tugas (misalnya 6 hari).
## Langkah 4: Tetapkan Sumber Daya ke Tugas
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Penjelasan: Tetapkan sumber daya untuk tugas tersebut.
## Langkah 5: Konfigurasikan Penetapan Sumber Daya
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Penjelasan: Tetapkan parameter seperti berhenti, melanjutkan, dan kontur kerja untuk penetapan sumber daya.
## Langkah 6: Tetapkan Garis Dasar
```java
project.setBaseline(BaselineType.Baseline);
```
Penjelasan: Tetapkan garis dasar untuk proyek tersebut.
## Langkah 7: Perbarui Penyelesaian Tugas
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Penjelasan: Tunjukkan persentase penyelesaian tugas.
## Langkah 8: Ambil Data Bertahap Waktu
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Penjelasan: Ambil data bertahap waktu untuk sisa pekerjaan tugas.
## Langkah 9: Tampilkan Data Berfase Waktu
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Kode tambahan untuk menampilkan nilai lainnya
```
Penjelasan: Keluarkan dan tampilkan data bertahap waktu.
## Kesimpulan
Mengelola data fase waktu tugas secara efektif sangat diperlukan untuk keberhasilan proyek. Aspose.Tasks untuk Java menyederhanakan proses ini, menyediakan serangkaian fungsi yang komprehensif. Dengan mengikuti tutorial ini, Anda dapat mengintegrasikan Aspose.Tasks dengan lancar ke dalam proyek Java Anda, memastikan kontrol yang tepat atas jadwal proyek dan alokasi sumber daya.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.Tasks untuk Java di proyek Java mana pun?
J: Ya, Aspose.Tasks for Java kompatibel dengan proyek berbasis Java apa pun.
### T: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks untuk Java?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mencoba uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 J: Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat membeli Aspose.Tasks untuk Java?
 J: Anda dapat membeli Aspose.Tasks untuk Java[Di Sini](https://purchase.aspose.com/buy).