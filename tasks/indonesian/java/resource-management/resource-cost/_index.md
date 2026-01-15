---
date: 2026-01-15
description: Pelajari cara bekerja dengan biaya yang dianggarkan yang dijadwalkan
  dalam file Microsoft Project menggunakan Aspose.Tasks untuk Java. Ikuti panduan
  langkah demi langkah kami.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Pekerjaan dengan biaya teranggarkan dijadwalkan menggunakan Aspose.Tasks untuk
  Java
url: /id/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# biaya kerja terjadwal yang dianggarkan dengan Aspose.Tasks untuk Java

## Pendahuluan

Mengelola **budgeted cost work scheduled** (BCWS) sangat penting untuk menjaga proyek tetap pada jalurnya dan memastikan bahwa perkiraan keuangan selaras dengan pekerjaan yang direncanakan. Di Microsoft Project, BCWS mewakili jumlah uang yang seharusnya telah dibelanjakan untuk pekerjaan yang dijadwalkan hingga tanggal tertentu. Aspose.Tasks untuk Java memberi Anda kontrol programatik penuh atas nilai‑nilai ini, memungkinkan Anda membaca, memodifikasi, dan melaporkan biaya sumber daya tanpa pernah membuka file .mpp secara manual. Dalam tutorial ini kami akan menelusuri contoh lengkap yang menunjukkan cara memuat proyek, mengiterasi sumber dayanya, dan menampilkan budgeted cost work scheduled bersama metrik biaya penting lainnya.

## Jawaban Cepat
- **Apa arti BCWS?** Budgeted Cost Work Scheduled – biaya yang direncanakan untuk pekerjaan yang dijadwalkan hingga saat ini.  
- **Properti API mana yang mengambil BCWS?** `Rsc.BCWS` pada objek `Resource`.  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya memodifikasi nilai BCWS?** Ya, Anda dapat mengatur `Rsc.BCWS` seperti bidang numerik lainnya.  
- **Versi Project yang didukung?** Semua versi Microsoft Project dari 2000 hingga format .mpp terbaru.

## Apa itu budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** adalah ukuran kinerja yang mencerminkan biaya yang seharusnya telah dikeluarkan untuk pekerjaan yang direncanakan hingga titik waktu tertentu. Ini merupakan fondasi Earned Value Management (EVM) dan membantu manajer proyek membandingkan perencanaan dengan pengeluaran aktual.

## Prasyarat

Sebelum menyelam ke kode, pastikan Anda memiliki:

1. Pemahaman yang kuat tentang dasar‑dasar Java.  
2. Aspose.Tasks untuk Java telah ditambahkan ke proyek Anda (Maven/Gradle atau JAR).  
3. File Microsoft Project (`.mpp`) yang berisi sumber daya dengan data biaya (misalnya *ResourceCosts.mpp*).

## Impor Paket

Pertama, impor kelas Aspose.Tasks yang diperlukan untuk menangani proyek dan sumber daya:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Langkah 1: Tentukan Direktori Data

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan jalur absolut atau relatif tempat *ResourceCosts.mpp* berada.

## Langkah 2: Muat File MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Konstruktor `Project` membaca file .mpp dan membangun representasi dalam memori yang dapat Anda kueri.

## Langkah 3: Iterasi Sumber Daya

```java
for (Resource res : prj.getResources()) {
```

Loop ini berjalan melalui setiap sumber daya yang didefinisikan dalam proyek, memberi Anda akses ke bidang‑bidang biaya mereka.

## Langkah 4: Periksa Nama Sumber Daya dan Biaya

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Di dalam blok `if` kami:

* Mencetak **total cost** (`Rsc.COST`).  
* Mencetak **actual cost of work performed** (`Rsc.ACWP`).  
* Mencetak **budgeted cost work scheduled** (`Rsc.BCWS`) – metrik utama yang kami fokuskan.  
* Mencetak **budgeted cost work performed** (`Rsc.BCWP`).

Keempat nilai ini memberikan gambaran cepat tentang posisi keuangan proyek.

## Mengapa memantau budgeted cost work scheduled penting

* **Peringatan dini:** Jika BCWS secara signifikan lebih tinggi daripada biaya aktual, Anda mungkin terlalu banyak mengalokasikan sumber daya.  
* **Analisis Earned Value:** BCWS adalah input kunci untuk menghitung Cost Variance (CV) dan Schedule Variance (SV).  
* **Peramalan:** Data BCWS yang akurat membantu memprediksi kebutuhan arus kas di masa depan dan memberi informasi pada pelaporan pemangku kepentingan.

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|--------|----------------------|--------|
| `null` printed for BCWS | Resource has no cost rate table defined | Define a cost rate table for the resource in Microsoft Project or set it programmatically via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` when iterating resources | Project file corrupted or contains empty resource entries | Validate the .mpp file in Microsoft Project and remove empty resources |
| Unexpected values (e.g., negative BCWS) | Custom fields overriding standard cost fields | Ensure you’re accessing the standard `Rsc.BCWS` and not a custom field with the same name |

## Pertanyaan yang Sering Diajukan

**Q: Can I update the BCWS value programmatically?**  
A: Yes. Use `res.set(Rsc.BCWS, newValue)` and then save the project with `prj.save("Updated.mpp")`.

**Q: Does Aspose.Tasks support multi‑currency projects?**  
A: Absolutely. Cost fields respect the currency settings defined in the Project file.

**Q: Is there a way to export these cost metrics to CSV?**  
A: You can iterate over the resources and write the values to a `StringBuilder` or use a CSV library to generate the file.

**Q: How does BCWS differ from BCWP?**  
A: BCWS is the planned cost for scheduled work, while BCWP (Budgeted Cost Work Performed) reflects the planned cost for work that has actually been completed.

**Q: Do I need a special license to read cost data?**  
A: The evaluation license provides full read/write access; a commercial license is required for production deployments.

## Kesimpulan

Dengan memanfaatkan Aspose.Tasks untuk Java, Anda mendapatkan akses programatik yang tepat ke **budgeted cost work scheduled** dan metrik biaya penting lainnya. Ini memungkinkan Anda membangun dasbor khusus, mengotomatisasi laporan Earned Value, dan menjaga proyek Anda tetap pada jalur keuangan—semua tanpa interaksi manual dengan Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-15  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (terbaru)  
**Penulis:** Aspose