---
title: Membaca Data Online Proyek MS yang Mudah dengan Aspose.Tasks
linktitle: Membaca Data Online Proyek di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membaca data Microsoft Project Online dengan mudah menggunakan Aspose.Tasks untuk Java. Tingkatkan kemampuan manajemen proyek Anda.
type: docs
weight: 13
url: /id/java/project-data-reading/read-project-online/
---
## Perkenalan
Dalam bidang manajemen proyek, menangani data Microsoft Project Online secara efisien sangat penting untuk kelancaran operasi. Aspose.Tasks untuk Java memberikan solusi tangguh untuk membaca data tersebut dengan mudah. Tutorial ini mempelajari pemanfaatan Aspose.Tasks untuk mengakses dan memanipulasi data MS Project Online dengan lancar.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Instal JDK untuk mengkompilasi dan menjalankan program Java.
2.  Aspose.Tasks untuk Java Library: Unduh dan sertakan perpustakaan Aspose.Tasks dalam proyek Java Anda. Anda dapat memperolehnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Akun Microsoft Project Online: Dapatkan kredensial yang valid untuk mengakses data MS Project Online.
4. Alamat Domain SharePoint: Alamat domain SharePoint tempat data MS Project Online Anda berada.
5. Nama Pengguna dan Kata Sandi: Kredensial untuk mengautentikasi akses ke MS Project Online.
## Paket Impor
Di proyek Java Anda, impor paket Aspose.Tasks yang diperlukan untuk integrasi yang lancar:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Langkah 1: Tetapkan Alamat Domain SharePoint, Nama Pengguna, dan Kata Sandi
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Mengganti`"https://contoso.sharepoint.com"` dengan alamat domain SharePoint Anda,`"admin@contoso.onmicrosoft.com"` dengan nama pengguna Anda, dan`"MyPassword"` dengan kata sandi Anda.
## Langkah 2: Otentikasi dengan Kredensial Server Proyek
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Membuat`ProjectServerCredentials` objek dengan alamat domain SharePoint, nama pengguna, dan kata sandi. Kemudian inisialisasi`ProjectServerManager` dengan kredensial ini.
## Langkah 3: Ambil Daftar Proyek dan Tampilkan Informasi
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Iterasi melalui daftar proyek yang diperoleh dari`reader.getProjectList()` dan menampilkan detail proyek seperti nama, tanggal pembuatan, dan tanggal terakhir disimpan.
## Langkah 4: Muat Proyek Individual dan Jumlah Sumber Daya Keluaran
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Untuk setiap proyek, muat menggunakan`reader.getProject(p.getId())` dan menampilkan nama proyek beserta jumlah sumber daya terkait.

## Kesimpulan
Aspose.Tasks untuk Java menyederhanakan proses membaca data MS Project Online, menawarkan pengembang perangkat yang kuat untuk menyederhanakan tugas manajemen proyek. Dengan mengikuti tutorial ini, Anda dapat mengintegrasikan Aspose.Tasks secara efisien ke dalam aplikasi Java Anda untuk mengakses dan memanipulasi data proyek dengan mudah.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks for Java untuk mengubah data MS Project Online?
J: Ya, Aspose.Tasks menyediakan kemampuan luas tidak hanya untuk membaca tetapi juga memodifikasi data MS Project Online secara terprogram.
### T: Apakah Aspose.Tasks mendukung format file manajemen proyek lainnya?
J: Tentu saja, Aspose.Tasks mendukung berbagai format file termasuk MPP, XML, dan lainnya, memastikan kompatibilitas dengan beragam sistem manajemen proyek.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat memanfaatkan uji coba gratis dari[Di Sini](https://releases.aspose.com/) untuk menjelajahi fitur dan fungsi Aspose.Tasks.
### T: Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Tasks untuk Java?
 J: Anda dapat merujuk ke dokumentasi detailnya[Di Sini](https://reference.aspose.com/tasks/java/)untuk panduan komprehensif dalam memanfaatkan Aspose.Tasks dalam proyek Java Anda.
### T: Opsi dukungan apa yang tersedia untuk Aspose.Tasks untuk Java?
 J: Jika Anda mengalami masalah atau memiliki pertanyaan, Anda dapat meminta bantuan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).