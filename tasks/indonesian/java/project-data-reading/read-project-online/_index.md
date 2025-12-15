---
date: 2025-12-15
description: Pelajari cara membaca data MS Project Online menggunakan Aspose Tasks
  Java. Panduan ini menunjukkan cara mengambil daftar proyek, daftar proyek SharePoint,
  dan mendapatkan jumlah sumber daya.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Membaca Data MS Project Online dengan Mudah'
url: /id/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Membaca Data MS Project Online dengan Mudah

## Introduction
Dalam dunia manajemen proyek, menangani data Microsoft Project Online secara efisien sangat penting untuk operasi yang terkelola dengan baik. **aspose tasks java** menyediakan API yang kuat dan mudah‑digunakan yang memungkinkan Anda membaca data Project Online tanpa harus berurusan dengan panggilan HTTP tingkat rendah. Pada tutorial ini kami akan menunjukkan cara mengambil daftar proyek, menampilkan proyek SharePoint, dan mendapatkan jumlah sumber daya dari setiap proyek—semua hanya dengan beberapa baris kode Java.

## Quick Answers
- **Apa yang dilakukan aspose tasks java?** Membaca dan memanipulasi file Microsoft Project serta data Project Online secara programatik.  
- **Apakah saya memerlukan lisensi untuk mencobanya?** Tersedia percobaan gratis; lisensi diperlukan untuk penggunaan produksi.  
- **Kredensial apa yang dibutuhkan?** Domain SharePoint, nama pengguna, dan kata sandi (atau token Azure AD).  
- **Bisakah saya menampilkan daftar proyek SharePoint?** Ya – gunakan `ProjectServerManager.getProjectList()` untuk mengambilnya.  
- **Bagaimana cara mendapatkan jumlah sumber daya?** Muat setiap objek `Project` dan panggil `project.getResources().size()`.

## What is aspose tasks java?
**aspose tasks java** adalah pustaka yang ditujukan bagi pengembang yang menyederhanakan kompleksitas format file Microsoft Project dan REST API Project Server. Pustaka ini memungkinkan Anda membaca, membuat, dan memodifikasi data proyek secara langsung dari aplikasi Java, sehingga integrasi dengan sistem perusahaan yang ada menjadi mudah.

## Why use aspose tasks java for reading MS Project Online?
- **Tidak perlu menangani HTTP secara manual** – pustaka mengurus otentikasi dan panggilan REST.  
- **Keamanan tipe yang kuat** – bekerja dengan `Project`, `ProjectInfo`, dan POJO lainnya alih‑alih JSON mentah.  
- **Lintas‑platform** – dapat dijalankan di lingkungan JVM apa pun.  
- **Fitur lengkap** – selain membaca, Anda juga dapat memperbarui tugas, sumber daya, dan timeline.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – JDK 8 atau yang lebih tinggi terpasang.  
2. **Aspose.Tasks for Java library** – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – dengan izin untuk membaca proyek.  
4. **SharePoint domain address** – tempat instance Project Online Anda berada.  
5. **Username and password** – atau kredensial Azure AD yang sesuai untuk otentikasi.

## Import Packages
Pertama, impor kelas Aspose.Tasks penting yang akan kita gunakan sepanjang tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Step 1: Set SharePoint Domain, Username, and Password
Tentukan detail koneksi untuk lingkungan Project Online Anda. Ganti nilai placeholder dengan kredensial Anda sendiri.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Step 2: Authenticate with Project Server Credentials
Buat objek `ProjectServerCredentials` dan inisialisasi `ProjectServerManager`. Manajer ini akan menangani semua panggilan selanjutnya ke Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Step 3: Retrieve Project List and Display Information
Gunakan manajer untuk **mengambil daftar proyek** (menampilkan proyek SharePoint) dan cetak detail dasar seperti nama, tanggal pembuatan, dan tanggal terakhir disimpan.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Step 4: Load Individual Projects and Output Resource Count
Untuk setiap proyek yang dikembalikan pada langkah sebelumnya, muat objek `Project` lengkap dan tampilkan **jumlah sumber daya**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Common Issues and Solutions
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **Authentication failed** | Domain, nama pengguna, atau kata sandi tidak tepat. | Verifikasi kredensial dan pastikan akun memiliki izin baca Project Online. |
| **SSLHandshakeException** | Runtime Java tidak memiliki versi TLS yang diperlukan. | Perbarui JDK ke rilis terbaru atau aktifkan TLS 1.2+. |
| **`reader.getProjectList()` returns empty** | Akun tidak memiliki akses ke proyek apa pun. | Periksa izin Project Online atau gunakan akun admin. |
| **Large projects cause OutOfMemoryError** | Memuat banyak proyek sekaligus menghabiskan memori. | Muat proyek satu per satu dan lepaskan referensi setelah selesai. |

## Frequently Asked Questions
### Q: Can I use aspose tasks java to modify MS Project Online data?
A: Yes, Aspose.Tasks provides extensive capabilities for both reading **and** modifying Project Online data programmatically.

### Q: Does Aspose.Tasks support other project management file formats?
A: Absolutely. It supports MPP, XML, Primavera, and many more, ensuring compatibility across diverse project ecosystems.

### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can avail of a free trial from [here](https://releases.aspose.com/) to explore the features and functionalities of Aspose.Tasks.

### Q: Where can I find comprehensive documentation for Aspose.Tasks for Java?
A: You can refer to the detailed documentation [here](https://reference.aspose.com/tasks/java/) for comprehensive guidance on utilizing Aspose.Tasks in your Java projects.

### Q: What support options are available for Aspose.Tasks for Java?
A: If you encounter any issues or have queries, you can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2025-12-15  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}