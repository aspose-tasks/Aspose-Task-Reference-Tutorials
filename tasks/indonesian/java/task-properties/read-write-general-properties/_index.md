---
date: 2026-02-26
description: Pelajari cara membuat proyek Aspose Java untuk tugas dan mendapatkan
  tanggal mulai tugas menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah
  untuk membaca dan menulis properti umum tugas.
linktitle: Read and Write General Properties of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Buat Tugas Aspose Java – Menguasai Properti Tugas
url: /id/java/task-properties/read-write-general-properties/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Tugas Aspose Java – Menguasai Properti Tugas

## Pendahuluan
Maksimalkan potensi penuh manajemen tugas di Java dengan Aspose.Tasks. Dalam panduan komprehensif ini, **Anda akan belajar cara membuat task Aspose Java** proyek, membaca dan menulis properti umum, serta bahkan **mengambil tanggal mulai tugas** untuk tugas apa pun dalam jadwal Anda. Baik Anda seorang pengembang berpengalaman maupun baru memulai, tutorial ini menyediakan kode praktis yang dapat Anda salin‑tempel ke dalam aplikasi Anda sendiri.

## Jawaban Cepat
- **Apa yang dapat saya lakukan dengan Aspose.Tasks untuk Java?** Membaca dan menulis properti tugas, termasuk tanggal mulai, durasi, dan bidang khusus.  
- **Bagaimana cara membuat tugas baru?** Gunakan `project.getRootTask().getChildren().add("TaskName")` dan atur properti melalui enum `Tsk`.  
- **Bagaimana cara mengambil tanggal mulai tugas?** Panggil `task.get(Tsk.START)` setelah memuat proyek atau membuat tugas.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Aspose.Tasks bekerja dengan Java 8 ke atas, termasuk Java 11 dan Java 17.

## Apa itu “create task Aspose Java”?
Membuat tugas dengan Aspose.Tasks berarti menambahkan entri baru secara programatik ke jadwal proyek, mendefinisikan nama, waktu mulai, waktu selesai, dan atribut lainnya tanpa harus mengedit file XML atau MPP secara manual.

## Mengapa menggunakan Aspose.Tasks untuk Java?
- **Kontrol penuh** atas setiap atribut tugas (ID, UID, nama, tanggal, dll.).  
- **Lintas‑platform** – berfungsi di Windows, Linux, dan macOS.  
- **Tanpa ketergantungan COM atau Office** – pustaka Java murni.  
- **API kaya** untuk membaca, menulis, dan memvalidasi data proyek.

## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda telah menyiapkan hal‑hal berikut:
- Java Development Kit (JDK) terpasang di sistem Anda.  
- Pustaka Aspose.Tasks untuk Java sudah diunduh dan disiapkan. Anda dapat menemukan tautan unduhan [di sini](https://releases.aspose.com/tasks/java/).  
- Editor kode seperti IntelliJ IDEA atau Eclipse.

## Impor Paket
Untuk memulai, impor paket yang diperlukan dalam proyek Java Anda. Langkah ini memastikan Anda memiliki akses ke fungsionalitas Aspose.Tasks. Berikut cuplikan kode untuk memandu Anda:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Cara membuat task Aspose Java
### Langkah 1: Buat Tugas
Mulailah dengan membuat tugas dalam proyek Anda. Ini melibatkan penetapan nama tugas, tanggal mulai, dan detail relevan lainnya. Kode di bawah ini memperlihatkan prosesnya:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```

### Langkah 2: Baca Properti Tugas
Setelah Anda membuat tugas, mari ambil dan tampilkan properti umum tugas tersebut, termasuk tanggal mulai yang baru saja Anda tetapkan:

```java
// Reading General Properties of Tasks
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```

## Cara mendapatkan tanggal mulai tugas
Jika Anda perlu **mengambil tanggal mulai tugas** untuk perhitungan lebih lanjut (misalnya penjadwalan atau pelaporan), cukup panggil properti `Tsk.START` pada objek `Task` mana pun, seperti yang ditunjukkan dalam loop di atas. Nilai yang dikembalikan adalah `java.util.Date` yang dapat Anda format atau bandingkan sesuai kebutuhan.

## Menulis Properti Umum Tugas
### Langkah 3: Muat Proyek dan Buat Collector
Untuk menulis atau memperbarui properti umum, muat proyek yang ada dan siapkan `ChildTasksCollector`:

```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```

### Langkah 4: Parse dan Tampilkan Properti
Akhirnya, iterasikan melalui tugas yang terkumpul dan tampilkan (atau ubah) properti mereka:

```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```

> **Pro tip:** Setelah memperbarui properti apa pun, panggil `prj.save("output.xml")` untuk menyimpan perubahan ke file proyek baru.

Selamat! Anda telah berhasil membaca, menulis, dan menanyakan properti umum tugas menggunakan Aspose.Tasks untuk Java.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|--------|----------|
| `NullPointerException` saat mengakses `task.get(Tsk.START)` | Tugas tidak ditambahkan ke hierarki proyek. | Pastikan Anda menambahkan tugas ke `project.getRootTask().getChildren()` sebelum mengatur properti. |
| Tanggal muncul satu hari lebih awal | Perbedaan zona waktu antara Java `Date` dan file proyek. | Gunakan `java.util.Calendar` dengan zona waktu eksplisit atau simpan tanggal dalam UTC. |
| Perubahan tidak tersimpan | Lupa memanggil `project.save(...)`. | Selalu simpan proyek setelah melakukan modifikasi. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Tasks kompatibel dengan Java 11?**  
J: Ya, Aspose.Tasks kompatibel dengan Java 11 dan versi yang lebih baru.

**T: Dapatkah saya menggunakan Aspose.Tasks untuk proyek komersial?**  
J: Tentu saja! Aspose.Tasks adalah alat yang kuat untuk proyek pribadi maupun komersial. Kunjungi [di sini](https://purchase.aspose.com/buy) untuk menjelajahi opsi lisensi.

**T: Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?**  
J: Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.

**T: Di mana saya dapat menemukan dukungan komunitas untuk Aspose.Tasks?**  
J: Bergabunglah dengan diskusi komunitas di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan dan kolaborasi.

**T: Apakah ada contoh proyek yang tersedia untuk referensi?**  
J: Jelajahi bagian contoh dokumentasi [di sini](https://reference.aspose.com/tasks/java/) untuk proyek contoh dan cuplikan kode.

## Kesimpulan
Dalam tutorial ini, kami telah mengeksplorasi langkah‑langkah dasar untuk **membuat task Aspose Java** proyek, membaca dan menulis properti umum, serta **mengambil tanggal mulai tugas** dengan mudah. Dengan menguasai teknik‑teknik ini, Anda dapat menyederhanakan manajemen tugas dalam aplikasi penjadwalan berbasis Java apa pun dan memberikan fitur perencanaan proyek yang lebih kaya kepada pengguna Anda.

---

**Terakhir Diperbarui:** 2026-02-26  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}