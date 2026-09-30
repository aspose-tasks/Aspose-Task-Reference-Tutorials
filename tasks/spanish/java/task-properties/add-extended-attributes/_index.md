---
date: 2026-09-30
description: Aprenda cómo crear un atributo extendido de tarea usando Aspose.Tasks
  para Java, la principal biblioteca de gestión de proyectos en Java para agregar
  campos de tarea personalizados.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Cómo crear un atributo extendido de tarea con Aspose.Tasks Java
og_description: Aprenda cómo crear un atributo extendido de tarea usando Aspose.Tasks
  para Java, la principal biblioteca de gestión de proyectos en Java para agregar
  campos de tarea personalizados.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Cómo crear un atributo extendido de tarea con Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Cómo crear un atributo extendido de tarea con Aspose.Tasks Java
url: /es/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un atributo extendido de tarea con Aspose.Tasks Java

## Introducción
En este tutorial aprenderás a **crear task extended attribute** en un archivo Microsoft Project usando Aspose.Tasks para Java. Agregar campos personalizados te permite capturar datos específicos del proyecto que no están cubiertos por las columnas incorporadas, dándote un control más fino sobre los informes y la planificación de recursos. Al final de la guía podrás agregar atributos de texto plano, con búsqueda habilitada y de duración a cualquier tarea.

## Respuestas rápidas
- **¿Qué significa “extended attribute”?** Es un campo personalizado que defines y adjuntas a tareas, recursos o asignaciones.  
- **¿Qué biblioteca agrega esta capacidad?** Aspose.Tasks for Java, una biblioteca de gestión de proyectos java.  
- **¿Necesito una licencia para probarlo?** Sí – una prueba gratuita de 30 días está disponible en el sitio web de Aspose.  
- **¿Puedo agregar valores de búsqueda?** Absolutamente; puedes proporcionar una lista de valores permitidos para campos de texto o duración.  
- **¿Es la API compatible con Java 8 y posteriores?** Sí, es compatible con Java 8+ y se ejecuta en todos los principales sistemas operativos.

## ¿Qué es un atributo extendido de tarea?
Un atributo extendido de tarea es una columna definida por el usuario que almacena información adicional para cada tarea en un archivo Project. Se comporta como un campo incorporado pero puede contener cualquier tipo de dato que necesites, como texto, números, fechas o duraciones.

## ¿Por qué usar Aspose.Tasks para Java?
Aspose.Tasks soporta **más de 50 formatos de archivo** y puede procesar proyectos con **más de 10 000 tareas** sin requerir que Microsoft Project esté instalado. La biblioteca funciona completamente sin conexión, garantizando la privacidad de los datos y un rendimiento determinista para soluciones a escala empresarial.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Conocimientos básicos de programación en Java.  
- La biblioteca Aspose.Tasks for Java instalada. Puedes descargarla desde el [website](https://releases.aspose.com/tasks/java/).  
- Un IDE de Java (IntelliJ IDEA, Eclipse o VS Code) configurado en tu máquina.

## Importar paquetes
Las sentencias `import` te dan acceso a las clases principales que necesitarás, como `Project`, `ExtendedAttributeDefinition` y `ExtendedAttribute`.  

`Project` representa un archivo Microsoft Project y proporciona métodos para leer, modificar y guardarlo.  
`ExtendedAttributeDefinition` define un campo personalizado que puede adjuntarse a tareas, recursos o asignaciones.  
`ExtendedAttribute` es una instancia de una definición que contiene el valor real para una entidad específica.

## ¿Cómo agregar un atributo extendido de texto plano a una tarea?
Para agregar un atributo extendido de texto plano, primero cargas el proyecto, luego creas una definición del tipo Text, la añades a la colección del proyecto, creas una tarea, instancias el atributo a partir de la definición, estableces su valor de texto, lo adjuntas a la tarea y finalmente guardas el proyecto.

### 1. Establecer la ruta del directorio del documento
Especifica dónde se encuentran tus archivos de origen y salida.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Crear un nuevo proyecto
Instanciar un objeto `Project`, opcionalmente cargando un archivo .mpp existente.

```java
String dataDir = "Your Document Directory";
```

### 3. Crear una definición de atributo extendido del tipo Text1
Define el campo personalizado como una columna de texto plano llamada “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Agregar la definición a la colección de atributos extendidos del proyecto
Registrar la nueva definición para que el proyecto la reconozca.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Agregar una tarea al proyecto
Crear una tarea que recibirá el campo personalizado.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Crear un atributo extendido a partir de la definición del atributo
Generar una instancia que puedes vincular a una tarea específica.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Asignar un valor al atributo extendido generado
Establecer el texto real que deseas almacenar, por ejemplo, “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Agregar el atributo extendido a la tarea
Adjuntar la instancia del atributo a la colección `ExtendedAttributes` de la tarea.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Guardar el proyecto
Escribir el proyecto actualizado de nuevo en disco en el formato deseado.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## ¿Cómo agregar un atributo de texto con opción de búsqueda?
Al agregar un atributo de texto con búsqueda, sigues los mismos pasos que para un atributo de texto plano, pero antes de añadir la definición rellenas su colección `LookupValues` con las cadenas permitidas. Estos valores aparecen como una lista desplegable en Microsoft Project, asegurando la consistencia de los datos.

## ¿Cómo agregar un atributo de duración con opción de búsqueda?
Para agregar un atributo de duración con búsqueda, reemplaza el tipo `Text1` por `Duration2` al crear la definición, luego llena la colección `LookupValues` con cadenas de duración como “1 day”, “2 days”, etc. Después de añadir la definición al proyecto, crea la instancia del atributo, establece un valor de duración, adjúntalo a una tarea y guarda el archivo.

## Problemas comunes y solución de problemas
- **Los valores de búsqueda no aparecen** – Asegúrate de agregar cada entrada de búsqueda a la colección `LookupValues` *antes* de llamar a `project.getExtendedAttributes().add(definition)`.  
- **El valor del atributo no se guarda** – Verifica que agregues la instancia `ExtendedAttribute` a la tarea *después* de establecer su valor.  
- **El tamaño del archivo crece inesperadamente** – Al trabajar con proyectos muy grandes, considera llamar a `project.setSaveOptions(new ProjectSaveOptions())` para habilitar el guardado incremental.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks para Java con otras bibliotecas Java?**  
R: Sí, Aspose.Tasks para Java se integra sin problemas con cualquier ecosistema Java, incluidos Spring, Hibernate y Apache POI.

**P: ¿Aspose.Tasks para Java es adecuado para aplicaciones de gestión de proyectos a gran escala?**  
R: Absolutamente. La biblioteca está diseñada para manejar proyectos con miles de tareas y soporta streaming para mantener bajo el uso de memoria.

**P: ¿Existen consideraciones de licencia para usar Aspose.Tasks para Java en un proyecto comercial?**  
R: Sí, necesitas una licencia comercial válida. Puedes revisar los detalles en el [Aspose.Tasks website](https://purchase.aspose.com/buy).

**P: ¿Cómo puedo obtener soporte o asistencia con Aspose.Tasks para Java?**  
R: Visita el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para ayuda de la comunidad, o abre un ticket de soporte a través de tu cuenta Aspose.

**P: ¿Puedo probar Aspose.Tasks para Java antes de comprar?**  
R: Sí, puedes acceder a una versión de prueba gratuita en la página de [Aspose.Tasks free trial](https://releases.aspose.com/).

**Última actualización:** 2026-09-30  
**Probado con:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Tutoriales relacionados

- [Columnas personalizadas y atributos extendidos en la gestión de proyectos Java](/tasks/java/project-management/extended-attributes/)
- [Leer atributos de tarea extendidos con Aspose.Tasks para Java](/tasks/java/task-properties/extended-task-attributes/)
- [Cómo crear proyecto aspose.tasks – Establecer nuevos atributos de tarea](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}