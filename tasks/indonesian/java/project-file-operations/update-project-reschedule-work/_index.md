---
date: 2025-12-23
description: Pelajari cara memperbarui file MS Project dan menjadwalkan ulang pekerjaan
  yang belum selesai menggunakan Aspose.Tasks untuk Java. Juga lihat cara menyimpan
  XML MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Perbarui MS Project dan Jadwalkan Ulang Pekerjaan dengan Aspose.Tasks
url: /id/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Perbarui MS Project dan Jadwalkan Ulang Pekerjaan dengan Aspose.Tasks

## Pendahuluan
Microsoft Project adalah alat manajemen proyek yang banyak digunakan yang membantu tim merencanakan, melacak, dan menyelesaikan pekerjaan tepat waktu. Ketika jadwal berubah, Anda sering perlu **memperbarui MS Project** secara programatis—menandai pekerjaan sebagai selesai, memindahkan tugas yang tersisa, dan menjaga baseline proyek tetap akurat. Aspose.Tasks untuk Java memberikan API yang bersih dan tipe‑aman untuk melakukan hal tersebut tanpa membuka antarmuka GUI. Pada tutorial ini Anda akan melihat cara memperbarui proyek, menandai pekerjaan selesai hingga tanggal tertentu, dan kemudian **cara menjadwalkan ulang MS Project** untuk pekerjaan yang masih tertunda.

## Jawaban Cepat
- **Apa arti “update MS Project”?** Itu menandai tugas sebagai selesai hingga tanggal yang diberikan dan menulis perubahan kembali ke file.  
- **Bisakah saya menjadwalkan ulang pekerjaan yang tersisa secara otomatis?** Ya—gunakan `rescheduleUncompletedWorkToStartAfter` untuk memindahkan tugas yang belum selesai ke depan.  
- **Format file apa yang disimpan?** Contoh menyimpan proyek sebagai XML (`SaveFileFormat.Xml`).  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** JDK 8 atau lebih tinggi.

## Apa itu “update MS Project” dalam kode?
Memperbarui proyek berarti mengubah tanggal tugas, durasi, atau persentase penyelesaian secara programatis dan menyimpan perubahan tersebut. Aspose.Tasks menyediakan metode seperti `updateProjectWorkAsComplete` yang menerapkan perubahan berdasarkan `Date` referensi yang Anda berikan.

## Mengapa menggunakan Aspose.Tasks untuk Java untuk memperbarui MS Project?
- **Tanpa ketergantungan UI** – mengotomatisasi perubahan massal pada banyak file.  
- **Preservasi tinggi** – perpustakaan mempertahankan semua data native Project (sumber daya, kalender, bidang khusus).  
- **Lintas‑platform** – jalankan kode yang sama di Windows, Linux, atau macOS.  
- **Simpan MS Project XML** – Anda dapat mengekspor proyek yang diperbarui ke format XML yang banyak didukung untuk alat downstream.

## Prasyarat
1. Java Development Kit (JDK) terpasang.  
2. Perpustakaan Aspose.Tasks untuk Java – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. Familiaritas dasar dengan sintaks Java dan konsep berorientasi objek.

## Impor Paket
Pertama, impor kelas Aspose.Tasks yang diperlukan serta utilitas Java:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Langkah 1: Siapkan Proyek
Buat instance `Project` baru, definisikan beberapa tugas contoh, atur durasinya, dan buat ketergantungan. Kemudian simpan keadaan awal sehingga Anda dapat melihat efek sebelum‑dan‑sesudah.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Langkah 2: Perbarui Pekerjaan Proyek
Tandai pekerjaan sebagai selesai hingga tanggal pemotongan tertentu. Inilah inti dari **update MS Project**—API akan menyesuaikan progres tugas dan tanggal secara otomatis.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Langkah 3: Jadwalkan Ulang Pekerjaan yang Belum Selesai
Setelah menandai pekerjaan selesai, Anda sering perlu memindahkan tugas yang tersisa ke depan. Panggilan berikut memindahkan semua pekerjaan yang belum selesai untuk mulai setelah tanggal pemotongan yang sama, secara efektif **cara menjadwalkan ulang MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya
| Masalah | Alasan | Perbaikan |
|-------|--------|-----|
| Tugas tidak menampilkan tanggal yang diperbarui | Proyek disimpan dalam format berbeda (mis., `.mpp`) | Gunakan `SaveFileFormat.Xml` untuk mempertahankan struktur XML. |
| `updateProjectWorkAsComplete` tampaknya tidak melakukan apa‑apa | Tanggal referensi lebih awal dari mulai proyek | Pastikan tanggal `Calendar` berada dalam rentang timeline proyek. |
| Tugas yang dijadwalkan ulang saling tumpang tindih | Tidak ada kalender atau leveling sumber daya yang diterapkan | Terapkan kalender `Project` atau gunakan `Task.setStart` secara manual setelah penjadwalan ulang. |

## Pertanyaan yang Sering Diajukan (Diperluas)

**Q: Bisakah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?**  
A: Ya, Aspose.Tasks untuk Java menyediakan API yang kuat untuk mengelola tugas, ketergantungan, sumber daya, dan elemen proyek lainnya secara efisien.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mendapatkan percobaan gratis dari [here](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mengunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.

**Q: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Ya, lisensi sementara tersedia untuk dibeli [here](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.Tasks untuk Java?**  
A: Anda dapat merujuk ke dokumentasi [here](https://reference.aspose.com/tasks/java/) untuk panduan lengkap dan referensi API.

## Kesimpulan
Dalam tutorial ini kami menelusuri proses lengkap **memperbarui MS Project**, menandai pekerjaan sebagai selesai, dan kemudian **cara menjadwalkan ulang MS Project** untuk tugas yang belum selesai. Dengan menyimpan proyek sebagai XML Anda mempertahankan kompatibilitas dengan alat lain dan menjaga jejak audit perubahan yang jelas. Gunakan pola ini untuk mengotomatisasi penyesuaian jadwal dalam portofolio besar, mengintegrasikan dengan pipeline CI, atau membangun dasbor pelaporan khusus.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}