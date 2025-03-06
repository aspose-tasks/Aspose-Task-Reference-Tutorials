---
title: WBS Terkait dengan Tugas di Aspose.Tasks
linktitle: WBS Terkait dengan Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Kuasai WBS dengan Aspose.Tasks untuk Java - Belajar membaca dan memberi nomor ulang kode WBS tugas. Tingkatkan efisiensi manajemen proyek!
weight: 36
url: /id/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS Terkait dengan Tugas di Aspose.Tasks

## Perkenalan
Selamat datang di dunia manajemen proyek dengan Aspose.Tasks untuk Java! Dalam tutorial ini, kita akan mempelajari seluk-beluk Struktur Perincian Kerja (WBS) yang terkait dengan tugas menggunakan Aspose.Tasks untuk Java. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan membantu Anda memahami esensi pengelolaan kode WBS secara efisien.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
-  Aspose.Tasks untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
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
Mari kita mulai dengan membaca kode WBS yang terkait dengan tugas. Ikuti langkah ini:
## Langkah 1: Muat Proyek
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Langkah 2: Kumpulkan Tugas
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Langkah 3: Parsing dan Sesuaikan
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Cuplikan ini membaca dan menyesuaikan kode WBS yang terkait dengan tugas di proyek Anda.
## Beri nomor ulang Kode WBS Tugas
Sekarang, mari kita jelajahi penomoran ulang kode WBS untuk tugas:
## Langkah 1: Muat Proyek
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Langkah 2: Pilih Semua Tugas
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Langkah 3: Keluarkan Kode WBS Awal
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Langkah 4: Beri nomor ulang Kode WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Langkah 5: Keluarkan Kode WBS yang Diperbarui
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Dengan mengikuti langkah-langkah ini, Anda akan secara efektif menomori ulang kode WBS untuk tugas-tugas di proyek Anda.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara bekerja dengan kode WBS menggunakan Aspose.Tasks untuk Java. Pengetahuan ini akan memberdayakan Anda untuk mengelola dan menyesuaikan hierarki tugas proyek Anda secara efisien.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk Java?
 J: Dokumentasinya tersedia[Di Sini](https://reference.aspose.com/tasks/java/).
### T: Bagaimana cara mengunduh Aspose.Tasks untuk Java?
 J: Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/tasks/java/).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 A: Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan.
### T: Dapatkah saya memperoleh lisensi sementara untuk Aspose.Tasks untuk Java?
 A: Ya, dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
