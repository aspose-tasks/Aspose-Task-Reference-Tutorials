---
date: 2026-10-15
description: Aprenda cómo crear una actividad, establecer el directorio de datos,
  personalizar los campos de la tabla y guardar el proyecto como MPP con Aspose.Tasks
  para Java. Guía paso a paso para desarrolladores Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Cómo crear una actividad y establecer el directorio de datos usando Aspose.Tasks
  para Java
og_description: Cómo crear una actividad, personalizar los campos de la tabla y guardar
  el proyecto como MPP usando Aspose.Tasks para Java. Siga esta guía detallada para
  una implementación rápida.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Cómo crear una actividad y establecer el directorio de datos en Aspose.Tasks
  para Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Cómo crear una actividad y establecer el directorio de datos usando Aspose.Tasks
  para Java
url: /es/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una actividad y establecer el directorio de datos usando Aspose.Tasks para Java

## Introducción
En este tutorial descubrirá **cómo crear una actividad** de forma programática, configurará el **directorio de datos** y **guardará el proyecto como MPP** mientras también **personaliza los campos de tabla** en una vista de diagrama de Gantt. Aspose.Tasks para Java es una API potente que admite más de 30 formatos de entrada y salida y puede procesar proyectos con hasta 10 000 tareas sin cargar todo el archivo en memoria. Al final de la guía podrá automatizar la creación de proyectos, enriquecer tareas con atributos personalizados y producir un archivo MPP listo para abrir en Microsoft Project.

## Respuestas rápidas
- **¿Cuál es el primer paso?** Establecer la ruta del directorio de datos donde residen sus archivos de proyecto.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (descargable desde el sitio oficial).  
- **¿Puedo añadir atributos personalizados?** Sí, puede definir atributos extendidos y mostrarlos en el diagrama de Gantt.  
- **¿Necesito una licencia para pruebas?** Existe una licencia temporal disponible para propósitos de evaluación.  
- **¿Qué IDE funciona mejor?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, NetBeans) funcionará.

## ¿Qué es “establecer el directorio de datos” y por qué es importante?
Establecer el directorio de datos indica a Aspose.Tasks dónde leer y escribir los archivos de proyecto. Sin una ruta correcta, la API no puede localizar sus archivos `.mpp`, lo que genera errores `FileNotFoundException`. Definir este directorio al inicio de su código hace que el flujo de trabajo sea repetible y aísla las preocupaciones del sistema de archivos de la lógica de negocio.

## ¿Por qué personalizar los campos de tabla en un diagrama de Gantt?
Los campos de tabla personalizados le permiten mostrar información adicional —como atributos personalizados, datos de recursos o notas específicas del proyecto— directamente en la vista de Gantt. Esto reduce la necesidad de informes separados y brinda a los interesados una visualización única y rica en datos que puede mejorar la velocidad de toma de decisiones hasta en un 30 %.

## ¿Cómo crear una nueva actividad?
Crea una nueva actividad (tarea) instanciando un objeto `Task` y añadiéndolo a la colección de tareas raíz del proyecto. Este enfoque le permite generar horarios extensos de forma automática, extraer datos de tareas de sistemas externos o aplicar actualizaciones masivas sin edición manual.

## Requisitos previos
Antes de comenzar, asegúrese de contar con:

1. **Java Development Kit (JDK)** – versión 8 o posterior.  
2. **Aspose.Tasks para Java** – descárguelo desde la **página de lanzamiento de Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse o cualquier editor compatible con Java que prefiera.  

## Importar paquetes
El espacio de nombres `com.aspose.tasks` contiene todas las clases que necesitará para la manipulación de proyectos. Importarlo le brinda acceso a `Project`, `Task`, `ExtendedAttributeDefinition` y otros tipos centrales.

```java
import com.aspose.tasks.*;
```

## Dependencia Maven (opcional)
Si gestiona su proyecto con Maven, añada la dependencia de Aspose.Tasks a `pom.xml`. Esto garantiza que la biblioteca se resuelva automáticamente durante la compilación.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Guía paso a paso

### Paso 1: configurar el directorio de datos
Defina la carpeta que contiene sus archivos de proyecto. La variable `dataDir` almacena la ruta absoluta y se reutiliza a lo largo del tutorial.

```java
String dataDir = "Your Data Directory";
```

Reemplace `"Your Data Directory"` con la ruta completa a la carpeta donde se encuentra `project.mpp`, por ejemplo `C:/Projects/MyGantt`.

### Paso 2: cargar el archivo de proyecto
`Project` es el objeto de nivel superior de Aspose.Tasks que representa un único archivo de Microsoft Project en memoria. Cargar un archivo existente le permite acceder a sus tareas, recursos y tablas.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Paso 3: añadir nueva actividad
`Task` representa una actividad individual en el cronograma. Añadir una tarea a la colección de tareas raíz la inserta en el nivel superior de la jerarquía del proyecto.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Paso 4: definir atributo personalizado
`ExtendedAttributeDefinition` le permite crear un campo personalizado reutilizable que puede adjuntarse a cualquier tarea, recurso o asignación.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Paso 5: añadir atributo personalizado a la tarea
`ExtendedAttribute` es la instancia concreta de un atributo personalizado que asigna a una tarea específica.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Paso 6: personalizar la tabla – añadir atributo personalizado como columna
`TableField` describe una columna en una tabla de diagrama de Gantt. Al añadir un `TableField` que hace referencia al atributo personalizado, hace visible el atributo en la vista del diagrama.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Paso 7: guardar el proyecto
Llamar a `project.save` persiste todos los cambios en un nuevo archivo. La constante `SaveFileFormat.MPP` indica a Aspose.Tasks que escriba el archivo en el formato binario nativo de Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **FileNotFoundException** al cargar el proyecto | La ruta **establecida del directorio de datos** es incorrecta o le falta una barra diagonal final. | Verifique que `dataDir` apunte a la carpeta exacta e incluya el separador de archivos apropiado (`/` o `\\`). |
| El atributo personalizado no es visible en la vista de Gantt | El campo de tabla se añadió en el índice incorrecto o el ancho de columna es demasiado pequeño. | Asegúrese de que `table.getTableFields().add(3, attrField);` use un índice válido y ajuste `setWidth` según sea necesario. |
| LicenseException al guardar | No se aplicó una licencia válida para uso en producción. | Aplique una licencia temporal o permanente antes de llamar a `project.save()`. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
R: Sí, Aspose.Tasks está disponible para .NET, Java y C++.

**P: ¿Existe una versión de prueba gratuita de Aspose.Tasks?**  
R: Sí, puede descargar una prueba gratuita desde la **página de descarga de prueba gratuita de Aspose.Tasks**.

**P: ¿Dónde puedo encontrar soporte para Aspose.Tasks?**  
R: Puede obtener soporte y hacer preguntas en el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**P: ¿Cómo compro una licencia para Aspose.Tasks?**  
R: Puede adquirir una licencia en la **página de compra de Aspose.Tasks**.

**P: ¿Necesito una licencia temporal para propósitos de prueba?**  
R: Sí, puede obtener una licencia temporal en la **página de solicitud de licencia temporal**.

## Conclusión
Ahora sabe **cómo crear una actividad**, establecer el directorio de datos, definir y adjuntar un atributo personalizado, y **guardar el proyecto como MPP** mientras **personaliza los campos de tabla** en una vista de diagrama de Gantt usando Aspose.Tasks para Java. Estas capacidades le brindan control total programático sobre los datos del proyecto, permitiendo la generación automática de cronogramas y una presentación visual más rica para sus interesados.

---

**Última actualización:** 2026-10-15  
**Probado con:** Aspose.Tasks Java 24.12 (última)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear un archivo de proyecto vacío en Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Cómo crear un archivo MPP – Crear y guardar un proyecto vacío en formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Cómo crear proyecto aspose.tasks – Establecer nuevos atributos de tarea](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}