---
date: 2026-03-29
description: Pelajari cara mengatur kata kunci dan tanggal pembuatan java dalam proyek
  MPP menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah dengan contoh
  kode.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menetapkan Kata Kunci dalam Ringkasan Proyek MPP dengan Aspose.Tasks
url: /id/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Kata Kunci dalam Ringkasan Proyek MPP dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan menemukan **cara mengatur kata kunci** dan informasi ringkasan lainnya untuk file proyek MPP dengan menggunakan Aspose.Tasks untuk Java. Apakah Anda perlu menyematkan detail penulis, nomor revisi, atau tanggal pembuatan khusus, panduan ini akan memandu Anda melalui langkah‑langkah yang tepat, lengkap dengan kode yang siap dijalankan. Pada akhir tutorial Anda akan dapat mengatur kata kunci, mengatur tanggal pembuatan java, dan mengambil data kembali dari file.

## Jawaban Cepat
- **Perpustakaan apa yang digunakan?** Aspose.Tasks for Java  
- **Tujuan utama?** Mengatur kata kunci, info penulis, dan tanggal pembuatan dalam file MPP  
- **Berapa banyak langkah kode?** Tiga blok kode sederhana (inisialisasi, simpan, baca)  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi  
- **Versi Java yang didukung?** Java 8 ke atas  

## Apa itu “cara mengatur kata kunci” dalam file MPP?
Kata kunci adalah bidang metadata yang disimpan di dalam file Microsoft Project (MPP). Mereka membantu mengkategorikan proyek, memungkinkan pencarian cepat, dan memberikan informasi kontekstual untuk alat‑alat downstream. Aspose.Tasks menyediakan properti `Prj.KEYWORDS`, sehingga mudah untuk menulis atau memperbarui nilai ini secara programatik.

## Mengapa menggunakan Aspose.Tasks untuk Java untuk mengatur kata kunci dan tanggal pembuatan?
* **Kompatibilitas .MPP penuh** – bekerja dengan semua format Project 2007‑2023.  
* **Tidak memerlukan instalasi COM atau Office** – Java murni, sempurna untuk lingkungan server‑side.  
* **API kaya** – selain kata kunci, Anda dapat mengatur penulis, revisi, komentar, dan tanggal dalam satu panggilan.  
* **Dioptimalkan untuk kinerja** – baca/tulis cepat bahkan untuk file proyek besar.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:
1. **Java Development Kit (JDK)** – JDK 8 atau yang lebih baru terpasang.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, atau editor apa pun yang Anda sukai.

## Mengimpor Paket
Pertama, impor kelas‑kelas yang Anda perlukan. Impor ini memberi Anda akses ke objek `Project`, enumerasi `Prj` untuk bidang ringkasan, dan enum `SaveFileFormat` untuk penyimpanan.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Langkah 1: Menyiapkan Proyek dan Mendefinisikan Informasi Ringkasan
Buat instance `Project`, lalu gunakan metode `set` untuk menulis metadata yang diinginkan. Perhatikan bagaimana kami **mengatur kata kunci** dan **mengatur tanggal pembuatan java** menggunakan objek `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Langkah 2: Menyimpan Informasi Ringkasan Proyek
Setelah mengisi bidang‑bidang, simpan perubahan. Di sini kami menyimpan proyek sebagai XML untuk inspeksi mudah, tetapi Anda juga dapat menyimpan kembali ke MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Langkah 3: Membaca Informasi Ringkasan Proyek
Untuk memverifikasi bahwa metadata telah ditulis dengan benar, muat ulang file dan baca kembali setiap properti. Langkah ini menunjukkan bahwa **cara mengatur kata kunci** benar‑benar berfungsi end‑to‑end.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **NullPointerException** pada `project.get(Prj.CREATION_DATE)` | Kalender tidak pernah diset sebelum penyimpanan. | Pastikan Anda memanggil `project.set(Prj.CREATION_DATE, cal.getTime())` sebelum `save()`. |
| **Kata kunci tidak muncul** di UI Microsoft Project | File disimpan sebagai XML dan dibuka langsung di Project. | Simpan kembali ke MPP (`SaveFileFormat.MPP`) atau buka XML melalui *Import* di Project. |
| **Nilai tanggal** bergeser karena zona waktu | Java Date mencakup informasi zona waktu. | Gunakan `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` jika Anda memerlukan tanggal UTC. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan pustaka Java lain?**  
A: Ya, Aspose.Tasks untuk Java dapat diintegrasikan secara mulus dengan pustaka Java lain untuk meningkatkan kemampuan manajemen proyek Anda.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis dari [here](https://releases.aspose.com/).

**Q: Seberapa sering Aspose.Tasks untuk Java diperbarui?**  
A: Aspose.Tasks untuk Java secara rutin diperbarui untuk memastikan kompatibilitas dengan versi terbaru Java dan file Microsoft Project.

**Q: Bisakah saya menyesuaikan informasi ringkasan proyek lebih lanjut?**  
A: Tentu saja, Aspose.Tasks untuk Java menyediakan opsi yang luas untuk menyesuaikan informasi ringkasan proyek sesuai dengan kebutuhan spesifik Anda.

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}