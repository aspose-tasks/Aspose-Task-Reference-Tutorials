---
date: 2026-01-18
description: Java'da görev listesi oluşturmayı ve Microsoft Project'e görev eklemeyi,
  Aspose.Tasks kullanarak MS Project olmadan bir temel çizgi ayarlamayı öğrenin.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Java'da Görev Listesi Oluştur – Aspose.Tasks ile MS Project Temel Çizgisi
url: /tr/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Görev Listesi Oluştur – Aspose.Tasks ile MS Project Baseline

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak bir Microsoft Project görev baseline'ı oluşturarak **Java görev listesi oluşturacaksınız**. Aspose.Tasks, Microsoft Project olmadan Project dosyalarıyla çalışmanıza olanak tanır; böylece **Microsoft Project'e görev ekleyebilir**, kaynakları yönetebilir ve hatta **MS Project olmadan baseline ayarlayabilirsiniz**—hepsi saf Java kodundan.

## Hızlı Yanıtlar
- **Aspose.Tasks ne yapar?** MS Project olmadan Microsoft Project dosyalarını oluşturmak, okumak ve düzenlemek için bir Java API'si sağlar.  
- **Microsoft Project yüklü olması gerekiyor mu?** Hayır, Aspose.Tasks bağımsız çalışır.  
- **Hangi Java sürümü gerekiyor?** JDK 8 veya üzeri.  
- **Tek bir görev için baseline ayarlayabilir miyim?** Evet, bir görev listesiyle `setBaseline` kullanın.  
- **Üretim için lisans gerekli mi?** Evet, ticari lisans değerlendirme sınırlamalarını kaldırır.

## Görev Baseline'ı Nedir?
Bir görev baseline'ı, bir görevin orijinal planlanan başlangıç, bitiş ve iş değerlerini kaydeder. Gerçek ilerlemeyi orijinal planla karşılaştırmak için bir referans noktası olarak hizmet eder.

## Neden Aspose.Tasks ile Java görev listesi oluşturmalısınız?
- **MS Project bağımlılığı yok** – sunucu‑tarafı otomasyon için idealdir.  
- **Tam kontrol** görevler, kaynaklar ve takvimler üzerinde Java kodu aracılığıyla.  
- **Sürümler arası uyumluluk** Project 2007‑2024 dosyalarıyla.

## Önkoşullar
1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürüm kurun.  
2. **Aspose.Tasks for Java** – kütüphaneyi [download link](https://releases.aspose.com/tasks/java/) adresinden indirin.  

## Paketleri İçe Aktarma
To start working with Aspose.Tasks in your Java project, import the necessary packages:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Adım 1: Project Nesnesi Oluşturma
```java
Project project = new Project();
```
Burada yeni bir `Project` nesnesi örnekliyoruz – bu, görev listemizi tutacak MS Project dosyasını temsil eder.

## Adım 2: Projeye Görev Ekleme
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()` kullanarak proje hiyerarşisinin köküne erişir ve **Microsoft Project'e görev ekleriz**. `"Task"` dizesi görev adıdır; ihtiyacınıza göre istediğiniz açıklamayı koyabilirsiniz.

## Adım 3: Belirtilen Görevler İçin Baseline Ayarlama
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**MS Project olmadan baseline ayarlamak** için, baseline'ını almak istediğiniz görevlerin bir listesini (burada `myList`) oluşturun ve `setBaseline`'a geçirin. Yalnızca seçmeli bir baseline'a ihtiyacınız varsa, eklediğiniz görevlerle `myList`'i doldurun.

## Adım 4: Tüm Proje İçin Baseline Ayarlama
```java
project.setBaseline(BaselineType.Baseline);
```
Tüm projeyi tek bir çağrıyla baseline'lamak isterseniz, istediğiniz `BaselineType` ile `setBaseline`'ı çağırmanız yeterlidir.

## Microsoft Project'e Görev Ekleme Aspose.Tasks Kullanarak
Yukarıda gösterilen tek görev dışında, birden fazla görev, alt‑görev ekleyebilir ve kaynak atayabilirsiniz. `add()`'ın her çağrısı, daha fazla yapılandırabileceğiniz bir `Task` nesnesi döndürür (süre, başlangıç tarihi vb.).

## MS Project Olmadan Baseline Ayarlama
Aspose.Tasks, tamamen kod üzerinden baseline oluşturmayı sağlar. `BaselineType` enum'ını değiştirerek farklı baseline türlerini (Baseline, Baseline1‑Baseline10) ayarlayabilir, MS Project'i hiç açmadan birden fazla revizyon baseline'ını izleyebilirsiniz.

## Yaygın Sorunlar ve Çözümleri
- **Baseline görünmüyor:** Baseline'ı ayarladıktan sonra `project.save("output.mpp")` çağrısını yaptığınızdan emin olun (kısalık için kaydetme adımı burada atlanmıştır).  
- **Görev listesi boş görünüyor:** Görevleri doğru ebeveyne (`getRootTask()` veya bir alt‑göreve) eklediğinizi doğrulayın.  
- **Sürüm uyumsuzluğu hataları:** Daha yeni .mpp formatlarıyla uyumluluğu garanti etmek için en son Aspose.Tasks JAR'ını kullanın.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java'ı Microsoft Project yüklü olmadan kullanabilir miyim?**  
C: Evet, Aspose.Tasks bağımsız çalışır ve ana makinede Microsoft Project gerektirmez.

**S: Aspose.Tasks for Java farklı Microsoft Project sürümleriyle uyumlu mu?**  
C: Kesinlikle. Kütüphane, 2007'den en yeni 2024 sürümlerine kadar Project dosyalarını destekler.

**S: Aspose.Tasks for Java ile proje kaynaklarını manipüle edebilir miyim?**  
C: Evet, görevler gibi kaynakları da programlı olarak ekleyebilir, güncelleyebilir ve silebilirsiniz.

**S: Aspose.Tasks for Java görev bağımlılıklarını ayarlamayı destekliyor mu?**  
C: Evet, `TaskLink` sınıfını kullanarak önceki‑sonraki ilişkileri tanımlayabilirsiniz.

**S: Aspose.Tasks for Java için teknik destek mevcut mu?**  
C: Evet, [support forum](https://forum.aspose.com/c/tasks/15) üzerinden yardım alabilirsiniz; Aspose çalışanları ve topluluk sorulara yanıt verir.

## Sonuç
Bu adımları izleyerek, Aspose.Tasks kullanarak **Java görev listesi oluşturmayı**, **Microsoft Project'e görev eklemeyi** ve **MS Project olmadan baseline ayarlamayı** öğrendiniz. Bu yaklaşım proje otomasyonunu basitleştirir, masaüstü Project kurulumuna gerek kalmaz ve proje verileriniz üzerinde tam programatik kontrol sağlar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose