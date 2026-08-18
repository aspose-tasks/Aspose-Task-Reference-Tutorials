---
date: 2026-02-18
description: Pelajari cara menyimpan proyek sebagai PDF dan membaca basis data Microsoft
  Project dengan Aspose.Tasks untuk Java, serta menghubungkan ke Project Server, mengonversi
  proyek ke HTML, dan mengekspor proyek ke XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Simpan proyek sebagai PDF dan baca DB Proyek dengan Aspose.Tasks untuk Java
url: /id/java/project-data-reading/read-project-database/
weight: 12
---

codes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan proyek sebagai PDF dan baca basis data Microsoft Project dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan menemukan cara **membaca basis data Microsoft Project** secara langsung dari Microsoft Project Server dan kemudian **menyimpan proyek sebagai PDF** menggunakan API Aspose.Tasks Java. Apakah Anda perlu menghasilkan laporan, memigrasi data, atau mengintegrasikan informasi proyek ke dalam aplikasi Anda sendiri, panduan ini akan memandu Anda melalui setiap langkah—dari menyiapkan koneksi basis data hingga mengekspor proyek ke PDF, XML, atau HTML. Pada akhir tutorial, Anda akan memiliki solusi siap produksi yang solid dan berfungsi tanpa menginstal Microsoft Project di mesin host.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks?** Ia menyediakan API pure‑Java untuk membaca, menulis, dan memanipulasi file serta basis data Microsoft Project.  
- **Apakah saya perlu menginstal Microsoft Project?** Tidak, Aspose.Tasks bekerja secara independen dari Microsoft Project.  
- **Jenis basis data apa yang didukung?** Microsoft SQL Server (backend dari Project Server).  
- **Bisakah saya mengekspor ke format lain?** Ya, selain PDF Anda dapat menyimpan ke XML, HTML, CSV, dan lainnya.  
- **Apa saja prasyarat utama?** JDK, pustaka Aspose.Tasks untuk Java, driver JDBC SQL Server, dan kredensial untuk **menghubungkan ke Project Server**.

## Apa itu “membaca basis data Microsoft Project”?
Membaca basis data Microsoft Project berarti menghubungkan ke repositori SQL Server Project Server, mengekstrak data proyek yang disimpan, dan memuatnya ke dalam objek `Project` yang dapat dimanipulasi oleh Aspose.Tasks. Pendekatan ini ideal untuk pelaporan otomatis, migrasi data, atau analitik khusus.

## Mengapa menggunakan Aspose.Tasks untuk Java?
- **Tanpa ketergantungan Microsoft Project** – dapat dijalankan di server mana pun atau lingkungan CI.  
- **Model objek yang kaya** – mengakses tugas, sumber daya, penugasan, kalender, dan bidang khusus secara programatik.  
- **Berbagai opsi ekspor** – PDF, XML, HTML, PNG, dll., dengan satu panggilan API.  
- **Kinerja tinggi** – dioptimalkan untuk proyek perusahaan besar.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih baru).  
2. Pustaka Aspose.Tasks untuk Java ditambahkan ke classpath proyek Anda.  
3. Kredensial akses untuk basis data SQL Project Server (nama server, port, nama basis data, nama pengguna, kata sandi) **untuk menghubungkan ke Project Server**.  
4. Driver JDBC Microsoft untuk SQL Server (misalnya, `sqljdbc4.jar`).  

## Impor Paket
Pertama, impor kelas-kelas yang Anda perlukan. Daftar ini mencakup kelas inti Aspose.Tasks dan utilitas Java standar.

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
Membangun koneksi yang dapat diandalkan adalah dasar untuk membaca data proyek. Pastikan instance SQL Server dapat dijangkau dari host Java Anda dan login yang Anda gunakan memiliki izin **SELECT** pada skema Project Server.

## Langkah 1: Siapkan Koneksi Basis Data
Buat instance `MspDbSettings` yang menyimpan string koneksi JDBC. Ganti nilai placeholder dengan detail server Anda yang sebenarnya.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Tip Pro:** Simpan string koneksi dalam file konfigurasi yang aman atau variabel lingkungan daripada menuliskan kredensial secara langsung.

## Langkah 2: Tambahkan Driver JDBC
Muat driver JDBC Microsoft SQL Server pada waktu berjalan sehingga JVM dapat berkomunikasi dengan basis data.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Peringatan:** Pastikan versi driver cocok dengan versi SQL Server Anda. Menggunakan driver yang tidak kompatibel dapat menyebabkan kegagalan koneksi.

## Langkah 3: Baca Data Proyek
Instansiasi objek `Project` dengan memberikan `MspDbSettings`. Aspose.Tasks akan secara otomatis mengambil data proyek dari basis data.

```java
Project project = new Project(settings);
```

Pada titik ini Anda dapat menjelajahi objek `project`—menampilkan daftar tugas, sumber daya, atau memodifikasi bidang sesuai kebutuhan.

## Langkah 4: Simpan proyek sebagai PDF
Ekspor proyek yang dimuat ke format file pilihan Anda. Contoh di bawah menyimpan proyek sebagai **PDF**, yang sempurna untuk laporan yang dapat dicetak. Anda juga dapat **mengekspor proyek ke XML** atau **mengonversi proyek ke HTML** dengan mengubah enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Jika Anda lebih suka XML, cukup ganti `SaveFileFormat.Pdf` dengan `SaveFileFormat.Xml`. Untuk output HTML, gunakan `SaveFileFormat.Html`.

## Masalah Umum & Solusi
| Masalah | Penyebab Umum | Solusi |
|-------|---------------|-----|
| **Timeout koneksi** | Server/port salah atau firewall memblokir | Verifikasi alamat server, buka port 1433, dan uji konektivitas dengan program tes JDBC sederhana. |
| **Kesalahan otentikasi** | Nama pengguna/kata sandi tidak valid atau SQL Server tidak dikonfigurasi untuk otentikasi SQL | Gunakan login SQL yang valid atau aktifkan otentikasi mode campuran pada server. |
| **Driver tidak ditemukan** | JDBC jar tidak ada di classpath | Pastikan `addJDBCDriver` mengarah ke file `.jar` yang benar dan bahwa path menggunakan double backslashes (`\\`). |
| **Proyek kosong setelah dimuat** | Izin tidak cukup untuk membaca tabel Project Server | Berikan login hak SELECT pada skema basis data Project Server. |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah Aspose.Tasks digunakan untuk membaca data proyek dari basis data lain selain Microsoft Project?**  
A: Ya, Aspose.Tasks mendukung pembacaan data proyek dari berbagai sumber, termasuk file XML, Primavera, dan basis data Microsoft Project.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi Microsoft Project?**  
A: Ya, Aspose.Tasks dirancang untuk bekerja dengan banyak versi Microsoft Project, memastikan integrasi yang mulus.

**Q: Dapatkah saya memanipulasi data proyek sebelum menyimpannya?**  
A: Tentu saja, Aspose.Tasks menyediakan API yang kaya untuk menambahkan tugas, memperbarui sumber daya, dan mengatur properti proyek sebelum ekspor.

**Q: Apakah Aspose.Tasks mendukung banyak format output?**  
A: Ya, Anda dapat menyimpan proyek sebagai PDF, XML, HTML, CSV, PNG, JPEG, dan lainnya.

**Q: Di mana saya dapat menemukan dukungan atau bantuan lebih lanjut tentang Aspose.Tasks?**  
A: Untuk bantuan tambahan, kunjungi forum Aspose.Tasks atau jelajahi dokumentasi yang tersedia di situs web [di sini](https://forum.aspose.com/c/tasks/15).

## Kesimpulan
Dengan mengikuti panduan langkah demi langkah ini, Anda kini tahu cara **membaca basis data Microsoft Project**, **menyimpan proyek sebagai PDF**, dan mengekspor ke format lain menggunakan Aspose.Tasks untuk Java. Pendekatan ini menghilangkan ketergantungan pada Microsoft Project, mempermudah pelaporan otomatis, dan membuka pintu untuk integrasi khusus yang kuat.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}