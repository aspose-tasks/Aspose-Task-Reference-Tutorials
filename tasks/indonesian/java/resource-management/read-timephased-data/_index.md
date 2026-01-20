---
date: 2026-01-20
description: Pelajari cara mendapatkan sumber daya berdasarkan ID dan mengekstrak
  data berwaktu dari sumber daya MS Project menggunakan Aspose.Tasks untuk Java.
linktitle: Get resource by id and read timephased data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Dapatkan sumber daya berdasarkan ID dan baca data berwaktu di Aspose.Tasks
url: /id/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan resource berdasarkan id dan baca data timephased di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, kami akan memandu Anda melalui **cara mendapatkan resource berdasarkan id** dan membaca data timephased untuk resource MS Project menggunakan Aspose.Tasks untuk Java. Baik Anda perlu menganalisis beban kerja resource atau distribusi biaya, mengekstrak informasi ini secara programatik menghemat banyak jam kerja manual.

## Jawaban Cepat
- **Apa kelas utama untuk memuat proyek?** `Project` dari `com.aspose.tasks`.
- **Bagaimana cara menemukan resource tertentu?** Gunakan `project.getResources().getByUid(resourceId)`.
- **Bisakah saya membaca data kerja dan biaya?** Ya – panggil `resource.getTimephasedData` dengan `TimephasedDataType` yang sesuai.
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.
- **Versi Java mana yang didukung?** Aspose.Tasks untuk Java mendukung JDK 8 dan yang lebih baru.

## Apa itu **get resource by id**?
`get resource by id` adalah pemanggilan metode yang mengambil objek `Resource` dari sebuah `Project` menggunakan pengidentifikasi unik (UID) resource tersebut. UID ini diberikan oleh Microsoft Project saat resource dibuat dan tetap konstan selama siklus hidup proyek.

## Mengapa membaca data timephased?
Data timephased memecah kerja atau biaya resource menjadi interval waktu terpisah (harian, mingguan, bulanan). Granularitas ini memungkinkan Anda:
- Membuat laporan khusus tentang pemanfaatan resource.
- Mengidentifikasi alokasi berlebih secara dini.
- Memberikan data ke alat peramalan atau penganggaran.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. **Java Development Kit (JDK)** – Instal JDK 8 atau yang lebih baru. Anda dapat mengunduhnya dari [situs web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) dan mengikuti petunjuk instalasi.  
2. **Aspose.Tasks for Java Library** – Unduh pustaka Aspose.Tasks untuk Java dari [halaman unduhan](https://releases.aspose.com/tasks/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.  

## Impor Paket
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Langkah 1: Siapkan Direktori Data
```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Baca File Template MS Project
```java
String fileName = "ResourceTimephasedData.mpp";
```

## Langkah 3: Muat Proyek (java read project resources)
```java
Project project = new Project(dataDir + fileName);
```

## Langkah 4: **Get resource by id**
Ambil resource yang diinginkan dari proyek menggunakan pengidentifikasi uniknya (ID). Pada contoh ini kami mengambil resource dengan UID = 1.

```java
Resource resource = project.getResources().getByUid(1);
```

## Langkah 5: Cetak Data Timephased untuk Pekerjaan Resource
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Langkah 6: Cetak Data Timephased untuk Biaya Resource
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| **NullPointerException when calling `resource.getTimephasedData`** | Tanggal mulai atau selesai proyek mungkin tidak ada. | Pastikan file proyek berisi tanggal mulai/selesai yang valid atau berikan tanggal secara eksplisit. |
| **Incorrect UID** | Resource dalam file mungkin memiliki UID yang berbeda dari yang diharapkan. | Gunakan `project.getResources().toList()` untuk menenumerasi UID yang tersedia sebelum mengambil. |
| **Missing license** | Aspose.Tasks melemparkan pengecualian jika lisensi yang valid tidak dimuat dalam build produksi. | Muat file lisensi Anda melalui `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## FAQ
### Bisakah Aspose.Tasks menangani jenis file proyek lain selain Microsoft Project?
Ya, Aspose.Tasks mendukung berbagai format file, termasuk MPP, XML, dan CSV.

### Apakah Aspose.Tasks kompatibel dengan berbagai lingkungan pengembangan Java?
Ya, Aspose.Tasks kompatibel dengan semua IDE.

### Bisakah saya memanipulasi data proyek menggunakan Aspose.Tasks?
Tentu saja, Aspose.Tasks menyediakan API yang luas untuk membuat, memodifikasi, dan menganalisis data proyek.

### Apakah Aspose.Tasks cocok untuk proyek tingkat perusahaan?
Ya, Aspose.Tasks banyak digunakan di lingkungan perusahaan karena keandalannya dan skalabilitasnya.

### Di mana saya dapat menemukan dukungan jika saya mengalami masalah saat menggunakan Aspose.Tasks?
Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan dari komunitas dan tim dukungan.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara **mengekstrak data proyek** untuk beberapa resource sekaligus?**  
A: Lakukan perulangan pada `project.getResources()` dan panggil `getTimephasedData` untuk setiap resource di dalam loop.

**Q: Apakah ada cara mengubah interval waktu (mis., harian → mingguan)?**  
A: Ya, berikan `TimephasedDataType` seperti `TimephasedDataType.ResourceWork` bersama dengan koleksi `TimephasedData` yang dapat Anda agregasikan secara manual.

**Q: Bisakah saya mengekspor data timephased ke CSV?**  
A: Setelah data diambil, tulis ke file CSV menggunakan I/O Java standar (`FileWriter`/`BufferedWriter`).

**Q: Apakah Aspose.Tasks mendukung membaca file proyek yang dibuat pada versi MS Project yang lebih baru?**  
A: Pustaka ini secara rutin diperbarui untuk mendukung format MPP terbaru; selalu gunakan versi Asp apa yang perlu diperA: Muose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}