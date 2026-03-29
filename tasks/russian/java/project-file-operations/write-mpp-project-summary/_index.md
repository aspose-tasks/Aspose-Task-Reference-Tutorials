---
date: 2026-03-29
description: Узнайте, как задать ключевые слова и дату создания в проекте MPP с использованием
  Aspose.Tasks for Java. Пошаговое руководство с примерами кода.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как установить ключевые слова в сводке проекта MPP с помощью Aspose.Tasks
url: /ru/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить ключевые слова в сводке проекта MPP с помощью Aspose.Tasks

## Введение
В этом руководстве вы узнаете **как установить ключевые слова** и другую сводную информацию для файла проекта MPP, используя Aspose.Tasks for Java. Независимо от того, нужно ли вам добавить сведения об авторе, номера ревизий или пользовательскую дату создания, это руководство проведёт вас через точные шаги, включая готовый к запуску код. К концу вы сможете установить ключевые слова, установить дату создания java и получить данные обратно из файла.

## Краткие ответы
- **Какая библиотека используется?** Aspose.Tasks for Java  
- **Основная цель?** Установить ключевые слова, информацию об авторе и дату создания в файле MPP  
- **Сколько шагов кода?** Три простых блока кода (инициализация, сохранение, чтение)  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия  
- **Поддерживаемая версия Java?** Java 8 and higher  

## Что такое «как установить ключевые слова» в файле MPP?
Ключевые слова — это поля метаданных, хранящиеся внутри файла Microsoft Project (MPP). Они помогают классифицировать проекты, обеспечивают быстрый поиск и предоставляют контекстную информацию для последующих инструментов. Aspose.Tasks предоставляет свойство `Prj.KEYWORDS`, что упрощает программную запись или обновление этого значения.

## Почему стоит использовать Aspose.Tasks for Java для установки ключевых слов и даты создания?
* **Полная совместимость с .MPP** – работает со всеми форматами Project 2007‑2023.  
* **Не требуется установка COM или Office** – чистый Java, идеально подходит для серверных сред.  
* **Богатый API** – помимо ключевых слов, вы можете установить автора, ревизию, комментарии и даты одним вызовом.  
* **Оптимизировано по производительности** – быстрый ввод/вывод даже для больших файлов проектов.  

## Требования
1. **Java Development Kit (JDK)** – установлен JDK 8 или новее.  
2. **Aspose.Tasks for Java** – скачайте последнюю JAR‑файл с [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans или любой предпочитаемый редактор.  

## Импорт пакетов
Сначала импортируйте необходимые классы. Эти импорты дают вам доступ к объекту `Project`, перечислению `Prj` для полей сводки и перечислению `SaveFileFormat` для сохранения.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Шаг 1: Настройка проекта и определение сводной информации
Создайте экземпляр `Project`, затем используйте метод `set` для записи нужных метаданных. Обратите внимание, как мы **устанавливаем ключевые слова** и **устанавливаем дату создания java** с помощью объекта `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Шаг 2: Сохранение сводной информации проекта
После заполнения полей сохраните изменения. Здесь мы сохраняем проект в формате XML для удобного просмотра, но вы также можете сохранить его обратно в MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Шаг 3: Чтение сводной информации проекта
Чтобы убедиться, что метаданные записаны правильно, перезагрузите файл и прочитайте каждое свойство. Этот шаг демонстрирует, что **как установить ключевые слова** действительно работает от начала до конца.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **NullPointerException при `project.get(Prj.CREATION_DATE)`** | Календарь никогда не был установлен перед сохранением. | Убедитесь, что вызываете `project.set(Prj.CREATION_DATE, cal.getTime())` перед `save()`. |
| **Ключевые слова не отображаются в пользовательском интерфейсе Microsoft Project** | Файл был сохранён как XML и открыт напрямую в Project. | Сохраните обратно в MPP (`SaveFileFormat.MPP`) или откройте XML через *Import* в Project. |
| **Значения дат смещены из‑за часового пояса** | Java `Date` включает информацию о часовом поясе. | Используйте `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`, если нужны даты в UTC. |

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.Tasks for Java с другими библиотеками Java?**  
A: Да, Aspose.Tasks for Java можно бесшовно интегрировать с другими библиотеками Java для расширения возможностей управления проектами.

**Q: Доступна ли пробная версия Aspose.Tasks for Java?**  
A: Да, вы можете скачать бесплатную пробную версию по ссылке [here](https://releases.aspose.com/).

**Q: Как часто обновляется Aspose.Tasks for Java?**  
A: Aspose.Tasks for Java регулярно обновляется, чтобы обеспечить совместимость с последними версиями Java и файлов Microsoft Project.

**Q: Могу ли я дальше настраивать сводную информацию проекта?**  
A: Конечно, Aspose.Tasks for Java предоставляет обширные возможности для настройки сводной информации проекта в соответствии с вашими требованиями.

**Q: Где я могу получить поддержку по Aspose.Tasks for Java?**  
A: Вы можете получить поддержку на форуме сообщества Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Последнее обновление:** 2026-03-29  
**Тестировано с:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}