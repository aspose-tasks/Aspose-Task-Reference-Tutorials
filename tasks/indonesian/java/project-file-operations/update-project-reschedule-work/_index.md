---
date: 2026-03-29
description: Pelajari cara menjadwal ulang pekerjaan yang belum selesai, memperbarui
  pekerjaan proyek, dan menyimpan file MS Project sebagai XML menggunakan Aspose.Tasks
  untuk Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jadwalkan Ulang Pekerjaan yang Belum Selesai dan Perbarui File MS Project dengan
  Aspose.Tasks
url: /id/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jadwalkan Ulang Pekerjaan yang Belum Selesai dan Perbarui File MS Project dengan Aspose.Tasks

## Pendahuluan
Microsoft Project adalah alat manajemen proyek yang banyak digunakan yang membantu tim merencanakan tugas, mengalokasikan sumber daya, dan melacak jadwal. Aspose.Tasks untuk Java memberikan pengembang API yang kaya untuk memanipulasi file Microsoft Project secara programatis. Dalam tutorial ini, Anda akan belajar cara **memperbarui pekerjaan proyek**, **menjadwalkan ulang pekerjaan yang belum selesai**, dan **menyimpan file MS Project** dalam format XML menggunakan Aspose.Tasks untuk Java.

## Jawaban Cepat
- **Apa arti “reschedule uncompleted work”?** Itu memindahkan semua pekerjaan tugas yang tersisa untuk mulai setelah tanggal yang dipilih, sementara bagian yang selesai tetap tidak berubah.  
- **Metode mana yang menandai pekerjaan sebagai selesai?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Bagaimana cara menyimpan perubahan?** Gunakan `project.save(<path>, SaveFileFormat.Xml)`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan komersial.  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru sepenuhnya didukung.

## Apa itu “reschedule uncompleted work”?
Menjadwalkan ulang pekerjaan yang belum selesai menyesuaikan tanggal mulai semua tugas yang belum selesai, memindahkannya untuk mulai setelah tanggal batas yang ditentukan. Ini berguna ketika jadwal proyek berubah karena penundaan atau perubahan ruang lingkup.

## Mengapa menggunakan Aspose.Tasks untuk memperbarui pekerjaan proyek dan menjadwalkan ulang tugas?
- **Kontrol detail:** Mengatur persentase penyelesaian pekerjaan dan tanggal secara langsung.  
- **Tidak memerlukan UI:** Mengotomatisasi pembaruan massal pada banyak file proyek.  
- **Lintas platform:** Berfungsi pada sistem apa pun yang menjalankan Java.  
- **Mempertahankan integritas data:** Semua ketergantungan, batasan, dan sumber daya tetap konsisten.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) terpasang di sistem Anda.  
2. Perpustakaan Aspose.Tasks untuk Java. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/tasks/java/).  
3. Pemahaman dasar tentang bahasa pemrograman Java.

## Impor Paket
Pertama, impor paket yang diperlukan dalam kode Java Anda:
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

## Langkah 1: Menyiapkan Proyek
Inisialisasi objek `Project` baru, definisikan tugas, atur durasi, dan tetapkan ketergantungan. Ini membuat proyek dasar yang nanti akan kita perbarui dan jadwalkan ulang.
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

## Langkah 2: Memperbarui Pekerjaan Proyek
Tandai pekerjaan sebagai selesai hingga tanggal tertentu. Langkah ini menunjukkan operasi **update project work**, yang biasanya merupakan tindakan pertama sebelum menjadwalkan ulang.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Langkah 3: Menjadwalkan Ulang Pekerjaan yang Belum Selesai
Sekarang kami memindahkan semua pekerjaan yang tersisa (belum selesai) sehingga mulai setelah tanggal batas yang sama. Ini adalah fungsi inti **reschedule uncompleted work**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Kesimpulan
Dalam tutorial ini, kami membahas cara **memperbarui pekerjaan proyek**, **menjadwalkan ulang pekerjaan yang belum selesai**, dan **menyimpan file MS Project** sebagai XML menggunakan Aspose.Tasks untuk Java. Kemampuan ini penting ketika jadwal proyek perlu disesuaikan berdasarkan kemajuan aktual atau prioritas bisnis yang berubah.

## FAQ
### Q: Dapatkah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?
A: Ya, Aspose.Tasks untuk Java menyediakan API yang kuat untuk mengelola tugas, ketergantungan, sumber daya, dan elemen proyek lainnya secara efisien.  
### Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks untuk Java?
A: Ya, Anda dapat mendapatkan percobaan gratis dari [here](https://releases.aspose.com/).  
### Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?
A: Anda dapat mengunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.  
### Q: Apakah saya dapat membeli lisensi sementara untuk Aspose.Tasks untuk Java?
A: Ya, lisensi sementara tersedia untuk dibeli [here](https://purchase.aspose.com/temporary-license/).  
### Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks untuk Java?
A: Anda dapat merujuk ke dokumentasi [here](https://reference.aspose.com/tasks/java/) untuk panduan komprehensif dan referensi API.

## Pertanyaan Umum Tambahan

**Q: Bagaimana saya memastikan file yang disimpan kompatibel dengan versi Microsoft Project yang lebih lama?**  
A: Simpan proyek menggunakan `SaveFileFormat.Xml`; XML secara luas didukung di semua versi Project.

**Q: Bisakah saya menjadwalkan ulang hanya sebagian tugas saja, bukan seluruh proyek?**  
A: Ya, Anda dapat mengiterasi tugas tertentu dan memanggil `task.setStart(date)` setelah menghitung tanggal mulai baru.

**Q: Apa yang terjadi pada alokasi sumber daya ketika saya menjadwalkan ulang pekerjaan yang belum selesai?**  
A: Penugasan sumber daya secara otomatis dipindahkan untuk menyesuaikan tanggal mulai tugas baru, mempertahankan logika alokasi.

**Q: Apakah memungkinkan untuk membatalkan operasi penjadwalan ulang secara programatis?**  
A: Anda dapat memuat ulang file proyek asli (atau cadangan) untuk mengembalikan perubahan apa pun.

**Q: Apakah Aspose.Tasks mendukung penyimpanan ke format lain seperti .mpp?**  
A: Tentu saja. Gunakan `SaveFileFormat.MPP` untuk menyimpan dalam format native Microsoft Project.

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}