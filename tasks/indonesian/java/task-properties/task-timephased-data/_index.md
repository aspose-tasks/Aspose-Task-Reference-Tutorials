---
date: 2026-02-28
description: Pelajari cara menggunakan Aspose.Tasks untuk Java untuk mengelola data
  tugas berwaktu, unduh perpustakaan, coba secara gratis, dan permudah pelacakan proyek.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menggunakan Aspose.Tasks untuk Mengelola Data Tugas Berfase Waktu (Java)
url: /id/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Aspose.Tasks untuk Data Waktu Tugas

## Pendahuluan
Jika Anda mencari **cara menggunakan Aspose** untuk mengendalikan jadwal proyek Anda dengan ketat, Anda berada di tempat yang tepat. Pelacakan tepat data waktu tugas merupakan fondasi manajemen proyek yang sukses, dan Aspose.Tasks for Java memberikan alat yang Anda perlukan untuk mengotomatisasi proses tersebut. Dalam tutorial ini kami akan membahas contoh lengkap, end‑to‑end yang menunjukkan cara menggunakan Aspose.Tasks untuk membuat proyek, menetapkan sumber daya, mengatur baseline, dan akhirnya mengambil serta menampilkan data waktu.

## Jawaban Cepat
- **Apa arti “timephased data”?** Itu adalah data yang dipecah berdasarkan interval waktu (hari, minggu, bulan) yang menunjukkan pekerjaan, biaya, atau pekerjaan yang tersisa selama garis waktu proyek.  
- **Perpustakaan mana yang menyediakan kemampuan ini?** Aspose.Tasks for Java.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih tinggi.  
- **Bisakah saya mengekspor hasil ke Excel?** Ya – Anda dapat mengiterasi koleksi `TimephasedData` dan menulis nilai ke format apa pun yang Anda perlukan.

## Apa Itu Data Waktu Tugas?
Data waktu tugas mewakili jumlah pekerjaan (atau biaya) yang dijadwalkan untuk sebuah tugas selama setiap segmen waktu pada kalender proyek. Ini memungkinkan Anda melihat bagaimana pekerjaan didistribusikan, mengidentifikasi kelebihan alokasi, dan membandingkan rencana vs. kemajuan aktual.

## Mengapa Menggunakan Aspose.Tasks untuk Mengelola Data Waktu?
- **Full control** – membuat, memodifikasi, dan mengkueri informasi timephased secara programatik tanpa membuka Microsoft Project.  
- **Cross‑platform** – bekerja pada sistem operasi apa pun yang mendukung Java.  
- **No COM dependencies** – ideal untuk otomatisasi sisi server.  
- **Rich API** – mendukung baseline, work contour, dan custom field secara langsung.

## Prasyarat
Sebelum menyelam ke dalam kode, pastikan Anda memiliki:

- **Java Development Environment** – JDK 8+ terpasang dan `JAVA_HOME` dikonfigurasi.  
- **Aspose.Tasks for Java Library** – Unduh dan sertakan pustaka Aspose.Tasks dalam proyek Anda. Anda dapat menemukan pustaka tersebut [di sini](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – Sebuah folder di mesin Anda tempat file proyek contoh (`project.xml`) akan dibaca dan ditulis.

## Impor Paket
Dalam proyek Java Anda, impor kelas Aspose.Tasks yang diperlukan:

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

## Langkah 1: Atur Tanggal Mulai Proyek
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* Kami membuat instance `Project`, menginisialisasi `Calendar` ke tanggal mulai yang diinginkan, dan menetapkannya ke properti `START_DATE` proyek.

## Langkah 2: Definisikan Tugas dan Sumber Daya
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* Tugas baru dengan nama **Task** ditambahkan di bawah tugas root. Kami juga membuat sumber daya bernama **Rsc** dan mengatur tarif standar serta lembur.

## Langkah 3: Atur Durasi Tugas
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* Tugas dijadwalkan dengan durasi **6 hari**.

## Langkah 4: Tugaskan Sumber Daya ke Tugas
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* Sumber daya yang telah didefinisikan sebelumnya dihubungkan ke tugas melalui `ResourceAssignment`.

## Langkah 5: Konfigurasikan Penugasan Sumber Daya
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* Kami mengatur tanggal berhenti dan melanjutkan penugasan (menggunakan nilai placeholder) dan menerapkan work contour **Back‑Loaded**, yang memindahkan lebih banyak pekerjaan ke akhir penugasan.

## Langkah 6: Atur Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* Menangkap baseline memungkinkan Anda membandingkan nilai rencana vs. aktual di kemudian hari.

## Langkah 7: Perbarui Penyelesaian Tugas
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* Tugas ditandai sebagai **50 % selesai**, yang akan memengaruhi perhitungan pekerjaan yang tersisa.

## Langkah 8: Ambil Data Timephased
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* Panggilan ini mengambil **remaining work** untuk penugasan, dipecah berdasarkan interval waktu proyek.

## Langkah 9: Tampilkan Data Timephased
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* Kami cukup mencetak jumlah entri timephased dan nilai entri pertama. Dalam skenario dunia nyata Anda akan mengiterasi daftar dan mengekspor data ke laporan atau UI.

## Masalah Umum dan Solusinya
- **NullPointerException pada `getTimephasedData`** – Pastikan tanggal `START` dan `FINISH` penugasan telah diatur sebelum memanggil metode tersebut.  
- **Work contour tidak tepat** – Verifikasi bahwa `WorkContourType` yang Anda pilih sesuai dengan strategi penjadwalan Anda; `BackLoaded` hanyalah salah satu dari beberapa opsi.  
- **Baseline tidak mencerminkan perubahan** – Ingatlah untuk memanggil `project.setBaseline` *setelah* Anda mendefinisikan tugas, sumber daya, dan penugasan.

## Pertanyaan yang Sering Diajukan
### Q: Bisakah saya menggunakan Aspose.Tasks for Java dalam proyek Java apa pun?
A: Ya, Aspose.Tasks for Java kompatibel dengan proyek berbasis Java apa pun.

### Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks for Java?
A: Kunjungi [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi.

### Q: Apakah ada percobaan gratis untuk Aspose.Tasks for Java?
A: Ya, Anda dapat menjelajahi percobaan gratis [di sini](https://releases.aspose.com/).

### Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks for Java?
A: Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q: Di mana saya dapat membeli Aspose.Tasks for Java?
A: Anda dapat membeli Aspose.Tasks for Java [di sini](https://purchase.aspose.com/buy).

---

**Terakhir Diperbarui:** 2026-02-28  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}