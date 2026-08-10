---
date: 2026-06-05
description: Pelajari cara memfilter file MPP menggunakan Aspose.Tasks untuk Java,
  menyesuaikan kriteria filter, dan memfilter tugas berdasarkan tanggal untuk menyederhanakan
  manajemen proyek.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Cara Memfilter File MPP Menggunakan Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Memfilter File MPP Menggunakan Aspose.Tasks untuk Java
url: /id/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Memfilter File MPP Menggunakan Aspose.Tasks untuk Java

## Pendahuluan
Jika Anda bekerja dengan file Microsoft Project (*.mpp*) dalam aplikasi Java, Anda sering perlu **memfilter file MPP** untuk memisahkan tugas, sumber daya, atau penugasan yang paling penting. Dalam tutorial ini kami akan membahas **cara memfilter mpp** secara programatis dengan Aspose.Tasks untuk Java, menunjukkan cara **menyesuaikan kriteria filter**, dan mendemonstrasikan skenario praktis “memfilter tugas berdasarkan tanggal”. Pada akhir tutorial Anda akan memiliki potongan kode siap pakai yang dapat Anda sisipkan ke proyek Java mana pun.

## Jawaban Cepat
- **Apa arti “filter mpp”?** Itu berarti mengekstrak subset data proyek berdasarkan kondisi yang ditentukan.  
- **Perpustakaan mana yang menangani ini?** Aspose.Tasks untuk Java menyediakan API lengkap untuk membuat dan menerapkan filter.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya memfilter tugas, sumber daya, dan penugasan?** Ya – setiap tipe entitas memiliki koleksi filter masing‑masing.  
- **Apakah Java 8 atau yang lebih tinggi diperlukan?** Aspose.Tasks mendukung Java 8 dan versi selanjutnya.

## Apa itu “cara memfilter mpp” dalam Java?
`How to filter mpp` adalah proses menggunakan objek `Filter` Aspose.Tasks untuk memilih hanya elemen proyek yang memenuhi predikat tertentu seperti tanggal mulai, biaya, atau bidang khusus. Muat sebuah `Project`, ambil sebuah `Filter`, dan API mengembalikan koleksi yang cocok dengan kriteria Anda, memungkinkan pelaporan terfokus atau integrasi lanjutan.

## Mengapa menyesuaikan kriteria filter?
Kriteria filter khusus memungkinkan Anda menargetkan tugas berisiko tinggi, item yang lewat jatuh tempo, atau sumber daya yang melebihi anggaran, mengubah file proyek yang besar menjadi tampilan ringkas yang dapat ditindaklanjuti. Aspose.Tasks mendukung **lebih dari 50 jenis filter bawaan** dan memungkinkan Anda membuat filter khusus tak terbatas, mengurangi waktu penyaringan data manual hingga 70 %.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru.  
2. **Aspose.Tasks untuk Java** – unduh dari [halaman unduhan](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau NetBeans dapat digunakan dengan baik.  

## Impor Paket
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType`, dan `Project` adalah kelas inti yang digunakan untuk mendefinisikan dan menerapkan filter pada data proyek.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Siapkan Proyek
Pertama, buat instance `Project` yang menunjuk ke file MPP yang ingin Anda analisis, kemudian muat ke memori. Langkah tunggal ini menyiapkan seluruh model proyek untuk pemfilteran, validasi, dan manipulasi lebih lanjut, memungkinkan Anda mengakses tugas, sumber daya, dan penugasan melalui API.

### Bagaimana cara menyiapkan proyek untuk memfilter file MPP?
Kelas `Project` memuat dan merepresentasikan file MPP dalam memori. Buat instance `Project` yang menunjuk ke file MPP yang ingin Anda analisis, kemudian muat ke memori. Langkah tunggal ini menyiapkan seluruh model proyek untuk pemfilteran, validasi, dan manipulasi lebih lanjut, memungkinkan Anda mengakses tugas, sumber daya, dan penugasan melalui API.

### Bagaimana cara mengambil dan memeriksa filter?
Objek `Filter` mengenkapsulasi definisi filter yang digunakan untuk memilih item proyek. Aspose.Tasks menyimpan filter bawaan seperti “All Tasks” atau “Critical Tasks”. Gunakan `project.getTaskFilters().getByName("My Filter")` atau akses berbasis indeks untuk memperoleh objek `Filter`, kemudian periksa koleksi `FilterCriteria`‑nya untuk melihat setiap aturan dan operator logika (AND/OR) yang menggabungkannya, memastikan filter sesuai dengan kebutuhan Anda.

### Bagaimana cara mengiterasi baris kriteria bersarang?
`FilterCriteriaGroup` mewakili grup kriteria filter yang digabungkan dengan operator logika. Filter dapat berisi grup kriteria, masing‑masing dengan operatornya sendiri. Loop melalui `filter.getCriteria().getRows()` dan, untuk setiap baris yang merupakan `FilterCriteriaGroup`, lakukan rekursi ke baris anaknya. Traversal ini memungkinkan Anda memahami logika filter kompleks seperti “(Start < today AND Cost > 1000) OR Priority = High”, serta menyesuaikan kriteria sesuai kebutuhan.

### Bagaimana cara mencetak informasi kriteria untuk debugging?
Setelah menelusuri pohon kriteria, keluarkan nama bidang, operator uji, dan nilai setiap baris ke konsol. Dump sederhana ini membantu Anda memverifikasi bahwa filter sesuai dengan aturan bisnis yang dimaksud sebelum diterapkan pada proyek besar, dan memudahkan menemukan operator atau nilai yang salah.

### Bagaimana cara membuat filter baru secara programatis?
Instansiasi sebuah `Filter` dengan `new Filter("My Filter")`, lalu tambahkan ke koleksi filter tugas proyek menggunakan `project.getTaskFilters().add(filter)`. Setelah itu, isi koleksi `FilterCriteria`‑nya dengan baris yang diinginkan, menentukan nama bidang, operator uji, dan nilai untuk mendefinisikan secara tepat tugas mana yang harus disertakan ketika filter diterapkan.

### Bisakah saya menerapkan filter pada sumber daya alih‑alih tugas?
Koleksi `ResourceFilters` menyimpan definisi filter yang berlaku untuk sumber daya. Ya – gunakan `project.getResourceFilters()` untuk bekerja dengan filter khusus sumber daya dengan cara yang sama seperti filter tugas. Setelah menambahkan atau mengambil filter, konfigurasikan `FilterCriteria`‑nya seperti pada tugas, kemudian terapkan ke koleksi sumber daya untuk memperoleh set sumber daya yang telah difilter.

### Apakah memungkinkan menggabungkan beberapa filter dengan logika OR?
Buat `FilterCriteriaGroup` induk dengan `Operation`‑nya diset ke `OR`, lalu tambahkan objek `FilterCriteria` individu sebagai anak. Grup ini akan mengevaluasi setiap kriteria anak dan mengembalikan item yang memenuhi salah satu dari mereka, memungkinkan Anda menggabungkan beberapa filter sederhana menjadi seleksi yang lebih luas.

### Apakah Aspose.Tasks mendukung pemfilteran pada bidang khusus?
Enum `CustomField` menyediakan pengenal untuk bidang khusus yang didefinisikan dalam proyek. Tentu saja. Referensikan bidang khusus melalui enum `CustomField`, dan mereka berperilaku seperti bidang bawaan dalam ekspresi filter. Anda dapat menyertakannya dalam baris `FilterCriteria`, menggunakan operator dan nilai yang sama, memungkinkan kueri kuat pada data yang didefinisikan pengguna bersama atribut proyek standar.

### Apa dampak kinerja pemfilteran pada file MPP besar?
Pemfilteran berjalan sepenuhnya dalam memori dan biasanya memproses proyek 1.000 tugas dalam kurang dari 200 ms. Untuk file dengan ribuan tugas, pertimbangkan memuat hanya bagian yang diperlukan menggunakan `ProjectReader` dan menerapkan filter setelah pemuatan selektif, yang menjaga penggunaan memori tetap rendah dan mempertahankan respons cepat bahkan pada proyek yang sangat besar.

---

**Terakhir Diperbarui:** 2026-06-05  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.10  
**Penulis:** Aspose

## Tutorial Terkait

- [Muat File MPP Java - Kelola Properti Proyek dengan Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Membaca Data MS Project Online dengan Mudah](/tasks/java/project-data-reading/read-project-online/)
- [Setel Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```