---
date: 2026-10-31
description: Pelajari cara menyimpan proyek sebagai PDF dan membaca basis data Microsoft
  Project dengan Aspose.Tasks for Java, serta menghubungkan ke Project Server, mengonversi
  proyek ke HTML, dan mengekspor proyek ke XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Membaca Data Proyek dari Basis Data Microsoft Project dalam Aspose.Tasks
og_description: Simpan proyek sebagai PDF dan baca basis data Microsoft Project menggunakan
  Aspose.Tasks for Java. Pelajari cara menghubungkan ke Project Server, mengekspor
  ke HTML, XML, dan CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Simpan proyek sebagai PDF dan baca basis data Microsoft Project dengan Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Simpan proyek sebagai PDF dan baca basis data Microsoft Project dengan Aspose.Tasks
  for Java
url: /id/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan proyek sebagai PDF dan baca basis data Microsoft Project dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan menemukan cara **membaca basis data Microsoft Project** secara langsung dari Microsoft Project Server dan kemudian **menyimpan proyek sebagai PDF** menggunakan Aspose.Tasks Java API. Baik Anda perlu menghasilkan laporan yang dapat dicetak, memigrasi data warisan, atau menyematkan informasi proyek ke portal khusus, panduan ini akan memandu Anda melalui setiap langkah—dari mengonfigurasi koneksi JDBC hingga mengekspor proyek ke PDF, XML, atau HTML. Pada akhir tutorial, Anda akan memiliki solusi siap produksi yang berjalan di server Java mana pun tanpa harus menginstal Microsoft Project.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks?** Menyediakan API pure‑Java untuk membaca, menulis, dan memanipulasi file serta basis data Microsoft Project.  
- **Apakah saya perlu menginstal Microsoft Project?** Tidak, Aspose.Tasks berfungsi secara independen dari Microsoft Project.  
- **Jenis basis data apa yang didukung?** Microsoft SQL Server, backend dari Project Server.  
- **Bisakah saya mengekspor ke format lain?** Ya—PDF, XML, HTML, CSV, PNG, JPEG, dan lainnya.  
- **Apa saja prasyarat utama?** JDK 8 atau lebih baru, perpustakaan Aspose.Tasks untuk Java, driver JDBC SQL Server, dan kredensial Project Server yang valid.

## Apa itu “baca basis data Microsoft Project”?
Membaca basis data Microsoft Project berarti menghubungkan ke repositori SQL Server Project Server, mengekstrak data proyek yang disimpan, dan memuatnya ke dalam objek `Project` yang dapat dimanipulasi oleh Aspose.Tasks. Pendekatan ini ideal untuk pelaporan otomatis, migrasi data, atau analitik khusus.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks untuk Java memungkinkan Anda bekerja dengan data Microsoft Project tanpa memerlukan aplikasi desktop, menawarkan solusi pure‑Java yang berjalan di platform apa pun. Ia menyediakan model objek yang komprehensif untuk tugas, sumber daya, kalender, dan bidang khusus, serta dapat menangani proyek perusahaan besar secara efisien, menjadikannya ideal untuk pelaporan otomatis, migrasi, dan skenario integrasi.

- **Tanpa ketergantungan Microsoft Project** – dapat dijalankan di server mana pun atau lingkungan CI.  
- **Model objek yang kaya** – mengakses tugas, sumber daya, penugasan, kalender, dan bidang khusus secara programatik.  
- **Berbagai opsi ekspor** – Aspose.Tasks mendukung ekspor ke **lebih dari 20 format file**, termasuk PDF, XML, HTML, CSV, PNG, dan JPEG, dengan satu panggilan API.  
- **Kinerja tinggi** – perpustakaan dapat memproses proyek yang berisi **hingga 10.000 tugas** dalam kurang dari satu menit, dan men-stream data untuk menghindari memuat seluruh file ke memori.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih baru).  
2. Perpustakaan Aspose.Tasks untuk Java ditambahkan ke classpath proyek Anda.  
3. Kredensial akses untuk basis data SQL Project Server (nama server, port, nama basis data, nama pengguna, kata sandi) untuk terhubung ke Project Server.  
4. Microsoft JDBC Driver untuk SQL Server (misalnya `sqljdbc4.jar`).  

## Impor paket
Pertama, impor kelas‑kelas yang diperlukan. Daftar ini mencakup kelas inti Aspose.Tasks dan utilitas standar Java.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Cara menghubungkan ke Project Server
Membangun koneksi yang andal adalah fondasi untuk membaca data proyek. Pastikan instance SQL Server dapat dijangkau dari host Java Anda dan login yang Anda gunakan memiliki izin **SELECT** pada skema Project Server. Anda juga harus memverifikasi latensi jaringan dan mengonfigurasi pengaturan SSL yang diperlukan untuk memastikan komunikasi yang aman.

## Langkah 1: menyiapkan koneksi basis data
Kelas `MspDbSettings` mengenkapsulasi detail koneksi JDBC yang diperlukan untuk mengakses basis data Microsoft Project Server. Buat instance `MspDbSettings` yang memuat string koneksi JDBC. Ganti nilai placeholder dengan detail server Anda yang sebenarnya.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Simpan string koneksi dalam file konfigurasi yang aman atau variabel lingkungan daripada menuliskan kredensial secara langsung di kode.

## Langkah 2: menambahkan driver JDBC
Muat driver Microsoft SQL Server JDBC pada runtime sehingga JVM dapat berkomunikasi dengan basis data.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Pastikan versi driver cocok dengan versi SQL Server Anda. Menggunakan driver yang tidak kompatibel dapat menyebabkan kegagalan koneksi.

## Langkah 3: membaca data proyek
Kelas `Project` mewakili file Microsoft Project yang dimuat ke memori, menampilkan tugas, sumber daya, dan penugasan. Buat objek `Project` dengan memberikan `MspDbSettings`. Aspose.Tasks akan mengambil data proyek dari basis data secara otomatis.

```java
Project project = new Project(settings);
```

Pada titik ini Anda dapat menjelajahi objek `project`—mendaftar tugas, sumber daya, atau memodifikasi bidang sesuai kebutuhan.

## Langkah 4: menyimpan proyek sebagai PDF
Enum `SaveFileFormat` menentukan format output untuk metode `Project.save`, seperti PDF, XML, atau HTML. Ekspor proyek yang telah dimuat ke format file pilihan Anda. Contoh di bawah menyimpan proyek sebagai **PDF**, yang sempurna untuk laporan yang dapat dicetak. Anda juga dapat **mengekspor proyek ke XML** atau **mengonversi proyek ke HTML** dengan mengubah enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Jika Anda lebih suka XML, cukup ganti `SaveFileFormat.Pdf` dengan `SaveFileFormat.Xml`. Untuk output HTML, gunakan `SaveFileFormat.Html`.

## Masalah umum & solusi
| Masalah | Penyebab umum | Solusi |
|-------|---------------|-----|
| **Connection timeout** | Server/port salah atau firewall memblokir | Verifikasi alamat server, buka port 1433, dan uji konektivitas dengan program tes JDBC sederhana. |
| **Authentication error** | Nama pengguna/kata sandi tidak valid atau SQL Server tidak dikonfigurasi untuk otentikasi SQL | Gunakan login SQL yang valid atau aktifkan otentikasi mode campuran pada server. |
| **Driver not found** | JDBC jar tidak ada di classpath | Pastikan `addJDBCDriver` mengarah ke file `.jar` yang tepat dan bahwa path menggunakan double backslashes (`\\`). |
| **Empty project after load** | Izin tidak cukup untuk membaca tabel Project Server | Berikan login hak SELECT pada skema basis data Project Server. |

## Pertanyaan yang sering diajukan

**Q: Bisakah Aspose.Tasks digunakan untuk membaca data proyek dari basis data lain selain Microsoft Project?**  
A: Ya, Aspose.Tasks mendukung pembacaan data proyek dari file XML, basis data Primavera, dan format proyek standar lainnya.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi Microsoft Project?**  
A: Ya, perpustakaan ini bekerja dengan Microsoft Project 2007 hingga rilis terbaru 2024, memastikan integrasi mulus di semua versi.

**Q: Dapatkah saya memanipulasi data proyek sebelum menyimpannya?**  
A: Tentu saja, Anda dapat menambah, memperbarui, atau menghapus tugas, sumber daya, dan bidang khusus menggunakan API yang kaya sebelum mengekspor.

**Q: Apakah Aspose.Tasks mendukung banyak format output?**  
A: Ya, Anda dapat menyimpan proyek sebagai PDF, XML, HTML, CSV, PNG, JPEG, dan lainnya—lebih dari 20 format secara total.

**Q: Di mana saya dapat menemukan dukungan atau bantuan lebih lanjut tentang Aspose.Tasks?**  
A: Untuk bantuan tambahan, kunjungi forum Aspose.Tasks atau jelajahi dokumentasi yang tersedia di situs web [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kesimpulan
Dengan mengikuti panduan langkah‑demi‑langkah ini, Anda kini tahu cara **membaca basis data Microsoft Project**, **menyimpan proyek sebagai PDF**, dan mengekspor ke format lain menggunakan Aspose.Tasks untuk Java. Pendekatan ini menghilangkan ketergantungan pada Microsoft Project, menyederhanakan pelaporan otomatis, dan membuka peluang integrasi khusus yang kuat.

---

**Terakhir Diperbarui:** 2026-10-31  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.5 (terbaru pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menyimpan Proyek sebagai PDF dengan Aspose.Tasks – Panduan Ekspor](/tasks/java/project-file-operations/save-as-pdf/)
- [Simpan Proyek sebagai PDF – Render Lembar Tugas dengan Aspose.Tasks untuk Java](/tasks/java/task-properties/render-task-sheet/)
- [Ekspor Proyek ke PDF dan Kurangi Jarak Antara Daftar Tugas dan Footer di Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}