---
title: Atur Properti Sumber Daya di Aspose.Tasks
linktitle: Atur Properti Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengatur properti sumber daya MS Project di Java menggunakan Aspose.Tasks untuk integrasi yang lancar dan manajemen tugas yang efisien.
weight: 20
url: /id/java/resource-management/set-resource-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur Properti Sumber Daya di Aspose.Tasks

## Perkenalan
Dalam bidang pengembangan Java, mengelola tugas secara efisien merupakan aspek penting dalam manajemen proyek. Aspose.Tasks untuk Java memberikan solusi tangguh bagi pengembang untuk berinteraksi dengan file Microsoft Project, memungkinkan integrasi fungsi manajemen tugas ke dalam aplikasi Java dengan lancar. Dalam tutorial ini, kita akan mempelajari pengaturan properti sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Di akhir panduan ini, Anda akan memiliki pemahaman komprehensif tentang cara memanipulasi properti sumber daya dalam proyek Java Anda.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
### Pengaturan Lingkungan Pengembangan Java
1.  Instal JDK: Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda. Anda dapat mengunduhnya dari[situs web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Pengaturan IDE: Pilih Lingkungan Pengembangan Terpadu (IDE) seperti IntelliJ IDEA, Eclipse, atau NetBeans dan atur di mesin Anda.
### Aspose.Tugas untuk Instalasi Java
1.  Unduh Aspose.Tasks untuk Java: Buka[Unduh Halaman](https://releases.aspose.com/tasks/java/)dan dapatkan Aspose.Tasks versi terbaru untuk Java.
2. Integrasikan dengan Proyek: Gabungkan pustaka Aspose.Tasks untuk Java ke dalam proyek Java Anda dengan menambahkannya sebagai dependensi.

## Paket Impor
Untuk memulai, Anda perlu mengimpor paket yang diperlukan dari Aspose.Tasks untuk Java ke proyek Anda. Langkah ini memastikan bahwa Anda memiliki akses ke fungsi yang diperlukan.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Langkah 1: Buat Objek Proyek
 Pertama, buat contoh a`Project` objek untuk mulai bekerja dengan data MS Project.

```java
Project project = new Project();
```
## Langkah 2: Tambahkan Sumber Daya
 Selanjutnya, tambahkan sumber daya ke proyek menggunakan`add()` metode`Resources` koleksi.

```java
Resource rsc = project.getResources().add("Rsc");
```
## Langkah 3: Tetapkan Properti Sumber Daya
 Sekarang, Anda dapat mengatur berbagai properti sumber daya seperti tarif standar dan tarif lembur menggunakan konstanta yang sesuai yang disediakan oleh`Rsc` kelas.

```java
// Tetapkan tarif standar untuk sumber daya
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Tetapkan tingkat lembur untuk sumber daya
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk Java menawarkan solusi mudah untuk mengelola properti sumber daya MS Project dalam aplikasi Java. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan fungsi manajemen sumber daya ke dalam proyek Anda, sehingga meningkatkan efisiensi dan produktivitas.
## FAQ
### Bisakah Aspose.Tasks untuk Java menangani file MS Project yang kompleks?
Ya, Aspose.Tasks untuk Java mampu menangani berbagai format file MS Project, termasuk format file kompleks dengan hierarki tugas yang luas.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat mengakses uji coba gratis Aspose.Tasks untuk Java dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
 Anda dapat mencari bantuan dan berpartisipasi dalam diskusi terkait Aspose.Tasks for Java di[forum dukungan](https://forum.aspose.com/c/tasks/15).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 Anda dapat memperoleh lisensi sementara dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.
### Di mana saya dapat membeli versi berlisensi Aspose.Tasks untuk Java?
 Anda dapat membeli versi berlisensi Aspose.Tasks untuk Java dari[halaman pembelian](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
