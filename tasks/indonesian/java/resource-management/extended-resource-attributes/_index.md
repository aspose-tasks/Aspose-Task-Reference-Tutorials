---
date: 2026-06-10
description: Pelajari cara membuat atribut tambahan di Java, memuat file Microsoft
  Project, mengatur nilai numerik, dan menyimpan proyek sebagai XML menggunakan Aspose.Tasks
  untuk Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Menangani Atribut Sumber Daya Tambahan di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara membuat atribut tambahan di Java dengan Aspose.Tasks
url: /id/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat atribut diperluas di Java dengan Aspose.Tasks

## Pendahuluan
Dalam panduan praktis ini Anda akan **create extended attribute in Java** untuk file Microsoft Project menggunakan Aspose.Tasks. Kami akan menjelaskan cara memuat proyek yang ada, mendefinisikan atribut numerik baru, menetapkan nilai ke sebuah sumber daya, dan akhirnya menyimpan perubahan sebagai file XML. Pada akhir panduan, Anda akan memiliki pola kode yang dapat digunakan kembali dan dapat dimasukkan ke dalam solusi manajemen proyek berbasis Java apa pun.

## Jawaban Cepat
- **Apa itu atribut diperluas?**  
  Bidang yang didefinisikan pengguna (mis., Usia, Tingkat Keterampilan) yang menyimpan data tambahan untuk sumber daya atau tugas.  
- **API mana yang membuatnya?**  
  Aspose.Tasks for Java menyediakan kelas `ExtendedAttributeDefinition` untuk mendefinisikan dan mengelola atribut khusus.  
- **Apakah saya memerlukan lisensi?**  
  Lisensi evaluasi sementara dapat digunakan untuk pengembangan; lisensi penuh diperlukan untuk penyebaran produksi.  
- **Bisakah saya menyimpan angka?**  
  Ya – gunakan `setNumericValue(BigDecimal)` untuk menetapkan nilai desimal yang tepat.  
- **Bagaimana cara menyimpan perubahan?**  
  Panggil `project.save("output.xml", SaveFileFormat.Xml)` untuk menulis proyek yang diperbarui dalam format XML.

## Apa itu atribut khusus?
**custom attribute** (juga dikenal sebagai atribut diperluas) adalah kolom tambahan yang dapat Anda tambahkan ke sumber daya atau tugas dalam Microsoft Project. Ini memungkinkan Anda menangkap data yang tidak tercakup oleh bidang bawaan, seperti usia karyawan, tingkat sertifikasi, atau metrik khusus bisnis apa pun.

## Mengapa membuat atribut diperluas di Java?
Membuat atribut diperluas di Java memungkinkan Anda memperkaya data proyek secara programatik, memastikan konsistensi antar file dan memungkinkan pelaporan otomatis. Dengan mendefinisikan atribut sekali, Anda dapat menerapkannya ke sejumlah sumber daya atau tugas tanpa entri manual, menghemat waktu dan mengurangi kesalahan.

- **Sesuaikan data dengan organisasi Anda** – simpan metrik apa pun yang penting bagi Anda tanpa solusi manual di Excel.  
- **Aktifkan pelaporan yang lebih kaya** – kueri bidang khusus nanti untuk dasbor atau analitik.  
- **Pertahankan konsistensi** – secara programatik terapkan definisi yang sama di puluhan proyek, menghilangkan kesalahan manusia.  
- **Diuji kinerja** – Aspose.Tasks memproses proyek dengan hingga 10.000 tugas dan 5.000 sumber daya tanpa memuat seluruh file ke memori, menurut tolok ukur produk.

## Prasyarat
1. **Java Development Kit** – JDK 8 atau yang lebih baru terpasang.  
2. **Aspose.Tasks for Java** – unduh rilis terbaru dari [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, atau lingkungan pengembangan yang kompatibel dengan Java apa pun.  

## Cara membuat atribut diperluas di Java?
Muat proyek Anda, definisikan atribut, lampirkan ke sebuah sumber daya, dan simpan file – semua dalam beberapa langkah sederhana. Bagian berikut memecah setiap langkah menjadi penjelasan singkat diikuti oleh placeholder tempat kode sebenarnya berada.

### Panduan Langkah‑demi‑Langkah

#### Impor Paket
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource`, dan kelas terkait berada di namespace `com.aspose.tasks`. Impor mereka di bagian atas file Java Anda.

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

#### Langkah 1: Definisikan Direktori Data
`Paths` adalah kelas utilitas yang menyediakan metode untuk memperoleh jalur sistem file secara independen platform.

```java
String dataDir = "Your Data Directory";
```

#### Langkah 2: Muat File Microsoft Project
`Project` mewakili file Microsoft Project dalam memori, memungkinkan akses baca dan tulis ke isinya.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Langkah 3: Definisikan Atribut Kustom
`ExtendedAttributeDefinition` mendefinisikan skema bidang kustom baru yang dapat dilampirkan ke sumber daya atau tugas.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Langkah 4: Tetapkan Nilai Numerik di Java
`ExtendedAttributeResource` menyimpan nilai atribut kustom untuk instance sumber daya tertentu.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Langkah 5: Tambahkan Sumber Daya dan Lampirkan Atribut Kustom
`Resource` memodelkan sumber daya proyek seperti orang, peralatan, atau material.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Langkah 6: Simpan Proyek sebagai XML
`SaveFileFormat` menyebutkan format output yang didukung untuk menyimpan proyek, termasuk XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Langkah 7: Tampilkan Hasil
`System.out.println` mencetak satu baris teks ke output konsol standar.

```java
System.out.println("Process completed Successfully");
```

## Kesalahan Umum & Tips
- **Konflik ID Atribut:** Selalu panggil `project.getExtendedAttributes().getById(id)` sebelum membuat definisi baru untuk mencegah duplikat identifier.  
- **Penanganan Presisi:** Lebih pilih `BigDecimal` daripada `float`/`double` untuk nilai numerik yang tepat; ini menghindari kesalahan pembulatan dalam pelaporan.  
- **Keandalan jalur file:** Gunakan `Paths.get(...).toAbsolutePath()` atau konfigurasikan direktori kerja IDE Anda untuk menghilangkan `FileNotFoundException`.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya membuat atribut kustom untuk tugas serta sumber daya?**  
A: Ya – gunakan `ExtendedAttributeTask` alih-alih `ExtendedAttributeResource` saat mendefinisikan skema atribut.

**Q: Apakah memungkinkan menambahkan beberapa atribut kustom sekaligus?**  
A: Tentu saja. Buat objek `ExtendedAttributeDefinition` terpisah untuk setiap atribut dan lampirkan ke sumber daya atau tugas yang diinginkan.

**Q: Format apa saja yang dapat saya gunakan untuk menyimpan proyek?**  
A: Aspose.Tasks mendukung XML, MPP, PDF, HTML, dan lebih dari 30 format tambahan. Dalam contoh ini kami menggunakan `SaveFileFormat.Xml`.

**Q: Apakah saya memerlukan lisensi untuk build pengembangan?**  
A: Lisensi evaluasi sementara sudah cukup untuk pengujian. Untuk penyebaran produksi apa pun, diperlukan lisensi komersial penuh.

**Q: Bagaimana cara membaca kembali nilai atribut kustom nanti?**  
A: Panggil `resource.getExtendedAttributes()` dan iterasi koleksi; ambil nilai yang disimpan dengan `getNumericValue()` atau `getTextValue()`.

---

**Terakhir Diperbarui:** 2026-06-10  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Sumber Daya – Manajemen Sumber Daya dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/)
- [Buat bidang kustom Aspose - Tangani atribut diperluas](/tasks/java/project-management/extended-attributes/)
- [Cara Membuat Proyek – Atur Atribut Tugas Baru dengan Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}