---
date: 2025-12-20
description: Pelajari cara mengambil kode outline MS Project secara programatis menggunakan
  Aspose.Tasks untuk Java. Tingkatkan kemampuan manajemen proyek Anda.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Mengambil Kode Outline MS Project di Aspose.Tasks
url: /id/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengambil Kode Outline MS Project di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, Anda akan menemukan **cara mengambil kode outline ms project** menggunakan Aspose.Tasks untuk Java. Kode outline dalam MS Project memberi Anda cara yang kuat untuk mengkategorikan tugas, sumber daya, dan penugasan, dan mengaksesnya secara programatik memungkinkan Anda membangun pelaporan khusus, otomatisasi, atau solusi integrasi. Kami akan membimbing Anda melalui contoh lengkap, langkah demi langkah yang dapat Anda salin ke proyek Anda sendiri.

## Jawaban Cepat
- **Apa yang dilakukan kode ini?** Kode ini memuat file Project dan mencetak setiap definisi kode outline, maskenya, dan nilainya.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java (versi terbaru apa pun).  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi penuh diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.  
- **Bisakah saya memodifikasi kode setelah mengambilnya?** Ya – API yang sama memungkinkan Anda menambah, mengedit, atau menghapus kode outline.

## Apa itu kode outline ms project?
Kode outline adalah bidang khusus yang memungkinkan manajer proyek mengelompokkan dan menyaring tugas di luar hierarki default. Mereka dapat berupa nilai numerik sederhana, string, atau bahkan kode khusus tingkat perusahaan yang didefinisikan pada level organisasi. Dengan membaca kode ini, Anda dapat menggerakkan dasbor, mengekspor data, atau menegakkan konvensi penamaan secara otomatis.

## Mengapa mengambil kode outline ms project dengan Aspose.Tasks?
- **Otomatisasi:** Menghasilkan laporan atau memicu alur kerja tanpa ekspor manual.  
- **Integrasi:** Menyinkronkan kode outline dengan ERP, PPM, atau alat BI.  
- **Kustomisasi:** Menerapkan aturan bisnis berdasarkan nilai kode (mis., alokasi biaya).  
- **Lintas‑platform:** Berfungsi di Windows, Linux, dan macOS, terlepas dari UI Microsoft Project.

## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan prasyarat berikut:

### 1. Lingkungan Pengembangan Java
Pastikan Anda memiliki Java Development Kit (JDK) terpasang di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari situs web Oracle.

### 2. Perpustakaan Aspose.Tasks
Unduh dan sertakan perpustakaan Aspose.Tasks dalam proyek Java Anda. Anda dapat mengunduh perpustakaan dari [Halaman Unduhan Aspose.Tasks untuk Java](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pertama, impor paket yang diperlukan dari Aspose.Tasks dalam kode Java Anda:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Sekarang mari kita uraikan contoh kode yang diberikan menjadi beberapa langkah:

## Langkah 1: Muat Proyek
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Pada langkah ini, kami memuat file Microsoft Project ke dalam objek `Project` menggunakan nama file yang diberikan.

## Langkah 2: Ambil Kode Outline
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Kami mengiterasi setiap definisi kode outline dalam proyek.

## Langkah 3: Akses Properti Kode Outline
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Kami mengambil dan mencetak berbagai properti dari definisi kode outline seperti Alias, Field ID, dan Field Name.

## Langkah 4: Periksa Kode Kustom Perusahaan
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Kami memeriksa apakah kode outline adalah kode kustom perusahaan dan mencetak hasilnya sesuai.

## Langkah 5: Tampilkan Masker Kode Outline
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Kami mengiterasi setiap masker yang terkait dengan kode outline dan mencetak level serta nilai maskernya.

## Langkah 6: Tampilkan Nilai Kode Outline
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Kami mengiterasi setiap nilai kode outline dan mencetak deskripsinya, ID nilai, nilai, dan tipe.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|---------|--------|--------|
| **Tidak ada output** | Path file proyek tidak benar | Verifikasi `projectName` mengarah ke file `.mpp` yang valid. |
| **Nilai null** | Kode outline tidak didefinisikan dalam file | Pastikan file Project benar-benar berisi kode outline (periksa di UI MS Project). |
| **LicenseException** | Menggunakan versi percobaan tanpa aktivasi yang tepat | Terapkan lisensi sementara atau penuh melalui `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java untuk memodifikasi kode outline dalam file Project?**  
A: Ya, Aspose.Tasks untuk Java menyediakan API untuk memodifikasi kode outline secara programatik. Anda dapat menambah, mengedit, atau menghapus definisi menggunakan objek `Project` yang sama.

**Q: Apakah tersedia versi percobaan untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks untuk Java dari [situs web Aspose.Tasks](https://releases.aspose.com/).

**Q: Bagaimana saya dapat mendapatkan dukungan teknis untuk Aspose.Tasks untuk Java?**  
A: Anda dapat memperoleh dukungan teknis dengan mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) dan mengirimkan pertanyaan Anda di sana.

**Q: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat membeli lisensi sementara untuk Aspose.Tasks untuk Java dari [halaman pembelian](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Tasks untuk Java?**  
A: Anda dapat merujuk ke [dokumentasi](https://reference.aspose.com/tasks/java/) untuk informasi detail tentang penggunaan Aspose.Tasks untuk Java.

## Kesimpulan
Dalam tutorial ini, kami telah mempelajari cara mengambil **kode outline ms project** menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah yang disediakan, Anda dapat secara efektif mengakses dan memanipulasi kode outline dalam aplikasi Java Anda, memungkinkan kemampuan manajemen proyek lanjutan seperti pelaporan khusus, otomatisasi, dan integrasi dengan sistem perusahaan lainnya.

---

**Terakhir Diperbarui:** 2025-12-20  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}