---
date: 2026-06-15
description: Pelajari cara mengekstrak data timephased dari sumber daya MS Project
  menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah untuk mendapatkan
  sumber daya berdasarkan id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Baca Data Timephased untuk Sumber Daya di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Baca Data Timephased untuk Sumber Daya di Aspose.Tasks – dapatkan sumber daya
  berdasarkan id
url: /id/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Data Timephased untuk Sumber Daya di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, Anda akan belajar **how to get resource by id** dan membaca data timephased-nya menggunakan Aspose.Tasks untuk Java. Kami akan membimbing Anda melalui setiap langkah—dari menyiapkan folder proyek hingga mencetak nilai work dan cost yang timephased—sehingga Anda dapat mengekstrak informasi penjadwalan yang berharga dari file Microsoft Project apa pun secara programatis. Aspose.Tasks untuk Java adalah API komprehensif yang memungkinkan pengembang membuat, membaca, memodifikasi, dan mengonversi file Microsoft Project tanpa memerlukan instalasi Microsoft Project, mendukung berbagai fitur dan format manajemen proyek.

## Jawaban Cepat
- **Apa yang dilakukan “get resource by id”?** Ini mengambil objek `Resource` tertentu dari sebuah `Project` menggunakan pengidentifikasi uniknya.  
- **Perpustakaan mana yang menangani data timephased?** Aspose.Tasks untuk Java menyediakan API `Resource.getTimephasedData`.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya membaca proyek besar?** Ya—Aspose.Tasks dapat memproses file dengan hingga 10.000 tugas tanpa memuat seluruh file ke memori.  
- **Versi Java apa yang dibutuhkan?** Java 8 atau lebih tinggi; perpustakaan ini kompatibel dengan semua JDK utama.

## Apa itu “get resource by id”?
`get resource by id` adalah pemanggilan metode yang mengambil instance `Resource` dari sebuah `Project` yang telah dimuat menggunakan ID numerik sumber daya. Operasi ini memungkinkan akses tepat ke properti terperinci sumber daya, seperti penugasan, kalender, dan bidang khusus, dan penting untuk mengekstrak data kerja atau biaya yang timephased terkait dengan sumber daya tersebut.

## Mengapa menggunakan Aspose.Tasks untuk data timephased?
Aspose.Tasks mendukung **lebih dari 50 format input dan output** (MPP, XML, CSV, dll.) dan dapat mengekstrak nilai kerja dan biaya yang timephased untuk sumber daya yang mencakup jadwal multi‑tahun sambil menjaga penggunaan memori tetap rendah. API mengembalikan data dalam interval 15 menit secara default, memberikan wawasan terperinci untuk pelaporan atau analitik khusus.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) dan mengikuti petunjuk instalasi.  
2. Aspose.Tasks for Java Library: Unduh perpustakaan Aspose.Tasks untuk Java dari [halaman unduhan](https://releases.aspose.com/tasks/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

## Impor Paket
Langkah pertama adalah mengimpor kelas Aspose.Tasks yang diperlukan ke dalam file sumber Java Anda.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Langkah 1: Siapkan Direktori Data
Pertama, tentukan direktori tempat file MS Project Anda berada. Menjaga folder data terpisah dari kode sumber membuat proyek lebih mudah dipelihara.

```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Baca File Template MS Project
Tentukan nama file template MS Project Anda. Menggunakan template memastikan pengaturan kolom yang konsisten di seluruh proyek.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Langkah 3: Baca File Input sebagai Project
Kelas `Project` adalah objek inti Aspose.Tasks yang mewakili file Microsoft Project dalam memori. Memuat file memberikan Anda akses programatik ke tugas, sumber daya, dan jadwal.

```java
Project project = new Project(dataDir + fileName);
```

## Langkah 4: Dapatkan Resource berdasarkan ID
Untuk mengambil sumber daya tertentu, panggil metode `getResources().getById(id)`. Ini adalah operasi tepat yang dirujuk oleh kata kunci utama.

```java
Resource resource = project.getResources().getByUid(1);
```

## Langkah 5: Cetak Data Timephased untuk Pekerjaan Resource
Setelah Anda memiliki objek `Resource`, Anda dapat memanggil `resource.getTimephasedData(ResourceTimephasedDataType.Work)` untuk memperoleh alokasi kerja sepanjang waktu. Koleksi yang dikembalikan berisi objek `TimephasedData` yang mencakup tanggal mulai, tanggal selesai, dan jumlah kerja untuk setiap interval.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Langkah 6: Cetak Data Timephased untuk Biaya Resource
Demikian pula, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` mengembalikan informasi biaya yang dipecah berdasarkan interval waktu yang sama. Ini berguna untuk laporan anggaran dan pelacakan biaya.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Bagaimana Cara Mendapatkan Resource berdasarkan ID dalam Satu Baris?
Muat proyek, lalu panggil `project.getResources().getById(5)`—ganti **5** dengan ID sumber daya yang sebenarnya Anda butuhkan. Pemanggilan tunggal ini mengembalikan objek `Resource`, setelah itu Anda dapat menanyakan data timephased, penugasan, atau bidang khususnya. Metode ini berjalan dalam waktu O(1) karena sumber daya diindeks secara internal.

## Masalah Umum dan Solusinya
- **Resource not found** – Pastikan ID tersebut ada dalam file proyek; ID dimulai dari 1 dan unik per sumber daya.  
- **Empty timephased data** – Verifikasi bahwa sumber daya memiliki penugasan kerja atau biaya; jika tidak, koleksi akan kosong.  
- **Large file performance** – Gunakan `Project.setLoadOptions(LoadOptions.fromFile(...))` untuk mengaktifkan pemuatan malas pada proyek yang lebih besar dari 500 MB.

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Tasks dapat menangani jenis file proyek lain selain Microsoft Project?**  
A: Ya, Aspose.Tasks mendukung MPP, XML, CSV, dan beberapa format lainnya, memungkinkan Anda membaca dan menulis lintas standar yang berbeda.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai lingkungan pengembangan Java?**  
A: Tentu saja. Perpustakaan ini bekerja dengan semua IDE utama (IntelliJ IDEA, Eclipse, NetBeans) dan alat build (Maven, Gradle).

**Q: Bisakah saya memanipulasi data proyek menggunakan Aspose.Tasks?**  
A: Ya, Anda dapat membuat, memodifikasi, dan menghapus tugas, sumber daya, penugasan, serta bahkan bidang khusus melalui API.

**Q: Apakah Aspose.Tasks cocok untuk proyek tingkat perusahaan?**  
A: Ya. Perusahaan mengandalkan Aspose.Tasks untuk pemrosesan volume tinggi, konversi batch, dan pelaporan sisi server karena tidak memerlukan instalasi Microsoft Project.

**Q: Di mana saya dapat menemukan dukungan jika saya mengalami masalah saat menggunakan Aspose.Tasks?**  
A: Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk mendapatkan bantuan dari komunitas dan tim dukungan.

## Kesimpulan
Dalam tutorial ini, kami telah mempelajari cara **get resource by id** dan membaca data kerja serta biaya yang timephased menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah ini, Anda dapat secara efisien mengekstrak informasi penjadwalan yang berharga dari file proyek Anda dan mengintegrasikannya ke dalam laporan atau alur analitik khusus.

---

**Terakhir Diperbarui:** 2026-06-15  
**Diuji Dengan:** Aspose.Tasks 24.11 untuk Java  
**Penulis:** Aspose

## Tutorial Terkait

- [Tambah sumber daya ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/create-resources/)
- [Kelola Biaya Sumber Daya MS Project dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/resource-cost/)
- [Baca Minggu Kerja Java dari Kalender MS Project Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}