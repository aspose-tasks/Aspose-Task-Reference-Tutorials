---
date: 2026-01-10
description: Pelajari cara menghentikan penugasan, mengelola penugasan sumber daya,
  dan melihat contoh penugasan sumber daya di Aspose.Tasks untuk Java dengan tutorial
  langkah demi langkah ini.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menghentikan Penugasan dan Melanjutkan Penugasan Sumber Daya di Aspose.Tasks
url: /id/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menghentikan Penugasan dan Melanjutkan Penugasan Sumber Daya di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, **Anda akan menemukan cara menghentikan pengugasan** dan kemudian melanjutkannya menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah API Java yang kuat yang memungkinkan Anda membaca file proyek dalam format Java, memanipulasi data Microsoft Project, dan mengelola pengugasan sumber daya tanpa harus menginstal Microsoft Project. Kami akan membahas setiap langkah, menjelaskan mengapa setiap baris penting, dan memberikan tip praktis yang dapat Anda terapkan pada proyek dunia nyata.

## Jawaban Cepat
- **Apa arti “berhenti penugasan”?** Itu menandai pengugasan sumber daya sebagai tidak aktif sementara mulai dari tanggal berhenti tertentu.
- **Apakah saya dapat melanjutkan penugasan yang sama nanti?** Ya, dengan mengatur tanggal melanjutkan pada penugasan yang sama.
- **Apakah saya memerlukan Microsoft Project untuk menggunakan API ini?** Tidak, Aspose.Tasks berfungsi secara independen dari Microsoft Project.
- **Versi Java apa yang diperlukan?** Java8 atau yang lebih tinggi disarankan.
- **Di mana saya dapat mengunduh perpustakaan?** Dari halaman unduh resmi Aspose.Tasks Java.

## Apa yang dimaksud dengan “cara menghentikan penugasan” dalam konteks Aspose.Tasks?
Menghentikan penugasan memberi tahu penjadwalan untuk mengabaikan pekerjaan yang dialokasikan ke sumber daya setelah **tanggal berhenti** hingga **tanggal melanjutkan** (jika ada). Ini berguna untuk menangani kerusakan, downtime peralatan, atau periode apa pun ketika sumber daya tidak dianggap aktif.

## Mengapa menggunakan Aspose.Tasks untuk mengelola penetapan sumber daya?
- **Tidak perlu Microsoft Project** – bekerja langsung dengan file .mpp.
- **Kontrol penuh atas tanggal** – Anda dapat memeriksa tanggal berhenti, tanggal melanjutkan, dan menyesuaikannya secara programatik.
- **Cross‑platform** – berjalan pada sistem operasi apa pun yang mendukung Java.
- **API kaya** – menyediakan *contoh pengugasan sumber daya* yang dapat Anda kembangkan untuk pelaporan khusus.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:
- Java Development Kit (JDK) terpasang di sistem Anda.
- Pustaka Aspose.Tasks for Java telah diunduh. Anda dapat mengunduhnya dari [sini](https://releases.aspose.com/tasks/java/).
- Pemahaman dasar tentang pemrograman Java.

## Impor Paket
Pertama, mari kita impor paket-paket yang diperlukan ke dalam proyek Java kita:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Langkah 1: Muat File Proyek
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Di sini kami **membaca file proyek Java** format (`.mpp`) dan membuat objek `Project` yang memberi kami akses ke semua data proyek, termasuk penugasan sumber daya.

## Langkah 2: Lakukan Iterasi Melalui Penugasan Sumber Daya
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Kami menetapkan **tanggal minimum** untuk menyaring tanggal placeholder dan kemudian melakukan iterasi melalui setiap penugasan. Ini adalah pola *contoh penugasan sumber daya* yang umum digunakan ketika Anda perlu memeriksa atau memodifikasi penugasan.

## Langkah 3: Periksa Tanggal Berhenti dan Mulai
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

Pada blok ini kami **memeriksa tanggal berhenti** dan **memeriksa tanggal melanjutkan** untuk setiap pengugasan. Jika tanggal tersebut sebelum `minDate` kami, perkiraan kami tidak diatur (`"NA"`); jika tidak, kami mencetak tanggal sebenarnya. Logika ini penting untuk **mengelola penagasan sumber daya** dengan benar.

## Masalah Umum dan Solusinya
- **Tanggal null** – `ra.get(Asn.STOP)` dapat mengembalikan `null`. Lindungi hal ini dengan menambahkan tanda centang nol sebelum memanggil `.before(minDate)`.
- **Path file tidak tepat** – Pastikan `dataDir` diakhiri dengan pemisah jalur (`/` atau `\\`) yang sesuai untuk OS Anda.
- **Versi tidak cocok** – Gunakan Aspose.Tasks terbaru untuk versi Java untuk menghindari nilai enum yang hilang.

## Pertanyaan yang Sering Diajukan

**T: Bagaimana cara menetapkan tanggal berhenti untuk suatu tugas secara terprogram?**
A: Gunakan `ra.set(Asn.STOP, yourDateObject);` di mana `yourDateObject` adalah `java.util.Date`.

**T: Bagaimana cara saya secara programatik mengatur tanggal berhenti untuk sebuah pengugasan?**
**J:** Gunakan `ra.set(Asn.STOP, yourDateObject);` dimana `yourDateObject` adalah `java.util.Date`.

**Q: Apa yang terjadi jika tanggal melanjutkan lebih awal dari tanggal berhenti?**
J: API tidak menerapkan urutan kronologis; namun, penjadwal akan menganggap tugas tersebut aktif hanya setelah tanggal terakhir dari dua tanggal tersebut, jadi Anda harus memvalidasi sendiri tanggalnya.

**T: Apa yang terjadi jika tanggal melanjutkan lebih awal daripada tanggal berhenti?**
**J:** API tidak memaksakan urutan kronologis; namun, penjadwalan akan menganggap pengugasan aktif hanya setelah tanggal yang lebih akhir di antara keduanya, jadi Anda harus memvalidasi tanggal secara manual.

**T: Bisakah saya memfilter tugas hanya untuk tugas yang tanggal berhentinya ditetapkan?**
A: Ya, ulangi `prj.getResourceAssignments()` dan centang `ra.get(Asn.STOP) != null`.

**T: Bisakah saya memfilter penugasan hanya yang memiliki tanggal berhenti yang diatur?**
**J:** Ya, iterasi melalui `prj.getResourceAssignments()` dan periksa `ra.get(Asn.STOP) != null`.

**Q: Apakah mungkin untuk menghapus tanggal berhenti setelah ditetapkan?**
A: Tetapkan tanggal berhenti ke `null` dengan `ra.set(Asn.STOP, null);` lalu simpan proyek.

**T: Apakah memungkinkan menghapus tanggal berhenti setelah diatur?**
**J:** Atur tanggal berhenti menjadi `null` dengan `ra.set(Asn.STOP, null);` lalu simpan proyek.

**T: Apakah Aspose.Tasks mendukung bidang terkait tanggal lainnya seperti awal, selesai, atau awal sebenarnya?**
J: Tentu saja. Enum `Asn` menyediakan konstanta untuk semua bidang tugas, seperti `Asn.START`, `Asn.FINISH`, dll.

**T: Apakah Aspose.Tasks mendukung bidang terkait tanggal lain seperti start, finish, atau aktual start?**
**J:** Tentu saja. Enum `Asn` menyediakan konstanta untuk semua bidang penugasan, seperti `Asn.START`, `Asn.FINISH`, dll.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini mengetahui **cara menghentikan pengugasan**, memeriksa tanggal berhenti/melanjutkan, dan melanjutkan penugasan bila diperlukan. Kemampuan ini memungkinkan Anda **mengelola pengugasan sumber daya** dengan lebih tepat, terutama dalam skenario seperti pemotongan sumber daya atau downtime peralatan. Jangan ragu untuk memperluas contoh ini untuk memperbarui tanggal, menghasilkan laporan, atau mengintegrasikannya dengan logika penjadwalan Anda sendiri.

---

**Terakhir Diperbarui:** 10-01-2026
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}