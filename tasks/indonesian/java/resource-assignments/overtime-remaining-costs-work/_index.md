---
date: 2026-01-07
description: Pelajari cara melakukan pemantauan biaya proyek, melacak lembur, menghitung
  sisa pekerjaan, dan mengelola biaya dalam proyek Java menggunakan Aspose.Tasks.
  Langkah mudah untuk manajemen proyek yang efektif.
linktitle: 'Project Cost Monitoring with Aspose.Tasks: Overtime & Work'
second_title: Aspose.Tasks Java API
title: 'Pemantauan Biaya Proyek dengan Aspose.Tasks: Lembur & Kerja'
url: /id/java/resource-assignments/overtime-remaining-costs-work/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pemantauan Biaya Proyek dengan Aspose.Tasks: Lembur & Pekerjaan

## Pendahuluan
Dalam tutorial ini Anda akan menemukan cara **pemantauan biaya proyek** menggunakan Aspose.Tasks untuk Java. Kami akan memandu proses pelacakan lembur, biaya yang tersisa, dan pekerjaan sehingga Anda dapat menjaga proyek Anda tetap sesuai jadwal dan dalam anggaran. Baik Anda seorang manajer proyek maupun pemimpin tim, langkah‑langkah ini akan membantu Anda mempertahankan visibilitas yang jelas atas metrik keuangan dan sumber daya.

## Jawaban Cepat
- **Apa yang dapat saya pantau?** Biaya lembur, pekerjaan lembur, biaya yang tersisa, pekerjaan yang tersisa, dan biaya lembur yang tersisa.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi diperlukan untuk produksi.  
- **Bisakah saya memuat file .mpp yang ada?** Ya, cukup berikan jalur ke file tersebut.  
- **Apakah Java 6 cukup?** API mendukung Java SE 6 dan yang lebih baru.

## Apa itu pemantauan biaya proyek?
Pemantauan biaya proyek adalah praktik melacak secara terus‑menerus semua aspek keuangan sebuah proyek—biaya yang dianggarkan, pengeluaran aktual, dan perkiraan biaya yang tersisa. Dengan mengintegrasikan ini dengan penugasan sumber daya, Anda memperoleh wawasan waktu nyata tentang biaya lembur dan kemajuan pekerjaan.

## Mengapa memantau lembur dan pekerjaan yang tersisa?
- **Mengendalikan anggaran:** Lembur sering menyebabkan pembengkakan biaya yang tidak terduga.  
- **Meningkatkan perkiraan:** Mengetahui pekerjaan yang tersisa membantu Anda menyesuaikan jadwal secara proaktif.  
- **Meningkatkan transparansi:** Pemangku kepentingan dapat melihat secara tepat di mana sumber daya sedang digunakan.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:
1. **Java Development Kit (JDK):** Aspose.Tasks untuk Java memerlukan Java SE 6 atau yang lebih baru.  
2. **Perpustakaan Aspose.Tasks untuk Java:** Unduh dan instal perpustakaan dari [di sini](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE):** IDE Java apa pun seperti Eclipse, IntelliJ IDEA, atau NetBeans.

## Impor Paket
Mulailah dengan mengimpor paket yang diperlukan dalam file Java Anda:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Langkah 1: Siapkan Direktori Data
Tentukan direktori tempat file proyek Anda berada:
```java
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan jalur ke file proyek Anda.

## Langkah 2: Muat Proyek
Buat objek `Project` dan muat file proyek:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
Ganti `"ResourceAssignmentOvertimes.mpp"` dengan nama file MPP Anda. Langkah ini menunjukkan penggunaan **load mpp file**.

## Langkah 3: Iterasi Penugasan Sumber Daya
Lakukan perulangan pada setiap penugasan sumber daya dalam proyek:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```

## Langkah 4: Cetak Biaya Lembur dan Pekerjaan
Ambil dan cetak biaya lembur serta pekerjaan untuk setiap penugasan sumber daya:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```

## Langkah 5: Cetak Biaya dan Pekerjaan yang Tersisa
Ambil dan cetak biaya serta pekerjaan yang tersisa untuk setiap penugasan sumber daya:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```

## Langkah 6: Cetak Biaya Lembur dan Pekerjaan yang Tersisa
Ambil dan cetak biaya lembur dan pekerjaan yang tersisa untuk setiap penugasan sumber daya:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Masalah Umum dan Solusinya
- **File tidak ditemukan:** Periksa kembali jalur `dataDir` dan pastikan nama file MPP sudah benar.  
- **Nilai null:** Beberapa penugasan mungkin tidak memiliki data lembur; hindari `null` saat mencetak.  
- **Versi tidak cocok:** Gunakan versi perpustakaan yang sesuai dengan format file MPP (misalnya versi MS Project yang lebih baru).

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan perpustakaan Java lainnya?**  
A: Ya, Aspose.Tasks untuk Java kompatibel dengan perpustakaan dan kerangka kerja Java lainnya.

**Q: Apakah Aspose.Tasks mendukung format file proyek yang berbeda?**  
A: Ya, Aspose.Tasks mendukung berbagai format termasuk MPP, XML, dan lainnya.

**Q: Apakah ada versi percobaan yang tersedia?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis dari [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dukungan jika saya mengalami masalah?**  
A: Anda dapat mengunjungi forum Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15) untuk dukungan.

**Q: Bagaimana cara membeli lisensi untuk Aspose.Tasks?**  
A: Anda dapat membeli lisensi dari [di sini](https://purchase.aspose.com/buy).

## Kesimpulan
Memantau lembur, biaya yang tersisa, dan pekerjaan merupakan fondasi dari **pemantauan biaya proyek** yang efektif. Dengan Aspose.Tasks untuk Java, Anda dapat mengekstrak metrik ini secara programatik, memberi Anda data yang diperlukan untuk menjaga proyek tetap pada jalur dan menghindari kejutan anggaran. Jelajahi fitur Aspose.Tasks tambahan untuk lebih meningkatkan perangkat manajemen proyek Anda.

---

**Terakhir Diperbarui:** 2026-01-07  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}