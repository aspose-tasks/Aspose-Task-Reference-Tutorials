---
date: 2026-02-23
description: Aspose.Tasks for Java kullanarak proje görevlerinde fazla mesaiyi nasıl
  yöneteceğinizi, fazla mesai maliyetini nasıl hesaplayacağınızı ve kaynak takibini
  nasıl basitleştireceğinizi öğrenin.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Görevlerde Fazla Mesaiyi Nasıl Yönetilir
url: /tr/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Görevlerde Fazla Mesaiyi Yönetme

## Introduction
Microsoft Project dosyasında **fazla mesaiyi nasıl yöneteceğinizi** arıyorsanız, doğru yerdesiniz. Bu öğreticide, Aspose.Tasks for Java'nın her görevin fazla mesaiyle ilgili özelliklerini okumanıza, değiştirmenize ve raporlamanıza nasıl olanak sağladığını göstereceğiz, böylece takviminizi ve bütçenizi doğru tutabilirsiniz.  

## Quick Answers
- **Projede “fazla mesai” ne anlama gelir?** Kaynağın normal kapasitesinin üzerindeki ek çalışma saatleri.  
- **Hangi API sınıfı fazla mesai verilerini sağlar?** `Task` sınıfı, `Tsk` alan koleksiyonu (ör. `Tsk.OVERTIME_COST`).  
- **Örneği çalıştırmak için lisans gerekir mi?** Evet, üretim kullanımı için geçici veya tam bir Aspose.Tasks lisansı gereklidir.  
- **Fazla mesai maliyetini otomatik olarak hesaplayabilir miyim?** Kesinlikle – `Tsk.OVERTIME_COST` değerini alıp maliyet‑oran mantığınızı uygulayabilirsiniz.  
- **Bu Java 17 ile uyumlu mu?** Evet, Aspose.Tasks for Java, Java 8 ve üzerini destekler.

## What is Overtime Management in Project Tasks?
Fazla mesai yönetimi, kaynakların normal çalışma süresini aşması durumunda ortaya çıkan ek iş ve maliyetin izlenmesi anlamına gelir. Bu verileri doğru bir şekilde yakalamak, bütçeleri öngörmenize, takvimleri ayarlamanıza ve gerçekçi proje sağlığını raporlamanıza yardımcı olur.

## Why Use Aspose.Tasks for Overtime?
* **Microsoft Project gerekmez** – .MPP dosyalarıyla doğrudan çalışın.  
* **Fazla mesai alanlarına tam erişim** – maliyet, iş ve yüzde‑tamamlanma değerleri `Tsk` enum'ı aracılığıyla sunulur.  
* **Programatik kontrol** – manuel UI adımları olmadan fazla mesai maliyetini okuyabilir, değiştirebilir veya hesaplayabilirsiniz.

## Prerequisites
Öğreticiye başlamadan önce aşağıdaki ön koşulların yerine getirildiğinden emin olun:
- Java Geliştirme Ortamı: Makinenizde bir Java geliştirme ortamının kurulu olduğundan emin olun.  
- Aspose.Tasks for Java: Aspose.Tasks kütüphanesini indirin ve kurun. Kütüphaneyi ve dokümantasyonunu [burada](https://reference.aspose.com/tasks/java/) bulabilirsiniz.  
- Proje Dosyası: Öğretici sırasında çalışmak için bir proje dosyası (ör. TaskOvertimes.mpp) hazırlayın.

## Import Packages
Java projenizde, Aspose.Tasks'in işlevlerini kullanmak için gerekli paketleri içe aktarın. Aşağıdaki import ifadelerini ekleyin:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
Yeni bir proje oluşturmak (veya mevcut bir projeyi yüklemek), herhangi bir analizdeki ilk adımdır. Bu aynı zamanda **create new project** ikincil anahtar kelimesini de karşılar.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
Şimdi her üst‑seviye görevi dolaşacak, fazla mesai bilgilerini gösterecek ve `OVERTIME_COST` alanını okuyarak **fazla mesai maliyetini nasıl hesaplayacağınızı** göstereceğiz.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **İpucu:** `OVERTIME_COST` değeri, kaynakların fazla mesai oranına göre Aspose.Tasks tarafından zaten hesaplanır. Özel bir hesaplama gerekiyorsa, `OVERTIME_WORK` değerini kendi oranınızla çarpın ve alanı `tsk.set(Tsk.OVERTIME_COST, yourValue);` ile güncelleyin.

## Common Issues and Solutions
| Sorun | Çözüm |
|-------|----------|
| **Fazla mesai alanları için null değerler** | Kaynak .MPP dosyasının gerçekten fazla mesai verisi içerdiğinden emin olun; aksi takdirde alanlar `null` döner. |
| **Değişiklik sonrası hatalı maliyet** | Fazla mesai işini veya maliyetini değiştirdikten sonra, değişiklikleri kalıcı kılmak için `project.save()` çağırın. |
| **Lisans bulunamadı** | `Aspose.Tasks.lic` dosyanızı proje köküne yerleştirin veya projeyi yüklemeden önce lisansı programatik olarak ayarlayın. |

## Frequently Asked Questions

**S: Aspose.Tasks büyük ölçekli proje yönetimi için uygun mu?**  
C: Evet, Aspose.Tasks, küçük girişimlerden büyük ve karmaşık programlara kadar çeşitli boyutlardaki projeleri yönetmek için tasarlanmıştır.

**S: Aspose.Tasks'i diğer Java çerçeveleriyle entegre edebilir miyim?**  
C: Kesinlikle! Aspose.Tasks, Spring, Jakarta EE ve diğer Java ekosistemleriyle sorunsuz bir şekilde entegre olur, çok yönlülüğünü artırır.

**S: Aspose.Tasks kullanımıyla ilgili lisans hususları var mı?**  
C: Evet, lisans detaylarını bulabilir ve geçici bir lisans alabilirsiniz [burada](https://purchase.aspose.com/temporary-license/).

**S: Yardım almak veya Aspose.Tasks ile ilgili soruları tartışmak için nereye başvurabilirim?**  
C: Toplulukla etkileşime geçmek ve destek almak için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

**S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) erişebilirsiniz.

**S: Belirli bir kaynak için fazla mesai maliyetini nasıl hesaplarım?**  
C: Kaynağın fazla mesai oranını alın, `OVERTIME_WORK` (saat cinsinden) ile çarpın ve özel bir hesaplama gerekiyorsa sonucu `OVERTIME_COST` alanına geri ayarlayın.

## Conclusion
Aspose.Tasks for Java, proje görevlerinde **fazla mesaiyi nasıl yöneteceğinizi** basitleştirir ve geliştiricilere fazla mesai maliyeti, işi ve ilerleme metriklerine doğrudan programatik erişim sağlar. Bu kılavuzu izleyerek bir projeyi yükleyebilir, fazla mesai detaylarını okuyabilir, yüzde değerlerini ayarlayabilir ve hatta özel fazla mesai maliyetlerini hesaplayabilirsiniz—hepsi Microsoft Project açmadan.

---

**Son Güncelleme:** 2026-02-23  
**Test Edilen Versiyon:** Aspose.Tasks for Java (latest version)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}