---
date: 2025-12-23
description: Aspose.Tasks for Java kullanarak MS Project dosyalarını nasıl güncelleyeceğinizi
  ve tamamlanmamış işleri nasıl yeniden zamanlayacağınızı öğrenin. Ayrıca MS Project
  XML dosyasını nasıl kaydedeceğinizi görün.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project'i Güncelle ve Aspose.Tasks ile Çalışmayı Yeniden Planla
url: /tr/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'i Güncelleme ve Aspose.Tasks ile Çalışmayı Yeniden Planlama

## Giriş
Microsoft Project, ekiplerin işleri zamanında planlamasına, izlemelerine ve teslim etmelerine yardımcı olan yaygın bir proje yönetim aracıdır. Programlar değiştiğinde, genellikle **MS Project'i güncellemeniz** gerekir; işi tamamlanmış olarak işaretlemek, kalan görevleri taşımak ve proje temel çizgisini doğru tutmak için dosyaları programlı olarak güncellemek. Aspose.Tasks for Java, GUI'yi açmadan bunu yapmanızı sağlayan temiz, tip‑güvenli bir API sunar. Bu öğreticide bir projeyi nasıl güncelleyeceğinizi, belirli bir tarihe kadar işi nasıl tamamlanmış olarak işaretleyeceğinizi ve ardından **MS Project'i nasıl yeniden planlayacağınızı** göreceksiniz.

## Hızlı Yanıtlar
- **“MS Project'i güncellemek” ne anlama geliyor?** Belirli bir tarihe kadar görevleri tamamlanmış olarak işaretler ve değişiklikleri dosyaya yazar.  
- **Kalan çalışmayı otomatik olarak yeniden planlayabilir miyim?** Evet—tamamlanmamış görevleri ileriye itmek için `rescheduleUncompletedWorkToStartAfter` kullanın.  
- **Hangi dosya formatı kaydedilir?** Örnekler projeyi XML (`SaveFileFormat.Xml`) olarak kaydeder.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gerekir.  
- **Hangi Java sürümü gerekiyor?** JDK 8 veya üzeri.

## Kodda “MS Project'i güncellemek” ne anlama geliyor?
Bir projeyi güncellemek, görev tarihlerini, sürelerini veya tamamlama yüzdelerini programlı olarak değiştirip bu değişiklikleri kalıcı hale getirmek anlamına gelir. Aspose.Tasks, sağladığınız referans `Date` değerine göre değişiklikleri uygulayan `updateProjectWorkAsComplete` gibi yöntemler sunar.

## MS Project'i güncellemek için Aspose.Tasks for Java neden kullanılmalı?
- **UI bağımlılığı yok** – birçok dosyada toplu değişiklikleri otomatikleştirin.  
- **Yüksek doğruluk** – kütüphane tüm yerel Project verilerini (kaynaklar, takvimler, özel alanlar) korur.  
- **Çapraz platform** – aynı kodu Windows, Linux veya macOS'ta çalıştırın.  
- **MS Project XML kaydet** – güncellenen projeyi yaygın olarak desteklenen XML formatına dışa aktararak sonraki araçlarda kullanabilirsiniz.

## Önkoşullar
1. Java Development Kit (JDK) yüklü.  
2. Aspose.Tasks for Java kütüphanesi – bunu [buradan](https://releases.aspose.com/tasks/java/) indirin.  
3. Java sözdizimi ve nesne‑yönelimli kavramlara temel aşinalık.

## Paketleri İçe Aktarma
İlk olarak, gerekli Aspose.Tasks sınıflarını ve Java yardımcılarını içe aktarın:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Adım 1: Projeyi Kurma
Yeni bir `Project` örneği oluşturun, birkaç örnek görev tanımlayın, sürelerini ayarlayın ve bağımlılıkları kurun. Ardından, başlangıç durumunu kaydedin, böylece önce‑sonra etkisini görebilirsiniz.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Adım 2: Proje Çalışmasını Güncelleme
Belirli bir kesim tarihine kadar işi tamamlanmış olarak işaretleyin. Bu, **MS Project'i güncelleme**nin özüdür—API görev ilerlemesini ve tarihlerini otomatik olarak ayarlar.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Adım 3: Tamamlanmamış Çalışmayı Yeniden Planlama
Tamamlanmış işi işaretledikten sonra, genellikle kalan görevleri ileriye itmeniz gerekir. Aşağıdaki çağrı, tamamlanmamış tüm çalışmayı aynı kesim tarihinden sonra başlatacak şekilde taşır; bu da **MS Project'i nasıl yeniden planlayacağınızı** gösterir.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümleri
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| Görevler güncellenmiş tarihleri göstermiyor | Proje farklı bir formatta kaydedildi (ör. `.mpp`) | `SaveFileFormat.Xml` kullanarak XML yapısını koruyun. |
| `updateProjectWorkAsComplete` hiçbir şey yapmıyor gibi görünüyor | Referans tarih proje başlangıcından daha erken | `Calendar` tarihinin proje zaman çizelgesinde olduğundan emin olun. |
| Yeniden planlanan görevler çakışıyor | Takvim veya kaynak dengelemesi uygulanmadı | `Project` takvimi uygulayın veya yeniden planlamadan sonra `Task.setStart` metodunu manuel olarak kullanın. |

## Sıkça Sorulan Sorular (Genişletilmiş)

**S: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?**  
C: Evet, Aspose.Tasks for Java, görevleri, bağımlılıkları, kaynakları ve diğer proje öğelerini verimli bir şekilde yönetmek için sağlam API'ler sunar.

**S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) alabilirsiniz.

**S: Aspose.Tasks for Java için destek nasıl alabilirim?**  
C: Yardım ve sorularınız için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?**  
C: Evet, geçici lisansları [buradan](https://purchase.aspose.com/temporary-license/) satın alabilirsiniz.

**S: Aspose.Tasks for Java için ayrıntılı belgeleri nerede bulabilirim?**  
C: Kapsamlı kılavuzlar ve API referansları için belgeleri [buradan](https://reference.aspose.com/tasks/java/) inceleyebilirsiniz.

## Sonuç
Bu öğreticide **MS Project** dosalarını **güncelleme**, işi tamamlanmış olarak işaretleme ve ardından **MS Project** görevlerini yeniden planlama** sürecini adım adım gösterdik. Projeyi XML olarak kaydederek diğer araçlarla uyumluluğu korur ve değişikliklerin net bir denetim izini tutarsınız. Bu desenleri büyük portföylerde takvim ayarlamalarını otomatikleştirmek, CI boru hatlarıyla bütünleştirmek veya özel raporlama panoları oluşturmak için kullanın.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}