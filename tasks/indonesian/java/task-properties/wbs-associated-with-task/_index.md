---
date: 2026-03-03
description: Pelajari cara menomori ulang WBS di Aspose.Tasks untuk Java, mengelola
  work breakdown, dan menyesuaikan kode WBS secara efisien dengan contoh langkah demi
  langkah.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menomori Ulang WBS di Aspose.Tasks untuk Java
url: /id/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menomori Ulang WBS di Aspose.Tasks untuk Java

## Pendahuluan
Jika Anda perlu **menomori ulang WBS** dalam file Microsoft Project menggunakan Aspose.Tasks untuk Java, Anda berada di tempat yang tepat. Tutorial ini memandu Anda melalui pembacaan kode WBS yang ada, menyesuaikannya, dan kemudian menomori ulang hierarki sehingga proyek Anda tetap teratur. Baik Anda sedang membersihkan jadwal warisan atau membangun yang baru dari awal, menguasai langkah‑langkah ini akan membantu Anda **mengelola struktur work breakdown** dengan percaya diri.

## Jawaban Cepat
- **Apa yang dilakukan penomoran ulang WBS?** Itu menghitung ulang penomoran hierarkis tugas untuk mencerminkan perubahan struktural apa pun.  
- **Kelas mana yang melakukan penomoran ulang?** `Project.renumberWBSCode`.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyesuaikan format WBS?** Ya—gunakan `Task.set(Tsk.WBS, "...")` untuk menetapkan string apa pun yang Anda inginkan.  
- **Apa saja prasyarat utama?** Java JDK, pustaka Aspose.Tasks untuk Java, dan file proyek yang valid (.mpp).

## Apa itu Work Breakdown Structure (WBS)?
Work Breakdown Structure (WBS) adalah representasi hierarkis dari deliverables dan tugas proyek. Setiap tugas menerima kode (misalnya 1.2.3) yang mencerminkan posisinya dalam hierarki. Penomoran ulang menjadi penting ketika tugas ditambahkan, dihapus, atau diubah urutannya, memastikan kode tetap logis dan mudah dibaca.

## Mengapa mengelola work breakdown dan menyesuaikan kode WBS?
- **Kejelasan:** Kode WBS yang jelas memudahkan pemangku kepentingan menemukan tugas.  
- **Pelaporan:** Banyak alat pelaporan mengandalkan penomoran yang konsisten.  
- **Fleksibilitas:** Kode khusus memungkinkan Anda menyelaraskan struktur proyek dengan standar internal.

## Prasyarat
Sebelum kita masuk ke kode, pastikan Anda memiliki hal berikut:

- Java Development Kit (JDK) terpasang di mesin Anda.  
- Pustaka Aspose.Tasks untuk Java ditambahkan ke proyek Anda. Anda dapat mendapatkannya dari [di sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pastikan Anda mengimpor paket yang diperlukan untuk memulai proyek Anda:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Baca Kode WBS
Pertama, kita akan membaca kode WBS yang ada sehingga Anda dapat melihat apa yang sedang Anda kerjakan.

### Langkah 1: Muat Proyek
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Langkah 2: Kumpulkan Tugas
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Langkah 3: Parse dan Sesuaikan
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Potongan kode di atas mencetak WBS dan level saat ini setiap tugas, kemudian mendemonstrasikan **menyesuaikan kode wbs** dengan menetapkan string baru.

## Nomori Ulang Kode WBS Tugas
Sekarang mari kita benar‑benar menomori ulang hierarki WBS.

### Langkah 1: Muat Proyek (Contoh Penomoran Ulang)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Langkah 2: Pilih Semua Tugas
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Langkah 3: Output Kode WBS Awal
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Langkah 4: Nomori Ulang Kode WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Langkah 5: Output Kode WBS yang Diperbarui
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Dengan mengikuti langkah‑langkah ini, Anda akan secara efektif **menomori ulang wbs** untuk kumpulan tugas apa pun dalam file proyek Anda.

## Masalah Umum dan Solusinya
- **WBS tidak berubah setelah pemanggilan `set`:** Pastikan Anda bekerja dengan instance tugas yang tepat dan proyek disimpan setelah modifikasi.  
- **`renumberWBSCode` melemparkan pengecualian:** Verifikasi bahwa daftar ID cocok dengan jumlah tugas level‑atas; jika tidak, metode tidak dapat memetakan nomor baru dengan benar.  
- **Nilai WBS hilang:** Beberapa tugas mungkin memiliki WBS `null` jika mereka diimpor dari file yang tidak mendefinisikannya. Gunakan nilai cadangan sebelum mencetak.

## Pertanyaan yang Sering Diajukan

**Q: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk Java?**  
A: Dokumentasi tersedia [di sini](https://reference.aspose.com/tasks/java/).

**Q: Bagaimana saya dapat mengunduh Aspose.Tasks untuk Java?**  
A: Anda dapat mengunduhnya [di sini](https://releases.aspose.com/tasks/java/).

**Q: Apakah ada percobaan gratis tersedia untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mendapatkan percobaan gratis [di sini](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan.

**Q: Bisakah saya memperoleh lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Ya, dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

**Q: Bisakah saya mengganti nama format WBS setelah penomoran ulang?**  
A: Tentu saja. Setelah memanggil `renumberWBSCode`, Anda dapat mengiterasi tugas‑tugas dan menerapkan `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` sesuai konvensi penamaan Anda.

**Q: Apakah penomoran ulang memengaruhi ketergantungan tugas?**  
A: Tidak. Metode hanya memperbarui string WBS; tautan tugas dan batasan tetap tidak berubah.

---

**Terakhir Diperbarui:** 2026-03-03  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}