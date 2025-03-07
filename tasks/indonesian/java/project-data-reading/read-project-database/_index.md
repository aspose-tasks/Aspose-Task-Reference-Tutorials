---
title: Membaca Data Proyek dari MS Project Database di Aspose.Tasks
linktitle: Membaca Data Proyek dari Microsoft Project Database di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membaca data proyek dari Microsoft Project Database menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah dengan contoh kode.
weight: 12
url: /id/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membaca Data Proyek dari MS Project Database di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara membaca data proyek dari Microsoft Project Database menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah Java API canggih yang memungkinkan pengembang memanipulasi dokumen Microsoft Project tanpa perlu menginstal Microsoft Project. Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda akan mempelajari cara mengekstrak data proyek secara efisien dari database dan menyimpannya dalam format yang diinginkan.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan dasar tentang pemrograman Java.
2. Java Development Kit (JDK) diinstal pada sistem Anda.
3. Aspose.Tasks untuk perpustakaan Java diunduh dan dikonfigurasi di proyek Anda.

## Paket Impor
Untuk memulai, impor paket yang diperlukan:
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
## Langkah 1: Siapkan Koneksi Basis Data
Pertama, Anda perlu mengatur koneksi ke Microsoft Project Database. Ini termasuk menentukan URL database, nama server, nomor port, nama database, nama pengguna, dan kata sandi.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Langkah 2: Tambahkan Driver JDBC
Selanjutnya, Anda perlu menambahkan driver JDBC ke proyek Anda. Driver ini memfasilitasi komunikasi antara aplikasi Java dan database Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Langkah 3: Baca Data Proyek
 Sekarang, buat a`Project` objek dan memuat data proyek dari database menggunakan pengaturan yang telah ditentukan sebelumnya.
```java
Project project = new Project(settings);
```
## Langkah 4: Simpan Data Proyek
Terakhir, simpan data proyek ke format yang diinginkan. Dalam contoh ini, kami menyimpannya sebagai file XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Selamat! Anda telah berhasil membaca data proyek dari Microsoft Project Database menggunakan Aspose.Tasks untuk Java.

## Kesimpulan
Dalam tutorial ini, kami membahas proses membaca data proyek dari Microsoft Project Database menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat mengekstrak informasi proyek dengan lancar dan memanipulasinya sesuai kebutuhan Anda. Aspose.Tasks menyederhanakan penanganan dokumen Microsoft Project, memungkinkan ekstraksi dan manipulasi data yang efisien.
## FAQ
### T: Bisakah Aspose.Tasks digunakan untuk membaca data proyek dari database lain selain Microsoft Project?
J: Ya, Aspose.Tasks mendukung pembacaan data proyek dari berbagai sumber, termasuk file XML, Primavera, dan database Microsoft Project.
### T: Apakah Aspose.Tasks kompatibel dengan versi Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks dirancang untuk bekerja dengan versi Microsoft Project yang berbeda, memastikan kompatibilitas dan integrasi yang lancar.
### T: Dapatkah saya memanipulasi data proyek sebelum menyimpannya?
J: Tentu saja, Aspose.Tasks menyediakan berbagai fitur untuk memanipulasi data proyek, seperti menambahkan tugas, memperbarui sumber daya, dan mengatur properti proyek.
### T: Apakah Aspose.Tasks mendukung berbagai format keluaran?
J: Ya, Aspose.Tasks mendukung berbagai format keluaran, termasuk XML, PDF, HTML, dan format gambar seperti PNG dan JPEG.
### T: Di mana saya dapat menemukan dukungan atau bantuan lebih lanjut dengan Aspose.Tasks?
 J: Untuk dukungan atau bantuan tambahan, Anda dapat mengunjungi forum Aspose.Tasks atau menjelajahi dokumentasi yang tersedia di situs web[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
