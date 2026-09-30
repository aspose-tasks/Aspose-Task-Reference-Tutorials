---
date: 2026-09-30
description: Pelajari cara membuat atribut extended task menggunakan Aspose.Tasks
  untuk Java, perpustakaan manajemen proyek Java terkemuka untuk menambahkan bidang
  tugas khusus.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Cara membuat atribut extended task dengan Aspose.Tasks Java
og_description: Pelajari cara membuat atribut extended task menggunakan Aspose.Tasks
  untuk Java, perpustakaan manajemen proyek Java terkemuka untuk menambahkan bidang
  tugas khusus.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Cara membuat atribut extended task dengan Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Cara membuat atribut extended task dengan Aspose.Tasks Java
url: /id/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat atribut tugas yang diperluas dengan Aspose.Tasks Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **membuat atribut tugas yang diperluas** dalam file Microsoft Project dengan menggunakan Aspose.Tasks untuk Java. Menambahkan bidang khusus memungkinkan Anda menangkap data spesifik proyek yang tidak tercakup oleh kolom bawaan, memberi Anda kontrol yang lebih halus atas pelaporan dan perencanaan sumber daya. Pada akhir panduan Anda akan dapat menambahkan atribut teks biasa, dengan pencarian, dan durasi ke tugas mana pun.

## Jawaban Cepat
- **Apa arti “extended attribute”?** Ini adalah bidang khusus yang Anda definisikan dan lampirkan ke tugas, sumber daya, atau penugasan.  
- **Perpustakaan mana yang menambahkan kemampuan ini?** Aspose.Tasks for Java, sebuah perpustakaan manajemen proyek Java.  
- **Apakah saya memerlukan lisensi untuk mencobanya?** Ya – percobaan gratis selama 30 hari tersedia di situs web Aspose.  
- **Bisakah saya menambahkan nilai lookup?** Tentu saja; Anda dapat menyediakan daftar nilai yang diizinkan untuk bidang teks atau durasi.  
- **Apakah API kompatibel dengan Java 8 dan versi lebih baru?** Ya, API ini mendukung Java 8+ dan berjalan di semua sistem operasi utama.

## Apa itu atribut tugas yang diperluas?
Atribut tugas yang diperluas adalah kolom yang didefinisikan pengguna yang menyimpan informasi tambahan untuk setiap tugas dalam file Project. Ia berperilaku seperti bidang bawaan tetapi dapat menyimpan tipe data apa pun yang Anda perlukan, seperti teks, angka, tanggal, atau durasi.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks mendukung **50+ format file** dan dapat memproses proyek dengan **10.000+ tugas** tanpa memerlukan instalasi Microsoft Project. Perpustakaan ini berfungsi sepenuhnya offline, menjamin privasi data dan kinerja deterministik untuk solusi skala perusahaan.

## Prasyarat
- Pengetahuan dasar pemrograman Java.  
- Perpustakaan Aspose.Tasks untuk Java terpasang. Anda dapat mengunduhnya dari [website](https://releases.aspose.com/tasks/java/).  
- IDE Java (IntelliJ IDEA, Eclipse, atau VS Code) yang telah diatur di mesin Anda.

## Impor paket
Pernyataan `import` memberi Anda akses ke kelas inti yang Anda perlukan, seperti `Project`, `ExtendedAttributeDefinition`, dan `ExtendedAttribute`.  
`Project` mewakili file Microsoft Project dan menyediakan metode untuk membaca, memodifikasi, dan menyimpannya.  
`ExtendedAttributeDefinition` mendefinisikan bidang khusus yang dapat dilampirkan ke tugas, sumber daya, atau penugasan.  
`ExtendedAttribute` adalah sebuah instance dari definisi yang menyimpan nilai aktual untuk entitas tertentu.

## Bagaimana cara menambahkan atribut tugas yang diperluas berupa teks biasa ke sebuah tugas?
Untuk menambahkan atribut tugas yang diperluas berupa teks biasa, pertama Anda memuat proyek, kemudian membuat definisi tipe Text, menambahkannya ke koleksi proyek, membuat sebuah tugas, menginstansiasi atribut dari definisi tersebut, mengatur nilai teksnya, melampirkannya ke tugas, dan akhirnya menyimpan proyek.

### 1. Tentukan jalur direktori dokumen
Tentukan di mana file sumber dan output Anda berada.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Buat proyek baru
Instansiasi objek `Project`, secara opsional memuat file .mpp yang sudah ada.

```java
String dataDir = "Your Document Directory";
```

### 3. Buat definisi atribut yang diperluas tipe Text1
Definisikan bidang khusus sebagai kolom teks biasa bernama “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Tambahkan definisi ke koleksi atribut yang diperluas proyek
Daftarkan definisi baru sehingga proyek mengenalinya.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Tambahkan tugas ke proyek
Buat tugas yang akan menerima bidang khusus.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Buat atribut yang diperluas dari definisi atribut
Hasilkan sebuah instance yang dapat Anda kaitkan ke tugas tertentu.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Tetapkan nilai ke atribut yang diperluas yang dihasilkan
Atur teks aktual yang ingin Anda simpan, misalnya “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Tambahkan atribut yang diperluas ke tugas
Lampirkan instance atribut ke koleksi `ExtendedAttributes` tugas.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Simpan proyek
Tuliskan proyek yang diperbarui kembali ke disk dalam format yang diinginkan.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Bagaimana cara menambahkan atribut teks dengan opsi lookup?
Saat menambahkan atribut teks dengan lookup, Anda mengikuti langkah yang sama seperti untuk atribut teks biasa, tetapi sebelum menambahkan definisi Anda mengisi koleksi `LookupValues`-nya dengan string yang diizinkan. Nilai-nilai ini muncul sebagai daftar drop‑down di Microsoft Project, memastikan konsistensi data.

## Bagaimana cara menambahkan atribut durasi dengan opsi lookup?
Untuk menambahkan atribut durasi dengan lookup, ganti tipe `Text1` dengan `Duration2` saat membuat definisi, lalu isi koleksi `LookupValues` dengan string durasi seperti “1 day”, “2 days”, dll. Setelah definisi ditambahkan ke proyek, buat instance atribut, atur nilai durasi, lampirkan ke tugas, dan simpan file.

## Masalah umum dan pemecahan masalah
- **Nilai lookup tidak muncul** – Pastikan Anda menambahkan setiap entri lookup ke koleksi `LookupValues` *sebelum* memanggil `project.getExtendedAttributes().add(definition)`.  
- **Nilai atribut tidak disimpan** – Verifikasi bahwa Anda menambahkan instance `ExtendedAttribute` ke tugas *setelah* mengatur nilainya.  
- **Ukuran file bertambah secara tak terduga** – Saat bekerja dengan proyek yang sangat besar, pertimbangkan memanggil `project.setSaveOptions(new ProjectSaveOptions())` untuk mengaktifkan penyimpanan inkremental.

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan perpustakaan Java lainnya?**  
A: Ya, Aspose.Tasks untuk Java terintegrasi dengan mulus ke dalam ekosistem Java apa pun, termasuk Spring, Hibernate, dan Apache POI.

**Q: Apakah Aspose.Tasks untuk Java cocok untuk aplikasi manajemen proyek berskala besar?**  
A: Tentu saja. Perpustakaan ini dirancang untuk menangani proyek dengan ribuan tugas dan mendukung streaming untuk menjaga penggunaan memori tetap rendah.

**Q: Apakah ada pertimbangan lisensi untuk menggunakan Aspose.Tasks untuk Java dalam proyek komersial?**  
A: Ya, Anda memerlukan lisensi komersial yang valid. Anda dapat meninjau detailnya di [situs web Aspose.Tasks](https://purchase.aspose.com/buy).

**Q: Bagaimana saya dapat mendapatkan dukungan atau bantuan dengan Aspose.Tasks untuk Java?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan komunitas, atau buka tiket dukungan melalui akun Aspose Anda.

**Q: Bisakah saya mencoba Aspose.Tasks untuk Java sebelum membeli?**  
A: Ya, Anda dapat mengakses versi percobaan gratis di halaman [Aspose.Tasks free trial](https://releases.aspose.com/).

**Terakhir diperbarui:** 2026-09-30  
**Diuji dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Tutorial Terkait

- [Kolom khusus dan atribut yang diperluas dalam manajemen proyek Java](/tasks/java/project-management/extended-attributes/)
- [Baca Atribut Tugas yang Diperluas dengan Aspose.Tasks untuk Java](/tasks/java/task-properties/extended-task-attributes/)
- [Cara Membuat Proyek aspose.tasks – Atur Atribut Tugas Baru](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}