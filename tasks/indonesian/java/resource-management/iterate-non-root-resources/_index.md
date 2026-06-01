---
date: 2026-01-13
description: Pelajari cara mengiterasi sumber daya non‑akar dalam file Microsoft Project
  menggunakan Aspose.Tasks untuk Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Iterasi Sumber Daya Non-Akar dengan Aspose.Tasks untuk Java
url: /id/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Iterasi Sumber Daya Non-Root dengan Aspose.Tasks untuk Java

## Perkenalan
Aspose.Tasks untuk Java adalah pustaka yang kuat yang memberikan pengembang cara bersih dan fokus‑objek untuk bekerja dengan file Microsoft Project. Dalam tutorial ini Anda akan belajar **cara mengiterasi sumber daya non-root** sehingga Anda dapat membaca, memodifikasi, atau menganalisis data sumber daya tanpa membuang dengan placeholder root. Baik Anda sedang membangun alat pelaporan, skrip migrasi, atau penjadwalan khusus, penguasaan teknik ini akan membuat kode Anda lebih tepat dan efisien.

## Jawaban Cepat
- **Apa arti “sumber daya non‑root”?**Sebuah sumber daya yang bukan placeholder “Project” default (node ​​root).
- **Mengapa menyaring sumber daya root?**Root tidak memiliki penjadwalan data yang berguna dan dapat membuat laporan menjadi berantakan.
- **Kelas Aspose.Tasks mana yang menyediakan koleksi sumber daya?**`Project.getResources()`.
- **Apakah saya memerlukan lisensi untuk kode ini?**Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- ** membujuk saya menggunakan ini dengan Java17?**Ya – Aspose.Tasks mendukung Java8 ke atas.

## Prasyarat
Sebelum menyelam ke dalam kode, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – Instal JDK terbaru dari [situs web Oracle](https://www.Oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **Pustaka Aspose.Tasks untuk Java** – Unduh JAR terbaru dari [download page](https://releases.aspose.com/tasks/java/).

## Impor Paket
Di proyek Java Anda, impor kelas Aspose.Tugas yang diperlukan:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Langkah 1: Siapkan Direktori Data
```java
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan path absolut tempat file `.mpp` Anda berada.

## Langkah 2: Muat File Proyek
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Ini membuat instance `Project` dengan memuat **ResourceCosts.mpp** dari folder yang Anda tentukan.

## Langkah 3: Iterasi Melalui Sumber Daya Non-Root
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Loop ini berjalan melalui setiap objek `Resource` dalam proyek. Pemeriksaan `isRoot()` melewatkan sumber daya root bawaan, dan pernyataan `System.out.println` mencetak nama setiap **sumber daya non‑root**.

## Cara Mengulang Sumber Daya Non-Root
Potongan kode di atas menampilkan pola inti:

1. Dapatkan koleksi lengkap dengan `prj.getResources()`.
2. Gunakan `isRoot()` untuk menyaring placeholder.
3. Akses bidang sumber daya apa pun (misalnya `Rsc.NAME`, `Rsc.COST`) sesuai kebutuhan.

Anda dapat memperluas pola ini untuk mengakumulasi biaya, mengekspor ke CSV, atau menerapkan aturan bisnis khusus.

## Kesalahan & Tip Umum
- **Pemeriksaan null** – Beberapa sumber daya mungkin memiliki bidang opsional; selalu melindungi terhadap `null` saat memanggil `get()`.
- **Kinerja** – Untuk proyek yang sangat besar, lakukan iterasi dengan loop berbasis indeks untuk menghindari pembuatan koleksi menengah.
- **Lisensi** – Batas kode tanpa lisensi yang valid akan menambahkan watermark pada file yang diekspor; pastikan Anda mengaktifkan lisensi di awal aplikasi.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini **tahu cara mengiterasi sumber daya non-root** menggunakan Aspose.Tasks untuk Java. Teknik ini membantu Anda fokus pada sumber daya proyek yang sebenarnya, membersihkan ekstrak data, dan membangun solusi manajemen proyek yang lebih andal.

## FAQ
### Dapatkah saya menggunakan Aspose.Tasks untuk Java untuk membuat file proyek baru?
Ya, Aspose.Tasks menyediakan kemampuan CRUD (Create, Read, Update, Delete) lengkap untuk format proyek MPP, MPT, dan XML.

### Apakah Aspose.Tasks mendukung semua versi file Microsoft Project?
Tentu saja. Ia menangani file Project 2003‑2019, termasuk spesifikasi MPP terbaru.

### Apakah Aspose.Tasks kompatibel dengan kerangka kerja Java seperti Spring?
Ya, Anda dapat menambahkan pustaka ke dalam bean Spring atau menggunakannya dalam aplikasi Java standar apa pun.

### Bisakah saya menyesuaikan bidang data proyek menggunakan Aspose.Tasks?
Tentu saja. API memungkinkan Anda menambah, memodifikasi, atau menghapus bidang khusus pada tugas, sumber daya, dan pengugasan.

### Apakah Aspose.Tasks menyediakan dukungan dan dokumentasi untuk pengembang?
Produk ini mencakup dokumentasi API yang komprehensif, contoh kode, dan forum dukungan khusus untuk bantuan cepat.

---

**Terakhir Diperbarui:** 13-01-2026
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12
**Penulis:** Berasumsi

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
