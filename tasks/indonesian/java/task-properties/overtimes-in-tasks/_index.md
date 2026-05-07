---
date: 2026-02-23
description: Pelajari cara mengelola lembur dalam tugas proyek menggunakan Aspose.Tasks
  untuk Java, termasuk cara menghitung biaya lembur dan menyederhanakan pelacakan
  sumber daya.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengelola Lembur pada Tugas dengan Aspose.Tasks
url: /id/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengelola Lembur pada Tugas dengan Aspose.Tasks

## Pendahuluan
Jika Anda mencari **cara mengelola lembur** dalam file Microsoft Project, Anda berada di tempat yang tepat. Pada tutorial ini kami akan menunjukkan bagaimana Aspose.Tasks untuk Java memungkinkan Anda membaca, memodifikasi, dan melaporkan properti terkait lembur pada setiap tugas, sehingga Anda dapat menjaga jadwal dan anggaran tetap akurat.  

## Jawaban Cepat
- **Apa arti “lembur” dalam sebuah proyek?** Jam kerja tambahan di luar kapasitas reguler sumber daya.  
- **Kelas API mana yang menyediakan data lembur?** `Task` dengan koleksi field `Tsk` (misalnya, `Tsk.OVERTIME_COST`).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Ya, lisensi Aspose.Tasks sementara atau penuh diperlukan untuk penggunaan produksi.  
- **Bisakah saya menghitung biaya lembur secara otomatis?** Tentu – ambil `Tsk.OVERTIME_COST` dan terapkan logika tarif biaya Anda.  
- **Apakah ini kompatibel dengan Java 17?** Ya, Aspose.Tasks untuk Java mendukung Java 8 dan yang lebih baru.

## Apa Itu Manajemen Lembur pada Tugas Proyek?
Manajemen lembur berarti melacak pekerjaan tambahan dan biaya yang terjadi ketika sumber daya melebihi waktu kerja normal mereka. Menangkap data ini secara akurat membantu Anda meramalkan anggaran, menyesuaikan jadwal, dan melaporkan kesehatan proyek yang realistis.

## Mengapa Menggunakan Aspose.Tasks untuk Lembur?
* **Tidak memerlukan Microsoft Project** – bekerja langsung dengan file .MPP.  
* **Akses penuh ke bidang lembur** – biaya, pekerjaan, dan nilai persentase‑selesai tersedia melalui enumerasi `Tsk`.  
* **Kontrol programatik** – Anda dapat membaca, memodifikasi, atau menghitung biaya lembur tanpa langkah UI manual.

## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda memiliki lingkungan pengembangan Java yang terpasang di mesin Anda.  
- Aspose.Tasks untuk Java: Unduh dan instal pustaka Aspose.Tasks. Anda dapat menemukan pustaka dan dokumentasinya [di sini](https://reference.aspose.com/tasks/java/).  
- File Proyek: Siapkan file proyek (misalnya, TaskOvertimes.mpp) untuk digunakan selama tutorial.

## Impor Paket
Di proyek Java Anda, impor paket Aspose.Tasks yang diperlukan untuk memanfaatkan fungsionalitasnya. Tambahkan pernyataan impor berikut:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Langkah 1: Buat Proyek Baru
Membuat proyek baru (atau memuat yang sudah ada) adalah langkah pertama untuk setiap analisis. Ini juga memenuhi kata kunci sekunder **create new project**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Langkah 2: Iterasi Tugas dan Cetak Detail Lembur
Sekarang kami akan melintasi setiap tugas tingkat atas, menampilkan informasi lemburnya, dan mendemonstrasikan cara **menghitung biaya lembur** dengan membaca field `OVERTIME_COST`.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **Tip:** Nilai `OVERTIME_COST` sudah dihitung oleh Aspose.Tasks berdasarkan tarif lembur sumber daya. Jika Anda memerlukan perhitungan khusus, kalikan `OVERTIME_WORK` dengan tarif Anda sendiri dan perbarui field dengan `tsk.set(Tsk.OVERTIME_COST, yourValue);`.

## Masalah Umum dan Solusi
| Masalah | Solusi |
|-------|----------|
| **Nilai null untuk bidang lembur** | Pastikan file .MPP sumber memang berisi data lembur; jika tidak, bidang akan mengembalikan `null`. |
| **Biaya tidak tepat setelah modifikasi** | Setelah mengubah pekerjaan atau biaya lembur, panggil `project.save()` untuk menyimpan perubahan. |
| **Lisensi tidak ditemukan** | Letakkan file `Aspose.Tasks.lic` Anda di root proyek atau atur lisensi secara programatik sebelum memuat proyek. |

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Tasks cocok untuk manajemen proyek berskala besar?**  
J: Ya, Aspose.Tasks dirancang untuk menangani proyek dengan berbagai ukuran, mulai dari inisiatif kecil hingga program besar dan kompleks.

**T: Bisakah saya mengintegrasikan Aspose.Tasks dengan kerangka kerja Java lainnya?**  
J: Tentu! Aspose.Tasks dapat terintegrasi mulus dengan Spring, Jakarta EE, dan ekosistem Java lainnya, meningkatkan fleksibilitasnya.

**T: Apakah ada pertimbangan lisensi untuk menggunakan Aspose.Tasks?**  
J: Ya, Anda dapat menemukan detail lisensi dan memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat mencari bantuan atau berdiskusi tentang pertanyaan terkait Aspose.Tasks?**  
J: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk berinteraksi dengan komunitas dan mendapatkan dukungan.

**T: Apakah ada versi percobaan gratis untuk Aspose.Tasks?**  
J: Ya, Anda dapat mengakses versi percobaan gratis [di sini](https://releases.aspose.com/).

**T: Bagaimana cara menghitung biaya lembur untuk sumber daya tertentu?**  
J: Ambil tarif lembur sumber daya, kalikan dengan `OVERTIME_WORK` (dalam jam), dan setel hasilnya kembali ke `OVERTIME_COST` jika Anda memerlukan perhitungan khusus.

## Kesimpulan
Aspose.Tasks untuk Java menyederhanakan **cara mengelola lembur** dalam tugas proyek, memberikan pengembang akses programatik langsung ke metrik biaya, pekerjaan, dan kemajuan lembur. Dengan mengikuti panduan ini Anda dapat memuat proyek, membaca detail lembur, menyesuaikan persentase, dan bahkan menghitung biaya lembur khusus—semua tanpa membuka Microsoft Project.

---

**Terakhir Diperbarui:** 2026-02-23  
**Diuji Dengan:** Aspose.Tasks untuk Java (versi terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}