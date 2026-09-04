---
date: 2026-06-15
description: Узнайте, как извлекать данные с временными интервалами из ресурсов MS
  Project с помощью Aspose.Tasks для Java. Пошаговое руководство по получению ресурса
  по идентификатору.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Чтение данных с временными интервалами для ресурсов в Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Чтение данных с временными интервалами для ресурсов в Aspose.Tasks – получение
  ресурса по идентификатору
url: /ru/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение данных с разбивкой по времени для ресурсов в Aspose.Tasks

## Введение
В этом руководстве вы узнаете **how to get resource by id** и как читать его данные с разбивкой по времени, используя Aspose.Tasks for Java. Мы пройдем каждый шаг — от настройки папки проекта до вывода значений работы и стоимости с разбивкой по времени — чтобы вы могли программно извлекать ценную информацию о расписании из любого файла Microsoft Project. Aspose.Tasks for Java — это комплексный API, позволяющий разработчикам создавать, читать, изменять и конвертировать файлы Microsoft Project без необходимости установки Microsoft Project, поддерживая широкий спектр функций и форматов управления проектами.

## Быстрые ответы
- **What does “get resource by id” do?** Он извлекает конкретный объект `Resource` из `Project`, используя его уникальный идентификатор.  
- **Which library handles timephased data?** Aspose.Tasks for Java предоставляет API `Resource.getTimephasedData`.  
- **Do I need a license?** Для разработки достаточно бесплатной пробной версии; для продакшн‑использования требуется коммерческая лицензия.  
- **Can I read large projects?** Да — Aspose.Tasks может обрабатывать файлы с до 10 000 задач без загрузки всего файла в память.  
- **What Java version is required?** Требуется Java 8 или выше; библиотека совместима со всеми основными JDK.

## Что такое “get resource by id”?
`get resource by id` — это вызов метода, который получает экземпляр `Resource` из загруженного `Project`, используя числовой идентификатор ресурса. Эта операция обеспечивает точный доступ к подробным свойствам ресурса, таким как его назначения, календари и пользовательские поля, и необходима для извлечения данных о работе или стоимости с разбивкой по времени, связанных с этим конкретным ресурсом.

## Почему использовать Aspose.Tasks для данных с разбивкой по времени?
Aspose.Tasks поддерживает **более 50 форматов ввода и вывода** (MPP, XML, CSV и т.д.) и может извлекать значения работы и стоимости с разбивкой по времени для ресурсов, охватывающих многолетние расписания, при этом потребляя минимум памяти. API возвращает данные с интервалом по умолчанию в 15‑минутных шагах, предоставляя детализированную информацию для отчетности или пользовательской аналитики.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть следующие требования:
1. Java Development Kit (JDK): Убедитесь, что JDK установлен в вашей системе. Вы можете скачать его с [веб‑сайта](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) и следовать инструкциям по установке.  
2. Библиотека Aspose.Tasks for Java: Скачайте библиотеку Aspose.Tasks for Java со [страницы загрузки](https://releases.aspose.com/tasks/java/) и следуйте инструкциям по установке, приведённым в документации.

## Импорт пакетов
Первый шаг — импортировать необходимые классы Aspose.Tasks в ваш Java‑файл.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Шаг 1: Настройка каталога данных
Сначала определите каталог, в котором находится ваш файл MS Project. Хранение папки данных отдельно от исходного кода упрощает поддержку проекта.

```java
String dataDir = "Your Data Directory";
```

## Шаг 2: Чтение шаблона файла MS Project
Укажите имя файла шаблона MS Project. Использование шаблона гарантирует согласованные настройки столбцов в разных проектах.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Шаг 3: Чтение входного файла как Project
Класс `Project` — это основной объект Aspose.Tasks, представляющий файл Microsoft Project в памяти. Загрузка файла предоставляет программный доступ к задачам, ресурсам и расписаниям.

```java
Project project = new Project(dataDir + fileName);
```

## Шаг 4: Получение ресурса по ID
Чтобы получить конкретный ресурс, вызовите метод `getResources().getById(id)`. Это именно та операция, на которую ссылается основной ключевой запрос.

```java
Resource resource = project.getResources().getByUid(1);
```

## Шаг 5: Вывод данных с разбивкой по времени для работы ресурса
После получения объекта `Resource` вы можете вызвать `resource.getTimephasedData(ResourceTimephasedDataType.Work)`, чтобы получить распределение работы во времени. Возвращаемая коллекция содержит объекты `TimephasedData`, включающие дату начала, дату окончания и объём работы для каждого интервала.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Шаг 6: Вывод данных с разбивкой по времени для стоимости ресурса
Аналогично, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` возвращает информацию о стоимости, разбитую по тем же временным интервалам. Это полезно для составления бюджетов и отчётов по отслеживанию расходов.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Как получить ресурс по ID в одну строку?
Загрузите проект, затем вызовите `project.getResources().getById(5)` — замените **5** фактическим идентификатором ресурса. Этот единственный вызов возвращает объект `Resource`, после чего вы можете запрашивать его данные с разбивкой по времени, назначения или пользовательские поля. Метод работает за O(1), поскольку ресурсы индексируются внутренне.

## Распространённые проблемы и решения
- **Resource not found** – Убедитесь, что указанный ID существует в файле проекта; идентификаторы начинаются с 1 и уникальны для каждого ресурса.  
- **Empty timephased data** – Проверьте, что у ресурса есть назначения работы или стоимости; иначе коллекция будет пустой.  
- **Large file performance** – Используйте `Project.setLoadOptions(LoadOptions.fromFile(...))`, чтобы включить отложенную загрузку для проектов размером более 500 МБ.

## Часто задаваемые вопросы

**Q: Может ли Aspose.Tasks работать с другими типами файлов проектов, помимо Microsoft Project?**  
A: Да, Aspose.Tasks поддерживает MPP, XML, CSV и несколько других форматов, позволяя читать и записывать данные в разных стандартах.

**Q: Совместима ли Aspose.Tasks с различными средами разработки Java?**  
A: Абсолютно. Библиотека работает со всеми основными IDE (IntelliJ IDEA, Eclipse, NetBeans) и инструментами сборки (Maven, Gradle).

**Q: Могу ли я манипулировать данными проекта с помощью Aspose.Tasks?**  
A: Да, через API можно создавать, изменять и удалять задачи, ресурсы, назначения и даже пользовательские поля.

**Q: Подходит ли Aspose.Tasks для проектов корпоративного уровня?**  
A: Да. Предприятия используют Aspose.Tasks для обработки больших объёмов, пакетных конверсий и серверных отчётов, поскольку не требуется установка Microsoft Project.

**Q: Где я могу получить поддержку, если столкнусь с проблемами при использовании Aspose.Tasks?**  
A: Вы можете посетить [форум Aspose.Tasks](https://forum.aspose.com/c/tasks/15) для получения помощи от сообщества и команды поддержки.

## Заключение
В этом руководстве мы изучили, как **get resource by id** и читать данные о работе и стоимости с разбивкой по времени ресурса, используя Aspose.Tasks for Java. Следуя этим шагам, вы сможете эффективно извлекать ценную информацию о расписании из файлов проекта и интегрировать её в пользовательские отчёты или аналитические конвейеры.

---

**Последнее обновление:** 2026-06-15  
**Тестировано с:** Aspose.Tasks 24.11 for Java  
**Автор:** Aspose

## Связанные руководства

- [Добавить ресурс в проект с Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [Управление стоимостью ресурсов MS Project с Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [Чтение рабочих недель Java из календаря MS Project Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}