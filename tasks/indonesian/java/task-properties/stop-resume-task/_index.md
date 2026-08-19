---
date: 2026-02-26
description: Pelajari cara melanjutkan tugas dan menghentikan tugas di Aspose.Tasks
  untuk Java, termasuk memfilter tugas berdasarkan tanggal untuk kontrol proyek yang
  tepat.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Melanjutkan Tugas dan Menghentikan Tugas di Aspose.Tasks
url: /id/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Melanjutkan Tugas dan Menghentikan Tugas di Aspose.Tasks

## Pendahuluan
Jika Anda membangun solusi manajemen proyek berbasis Java, Anda sering perlu **menjeda** sebuah tugas sementara dan kemudian **melanjutkannya** nanti. Aspose.Tasks for Java mempermudah hal ini dengan properti bawaan untuk menghentikan dan melanjutkan tugas. Dalam tutorial ini Anda akan menemukan **cara melanjutkan tugas** dan **cara menghentikan tugas** secara programatik, serta Anda juga akan melihat cara **menyaring tugas berdasarkan tanggal** sehingga Anda hanya bekerja dengan item yang relevan dalam jadwal Anda.

## Jawaban Cepat
- **Apa arti “stop” untuk sebuah tugas?** Itu menetapkan tanggal berhenti, menghentikan pekerjaan setelah titik tersebut.  
- **Bagaimana saya dapat melanjutkan tugas yang dihentikan?** Dengan menetapkan tanggal melanjutkan yang lebih lama daripada tanggal berhenti.  
- **Bisakah saya membatasi operasi ke rentang tanggal?** Ya – gunakan tanggal minimum untuk menyaring tugas.  
- **Versi perpustakaan apa yang diperlukan?** Rilis terbaru Aspose.Tasks for Java (API tetap stabil).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis cukup untuk pengujian; lisensi diperlukan untuk produksi.

## Apa itu “cara melanjutkan tugas” di Aspose.Tasks?
Melanjutkan sebuah tugas berarti memberikan tanggal **RESUME** pada objek `Task`. Ketika mesin proyek memproses jadwal, pekerjaan akan berlanjut mulai dari tanggal tersebut. Ini sangat berguna untuk menangani gangguan seperti ketidaktersediaan sumber daya atau ketergantungan eksternal.

## Mengapa menggunakan fitur stop/resume?
- **Kontrol atas garis waktu:** Menjeda pekerjaan tanpa menghapus tugas.  
- **Pelaporan akurat:** Menampilkan tanggal mulai/selesai yang realistis pada diagram Gantt.  
- **Otomatisasi mudah:** Menggabungkan dengan filter tanggal untuk memperbarui banyak tugas sekaligus.

## Prasyarat
- Pemahaman yang kuat tentang dasar-dasar Java.  
- JDK terpasang di mesin Anda.  
- Perpustakaan Aspose.Tasks for Java ditambahkan ke proyek Anda (unduh dari [here](https://releases.aspose.com/tasks/java/)).  

## Impor Paket
Pertama, bawa kelas yang diperlukan ke dalam ruang lingkup sehingga Anda dapat bekerja dengan proyek dan tugas.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Langkah 1: Inisialisasi Proyek dan Pengumpul
Buat instance `Project` yang menunjuk ke file MPP Anda dan siapkan `ChildTasksCollector` untuk mengumpulkan setiap tugas dalam hierarki.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Langkah 2: Tentukan Tanggal Minimum untuk Penyaringan
Jika Anda hanya ingin bekerja dengan tugas yang memiliki tanggal stop atau resume yang bermakna, tentukan **tanggal minimum**. Ini adalah inti dari teknik *menyaring tugas berdasarkan tanggal*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Langkah 3: Iterasi, Periksa, dan Tampilkan Nilai Stop/Resume
Sekarang lakukan perulangan pada tugas yang dikumpulkan, terapkan logika **cara menghentikan tugas**, dan cetak tanggalnya. Kode juga menunjukkan **cara melanjutkan tugas** dengan membaca properti `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Tips Pro:** Ganti pemanggilan `System.out.println` dengan logika Anda sendiri (mis., memperbarui tanggal, mencatat ke file, atau memodifikasi objek tugas) untuk benar‑benarnya *menghentikan* atau *melanjutkan* tugas sesuai kebutuhan.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| `NullPointerException` pada `tsk.get(Tsk.STOP)` | Tugas tidak memiliki tanggal stop yang ditetapkan. | Periksa `null` sebelum memanggil `.before(minDate)`. |
| Tanggal muncul sebagai `NA` meskipun sudah diatur | Tanggal minimum terlalu baru. | Gunakan `minDate` yang lebih awal atau hapus filter. |
| Perubahan tidak tercermin dalam MPP yang disimpan | Proyek tidak disimpan setelah modifikasi. | Panggil `project.save("output.mpp");` setelah memperbarui tugas. |

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Tasks for Java cocok untuk proyek berskala besar?
Tentu saja! Aspose.Tasks for Java dirancang untuk menangani proyek dengan berbagai ukuran, memastikan efisiensi dan keandalan.

### Bisakah saya menyesuaikan tanggal untuk menghentikan dan melanjutkan tugas?
Ya, contoh yang diberikan memungkinkan fleksibilitas dalam menetapkan tanggal minimum sesuai kebutuhan proyek Anda.

### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks for Java?
Kunjungi [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas dan diskusi.

### Apakah ada percobaan gratis untuk Aspose.Tasks for Java?
Ya, Anda dapat mengakses [free trial](https://releases.aspose.com/) untuk menjelajahi fitur sebelum melakukan pembelian.

### Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Tasks for Java?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/) untuk keperluan pengujian.

**Additional Q&A**

**Q: Bagaimana cara saya benar‑benar menetapkan tanggal stop baru untuk sebuah tugas?**  
A: Gunakan `tsk.set(Tsk.STOP, new Date(...));` lalu simpan proyek.

**Q: Bisakah saya menyaring tugas berdasarkan rentang tertentu selain hanya tanggal minimum?**  
A: Ya—bandingkan baik `before` maupun `after` terhadap tanggal mulai dan akhir Anda.

**Q: Apakah API secara otomatis menghitung ulang jadwal setelah mengubah tanggal stop/resume?**  
A: Setelah mengubah tanggal, panggil `project.calculateCriticalPath();` untuk memperbarui jadwal.

## Kesimpulan
Dalam panduan ini kami membahas **cara melanjutkan tugas** dan **cara menghentikan tugas** menggunakan Aspose.Tasks for Java, serta metode praktis untuk **menyaring tugas berdasarkan tanggal**. Dengan mengintegrasikan potongan kode ini ke dalam aplikasi Anda, Anda memperoleh kontrol yang sangat detail atas garis waktu proyek dan dapat mengotomatiskan penyesuaian jadwal dengan percaya diri.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}