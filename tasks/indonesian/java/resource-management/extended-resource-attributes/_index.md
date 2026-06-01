---
date: 2026-01-13
description: Pelajari cara membuat atribut khusus, memuat file Microsoft Project,
  mengatur nilai numerik di Java, dan menyimpan proyek sebagai XML dengan Aspose.Tasks
  untuk Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membuat Atribut Kustom di MS Project menggunakan Aspose.Tasks
url: /id/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Atribut Kustom di MS Project menggunakan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, **Anda akan mempelajari cara membuat atribut kustom** untuk sumber daya dalam file Microsoft Project menggunakan Aspose.Tasks untuk Java. Kami akan memandu Anda memuat file Microsoft Project, mendefinisikan atribut numerik baru, menetapkan nilai, dan akhirnya menyimpan proyek sebagai XML. Pada akhir tutorial, Anda akan memiliki contoh praktis yang jelas yang dapat Anda sesuaikan dengan solusi manajemen proyek Anda sendiri.

## Jawaban Cepat
- **Apa arti “atribut kustom”?**  
  Sebuah bidang yang didefinisikan pengguna untuk menyimpan informasi tambahan (misalnya, Usia, Tingkat Keterampilan) bagi sumber daya atau tugas.  
- **Perpustakaan mana yang menangani ini?**  
  Aspose.Tasks untuk Java menyediakan API yang fluida untuk membuat dan mengelola atribut kustom.  
- **Apakah saya memerlukan lisensi?**  
  Lisensi sementara gratis dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya menetapkan nilai numerik?**  
  Ya – gunakan `setNumericValue` dengan `BigDecimal` (misalnya, `30.5345`).  
- **Bagaimana proyek disimpan?**  
  File yang telah dimodifikasi dapat disimpan sebagai XML menggunakan `SaveFileFormat.Xml`.

## Apa Itu Atribut Kustom?
Sebuah **atribut kustom** (juga disebut atribut ekstended) adalah kolom tambahan yang dapat Anda tambahkan ke sumber daya atau tugas di Microsoft Project. Ini memungkinkan Anda menangkap data yang tidak tercakup oleh bidang bawaan, seperti usia karyawan, tingkat sertifikasi, atau metrik khusus bisnis lainnya.

## Mengapa Membuat Atribut Kustom di MS Project?
- **Sesuaikan data proyek** dengan kebutuhan organisasi Anda.  
- **Aktifkan pelaporan lanjutan** dengan menyimpan nilai yang dapat dipertanyakan kemudian.  
- **Pertahankan konsistensi** di seluruh proyek dengan menerapkan definisi atribut yang sama secara programatis.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Lingkungan Pengembangan Java** – JDK 8 atau lebih tinggi terpasang.  
2. **Aspose.Tasks untuk Java** – Unduh versi terbaru dari [di sini](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, atau IDE lain yang kompatibel dengan Java.  

## Panduan Langkah‑per‑Langkah

### Mengimpor Paket
Pertama, impor kelas Aspose.Tasks yang diperlukan. Kelas‑kelas ini menyediakan fungsionalitas inti untuk menangani proyek, sumber daya, dan atribut ekstended.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Langkah 1: Tentukan Direktori Data
Atur folder tempat file proyek sumber Anda berada dan tempat output akan ditulis.

```java
String dataDir = "Your Data Directory";
```

### Langkah 2: Muat File Microsoft Project
Buat instance `Project` dengan memuat file yang ada. Ini adalah langkah **memuat file Microsoft project** yang memberi Anda akses penuh ke isinya.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Langkah 3: Definisikan Atribut Kustom
Kita akan mendefinisikan atribut numerik baru bernama **Age**. API memeriksa apakah definisi sudah ada; jika tidak, ia akan membuatnya.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Langkah 4: Tetapkan Nilai Numerik di Java
Buat instance atribut untuk sumber daya tertentu dan tetapkan nilai numerik menggunakan `setNumericValue`. Ini memperlihatkan **set numeric value java** dalam aksi.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Langkah 5: Tambahkan Sumber Daya dan Lampirkan Atribut Kustom
Tambahkan sumber daya baru bernama **R1** dan lampirkan atribut kustom yang telah dibuat sebelumnya kepadanya.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Langkah 6: Simpan Proyek sebagai XML
Akhirnya, persist perubahan dengan menyimpan proyek. Ini adalah langkah **save project as xml**, yang menghasilkan representasi XML bersih dari file yang telah diperbarui.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Langkah 7: Tampilkan Hasil
Cetak konfirmasi ramah sehingga Anda tahu proses selesai tanpa error.

```java
System.out.println("Process completed Successfully");
```

Dengan mengikuti langkah‑langkah ini, Anda telah berhasil **membuat atribut kustom**, memuat file Microsoft Project, menetapkan nilai numerik menggunakan Java, dan menyimpan proyek sebagai XML.

## Kesalahan Umum & Tips
- **Konflik ID Atribut:** Selalu periksa `getById` sebelum membuat definisi baru untuk menghindari duplikasi ID.  
- **Penanganan Presisi:** `BigDecimal` mempertahankan presisi desimal; hindari penggunaan `float` atau `double` untuk nilai yang tepat.  
- **Path File:** Gunakan path absolut atau konfigurasikan direktori kerja IDE Anda untuk mencegah `FileNotFoundException`.  

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya membuat atribut kustom untuk tugas serta sumber daya?**  
J: Ya – gunakan `ExtendedAttributeTask` alih‑alih `ExtendedAttributeResource` saat mendefinisikan atribut.

**T: Apakah memungkinkan menambahkan beberapa atribut kustom sekaligus?**  
J: Tentu saja. Buat objek `ExtendedAttributeDefinition` terpisah untuk setiap atribut dan lampirkan ke sumber daya atau tugas yang diinginkan.

**T: Format apa saja yang dapat saya gunakan untuk menyimpan proyek?**  
J: Aspose.Tasks mendukung XML, MPP, dan beberapa format lain seperti PDF serta HTML. Pada contoh ini kami menggunakan `SaveFileFormat.Xml`.

**T: Apakah saya memerlukan lisensi Aspose.Tasks untuk build pengembangan?**  
J: Lisensi sementara sudah cukup untuk evaluasi. Untuk penyebaran produksi, lisensi penuh diperlukan.

**T: Bagaimana cara membaca kembali nilai atribut kustom nanti?**  
J: Gunakan `resource.getExtendedAttributes()` untuk mengiterasi atribut yang terlampir dan ambil nilainya dengan `getNumericValue()` atau `getTextValue()`.

## Kesimpulan
Membuat **atribut kustom** di Microsoft Project dengan Aspose.Tasks untuk Java menjadi mudah setelah Anda memahami alur kerja: muat proyek, definisikan atribut, tetapkan nilainya, lampirkan ke sumber daya, dan simpan file. Pendekatan ini memungkinkan Anda memperluas model data proyek secara programatis, memberikan pelaporan yang lebih kaya dan integrasi yang lebih erat dengan proses bisnis Anda.

---

**Terakhir Diperbarui:** 2026-01-13  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}